## Description
Often times for APIs or libraries, invoking private methods is needed to get a certain desired effect. This can be done with relative ease with Java's built-in Reflection API.

This is the example class that this example is going to be setting a value to.
```Java
public class MyClass {

    private int number = 0;
    
    public int getNumber() {
        return number;
    }
    
    private void setNumber(int number) {
        this.number = number;
    }

}
```

The start of this code created an object of the defined class above, then prints out its `number` value to show it really is `0`. Then, it gets the declared method from the class `MyClass`, using `getDeclaredMethod` instead of `getMethod` because it is a private method. The `getDeclaredMethod` method requires the classes of the method's arguments, as well. In this case the only argument is an `int`, so the argument in the `getDeclaredMethod` methos will just be `int.class`. After the method has been fetched, it sets the method as accessable so the code can invoke it. Then, it invokes it upon the given instance of the class, which is called in this case `setNumberMethod`, with all arguments after the instance, which for this example is just `100`. That just runs the method as if it were public. After, it just prints out the value of the `getNumber` method, which returns the value that has been modified, to show it has actually changed.
```Java
MyClass myClass = new MyClass();

System.out.println(myClass.getNumber()); // Prints "0"

try {
    Method setNumberMethod = MyClass.class.getDeclaredMethod("setNumber", int.class);
    setNumberMethod.setAccessible(true);
    setNumberMethod.invoke(myClass, 100);
} catch (IllegalAccessException | NoSuchMethodException | InvocationTargetException e) {
    e.printStackTrace();
}

System.out.println(myClass.getNumber()); // Prints "100"
```

## Tags
+ Java
+ Reflection
+ Invoke
+ Method

## References
+ http://tutorials.jenkov.com/java-reflection/methods.html
+ https://www.journaldev.com/1789/java-reflection-example-tutorial#reflection-methods
