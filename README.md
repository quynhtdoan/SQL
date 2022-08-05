# JSON data in SQL Server
https://docs.microsoft.com/en-us/sql/relational-databases/json/json-data-sql-server?view=sql-server-ver16 


### Create Table ####

```{sql, connection = mydb, eval = FALSE}
CREATE TABLE "table2" (
    "id" int NOT NULL,
    "last_name" varchar(255) NOT NULL,
    "first_name" varchar(255),
    "age" int,
    PRIMARY KEY ("id")
);
```

There is also `dbWriteTable` which exports the whole data frame as a table of the database.


- delete a table permanently.

```{sql connection = mydb, eval = FALSE}
DROP TABLE "table2";
```

```{r, eval = FALSE}
mydb %>% dbExecute('DROP TABLE "table2";')
```

```{r, eval = FALSE}
drop_sql <- sqlInterpolate(mydb, "DROP TABLE ?tablename;", tablename = "table1")
mydb %>% dbExecute(drop_sql)
```
### Insert new values

```{sql, connection = mydb, eval = FALSE}
INSERT INTO 'table2' (id, last_name, first_name, age)
  VALUES (1, "Lai", "Randy", 16);  
```

```{sql, connection = mydb, eval = FALSE}
INSERT INTO 'table2' (id, last_name, first_name)
  VALUES (2, "Lai", "Natalie");
```
