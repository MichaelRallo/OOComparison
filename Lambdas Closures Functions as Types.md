# Lambda expressions, Closures, or Functions as Types
[Back to Home](README.md)
#### Both Java and C++ support lambda expressions, allowing for functions to be created at runtime with certain custimizable features.

##Java
#####Since Java 8, Java has begun supporting several features of functional programming, including lambda expressions and closures. These functions are bound to variables, which can be called using that object. 

####A basic addition example:
```Java
    import java.util.function.*;

    //Creating the function
    Function <Integer,Integer> add1 = x -> x + 1;

    //Executing the function
    Integer two = add1.apply(1); //yields 2
```

The only contingency is that in a Java lambda, all interior variables must declared as final. For example, with this function: 
```Java
    public Function<Integer, Integer> increment() {
        // Outside the scope of the returned function:
        int n = 0;
        return arg -> {
            System.out.print(n + " " + arg + ": ");
            arg += 1;
            // n += arg; // Produces error message
            return n + arg;
        };
    }

    Function<Integer, Integer> x = increment()
```

```n``` can be used, but not modified. If you try to add or modify ```n```, you will get the message ```local variables referenced from a lambda expression must be final or effectively final``` Effectively, this means that ```n``` is final


##C++ 
C++ offers implementation for lambda functions that follows this basic framework.

####```[]() {}```  
```[]```: List of resources outside of the lambda that it should be avaliable to it  
```()```: Argument List  
```{ }```: Function body 

An example of this in in use: 

```Java
    auto lambda = [](auto x, auto y) {return x + y;};
```

A notable behavior of C++ lambdas is that their return type is usually deduced by the compiler. 