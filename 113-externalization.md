# Code Externalization

Write R code in external R scripts, and use `read_chunk()` to read them into the current document.


```{.r .chunk-source}
knitr::read_chunk("113-foo.R")
```

The following two chunks are from the external R script `113-foo.R`:


```{.r .chunk-source}
1 + 1
```

```{.chunk-output}
## [1] 2
```

```{.r .chunk-source}
x = rnorm(10)
```

```{.r .chunk-source}
mean(x)
```

```{.chunk-output}
## [1] 0.07463
```

```{.r .chunk-source}
sd(x)
```

```{.chunk-output}
## [1] 0.9538
```
