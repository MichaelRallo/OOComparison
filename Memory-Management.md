# Memory Management
[Back to Home](README.md)
### Java and C++ have their similarities when it comes to Memory Management. However, C++ offers much more functionality and flexibility.

---
## How is it handled?
### Java: Memory Management is handled via its automatic Garbage Collection. It does support non-deterministic finalize method as a means to manage memory, however it is uncommon and not recommended.
### C++: There are multiple ways the C++ may handle memory. Like Java, it does offer a Garbage Collection. Note, compilers are not required to implement this, though. Memory may also be managed manually though the use of keyword such as 'new' and 'delete.' It may also be managed via scope, as well as smart pointers.
---
## How does it work?
### Java: Java's Garbage Collection kicks in when there no are longer any references to an object. This can be difficult to track when objects are cleaned. Memory is taken care of behind the scene so that users will not have to worry about allocating and deallocating memory.
#### Example of Creating an Object in Java:

```Java
public class Box {
	public double length;
	public double breadth;
	public double height;
}
//Normal
Box box1 = new Box();
```

### C++: Like Java's Garbage Collection, C++'s Garbage Collection reclaims memory when an object will never be accessed again. The new and delete keywords can be used like in the example below to create (allocate) and delete (deallocate) memory as needed. Note if unsuccessful, new returns zero or throws an exception (super useful!). With Smart Pointers, you may use the new keyword without needing to use the delete keyword after, for it will be destroyed automatically.
#### Example of Creating an Object in C++:

```C++
class Box {
   public:
      double length;
      double breadth;
      double height;
};
//Normal
Box box1();
//New/Delete KeyWord (Normal Pointer)
Box* box2 = new Box();
delete box2;
```
---
## Garbage Collection?
### Both Java and C++ may have Garbage Collections. C++ provides more options than just Garbage Collection when it come to memory management, though. It is important to keep in mind not all C++ compilers implement Garbage Collection.  
---
## Automatic Reference Counting
### Both Java and C++ keep track of reference counts. This aids is signaling when their Garbage Collector need to collect said garbage.
