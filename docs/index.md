# SAN

(pronounce `/seɪn/`, like `sane`)

The Simple And Nedded configuration format

By <a href="https://kerkour.com" target="_blank" rel="noopener noreferrer">Sylvain Kerkour</a>

## Goals

SAN aims to be a minimal data serialization format that's easy to read due to obvious semantics.
SAN is designed to map unambiguously to a hash map (a.k.a hash table).
SAN should be easy to parse into data structures in a wide variety of languages.



## Specs

* [v1.0.0 (draft)](versions/v1.0.0)



## Issues and discussions

<a href="https://github.com/astrocorp42/san/issues" target="_blank" rel="noopener noreferrer">On GitHub</a>


## Why

Prior to SAN, the software we built at [AstroCorp](https://astrocorp.net) used a variety of
configuration languages from full programming languages such as JavaScript to complete data structure
languages such as TOML or JSON. The problem is that each of these languages have serious flaws which are
not acceptable to build software for the next 42 years on top of.

Because of this, we decided to create our own configuration language designed to be written and read
by humans for at least the next 42 years.

That being said you will easily notice that SAN found great inspiration from languages like TOML,
HCL, JSON.

Here are some of the killer features:

* Safe
* Comments are parsed as any other values and can be written by programs
* Human and parser friendly
* Libraries should implement a way to preserve comments across a deserialization/serialization round
* Pure data
* Less is more
* Easy to use, event without syntax coloration



## Example

```san
# This is a SAN document

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
  # Indentation (only spaces) is allowed but not required
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

## SAN for

* Simple And Nedded
* Simple And Neat
* Simple And New
* Simple And Noble
* Sane And Nice
* Sylvain's Astral Notation
