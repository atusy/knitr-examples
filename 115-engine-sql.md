---
title: "Knit SQL Demo"
---


```{.r .chunk-source}
library(DBI)
db <- dbConnect(RSQLite::SQLite(), dbname = ":memory:")
```


```{.sql .chunk-source}
DROP TABLE IF EXISTS packages
```


```{.sql .chunk-source}
CREATE TABLE packages (id INTEGER, name TEXT)
```


```{.sql .chunk-source}
INSERT INTO packages VALUES (1, 'readr'), (2, 'readxl'), (3, 'haven')
```


```{.sql .chunk-source}
SELECT * FROM packages
```




|id |name   |
|:--|:------|
|1  |readr  |
|2  |readxl |
|3  |haven  |


```{.r .chunk-source}
packageReadR <- "readr"
```


```{.sql .chunk-source}
SELECT * FROM packages
WHERE name = ?packageReadR
```


```{.r .chunk-source}
readrPackage
```

```{.chunk-output}
##   id  name
## 1  1 readr
```

