## Description
Getting private fields is sometimes necessary to get the desired effect out of APIs or libraries, but often times there are no getters for the desired object. By using reflection, you can get any field value, public or private.

This is the example class that this example is going to be setting a value to.
```Java
public class MyClass {
    private int number = 100;
}
```

This code at first created a new instance of `MyClass`, then gets the `Field` of `number` from the above class. This is using `getDeclaredField` and not `getField` because the field is private. The next line sets the field as accessable, so your program can access the private field. After that, the code gets the value of the field and prints it out, based on the instance of the class given, in this case the instance was previously defined as `myClass`. In this case it will print out `100`.
```Java
MyClass myClass = new MyClass();

try {
    Field numberField = MyClass.class.getDeclaredField("number");
    numberField.setAccessible(true);
    System.out.println(numberField.get(myClass));
} catch (NoSuchFieldException | IllegalAccessException e) {
    e.printStackTrace();
}
```

## Tags
+ Java
+ Reflection
+ Field
+ Get

## References
+ http://tutorials.jenkov.com/java-reflection/fields.html
+ https://www.journaldev.com/1789/java-reflection-example-tutorial#reflection-fields
