# ghc-plugs-out
This package's GHC plugins that do not behave well. They have undefined
implementations for plugin functions init, solve and stop. When GHC calls into
any of these plugins it panics. This can be seen while building any one of the
test suites.

```
> cabal build test-undefined-init
[1 of 1] Compiling Undefined.Init.Plugin
[1 of 1] Compiling Main
ghc: panic! (the 'impossible' happened)
Please report this as a GHC bug:  http://www.haskell.org/ghc/reportabug
```

```
> stack test ghc-plugs-out:test-undefined-stop
[1 of 1] Compiling Undefined.Solve.Plugin
[1 of 1] Compiling Undefined.Stop.Plugin
[1 of 1] Compiling Main
ghc: panic! (the 'impossible' happened)
Please report this as a GHC bug:  https://www.haskell.org/ghc/reportabug
```
