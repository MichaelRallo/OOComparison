# Functional Programming
[Back to Home](README.md)
## Does the language support functional programming?
#### Java does not offer functional programming in a sense that functions cannot stand on their own. All functions in Java must be contained within a Class and be called off an Object.

##### Example functions on Java. Notice how we cannot place the calculateSquareArea() function by itself and that it must be placed within a Class.
```Java
//Note this Class would be in its separate .java file.
public class Square{
  public double height;
  public double width;
  //Constructor
  public Box(double height, double width){
    this.height = height;
    this.width = width;
  }
  public double calculateSquareArea(double height, double width){
    return height*width;
  }
}

public static void main(String[] args) {

  Box box1 = new Box(5,10);
  double area1 = square1.calculateSquareArea(square1.height, square1.width);

  Box box2 = new Box(5,10);
  double area2 = square2.calculateSquareArea(square2.height, square2.width);
}
```

#### C++ does offer functional programming and is highly encouraged.
```C++
class Square {
  public:
  double height;
  double width;

  //Constructor
  Square(double height, double width) {
    this->height = height;
    this->width = width;
  }
};

double calculateSquareArea(double height, double width) {
  return height*width;
}

int main() {

  Square square1(5, 10);
  double area1 = calculateSquareArea(square1.height, square1.width);

  Square square2(5, 10);
  double area2 = calculateSquareArea(square2.height, square2.width);
  return 0;
};
```
#### Notice how C++ functions may be standalone and do not need to be within a Class.
