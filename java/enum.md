1) Important point to note about enum constructors: All enum constructors, including of course the Department enum constructor defined above, are implicitly private. So, even in case there is no access modifier defined for an enum constructor (as is the case in example shown above), the compiler implicitly assumes it to be private. Also, note that defining an enum constructor with public or protected access would result in a compiler error.

2) Two enum variables can be compared either the "==" or "equals()" method, without the need to override the Object.equals method in enum defination

3) Enum objects cannot be created explicitly except by using reflection.


For more on ENUM (https://www.javabrahman.com/corejava/the-complete-java-enums-tutorial-with-examples/)

