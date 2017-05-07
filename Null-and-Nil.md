# Null/Nil References
[Back to Home](README.md)
## Which does the language use? (null/nil/etc)
#### Java supports null. C++ supports NULL, however this is different from Java's null. C++'s NULL is defined as and may be converted to the integral (void *)0. C++ also offers nullptr which, unlike NULL, is not implicitly convertible or comparable to integral types but rather can be compared to, as well as converted to, a bool. C++ also offers a null character: '\0'.


## Does the language have features for handling null/nil references?
#### They Sure Do, examples found below:

###### Java Example of Handling nulls:
```Java
//Note this Class would be in it's separate .java file.
public class TestClass {}

public static void main(String[] args) {
  TestClass nullTest = null;
  if(nullTest == null){
    System.out.println("nullTest is False!");
  }
  else{
    System.out.println("nullTest is False!");
  }
  System.out.println("End of Program!");
}
```
###### The output would be:
nullTest is False  
End of Program!

---

###### C++ Example of Handling NULLS:

```C++
class TestClass {};

int main() {
  TestClass* nullTest = NULL;
  TestClass* nullPtrTest = nullptr;

  if (!nullTest && nullTest == NULL && nullTest == 0) {
    std::cout << "nullTest is False" << std::endl;
  }
  else {
    std::cout << "nullTest is True" << std::endl;
  }

  if (!nullPtrTest && nullPtrTest == nullptr && nullPtrTest == NULL && nullPtrTest == 0) {
    std::cout << "nullPtrTest is False" << std::endl;
  }
  else {
    std::cout << "nullPtrTest is True" << std::endl;
  }

  std::cout << "End of Program!" << std::endl;
  std::string exit;
  getline(std::cin, exit);
  return 0;
}
```
###### The output would be:
nullTest is False  
nullPtrTest is False  
End of Program!

##### C++ does offer more flexibility and options when it comes to handling and checking nulls as seen above.
