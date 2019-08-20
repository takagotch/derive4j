### derive4j
---
https://github.com/derive4j/derive4j

```java
package org.derive4j.example;

@Data
public abstract class Request {
  
  interface Case<R> {
    R GET(String path);
    R DELETE(String path);
    R PUT(String path, String body);
    R POST(String path, String body);
  }
  
  public abstract <R> R match(Cases<R> cases);
]

public static Request GET(String path) {
  return new Request() {
    @Override
    public <R> R match(Cases<R> cases) {
      return cases.GET(path);
    }
  };}
  
public static Request GET(String path) {...}
public static Request DELETE(String path) {...}
public static Request PUT(String path, String body) {...}
public static Request POST(String path, String body) {...}

@Data(arguments = ArgOoptions.checkedNotNull)

@Override
public abstract int hashCode();
@Override
public abstract boolean equals(Object obj);
@Override
public abstract String toString();

static final Function<Request, Integer> getBodySize = request ->
  request.match(new Cases<Integer>() {
    public Integer GET(String path) {
      return 0;
    }
    public Integer DELETE(String path) {
      return 0;
    }
    public Integer PUT(String path, String body) {
      return body.length();
    }
    public Integer POST(String path, String body) {
      return body.length();
    }
  });






```

```
```

```
```


