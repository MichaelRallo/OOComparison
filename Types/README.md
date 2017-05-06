# Types

## What types does the language support?
#### Java supports Reference Types and Value Types. No signed (keyword)/unsigned data types are supported in Java.  
#### C++ supports Reference Types and Value Types as well as Pointers. Signed/Unsigned Types are supported in C++.

#### Enumerations, static, final, simple primitive types such a valueless (void), char, int, long, short, ... etc. are supported in both languages. Both languages also support public, private, and protected variables as well.

## Are both reference and value types supported?
#### Yes, both Java and C++ offer Reference and Value types.


## Can new value types be created?
#### Java does not offer support for type definitions. Java does, however, offer Generics.
#### C++ does offer the ability to create new types through the keyword typedef. Like Java, C++ offers Generics as well.








#### In both Java and C++, Reflection can be used as a means of serialization to JSON and XML. It can also be used for object relationship mapping to a database.

##### Example of Reference and Value Types in Java
```Java
//Note this Class would be in it's separate .java file.
public class Box {
  private int boxID;

  //Constructor
  public Box(int boxID){
    //We may treat 'this' as an Object.
    this.boxID = boxID;
  }
}

public static void main(String[] args) {
  //Value Type
  int number = 24;
  //Reference Type
  Box box1 = new Box(1);
}
```
---
##### Example of Reference and Value Types, as well as Pointers, in C++
```C++
int main() {

  int number = 5;
  int* numberPtr = &number;
  int& numberRef = number;

  std::cout << "Using Value Type: " << number << std::endl;
  std::cout << "Using Pointer Type: " << *numberPtr << std::endl;
  std::cout << "Using Reference Type: " << numberRef << std::endl;

  std::cout << "End of Program!" << std::endl << "Press Enter to Exit!" << std::endl;
  std::string exit;
  getline(std::cin, exit);
  return 0;
};
```

###### The output would be:  
Using Value Type: 5  
Using Pointer Type: 5  
Using Reference Type: 5

---
