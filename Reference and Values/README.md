# References and Values
### When it comes to references and values, Java and C++ have their similarities and differences. For example, Java always passes types (primitive and reference) by value and objects by reference. In C++, however, there is support to pass types (primitive and user defined) by pointers, references, values.  

## How are values compared?
### Java: Values (strings) may be compared using the .equals() method is used. For reference/object comparisons (to see if two variables are pointing to the same object) the == is used. Below is an example of both:
```Java
public static void main(String[] args) {
  //Value Comparison
  String str1 = "hello";
  if(str1.equals("hello")){
    System.out.println("Value, We have a match!");
  }

  //Reference Comparison
  Box box1 = new Box();
  Box box2 = box1;
  if(box1 == box2){
    System.out.println("Reference, We have a match!");
  }
}
```
### C++: Like Java, C++ has a .compare() method to compare values (strings). Unlike Java, however, C++ utilizes the == to not just compare references, but also values.
```C++
int main() {
  //Value Comparison
  std::string str1 = "hello";
  if (str1.compare("hello") == 0 && str1 == "hello") {
    std::cout << "Value, We have a match!" << std::endl;
  }

  //Reference Comparison
  Box* box1 = new Box();
  Box* box2 = box1;
  if (box1 == box2) {
    std::cout << "Reference, We have a match!" << std::endl;
  }

  return 0;
};
```
