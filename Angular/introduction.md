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

**Template Expression**
Exp {{expression}}
**Template Statement**
(event) = statement
Exp (click) = "changeName()"

**Directives**
Directives are used to change the behaviour of the components or elements. We can use directives in the of HTML attributes.

**Why Directives?**

We need to modify thr DOM elements.
Reusable and independent code.
Create custom elements to implements the requered funtionality.

Types of directives

Component:  directive with templates
Strucral directives :  it helps to add or remove DOM elements. * derective-name = expression exp: ngIf,ngFor (it doesn't hide elements)
Attributes directives: 

-------------------------------------------
Custom directive:
1.
@Directive{
	selector: '[appRoot]'
}
we have to give directive name
2.
Create a constructor by injecting two classes
a) TemplateRef which acquires <ng-template> content
b) ViewcontainerRef which use bor add or remove elements
3. 
@Input() decorator
directive will receive value from the components

exportAs:
This is a directive properties using which we can access directive classes properties and methods in a components template.


Data Binding
It is a mechanisam to communicate between view and class.
Oneway Data Binding
1) Property Binding <img [src] = 'imageURL'> or <img bind-src = 'imageURL'>
2) Attribute Binding
3) Event Binding (click) = "onSubmit()"
4) Style Binding [style.stleProperty]
5) class Binding
{{expression}}
(event) = "expression"

TwoWay Data Binding
[()]

What is Pipe?
Pipe is use to transform the data inside template. 
exp: {{expression | titlecase}}


<select #language (change) = "message = language.value">
  <option value= "en">English </option>
 </select> 
 








