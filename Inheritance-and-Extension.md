# Inheritance / Extension
[Back to Home](README.md)

#### Both Java and C++ offer Inheritance/Extension. Java may extend a class using the keyword 'extends' while C++ uses the ':' character instead. Java may subclass, or extend, from a base class only once. C++, however, may Inherit from as many classes as it likes.

#### In Java one can use the keyword 'super' to refer to the base class. Because C++ may inherit from multiple classes, there is no 'super' keyword like in Java to refer to the base class (For this would be too ambiguous). However, C++ offers a was to disambiguate such things by using "::".

##### Example of a Java Class extending another Class.
```Java
//Note this Class would be in it's separate .java file.
public class Delicious {
  public void texture(){
    System.out.println("Delicious Texture!");
  }
}

//Note this Class would be in it's separate .java file.
public class Cake extends Delicious{
  public void texture(){
    System.out.println("Cakey Texture!");
    //Because we can only extend one class its not ambiguous
    super.texture();
  }
}

public static void main(String[] args) {
  Cake cake = new Cake();
  cake.texture();
  System.out.println("End of Program!");
}
```
###### The output would be:    
Cakey Texture!  
Delicious Texture!  
End of Program!  


##### Example of a C++ Class extending 2 other Classes.
```C++
class Delicious {
  public:
    void texture() { std::cout << "Delicious Texture!" << std::endl; };
};

class Food {
  public:
      void texture() { std::cout << "Foody Texture!" << std::endl; };
};

class Cake : public Delicious, public Food {
  public:
    void texture() {
      std::cout << "Cakey Texture!" << std::endl;
      //base::texture(); or super.texture() is too ambiguous
      Delicious::texture();
      Food::texture();  
    }
};

int main() {
  Cake cake();
  cake.texture();
  return 0;
}

```
###### The output would be:    
Cakey Texture!  
Delicious Texture!  
Foody Texture!  
End of Program!  

[This Example was inspired from here.](http://stackoverflow.com/questions/357307/how-to-call-a-parent-class-function-from-derived-class-function)
