# SAN

(pronounce `/seɪn/`, like `sane`)

The Simple And Nedded configuration format

By <a href="https://kerkour.com" target="_blank" rel="noopener noreferrer">Sylvain Kerkour</a>

## Goals

SAN aims to be a minimal data serialization format that's easy to read due to obvious semantics.
SAN is designed to map unambiguously to a hash map (a.k.a hash table).
SAN should be easy to parse into data structures in a wide variety of languages.


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

## Specs

* [Latest (v1.0.0, draft)](versions/latest)



## Issues and discussions

[On GitHub](https://github.com/astrocorp42/san/issues)


## Why

Prior to SAN, the software we built at [AstroCorp](https://astrocorp.net) used a variety of
configuration languages from full programming languages such as JavaScript to complete data structure
languages such as TOML or JSON. The problem is that each of these languages have serious flaws which are
not acceptable to build software for the next 10 years on top of.

Because of this, we decided to create our own configuration language designed to be written and read
by humans for at least the next decade.

Here are some of the killer features:

* Human and parsing friendly
* Comments
* Libraries should implement a way to preserve comments across a deserialization/serialization round
* Pure data
* Less is more


## SAN for

* Simple And Nedded
* Simple And Neat
* Simple And New
* Sylvain Astral Notation
* Simple And Noble
* Simple And Nice
* Sane And 
