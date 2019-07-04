We can exit a document early using the `knit_exit()` function.

Below is a simple chunk, and there is a time-consuming chunk after it.


```{.r .chunk-source}
library(knitr)
1 + 1
```

```{.chunk-output}
## [1] 2
```

```{.r .chunk-source}
knit_exit()
```



