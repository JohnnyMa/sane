# SANE vs ...


## SANE vs TOML

TOML is the primary inspiration for SANE, but there are some differences:

* Lists MUST be homogenous
* Maps (Tables) and Lists (Arrays) are cleaner / not mixed.
* Types are obvious (in TOML, is type of `[[my_conf]]` really obvious ?).
* Duplicated keys are not allowed: SANE is typo safe unlike TOML



## SANE vs JSON

* Comments are allowed
* No `null`
* Less ambiguous
* Duplicate keys are NOT allowed


## SANE vs YAML

* Cleaner
* Safer
* Better
* Not indentation based
