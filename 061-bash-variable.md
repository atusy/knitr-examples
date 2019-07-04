# Pass variables to bash scripts

Use `Sys.setenv()`:


```{.r .chunk-source}
Sys.setenv(EXAMPLES = "example/path")
```

Now we write a `bash` code chunk:


```{.bash .chunk-source}
echo $EXAMPLES
```

```{.chunk-output}
## example/path
```

It works.
