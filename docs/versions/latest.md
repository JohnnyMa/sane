# v1.0.0 (latest)


## Table of content

* [Example](#example)
* [Spec](#spec)
* [Filename extension](#filename-extension)
* [MIME type](#mime-type)
* [Comment](#comment)
* [Key/Value pair](#keyvalue-pair)
* [Keys](#keys)




## Example

```san
// This is a SAN document

/*
This is a
multiline
comment
*/

title = "SAN Example"

creator = {
  name = "Sylvain Kerkour"
  website = "https://kerkour.com"
}

database = {
  server = "192.168.1.1"
  ports = [ 8001, 8001, 8002 ]
  connection_max = 5000
  enabled = true
}

servers = {
  // Indentation (only spaces) is allowed but not required
  alpha = {
    ip = "10.0.0.1"
    dc = "eqdc10"
  }

  beta = {
    ip = "10.0.0.2"
    dc = "eqdc10"
  }
}

empty_map = {}

hosts = [
  "alpha",
  "omega",
]
```



## Spec

* SAN is case sensitive.
* A SAN file must be a valid UTF-8 encoded Unicode document.
* Whitespace means space (0x20).
* Newline means LF (0x0A) or CRLF (0x0D0A).




## Filename extension

SAN files should use the extension `.san`.



## MIME type

When transferring SAN files over the internet, the appropriate MIME type is `application/san`.



## Comment

Comments serve as documentation. There are two forms:

1. Line comments start with the character sequence `//` and stop at the end of the line.
2. General comments start with the character sequence `/* and stop with the first subsequent character sequence */`.

A comment cannot start inside a string or inside a comment. A general comment containing no newlines acts like a space. Any other comment acts like a newline. 




## Key/Value pair

The primary building block of a SAN document is the key/value pair.

Keys are on the left of the equals sign and values are on the right. Whitespaces are ignored around
key names and values. The key, equals sign, and value must be on the same line (though some values
can be broken over multiple lines).

```san
key = "value"
```

Values must be of the following types: String, Integer, Float, Boolean, Array, or Map. Unspecified
values are invalid.

```san
key = // INVALID
```



## Keys

A key may be either bare or quoted.

**Bare keys** may only contain ASCII letters, ASCII digits, underscores, and dashes (`A-Za-z0-9_-`).
Note that bare keys are allowed to be composed of only ASCII digits, e.g. 1234, but are always interpreted as strings.

```san
key = "value"
bare_key = "value"
bare-key = "value"
1234 = "value"
```

**Quoted keys** follow the exact same rules as either basic strings or literal strings and allow you
to use a much broader set of key names. Best practice is to use bare keys except when absolutely necessary.

```san
"127.0.0.1" = "value"
"character encoding" = "value"
"ʎǝʞ" = "value"
'key2' = "value"
'quoted "value"' = "value"
```

A *bare key* **must not be empty**.

```san
= "no key name"  // INVALID
"" = "blank"     // INVALID
'' = 'blank'     // INVALID
```
