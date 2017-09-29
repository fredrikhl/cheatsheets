# Java

## run simple java class file

Given the file /tmp/java/test.java

```java
import java.lang.System;
public class test {
    public static void main(String[] args) {
        String foo = "Hello World";
        int idx = foo.indexOf(' ');
        System.out.println(foo.substring(idx+1));
        System.out.println(foo.substring(0, idx));
    }
}
```

To compile and run this code, use

```bash
javac /tmp/java/test.java
java -cp /tmp/java/ test
```


## run jar-file

```bash
java -jar /path/to/file.jar
```
