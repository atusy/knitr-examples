R works, of course.


```{.r .chunk-source}
library(knitr)
set.seed(123)
rnorm(5)
```

```{.chunk-output}
## [1] -0.56048 -0.23018  1.55871  0.07051  0.12929
```

Does **knitr** work with Python? Use the chunk option `engine='python'`:


```{.python .chunk-source}
x = 'hello, python world!'
print(x)
```

```{.chunk-output}
## hello, python world!
```

```{.python .chunk-source}
print(x.split(' '))
```

```{.chunk-output}
## ['hello,', 'python', 'world!']
```

Or use the syntax ```` ```{python} ````:


```{.python .chunk-source}
x = 'hello, python world!'
print(x.split(' '))
```

```{.chunk-output}
## ['hello,', 'python', 'world!']
```

If all the chunks below are python chunks, we can set the engine globally:



## Chunk Options

You can use some chunk options like `eval`, `echo` and `results`. For example, `eval=FALSE` (do not evaluate code):


```{.python .chunk-source}
x = 'hello, python world!'
print(x)
print(x.split(' '))
```

or `echo=FALSE` (hide source code):


```{.chunk-output}
## hello, python world!
```

```{.chunk-output}
## ['hello,', 'python', 'world!']
```

or `results='hide'`:


```{.python .chunk-source}
x = 'hello, python world!'
print(x)
```

```{.python .chunk-source}
print(x.split(' '))
```

or `results='asis'`:


```{.python .chunk-source}
print '**Write** _something_ in `Markdown` from `Python`!'
```

**Write** _something_ in `Markdown` from `Python`!

You can also cache the computation:


```{.python .chunk-source}
import time
# pretend this is a time-consuming task...
time.sleep(10)
print(1+1)
```

```{.chunk-output}
## 2
```

## Strict Markdown

You can use strict markdown (i.e. indent by 4 spaces) by setting `render_markdown(TRUE)`.


    render_markdown(TRUE)

Now see how the output is changed:


    x = 'hello, python world!'
    print(x)

    ## hello, python world!

    print(x.split(' '))

    ## ['hello,', 'python', 'world!']
