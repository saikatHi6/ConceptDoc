## What is an immutable class?

An immutable class is a class whose instances can not be modified. Information store in immutable object store when object is created and after that it is unchangable and read-only forever.

## Advantages & Disadvantages

1. Are stable (reduce code duplicay, better design approach)
2. fault taularance (Failure atomicity: safe automatically when give exception)
3. Can be share freely (caste algoritham compare and swap)
4. works well as map key and set elements.

## How to create immutable class?

May lead performance problem

## When to create immutable class?

1. Make all final attributes in class.
2. Dont' provide any method to modify the object's attributes.
3. Ensure that class can't be extended
4. Ensure exclusive access to any mutable attributes.

Enforce encapsulation
Enforce Architechture

(Ref1)[https://www.youtube.com/watch?v=ffMA1t9OiNs]
(Ref2)[https://dzone.com/articles/immutables-in-java]
