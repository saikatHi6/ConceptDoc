## What is serializtion?

The process of writing state from object to a file is call serialization. Process of converting object supported form to file or network supported form. We can achive this by using FileOtputStream and ObjectOutputStream. 

## What is Deserialization?

The process of reading state from file to object is call deserialization. Process of converting File or Network supported form to Object supported form. We can achive this by using FileInputStream and ObjectInputStream.

## transient keyword

1) transient is modifier applicable only for variable
2) we use transient keyword before a variable when do not want save the value of particular variable for a object in a file during serialization. It use to meet security reason.
3) At the time of serialization JVM avoid the object value and save the default value in the file.

## static vs trasient

Static varizbles are not part of the object state hecnce they won't participate in serialization.


## final vs transient

final variables will be participated in serialization directly by values.

## object graph in serialization

Whenever we are serializing an object the set of all objects which are reachable from object will serialized automatically. This all object call object graph.

Inside the serialized object all class should be implement serialized . If it is not it will throw NotSerializableException.

## customized serialization

If default serialization there may be a data loss of information because of transient. To recover the data loss we should implement custom serialization. We can provide customized serialization by using two methods.

1) private void writeObject(ObjectOutputStream os) throws Exception : It will be executed on the time of serialization. If we want to perform any extra work we can perform inside this method.
2) private void readObject(ObjectInputStram is) throws Exception : It will be executed on the time of Deserialization. If we want to perform extra work.

<b>Note: Above methods are callback function which is call by JVM. We should implement this methods in implemented serialized class</b> 

## Serialization respect to Inheritance

1) Child will be serializable if parent is serializable thogh child does not implement .
<b> Note: Object class not implement serializable but GenricServlet implement </b>
 ## If child implement serializable but parent not
2) Even though parent class does't implement serializable we can serialize child class by implementing serializable on child class. During serialization JVM check child class inheriting any Non-serializable class or not. If it is then JVM ignore orginal value of parent class and store default value.

3) During deserialization if parent class is not implemented serializable then JVM will call <b> Instance Control Flow </b> ( a. identification of instance member b. Execution of instance variable assignment and instanceate c. Execution of no-arg constructor

4) During de-serialization JVM will throw InvalidClassException if parent non-serialized class doesn't contain no-arg constructor. 


