# Errors and Exception Handling
#### Java handles error and exception handling quite extensively.
###### Checking whether an expected object is null or not is the one of the more simpler approaches. This can be done using a simple if statement. This becomes greatly useful when parsing (JSON, XML, etc.).  
###### Using Try-Catch blocks and throwing exceptions is Java's biggest combatant against errors and exceptions. Java an error occurs within the Try portion of the Block, the Catch portion of the block will execute throwing in the exception as a parameter.

##### Example of Java Try-Catch without Exception:
```Java
//Note this Class would be in it's separate .java file.
public class Box {
  private int boxID;

  //Constructor
  public Box(int boxID){
    this.boxID = boxID;
  }
}

public static void main(String[] args) {
  Box box1 = new Box(1);
  try {
    //Get Information about the Private Field *** THIS FIELD DOES EXIST ***
    Field boxIDField = box1.getClass().getDeclaredField("boxID");
    System.out.println("Box ID field: " + boxIDField);

    //Get Value of the Private Field
    boxIDField.setAccessible(true);
    System.out.println("Box ID value: " + boxIDField.get(box1));
  }
  catch (Exception e) {
    e.printStackTrace();
  }
  System.out.println("End of Program!");
}
```
###### The output would be:  
Box ID field: private int oofinalproject.Box.boxID  
Box ID value: 1  
End of Program!

##### Example of Java Try-Catch with Exception:
```Java
//Note this Class would be in it's separate .java file.
public class Box {
  private int boxID;

  //Constructor
  public Box(int boxID){
    this.boxID = boxID;
  }
}

public static void main(String[] args) {
  Box box1 = new Box(1);
  try {
    //Get Information about the Private Field *** THIS FIELD DOES NOT EXIST ***
    Field boxIDField = box1.getClass().getDeclaredField("someFieldThatDoesNotExist");
    System.out.println("Box ID field: " + boxIDField);

    //Get Value of the Private Field
    boxIDField.setAccessible(true);
    System.out.println("Box ID value: " + boxIDField.get(box1));
  }
  catch (Exception e) {
    e.printStackTrace();
  }
  System.out.println("End of Program!");
}
```
###### The output would be:  
End of Program!  
<span style="color:red">java.lang.NoSuchFieldException: boxIDThrowException  
	at java.lang.Class.getDeclaredField(Class.java:2070)  
	at oofinalproject.OOFinalProject.main(OOFinalProject.java:25)</span>

##### Note, the program did not crash and stop entirely even though an error occured. The "End of Program!" still outputted. This is the power of Java's try-catch block.
---
### C++ offers a very similar approach to handling Errors and Exception Handling like Java does.
