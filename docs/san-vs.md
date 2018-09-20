# SAN vs ...


## SAN vs TOML

TOML is the primary inspiration for SAN but there is some differences:

* Lists MUST be homogenous
* Maps (Tables) and Lists (Arrays) are cleaner / not mixed.
* Types are obvious (in TOML, is type of `[[my_conf]]` really obvious ?).
* Duplicated keys are not allowed: SAN is typo safe unlike TOML



## SAN vs JSON

* Comments are allowed
* No `null`
* Less ambiguous
* Duplicate keys are NOT allowed


## SAN vs YAML

* Cleaner
* Safer
* Better
* Not indentation based
