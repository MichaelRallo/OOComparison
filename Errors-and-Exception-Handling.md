# Errors and Exception Handling
[Back to Home](README.md)
#### Java and C++ handles error and exception handling quite extensively in very similar ways.
###### Checking whether an expected object is null or not is the one of the more simpler approaches, which can be done using a simple if statement. This becomes greatly useful when parsing (JSON, XML, etc.).  
###### Using Try-Catch blocks and throwing exceptions is the biggest combatant against errors and exceptions in both Java and C++. When an error occurs within the Try portion of the Block, the Catch portion of the block will execute throwing in the exception as a parameter. These errors can be thrown manually and unexpectedly throughout the program.

##### Example of Java Try-Catch without Exception:
```Java
//Note this Class would be in its separate .java file.
public class Box{
  private int boxID;

  //Constructor
  public Box(int boxID){
    if(boxID > 10){
      throw new IndexOutOfBoundsException("No BoxIDs cannot be greater than 10!");
    }
    this.boxID = boxID;
    System.out.println("BoxID is: " + boxID);
  }
}

public static void main(String[] args) {

  try {
    Box box1 = new Box(1);
  }
  catch (Exception e) {
    e.printStackTrace();
  }
  System.out.println("End of Program!");
}
```
###### The output would be:  
BoxID is: 1  
End of Program!

##### Example of Java Try-Catch with Exception:
```Java
//Note this Class would be in its separate .java file.
public class Box{
  private int boxID;

  //Constructor
  public Box(int boxID){
    if(boxID > 10){
      throw new IndexOutOfBoundsException("No BoxIDs cannot be greater than 10!");
    }
    this.boxID = boxID;
    System.out.println("BoxID is: " + boxID);
  }
}

public static void main(String[] args) {

  try {
    Box box1 = new Box(11);
  }
  catch (Exception e) {
    e.printStackTrace();
  }
  System.out.println("End of Program!");
}
```
###### The output would be:  
End of Program!  
<span style="color:red">java.lang.IndexOutOfBoundsException: No BoxIDs cannot be greater than 10!  
	at oofinalproject.Box.<init>(Box.java:19)  
	at oofinalproject.OOFinalProject.main(OOFinalProject.java:24)</span>

##### Note, the program did not crash and stop entirely even though an exception was thrown. The "End of Program!" still outputted.  Exceptions can be thrown manually like in the above example, or triggered whenever ever an error in the program occurs.
---
### C++ offers a very similar approach to handling Errors and Exception Handling like Java does.

##### Example of C++ Try-Catch without Exception:
```C++
class Box {
  public:
    //Constructor
    Box(int boxID) {
      if (boxID > 10) {
        throw std::invalid_argument("No BoxIDs cannot be greater than 10!");
      }
      this->boxID = boxID;
      std::cout << "BoxID is: " << boxID << std::endl;
    }
  private:
    int boxID;
};

int main() {

  try {
    Box box1(11);
  }
  catch (std::invalid_argument& e) {
    std::cout << e.what() << std::endl;
  }
  std::cout << "End of Program!" << std::endl;
  return 0;
};
```
###### The output would be:  
BoxID is: 1  
End of Program!

##### Example of C++ Try-Catch with Exception:
```C++
class Box {
  public:
    //Constructor
    Box(int boxID) {
      if (boxID > 10) {
        throw std::invalid_argument("No BoxIDs cannot be greater than 10!");
      }
      this->boxID = boxID;
      std::cout << "BoxID is: " << boxID << std::endl;
    }
  private:
    int boxID;
};

int main() {

  try {
    Box box1(11);
  }
  catch (std::invalid_argument& e) {
    std::cout << e.what() << std::endl;
  }
  std::cout << "End of Program!" << std::endl;
  return 0;
};
```
###### The output would be:  
No BoxIDs cannot be greater than 10!  
End of Program!

##### Like in Java note how the program did not crash and stop entirely even though an exception was thrown. The "End of Program!" still outputted.  Exceptions can be thrown manually like in the above example, or triggered whenever ever an error in the program occurs.
