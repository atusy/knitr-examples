# Testing text output

See if chunk options like `tidy`, `prompt` and `echo`, etc work as expected.

## A normal chunk


```{.r .chunk-source}
1 + 1
```

```{.chunk-output}
## [1] 2
```

```{.r .chunk-source}
for (i in 1:10) {
    # nothing before 10
    if (i >= 10) 
        print(i)
}
```

```{.chunk-output}
## [1] 10
```

```{.r .chunk-source}
# two blank lines below


dnorm(0)
```

```{.chunk-output}
## [1] 0.3989
```

## Do not evaluate


```{.r .chunk-source}
1 + 1
for (i in 1:10) {
    # nothing before 10
    if (i >= 10) 
        print(i)
}
# two blank lines below


dnorm(0)
```

## Add prompts


```{.r .chunk-source}
> 1 + 1
```

```{.chunk-output}
## [1] 2
```

```{.r .chunk-source}
> for (i in 1:10) {
+     # nothing before 10
+     if (i >= 10) 
+         print(i)
+ }
```

```{.chunk-output}
## [1] 10
```

```{.r .chunk-source}
> # two blank lines below
> 
> 
> dnorm(0)
```

```{.chunk-output}
## [1] 0.3989
```

## No evaluate or tidy


```{.r .chunk-source}
1+1
for (i in 1:10) {
# nothing before 10
if(i>=10)print(i)
}
# two blank lines below


dnorm(0)
```

## Do not tidy


```{.r .chunk-source}
1+1
```

```{.chunk-output}
## [1] 2
```

```{.r .chunk-source}
for (i in 1:10) {
# nothing before 10
if(i>=10)print(i)
}
```

```{.chunk-output}
## [1] 10
```

```{.r .chunk-source}
# two blank lines below


dnorm(0)
```

```{.chunk-output}
## [1] 0.3989
```

## Do not echo


```{.chunk-output}
## [1] 2
```

```{.chunk-output}
## [1] 10
```

```{.chunk-output}
## [1] 0.3989
```

## Do not comment out results


```{.r .chunk-source}
1 + 1
```

```{.chunk-output}
[1] 2
```

```{.r .chunk-source}
for (i in 1:10) {
    # nothing before 10
    if (i >= 10) 
        print(i)
}
```

```{.chunk-output}
[1] 10
```

```{.r .chunk-source}
# two blank lines below


dnorm(0)
```

```{.chunk-output}
[1] 0.3989
```

## Do not echo the 2nd expression


```{.r .chunk-source}
1 + 1
```

```{.chunk-output}
## [1] 2
```

```{.chunk-output}
## [1] 10
```

```{.r .chunk-source}
# two blank lines below


dnorm(0)
```

```{.chunk-output}
## [1] 0.3989
```

## Do not evaluate, echo the 2nd expression


```{.r .chunk-source}
for (i in 1:10) {
    # nothing before 10
    if (i >= 10) 
        print(i)
}
```

## Only evaluate the first two expressions


```{.r .chunk-source}
1 + 1
```

```{.chunk-output}
## [1] 2
```

```{.r .chunk-source}
for (i in 1:10) {
    # nothing before 10
    if (i >= 10) 
        print(i)
}
```

```{.chunk-output}
## [1] 10
```

```{.r .chunk-source}
## # two blank lines below
## 
## 
## dnorm(0)
```

## Add prompts but no tidy


```{.r .chunk-source}
> 1+1
```

```{.chunk-output}
## [1] 2
```

```{.r .chunk-source}
> for (i in 1:10) {
+ # nothing before 10
+ if(i>=10)print(i)
+ }
```

```{.chunk-output}
## [1] 10
```

```{.r .chunk-source}
> # two blank lines below
> 
> 
> dnorm(0)
```

```{.chunk-output}
## [1] 0.3989
```

## Prompts, no evaluate or tidy


```{.r .chunk-source}
> 1+1
> for (i in 1:10) {
+ # nothing before 10
+ if(i>=10)print(i)
+ }
> # two blank lines below
> 
> 
> dnorm(0)
```

## Change prompts


```{.r .chunk-source}
options(prompt = "R> ", continue = "+  ")
```


```{.r .chunk-source}
R> 1 + 1
```

```{.chunk-output}
## [1] 2
```

```{.r .chunk-source}
R> for (i in 1:10) {
+      # nothing before 10
+      if (i >= 10) 
+          print(i)
+  }
```

```{.chunk-output}
## [1] 10
```

```{.r .chunk-source}
R> # two blank lines below
R> 
R> 
R> dnorm(0)
```

```{.chunk-output}
## [1] 0.3989
```

## Backslashes


```{.r .chunk-source}
{
    # can you deal with \code{foo} or \n, \a?
    gsub("\\.", "\\\\", "a.b.c")  # \link{bar}
}
```

```{.chunk-output}
## [1] "a\\b\\c"
```

```{.r .chunk-source}
cat("a\tb\nc")
```

```{.chunk-output}
## a	b
## c
```

## Other formatR options

We can set **formatR** options globally:


```{.r .chunk-source}
options(formatR.blank = FALSE)
```


```{.r .chunk-source}
1 + 1
for (i in 1:10) {
    # nothing before 10
    if (i >= 10) 
        print(i)
}
# two blank lines below
dnorm(0)
```

Or locally in one chunk via `tidy.opts`. Do not keep comments:


```{.r .chunk-source}
1 + 1
for (i in 1:10) {
    if (i >= 10) 
        print(i)
}
dnorm(0)
```

Move left braces to the next line:


```{.r .chunk-source}
for (i in 1:10)
{
    # nothing before 10
    if (i >= 10) 
        print(i)
}
```

```{.chunk-output}
## [1] 10
```

Indent by 2 spaces:


```{.r .chunk-source}
1 + 1
for (i in 1:10) {
  # nothing before 10
  if (i >= 10) 
    print(i)
}
# two blank lines below
dnorm(0)
```

See <http://yihui.name/formatR> for details.

## Empty chunks



## Messages

Do not include messages:


```{.r .chunk-source}
1 + 1
```

```{.chunk-output}
## [1] 2
```

```{.r .chunk-source}
message("helloooo!")
```

No warnings:


```{.r .chunk-source}
1:2 + 1:3
```

```{.chunk-output}
## [1] 2 4 4
```

```{.r .chunk-source}
warning("no no no")
```

Select warnings using numeric indices:


```{.r .chunk-source}
1:2 + 1:3
```

```{.chunk-output}
## [1] 2 4 4
```

```{.r .chunk-source}
warning("no no no")
```

```{.chunk-warning}
## Warning: no no no
```

Invalid indices will select nothing:


```{.r .chunk-source}
1:2 + 1:3
```

```{.chunk-output}
## [1] 2 4 4
```

```{.r .chunk-source}
warning("no no no")
```

## The results option

Do not show text results:


```{.r .chunk-source}
1 + 1
for (i in 1:10) {
    # nothing before 10
    if (i >= 10) 
        print(i)
}
# two blank lines below
dnorm(0)
```

Flush all results to the end of a chunk:


```{.r .chunk-source}
1 + 1
for (i in 1:10) {
    # nothing before 10
    if (i >= 10) 
        print(i)
}
# two blank lines below
dnorm(0)
```

```{.chunk-output}
## [1] 2
## [1] 10
## [1] 0.3989
```

Output as is:


```{.r .chunk-source}
cat("_Markdown_,", "oh yeah, **Markdown**")
```

_Markdown_, oh yeah, **Markdown**
