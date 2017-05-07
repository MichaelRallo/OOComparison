# Multithreading
[Back to Home](README.md)
## Threads or thread-like abilities
### Both Java and C++ have Thread abilities.

#### There are 2 ways Java may Define and Start a Thread. These methods are via implementing the Runnable interface or by Subclassing the Thread Class.
##### Below is an example of implementing Threads via Subclassing (Java).

```Java
//Note this Class would be in it's separate .java file.
public class MyThread extends Thread{

  int id;
  //Constructor
  public MyThread(int id){
    this.id = id;
  }

  @Override
  public void run() {
    for(int counter = 0; counter < 5; counter++){
      try {
        Thread.sleep(1000);
        System.out.println("Thread " + id + "'s count is: " + counter);
      }
      catch (InterruptedException ex) {
        Logger.getLogger(MyThread.class.getName()).log(Level.SEVERE, null, ex);
      }
    }
  }
}

public static void main(String[] args) {
  MyThread thread1 = new MyThread(1);
  MyThread thread2 = new MyThread(2);
  thread1.start();
  thread2.start();
  System.out.println("End of Program!");
}

```
###### The output would be:  
End of Program!  
Thread 1's count is: 0  
Thread 2's count is: 0  
Thread 1's count is: 1  
Thread 2's count is: 1  
Thread 1's count is: 2  
Thread 2's count is: 2  
Thread 2's count is: 3  
Thread 1's count is: 3  
Thread 1's count is: 4  
Thread 2's count is: 4  

###### Notice how the Main Thread ended First, and then the other Threads kicked in. This is because of the Thread.sleep() added within the Thread before continuing to output.

[More examples on both Implementing Runnable and Subclassing Thread here. ](https://docs.oracle.com/javase/tutorial/essential/concurrency/runthread.html)

---

##### Below is an example of implementing Threads in C++. In C++, we can give Threads tasks by assigning them standalone functions. We can do this because unlike in Java, there is no need to include functions with a class.
```C++
void myThread(int id) {

  for (int counter = 0; counter < 5; counter++) {
    try {
      std::this_thread::sleep_for(std::chrono::seconds(1));
      std::cout << "Thread " << id << "'s count is: " << counter << std::endl;
    }
    catch (const std::exception& e) {
      std::cout << e.what();
    }
  }
}

int main() {
  std::thread thread1(myThread, 1);
  std::thread thread2(myThread, 2);

  thread1.join();
  thread2.join();

  std::cout << "End of Program!" << std::endl;
  return 0;
};
```

###### The output would be:  
End of Program!  
Thread 1's count is: 0  
Thread 2's count is: 0  
Thread 1's count is: 1  
Thread 2's count is: 1  
Thread 1's count is: 2  
Thread 2's count is: 2  
Thread 2's count is: 3  
Thread 1's count is: 3  
Thread 1's count is: 4  
Thread 2's count is: 4  

---

[A more in depth explanation may be found here.](http://www.cplusplus.com/reference/thread/thread/)

## How is multitasking accomplished?
#### Referring to the above code segments, we see particularly interesting methods/functions being code on the Thread objects. In Java, it is the start() and in C++ it is the join(). These methods are use to sunchronize threads/tasks to the main thread to ensure they begin and end as needed.
