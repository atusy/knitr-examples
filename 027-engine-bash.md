# Run bash scripts


```{.r .chunk-source}
# should exist
Sys.which("bash")
```

```{.chunk-output}
##        bash 
## "/bin/bash"
```

```{.r .chunk-source}
Sys.which("sh")
```

```{.chunk-output}
##        sh 
## "/bin/sh"
```

Does `bash` work?


```{.bash .chunk-source}
echo hello world
echo 'a b c' | sed 's/ /\|/g'
# number of lines
awk 'END{print NR;}' 027-engine-bash.Rmd
```

```{.chunk-output}
## hello world
## a|b|c
## 23
```

How about `sh`?


```{.sh .chunk-source}
# run wc on all engine examples
ls | grep engine | head -n8 | xargs wc
```

```{.chunk-output}
##  124  230 1634 023-engine-python.md
##   73  179 1416 023-engine-python.Rmd
##   16   38  161 024-engine-awk.md
##   11   41  252 024-engine-awk.Rmd
##   12   21  127 025-engine-ruby.md
##    7   17  109 025-engine-ruby.Rmd
##   13   37  234 026-engine-haskell.md
##    8   37  267 026-engine-haskell.Rmd
##  264  600 4200 total
```
