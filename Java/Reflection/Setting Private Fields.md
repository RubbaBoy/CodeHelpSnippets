## Description
Setting private fields is sometimes necessary to get the desired effect out of APIs or libraries, but often times there are no setters for the desired object. By using reflection, you can set any field value, public or private.

This is the example class that this example is going to be setting a value to.
```Java
public class MyClass {

    private int number = 0;

    public int getNumber() {
        return number;
    }

}
```

This code at first prints out the value of `number` to show its initial value, then gets the `Field` of `number` from the above class. This is using `getDeclaredField` and not `getField` because the field is private. The next line sets the field as accessable, so your program can modify anbd access the private class. After that, the code sets the value of the previously set field, in this case `100`, using the instance of the class named `myClass`. If you are setting the value of a static field, you can put `null` for the instance. The last line of code just prints out the new number value to show it has changed.
```Java
MyClass myClass = new MyClass();
System.out.println(myClass.getNumber()); // Prints "0"

try {
    Field numberField = MyClass.class.getDeclaredField("number");
    numberField.setAccessible(true);
    numberField.set(myClass, 100);
} catch (NoSuchFieldException | IllegalAccessException e) {
    e.printStackTrace();
}

System.out.println(myClass.getNumber()); // Prints "100"
```

## Tags
+ Java
+ Reflection
+ Field

## References
+ http://tutorials.jenkov.com/java-reflection/fields.html
+ https://www.journaldev.com/1789/java-reflection-example-tutorial#reflection-fields
