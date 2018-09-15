# tlc-elpi
Implementation of some type theories in ELPI, an [embeddable λProlog interpreter](https://hal.inria.fr/hal-01176856/), as part of a curricular internship with professor [Claudio Sacerdoti Coen](https://github.com/sacerdot).
These theories can be used to prove some (basic) theorems using the interactive theorem prover found in `itp.elpi`. Given a type it gradually builds a typed λ-term through the use of tactics given as input by the user.

`stlc` contains term definitions, typing, conversion and tactics for the simply typed λ-calculus.

`itt` contains all of the above for a fragment Martin-Löf's [Intuitionistic Type Theory](https://archive-pml.github.io/martin-lof/pdfs/Bibliopolis-Book-retypeset-1984.pdf) (namely pi, sigma and nats).

## How to use this thing.
### 1. Install ELPI
Who could have guessed it! Go [here](https://github.com/LPCIC/elpi#how-to-install-elpi).
### 2. Prove stuff using `stlc` or `itt`
1. Create a file where you'll put what you want to prove,
2. using `accumulate` add `stlc/theory` or `itt/theory` to accumulate the whole "theory",
3. accumulate the `itp` and start the itp loop by
    1. writing something like `of X TypeDecl` where `TypeDecl` is what you want to prove and
    2. running the actual loop using: `run_itp X InScript` where `InScript` is a list of tactics that can be given as input.

As an example of how one such file could look see `test_itt.elpi`.

NOTE: `stlc` and everything concerning it is slightly outdated and may or may not be incomplete and or contain bugs.
