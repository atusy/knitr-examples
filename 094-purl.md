# An example for `purl()`

The function `purl()` can be used to extract code chunks from a document.


```{.r .chunk-source}
1 + 1
```

```{.chunk-output}
## [1] 2
```

```{.r .chunk-source}
strsplit("hello world", " ")
```

```{.chunk-output}
## [[1]]
## [1] "hello" "world"
```

A second chunk.


```{.r .chunk-source}
if (FALSE) plot(1:10)
```

When we do not evaluate a chunk, the code from `purl()` will be commented out.


```{.r .chunk-source}
paste(letters, collapse = "|")
if (1 == 1) {
    "Awesome!"
}
```

If one chunk should not be included in the results from `purl()`, just use the chunk option `purl = FALSE`:


```{.r .chunk-source}
# we do not like significance stars!
options(stringsAsFactors = FALSE, show.signif.stars = FALSE)
```

That is it.
