# Interfaces / protocols
[Back to Home](README.md)
#### Java -> implements interfaces. C++ -> uses virtual keyword.
## Java
### What does the language support?
Java supports the use of Interfaces in order to provide a framework for a class, and make it compatible with other classes that may want to interact with it. 
### What abilities does it have?
By implementing an interface, a class can specifications for the methods that a class of that type should behave. It can specify the methods that it needs to have, and contain variables that the class will need to implement those methods. It shouldn't specify any of the actual logic of those methods, but rather be used as a guide for how the class should be implemented. 
## How is it used?
**Basic declaration of an interface:**  
```Java
public interface MyInterface {

    public String hello = "Hello";

    public void sayHello();
}
```

Using the interface keyword, an interface can be created with a similar format to a class. This interface contains one variable and one method. The variable will be reachable in any class that implements it, and that class will also need to contain a ```sayHello()``` method concretely.  

**A class implementing this interface:**
```Java
public class MyInterfaceImpl implements MyInterface {

    public void sayHello() {
        System.out.println(MyInterface.hello);
    }
}
```


Example code borrowed from [here](http://tutorials.jenkov.com/java/interfaces.html)

## C++
### What does the language support?

### What abilities does it have?

### How is it used?

