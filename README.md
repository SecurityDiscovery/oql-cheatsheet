# oql-cheatsheet
OQL pentesting cheatsheet

## Framework specific

### Spring

#### Configuration Properties

```oql
select property from org.springframework.boot.context.properties.source.ConfigurationProperty property
```

**This command below is helpful to discover secrets!**
```oql
select {name: property.name.string.toString(), value: property.value.toString()} from org.springframework.boot.context.properties.source.ConfigurationProperty property
```

# General

#### all strings
```oql
select s from java.lang.String s
```

#### all strings as strings
```oql
select s.toString() from java.lang.String s
```


#### strings containing a keyword

```oql
select s from java.lang.String s where s.toString().contains("sentinel")
```


