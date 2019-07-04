Does Haskell work with **knitr**?

Note we have to specify the compiler manually, e.g. `engine.path='ghc'` (`haskell` itself may not exist as an executable program).


```{.haskell .chunk-source}
[x | x <- [1..10], odd x]
```

```{.chunk-output}
## [1,3,5,7,9]
```

