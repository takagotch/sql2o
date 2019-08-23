### sql2o
---
https://github.com/aaberg/sql2o

https://www.sql2o.org/

```java
// core/src/test/java/org/sql2o/converters/CustomUUIDConverter.java

public class CustomUUIDConverter implements Converter<UUID> {
  public UUID convert(Object val) throws ConverterException {
    if (val == null) {
      return null;
    }
    
    if (String.class.isAssignableFrom(val.getClass())) {
      return UUID.fromString(((String)val).replace('!', '-'));
    }
    
    throw new ConverterException("Cannot convert type " + val.getClass() + " " + UUID.class);
  }
  
  public Object toDatabaseParam(UUID val) {
    return val.toString().replace('-', '!');
  }
}

```

```
```

```
```


