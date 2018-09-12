# SAN

(pronounce `/seɪn/`, like `sane`)

The Simple And Needed configuration format

By <a href="https://kerkour.com" target="_blank" rel="noopener noreferrer">Sylvain Kerkour</a>

## Goals

SAN aims to be a simple open configuration format that's easy to read due to obvious semantics.
SAN is designed to map unambiguously to a map (a.k.a hash table).
SAN should be easy to parse into data structures in a wide variety of languages.



## Specs

* [v1.0.0 (draft)](versions/v1.0.0)



## Issues and discussions

<a href="https://github.com/astrocorp42/san/issues" target="_blank" rel="noopener noreferrer">On GitHub</a>


## Why

Prior to SAN, the software we built at [AstroCorp](https://astrocorp.net) used a variety of
configuration languages from full programming languages such as JavaScript to complete data structure
languages such as TOML or JSON. The problem is that each of these languages have serious flaws which are
not acceptable to build software for the future.

Because of this, we decided to create our own configuration format designed to be written and read
by humans.

That being said you will easily notice that SAN found great inspiration from languages like TOML,
HCL, JSON.

Here are some of the killer features:

* Safe
* Comments are parsed as any other values and can be written by programs
* Less is more
* Human and parser friendly
* Pure data (no templating)
* Easy to use, event without syntax coloration



## Example

```san
# This is a SAN document

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

* Simple And Needed
* Sane And Neat
* Safe And Nice
* Simple And New
* Simple And Noble
* Sylvain's Astral Notation
