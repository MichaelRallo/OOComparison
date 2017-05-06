# Instance Reference
## What reflection abilities are supported?
#### In both Java and C++, With Reflection, we can learn about an Class's/Object's Members. It is an introspection on Types.

---

## How is reflection used?
#### In both Java and C++, Reflection can be used as a means of serialization to JSON and XML. It can also be used for object relationship mapping to a database.


#### Example of Java Reflection:
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
  Box box1 = new Box(1);
  try {
    //Get Information about the Private Field
    Field boxIDField = box1.getClass().getDeclaredField("boxID");
    System.out.println("Box ID field: " + boxIDField);

    //Get Value of the Private Field
    boxIDField.setAccessible(true);
    System.out.println("Box ID value: " + boxIDField.get(box1));
  }
  catch (Exception e) {
    e.printStackTrace();
  }
}
```

###### The output would be:  
Box ID field: private int oofinalproject.Box.boxID  
Box ID value: 1

---

#### Example of C++ Reflection:
```C++
class Box {
  public:
    //Constructor
    Box(int boxID) {
      //Note, 'this' is a pointer to itself, it's not an actual object!
      this->boxID = boxID;
    }

  private:
    int boxID;
};
```
