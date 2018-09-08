Read a file:

``` 
myFile = open("test.txt")
content = myFile.read();

## to reset the cursuor

myFile.seek(0)

## to read each line and return a list

myFile.readLine()

```
To find current directory "pwd" is the command

Best practices to open a file

``` 
with open("test.text") as my_file:
  content = my_file.read()
  
```  
