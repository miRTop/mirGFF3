# 1.1 October, 24th, 2018

* UID is following exactly MINTplates licenses since this commit: 7f7717d5f23ea638f1a14fccc6386e1dbb8a7e1a in mirtop applied
* iso_5p and iso_3p changed their meaning. Nows the sign means whether the isomiR starts or ends upstream or downstream the refence sequence. This mainly affects iso_5p where the sign will be the opposite than in version 1.0. `-` -> `+` and `+` -> `-`.
* `snp` word was change to `snv` to support any kind of variant
* `iso_add` is renamed to `iso_add3p` and the category `iso_add5p` is added to the list
