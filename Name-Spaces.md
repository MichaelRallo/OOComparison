# Name Spaces
[Back to Home](README.md)
## How are name spaces implemented?
#### In Java, namespaces are called packages. They contain Classes which can be imported into Classes of other packages to gain access to them.
#### In C++, namespaces and unsurprisingly called namespaces. Like Java, you may include chunks of code and classes. These may also contain stand-alone functions, constants, definitions and more may also be imported (C++ only).

###### Example of importing and using a package in Java:
```Java
//Located in a Separate Folder
package newpackage;
  public class NewClass {
    public NewClass(){
      System.out.println("I've come from a different Package!!!");
    }
}

//Located in a Separate Folder
package oofinalproject;
import newpackage.*;

  public class OOFinalProject {
    public static void main(String[] args) {
      NewClass newClass = new NewClass();
      System.out.println("End of Program!");
    }
}
```
###### The output would be:  
I've come from a different Package!!!  
End of Program!



###### Example of importing and using a namespace in C++:
```C++
namespace newnamespace {
  #include <iostream>
  class NewClass {
    public:
      NewClass() {
        std::cout << "I've come from a different namespace!!!" << std::endl;
      }
  };
}

namespace newnamespace2 {
  #include <iostream>
  class NewClass2 {
    public:
      NewClass2() {
        std::cout << "I've come from a different namespace2!!!" << std::endl;
      }
  };
}

using namespace newnamespace2;
int main() {
  //Because we didn't say using namespace newnamespace, we must use the '::'
  newnamespace::NewClass* newClass = new newnamespace::NewClass();
  NewClass2* newClass2 = new NewClass2();

  std::cout << "End of Program!" << std::endl;
  return 0;
}
```
###### The output would be:  
I've come from a different namespace!!!  
I've come from a different namespace2!!!  
End of Program!

## How are name spaces used?

#### In Java, namespaces are used to modulate code. They bundle classes together making it easy to organize large, similar quantities of code.

#### Unlike Java, C++ allows for namespace-level constants, variables, and functions without having to put them into a Class/Interface. Also unlike in Java, C++ may reference a namespace they has not been included using the 'using' keyword via the '::'. Nested namespaces are also supported in C++.
