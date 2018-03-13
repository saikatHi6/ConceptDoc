
[Can constructors throw exceptions in Java?](https://stackoverflow.com/questions/1371369/can-constructors-throw-exceptions-in-java#)

Constructors are nothing more than special methods, and can throw exceptions like any other method. A constructor CAN throw any exception. 
But if any subclass constructor calls a super class constructor which throws an exception,
then the subclass constructor must either catch the exception or throw it.
