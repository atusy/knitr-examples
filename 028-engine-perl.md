# Run perl scripts


```{.r .chunk-source}
# should exist
Sys.which("perl")
```

```{.chunk-output}
##            perl 
## "/usr/bin/perl"
```

Does `perl` work?


```{.perl .chunk-source}
$test = "jello world";
$test =~ s/j/h/;
print $test
```

```{.chunk-output}
## hello world
```
