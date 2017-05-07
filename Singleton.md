# Singleton
[Back to Home](README.md)

### Singletons are used to ensure only one instance of an Object is created. This patterns proves useful in cases where exactly one objects is needed to coordinate actions across a system.
## How is a singleton implemented?
###### Example of Java's Singleton (Pugh's Singleton):
```Java
//Note this Class would be in it's separate .java file.
public class MyThread extends Thread{

    MySingletonLazy singletonLazyObject;
    int id;
    public MyThread(int id){
        this.id = id;
    }

    @Override
    public void run() {
        this.singletonLazyObject = MySingletonLazy.getInstance();
        System.out.println("From Thread "+ this.id);
    }
}

//Note this Class would be in it's separate .java file.
public class MySingletonLazy {
    private MySingletonLazy() {System.out.println("New Instance Created!");}

    private static class SingletonHolder {
        private static final MySingletonLazy INSTANCE = new MySingletonLazy();
    }

    public static MySingletonLazy getInstance() {
        return SingletonHolder.INSTANCE;
    }
}

public static void main(String[] args) {
  MyThread thread1 = new MyThread(1);
  MyThread thread2 = new MyThread(2);
  MyThread thread3 = new MyThread(3);
  thread1.start();
  thread2.start();
  thread3.start();

  System.out.println("End of Program!");
}
```
###### The output would be:
End of Program!
New Instance Created!
From Thread 1
From Thread 2
From Thread 3


###### Example of C++'s Singleton (Meyer's Singleton):
```C++
class MySingletonLazy {
  public:
    static MySingletonLazy& GetInstance() {
      static MySingletonLazy keyboard;
      return keyboard;
    }

  private:
    MySingletonLazy() {
      std::cout << "New Instance Created!" << std::endl;
    }
    MySingletonLazy(const MySingletonLazy&);
    MySingletonLazy& operator=(const MySingletonLazy&);
};

void myThread(int id) {
  MySingletonLazy::GetInstance();
  std::cout << "From Thread " << id << std::endl;
}

int main() {
  std::thread thread1(myThread, 1);
  std::thread thread2(myThread, 2);
  std::thread thread3(myThread, 3);

  thread1.join();
  thread2.join();
  thread3.join();

  std::cout << "End of Program!" << std::endl;
  return 0;
}
```
###### The output would be:
New Instance Created!   
From Thread 1  
From Thread 2  
From Thread 3  
End of Program!  

---

## Can it be made thread-safe?
### Both This normal and lazy implementations in the examples provided are thread safe, though the C++ implementation requires C++ 11+.

---

## Can the singleton instance be lazily instantiated?
#### Yes, both Java and C++ offers lazy instantiation of singletons. The examples used above are implemented using this technique.




[For more ways and information on C++ Singletons, click here.](http://www.devartplus.com/3-simple-ways-to-create-singleton-in-c/)
