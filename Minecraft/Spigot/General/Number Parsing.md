## Description
For things like user inputs such as commands, chat input, sign input, or any number of other things, sometimes a number required. It is important to check if a specific string _is_ a number, before converting it to an Integer, or else it will throw errors, and just catching for the errors makes you look unprofessional, and makes your code very messy, along with some othe rreasons.

The code starts off with a base string, this should be the number you want to check and convert to an Integer, named `anyString`. The first method that is ran is the `NumberUtils.isNumber(String)` method from Apache Commons, that just checks if the argument string is an Integer, returning true if it is, false if it isn't. If it is an Integer, the code runs the method `Integer.parseInt(String)` that turns the string argument into an Integer, throwing errors if it can't be parsed into an Integer. The integer value is saved as an int variable `intValue`.
```Java
String anyString = "100";

if (NumberUtils.isNumber(anyString)) {
    int intValue = Integer.parseInt(anyString);
}
```

## Tags
+ Minecraft
+ Spigot
+ Integer
+ Parse
+ Apache
+ Commons
+ Argument

## References
+ https://commons.apache.org/proper/commons-lang/apidocs/org/apache/commons/lang3/math/NumberUtils.html#isNumber-java.lang.String-
+ https://www.mkyong.com/java/java-convert-string-to-int/
