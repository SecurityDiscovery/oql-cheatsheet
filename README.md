# oql-cheatsheet
OQL pentesting cheatsheet


#### strings containing a keyword

```oql
select s from java.lang.String s where s.toString().contains("sentinel")
```
