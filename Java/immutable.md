An immutable object is an **object whose internal state remains constant after it has been entirely created**.

This means that the public API of an immutable object guarantees us that it will behave in the same way during its whole lifetime.

Before trying to achieve immutability in Java, we should talk about the _final_ keyword.

In Java, **variables are mutable by default, meaning we can change the value they hold**.

By using the _final_ keyword when declaring a variable, the Java compiler won't let us change the value of that variable. Instead, it will report a compile-time error.
```java
final String name = "baeldung";
name = "bael...";
```

Note that _final_ only forbids us from changing the reference the variable holds, it doesn't protect us from changing the internal state of the object it refers to by using its public API:

```java
final List<String> strings = new ArrayList<>();
assertEquals(0, strings.size());
strings.add("baeldung");
assertEquals(0, strings.size());
```

The second _assertEquals_ will fail because adding an element to the list changes its size, therefore, it isn't an immutable object

#immutable
#final
https://www.baeldung.com/java-immutable-object#benefits-of-immutability