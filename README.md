# oql-cheatsheet
OQL pentesting cheatsheet

## Framework specific

### Spring

#### Configuration Properties

```sql
select property from org.springframework.boot.context.properties.source.ConfigurationProperty property
```

**This command below is helpful to discover secrets!**
```sql
select {name: property.name.string.toString(), value: property.value.toString()} from org.springframework.boot.context.properties.source.ConfigurationProperty property
```

# General

#### all strings
```sql
select s from java.lang.String s
```

#### all strings as strings
```sql
select s.toString() from java.lang.String s
```


#### strings containing a keyword

```sql
select s from java.lang.String s where s.toString().contains("sentinel")
```


