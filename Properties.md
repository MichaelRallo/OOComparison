# Properties
[Back to Home](README.md)

## Java
#### Getters and setters...write your own or built in?
It's required to write your own getters and setters in Java.  
**Example:**
```Java
    private String name;

    public void setName(String name) {
       this.name = name;
    }

    public String getName() {
       return this.name;
    }
```
#### Backing variables?
Java does not use backing variables. With how it handles getters and setters, they are not required.
#### Computed properties?
Java does not support computed properties, instead relying on methods to provide values that need to be computed from local instance variables.

## C++
#### Getters and setters...write your own or built in?
C++ also requires that you write in your own getters and setters.

```Java
    
class player
{
    private:
        string name;
    public:      
        void setName(string y)
        {
            name = y;
        }

        string getName();
        {
            return(name);
        }
};
```
#### Backing variables?
C++ does not use backing variables. With how it handles getters and setters, they are not required.
#### Computed properties?
C++ does not support computed properties, instead relying on methods to provide values that need to be computed from local instance variables.
