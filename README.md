### jmlok2
---
https://github.com/alyssonfm/jmlok

https://massoni.computacao.ufcg.edu.br/home/jmlok

```java
// src/utils/commons/ClassPathHacker.java
package utils.commons;

import java.io.File;
import java.io.IOException;
import java.lang.reflect.Method;
import java.net.URL;
import java.net.URLClassLoader;

public class ClassPathHacker {
  @SupressWarnings("rawtypes")
  private static final Class[] parameters = new Class[]{URL.class};
  
  public static void addFile(String s) throws IOException {
    addURL(f.toURL());
  }
  
  @SuppressWarnings("unchecked")
  public static void addURL(URL u) throws IOException {
    URLClassLoader sysloader = (URLClassLoader) ClassLoader.getSystemClassLoader();
    @SuppressWarnings("rawtypes")
    Class sysclass = URLClassLoader.class;
    
    try {
      Method method = sysclass.getDeclaredMethod("addURL", parameters);
      method.setAccessible(true);
      method.invoke(sysloader, new Object[]{u});
    } catch (Throwable t) {
      t.printStackTrace();
      throw new IOException("Error, could not add URL to system classloader");
    }
  }
}

```

```
```

```
```
