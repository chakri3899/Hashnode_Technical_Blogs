## Understanding Object Class in Java

Hello Everyone😋!!

This article is everything you need to know about Object class in Java. Object class is a very important yet least celebrated class in Java.

# CONTENTS

* [What is an Object class?](#what-is-an-object-class)
* [Significance of Object class in Java](#significance-of-object-class-in-java)
* [In-built methods of Object class](#in-built-methods-of-object-class)

# **What is an Object class?**

**Object class** is the parent class of all classes in Java. Every class in Java is derived from Object class directly or indirectly. For example, if a class does not extend any other class then it is a direct child of the Object class and if it already extends another class then it is an indirect child of the Object class. Hence, if you consider the Java Inheritance hierarchy as a tree then the Object class will the root node of that tree. Object class is a part of **java.lang** package.

# **Significance of Object class in Java**

**Object class** can be used to refer to an object whose type is not known because it is the parent class of all classes and parent class reference can be used to refer to the child class objects. For example, let us consider a method getObject() that returns an object but it can be of any type which is unknown. Here, we can use object class reference to refer to that object as shown below.

>Object obj=getObject();

**Object class** also provides many **in-built methods**. These methods can be inherited by all the classes in Java. We can override each of these methods as per our requirement. Let us discuss some of these methods. 

# **In-built methods of Object class**

#### hashCode() Method: 
JVM generates a unique number for every object, which is called Hashcode. The hashCode() method will return this hashcode value of an object.
Let us see an example:
``` java
public class Example{
    public static void main(String args[])
    {
        Example ex1 = new Example();
        Example ex2 = new Example();
        System.out.println(ex1.hashCode());
        System.out.println(ex2.hashCode());
    }
}
```
```
Output:
1159190947
925858445
```
As observed above, the hashcode method returns different hashcode value for each object. 
> Note: The value returned by the hashCode() is not the address of an object. 

#### equals() Method:
This method compares two objects for equality and returns true if they are equal. This method tests whether the object references are equal—that is, if the objects compared are the exact same object. Let's see an example
``` java
public class Example{
    public static void main(String args[])
    {
        Example ex1 = new Example();
        Example ex2 = new Example();
        Example ex3 = ex2;
        System.out.println(ex1.equals(ex2)); //comparing objects with different reference 
        System.out.println(ex2.equals(ex3)); //comparing objects with same reference
    }
}
```
```
Output:
false
true
```
Here, ex1 and ex2 have different references, so equals() returns false whereas ex2 and ex3 are pointing to the same reference so equals() returns true. 
> Note: If we override the equals() method then we have to override the hashCode() method also.

#### getClass() Method:
This method returns the actual run time class of the current object. Let's see an example.
``` java
public class Example{
    public static void main(String args[])
    {
        Example ex1 = new Example();
        System.out.println(ex1.getClass());
    }
}
```
```
Output: class Example
```
> Note: We cannot override getClass() method.

#### toString() Method:
This method provides the string representation of an object and used to convert an object to a string.  The default toString() method of Object class returns the name of the class followed by the character '@' and the unsigned hexadecimal representation of the hash code of the object. Let's see an example.
``` java
public class Example{
    public static void main(String args[])
    {
        Example ex1 = new Example();
        // Below two statements give the same result
        System.out.println(ex1);
        System.out.println(ex1.toString());
    }
}
```
```
output:
Example@4517d9a3
Example@4517d9a3
```
As we can observe, the above result doesn't make any sense. So we should always override the toString() method when we are using it in our classes.
#### finalize() Method:
This method is called when the object is ready for [garbage collection](https://www.geeksforgeeks.org/garbage-collection-java/). It is called by the Garbage Collector on an object when the garbage collector determines that there are no more references to the object. 
>Note: finalize() method is called only once on an object even though that object is eligible for garbage collection multiple times.

#### clone() Method:
This method is used to create an exact copy of the current object. It creates a new instance of the class of the current object and initializes all its fields with exactly the same contents of the corresponding fields of this object.

There are other three methods **notify()**, **notifyAll()** and **wait()** which are related to `concurrency and multi-threading in Java.`

This is all you need to know about the Object class in Java😃. Stay tuned for my next article on how to override these methods of the Object class😉. 

Happy programming😍 people. 













