# Classes
[Back to Home](README.md)
### Classes in Java and C++ can be pretty similar in functionality. There are a few structural differences when it comes to classes in each of the languages, though. Inner/Nested classes are supported in both Java and C++, however unlike C++, Java allows for anonymous classes to capture variables that may be out of scope otherwise.

---
## Defining
### Java: Each Class in Java, with the exceptions of inner/anonymous classes, must be in their own file.
#### Defining a Class in Java:
```Java
public class Box {
  public double length;
  public double breadth;
  public double height;
  protected int groupID;
  private int boxID;

  public int getBoxID(){ return boxID; }
  public void setBoxID(int id){ boxID = id; }
}
```

### C++:
#### Defining a Class in C++:
```C++
class Box {
  public:
    double length;
    double breadth;
    double height;

    int getBoxID() const { return boxID; }
    void setBoxID(const int id) { boxID = id; }

  protected:
    int groupID;

  private:
    int boxID;
};
```

---
## Creating new instances
#### Example of Creating an Instance of an Object in Java:

```Java
//Normal
Box box1 = new Box();
```

#### Example of Creating an Instance of an Object in C++:

```C++
//Normal
Box box1();

//A Pointer may also be used.
Box* box2 = new Box();
delete box2;
```
---
## Constructing/initializing
### Java: The Constructor can be implemented simply by creating a method using the Class name. Overloading and Overriding are available as well.
```Java
//Note this Class would be in it's separate .java file.
public class Shape{
    public void color(){
      System.out.println("I love Colors!");
    }
}

//Note this Class would be in it's separate .java file.
public class Box extends Shape{
  public double length;
  public double breadth;
  public double height;
  protected int groupID;
  private int boxID;

  public int getBoxID(){ return boxID; }
  public void setBoxID(int id){ boxID = id; }

  //Constructor
  public Box(){
    System.out.println("Box Created!");
  }

  //Constructor Overload
  public Box(int id){
    boxID = id;
    System.out.println("Box Created with ID!");
  }

  //Constructor Overriding
  public void color(){
    System.out.println("I love Boxy Colors!");
  }
}
```
### C++: Can be implemented similar to java. Overloading and Overriding are available as well.

```C++
class Shape {
  public:
    void color() {
      std::cout << "I love Colors!" << std::endl;
    }
};

class Box {
  public:
    double length;
    double breadth;
    double height;

    int getBoxID() const { return boxID; }
    void setBoxID(const int id) { boxID = id; }

    //Constructor
    Box() {
      std::cout << "Box Created!" << std::endl;
    }

    //Constructor Overload
    Box(int id) {
      boxID = id;
      std::cout << "Box Created with ID!" << std::endl;
    }

    //Constructor Overriding
    void color() {
      std::cout << "I love Boxy Colors!" << std::endl;
    }

  protected:
    int groupID;

  private:
    int boxID;
  };
```
---
## Destructing/de-initializing
### Java: Java is a Garbage Collected Language, which makes is very difficult to predict when an object will be destroyed. As a result, there are no destructors in Java, however, there is a finalize method which can be used to determine is an object has been closed or not.
### C++: The delete Keyword makes it easy to determine when/where an Object is being destructed/de-initialized. Note by adding a ~ before the class name we create the constructor method. The Example below outputs: "Box Created! Box Destroyed!"

```C++
class Box {
  public:
    double length;
    double breadth;
    double height;

    int getBoxID() const { return boxID; }
    void setBoxID(const int id) { boxID = id; }

    //Constructor
    Box() {
      std::cout << "Box Created!" << std::endl;
    }

    //Destructor
    ~Box() {
      std::cout << "Box Destroyed!" << std::endl;
    }

  protected:
    int groupID;

  private:
    int boxID;
};

int main() {
  Box* Box2 = new Box();
  delete Box2;
  return 0;
};
```
