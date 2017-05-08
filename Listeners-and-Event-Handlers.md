# Implementation of listeners and event handlers
[Back to Home](README.md)

## Java
Java provides an interface for listeners called PropertyChangeListener. This allows you to add listeners to classes that have a PropertyChangeSupport object in their instance variables. This allows you to fire events from the larger class, that can be detected by any other classes that have placed listeners on them. These are particularly useful for threads, letting them pass information between themselves without risking error.

**Example:**
```Java
public class ExampleEventProducer {

    //Object to handle PropertyChange operations
    private final PropertyChangeSupport pcs = new PropertyChangeSupport(this);

    //Functions to add or remove listeners to this object
    public void addPropertyChangeListener(PropertyChangeListener listener) {
       this.pcs.addPropertyChangeListener(listener);
    }

    public void removePropertyChangeListener(PropertyChangeListener listener) {
      this.pcs.removePropertyChangeListener(listener);
    }

    //Arbitrary variable to demonstrate with
    private String value;

    public String getValue() {
       return this.value;
    }

    public void setValue(String newValue) {
        String oldValue = this.value;
        this.value = newValue;
        this.pcs.firePropertyChange("value", oldValue, newValue);
    }
}
```
This class sets up the framework for being able to detect changes to the value variable. First, we establish the operations that will allow exterior class add and remove listeners into this class. Then, in the setter for the variable that we are tracking, we call the ```firePropertyChange``` function, which will notify all listeners that have been added that something has changed.   

**Adding a listener to ExampleEventProducer class:**
```Java
...
ExampleEventProducer producer=new ExampleEventProducer()
producer.addPropertyChangeListener(new PropertyChangeListener() {
    @Override
    public void propertyChange(PropertyChangeEvent evt) {
        //when event caught, do this
    }
});
...
```
This function creates a new PropertyChangeListener on the fly, and passes it to the producer. It's required to override the ```propertyChange``` function, which will be executed whenever an event is detected. 

## C++
C++ does not have any kind of native support for event handling or listeners. However, like in most other languages, an equivalent functionality can be generated using an Observer design pattern. This has to be designed and customized by hand to fit the programmers specific use case.