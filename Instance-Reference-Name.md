# Instance Reference
[Back to Home](README.md)
### Instance references in Java and C++ both use this keyword this. However, implementation is a bit different when it comes to using 'this.' Note the primary difference of Java using a '.' operator while C++ uses a '->' operator. The this in Java is a reference, while the this in C++ is a pointer.

#### Example of Java Instance Reference:
```Java
public class Box {
  private int boxID;

  //Constructor
  public Box(int boxID){
    //We may treat 'this' as an Object.
    this.boxID = boxID;
  }
}
```
---

#### Example of C++ this Instance Reference:
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
