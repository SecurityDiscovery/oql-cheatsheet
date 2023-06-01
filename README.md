# oql-cheatsheet
OQL pentesting cheatsheet

## Framework specific

### Spring
---

#### Configuration Properties

```sql
select property from org.springframework.boot.context.properties.source.ConfigurationProperty property
```
```sql
select property.name.string.toString() + "=" + property.value.toString() from org.springframework.boot.context.properties.source.ConfigurationProperty property
```


**List registered path patterns**
```sql
select pathPattern from org.springframework.web.util.pattern.PathPattern pathPattern
```
```sql
select pathPattern.patternString.toString() from org.springframework.web.util.pattern.PathPattern pathPattern
```

## General

### Strings (`java.lang.String`)
---
**Return all strings**
```sql
select s from java.lang.String s
```

**Return strings as strings**
```sql
select s.toString() from java.lang.String s
```

**Search for the keyword `sentinel` in all strings**
```sql
select s from java.lang.String s where s.toString().contains("sentinel")
```

**Search for PRIVATE KEYs**
```sql
select s from java.lang.String s where s.toString().contains("PRIVATE KEY")
```
