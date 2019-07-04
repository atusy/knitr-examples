---
title: "Merging messages"
---

Different messages are placed in separate blocks:


```{.r .chunk-source}
f = function() {
    message("Hello")
    message("World!")
}
f()
```

```{.chunk-message}
## Hello
```

```{.chunk-message}
## World!
```

Consecutive identical messages are automatically merged into a single block:


```{.r .chunk-source}
f1 = function() {
    for (i in 1:5) message("Hello")
}
f1()
```

```{.chunk-message}
## Hello
## Hello
## Hello
## Hello
## Hello
```

```{.r .chunk-source}
f2 = function() {
    for (i in 1:5) warning("Hello")
}
f2()
```

```{.chunk-warning}
## Warning in f2(): Hello

## Warning in f2(): Hello

## Warning in f2(): Hello

## Warning in f2(): Hello

## Warning in f2(): Hello
```

A message in `message(..., appendLF = FALSE)` will be merged with the next adjacent message:


```{.r .chunk-source}
f3 = function() {
    message("Hello ", appendLF = FALSE)
    message("World!")
}
f3()
```

```{.chunk-message}
## Hello World!
```
