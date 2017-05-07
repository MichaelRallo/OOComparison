# Interfaces / protocols
[Back to Home](README.md)
#### Java -> implements interfaces. C++ -> uses virtual keyword.
##Java
### What does the language support?
Through Java Servlets, Java has been heavily used for web dev applications. Therefore, it supports most protocols that are needed for web applications, including TCP, UDP and HTTPS. Java has expanded it's use cases into nearly every type of application that there is, so it natively supports most basic interfaces and protocols that
### What abilities does it have?
The abilities of these protocols extends mostly to the limits of the protocols themselves. Java's libraries are made to be exhaustive, so most features are implemented. 
### How is it used?
I'll use an example for how to make a basic SSL connection, although this interface can be used to make connections through a few different protocols. 
```Java
    //Required Library
    import java.net.*;  


    URL url=new URL("http://www.example.com");  
    try(final InputStream in = url.openStream()){
        //...
    }
```
A URL object is created that holds on to the URL of the target. This can be formatted to represent a few different formats, doing anything from requesting JSON to making database changes. Once you call ```openStream()```, then the request is made and the results are put in the InputStream object where they can be extracted and read. 
##C++
### What does the language support?

### What abilities does it have?

### How is it used?

