## What Is Equivalence Partitioning?
Equivalence Partitioning is a testing technique that divides a program's input domain into data classes known as equivalence classes, which are then used to generate test cases. Each class specifies a group of inputs that the software should treat similarly.

The links within an equivalence class are symmetric, transitive, and reflexive, meaning that all components in the class are treated equally in terms of how the software processes them.

Testing one representative from each equivalence class allows testers to detect flaws efficiently without having to test every potential input.

This strategy ensures that the various input possibilities are sufficiently handled while reducing the number of test cases, making it a valuable concept to appear in software engineering interview questions.

## What Are the Steps Involved in STLC?

![image](https://github.com/user-attachments/assets/413e225e-e6c3-441c-ae3e-695783e12fd6)


## What Is Stamp Coupling?
Stamp coupling arises when part of a data structure is passed through the module interface instead of using simple data types, which can create unnecessary dependencies between components.

## What Do You Understand by Coupling?
In software engineering, coupling is the degree of interdependence between software units, often discussed in software engineering interview questions. It evaluates how closely integrated certain modules are within a system.

Lower coupling is generally preferred because it means that changes in one module are less likely to require changes in another, making the system more adaptable and easier to manage.

## What Is Common Coupling?
Common coupling occurs when multiple modules have access to the same global data area, making the system more complex to comprehend and maintain. Changes to the global data can affect all modules that reference it.


## Define Cohesion
In software engineering, cohesion is a measure of the closeness of the relationship between the various elements of a module. High cohesion means that a module performs one task or a set of related tasks and has minimal dependency on other modules, making it simpler to understand, maintain, and reuse.

## What Is Temporal Cohesion?
Temporal cohesion refers to a circumstance in which a module comprises tasks that are related because they must be completed within the same time frame.
