# oql-cheatsheet
OQL pentesting cheatsheet


#### strings containing a keyword

`select s from java.lang.String s where s.toString().contains("sentinel")`
