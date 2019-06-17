## What is serializtion?

The process of writing state from object to a file is call serialization. Process of converting object supported form to file or network supported form. We can achive this by using FileOtputStream and ObjectOutputStream. 

## What is Deserialization?

The process of reading state from file to object is call deserialization. Process of converting File or Network supported form to Object supported form. We can achive this by using FileInputStream and ObjectInputStream.

## transient keyword

1) transient is modifier applicable only for variable
2) we use transient keyword before a variable when do not want save the value of particular variable for a object in a file during serialization. It use to meet security reason.
3) At the time of serialization JVM avoid the object value and save the default value in the file.

## static vs trasient

## final vs transient
