## What is Externalization?

To overcome the serialization we need this. Programers do not have any control over the serialization process JVM do all the oparations. All properties will store in the file during serialization. 

Programers get full control on Externalization. JVM does not have any control. So we can manipulate objects properties to store in the file. 

Performance wise Externalization is better because of programer control.

<b>Externalizable extends to serializable.</b>
There are two methods:
1. public void writeExternal(ObjectOutput o) throws IOException
  This method will be executed automatically during serialization. We have to mention required variable inside the method to save.
2. public void readExternal(ObjectInput i)throws IOException, ClassNotFoundException
  This method will be call during de-serialization. we have to write code to read required variable from the file and restore to the current object. 
  
  <b> Note: during de-serialization JVM create a new instance of serialized object by calling no-arg constructor. Hence no-arg constructor is mandatory otherwise JVM will throw InvalidClassException </b>
