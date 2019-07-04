# Compile C code


```{.r .chunk-source}
# is gcc there?
Sys.which("gcc")
```

```{.chunk-output}
##            gcc 
## "/usr/bin/gcc"
```

Does `engine = 'c'` work?


```{.c .chunk-source}
void square(double *x) {
  *x = *x * *x;
}
```

Test the `square()` function:


```{.r .chunk-source}
.C("square", 9)
```

```{.chunk-output}
## [[1]]
## [1] 81
```

```{.r .chunk-source}
.C("square", 123)
```

```{.chunk-output}
## [[1]]
## [1] 15129
```
