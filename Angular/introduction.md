**Component:**

1) Components are basic building block of Angular application.
2) Components are reusable
3) Components are depends on diffrent concern and they are indipendent.

How to build component:
We can build a class as component using @component decorator.
Every component is a Class and export is used to make it accessable to other components.


**Databinding:** 

we can use interpolation "{{}}" in template file for two way binding.

**Module:**

Module in angular used to organize the application. Angular applications are collection of modules.
 A module in a angular is a class with @ngModule decorator. @ngModule decorator will contain  component,Service, directive,pipes whic are use to be across the application.
Every angular module has to be one root module which is loaded first to launch the application.
Submodule is configuarable which can configured in root module.

**Meta data of ngModule**
1) declaration: It should containe all user defined components,pipes, directives classes to be used across the application. 
2) import: All module classes to be used across the application.
3) provider: All service classes
4) bootstrap: Root components to load.

**Note main.ts is help to bootstrap main module/class "AppModule"**

