## Overriding Java Object Class Methods

Hello Everyone!!😋

This article is the continuation of my previous article [Understanding Object class in Java](https://chakradharblogs.hashnode.dev/understanding-object-class-in-java). In this article, we will discuss how to override some important methods of Object class in java. Make sure that you have read my previous article before reading this. Let's start😃

## Overriding equals() and hashCode() methods:
The hashCode() method will return a unique number for every object which is called as hashcode and the equals() method compares two objects for equality and returns true if they have same references. Now we will override these two methods so that, the equals method checks for the arguments of the object instead of checking for the references and returns true if both the objects have same arguments. If we are overriding the equals() method then it is compulsory to override the hashCode() method. Let's see an example.

``` java
class Example 
{ 
    String name; 
    int id; 
    Example(String name, int id) 
    { 
        this.name = name; 
        this.id = id; 
    } 
    @Override
    public boolean equals(Object obj) 
    {
        // first checking if both the object references are same
        if(this == obj) 
            return true; 
        // checking whether the both the objects belongs to same class or not
        if(obj == null || obj.getClass()!= this.getClass()) 
            return false; 
        // typecasting the argument to current class object
        Example ex = (Example) obj; 
        // comparing the attributes of the passed object with the current object 
        return (ex.name.equals(this.name)  && ex.id == this.id); 
    } 
    @Override
    public int hashCode() 
    { 
        // returning id as the hashcode value
        return this.id; 
    } 
} 
class Main 
{ 
    public static void main (String[] args)  
    { 
        Example ex1 = new Example("Chakri", 1); 
        Example ex2 = new Example("Chakri", 1); 
        Example ex3 = new Example("Guru", 2);
        System.out.println(ex1.equals(ex2));
        System.out.println(ex1.equals(ex3));
        System.out.println("HashCode of ex1:"+ex1.hashCode());
        System.out.println("HashCode of ex3:"+ex3.hashCode());
    } 
}

```
```
Output:
true
false
HashCode of ex1:1
HashCode of ex3:2
```
Here we have created three objects for the class Example. ex1 and ex2 have the same arguments and ex3 has different arguments. So, according to the overridden equals() method, **ex1.equals(ex2) returns true because they have same arguments and ex1.equals(ex3) returns false because they have different arguments.**

Also, here in the hashCode() method, we have returned the value of the class attribute 'id'. However, the hashCode() method can be implemented in many other ways. For example, we can return a new value which is obtained by performing a calculation of our choice inside the method itself. In this way, we can override hashCode() and equals() methods of Java Object class.
>Note: If we don't override the hashCode() method along with the equals() method, then it will prevent our class from functioning properly when the hash-based collections like HashMap, HashSet, and Hashtable are used in our class.

## Overriding toString() method:
The toString() method returns the name of the class followed by the character '@' and the unsigned hexadecimal representation of the hash code of the object as shown below.

``` java
 class A
   {
        Example a = new A();
        System.out.println(toString(a));
   }
   //Output: A@4517d9a3
```
Now let's override the toString() method to print the name and id of a person.

``` java
public class Person 
{
    String name;
    int id;
    Person(String name, int id)
    {
        this.name = name;
        this.id = id;
    }
    @Override
	public String toString() {
		return "Name:" + name + "  Id:" + id ;
    }

    public static void main(String[] args)
    {
        Person a = new Person("Chakri", 157);
        System.out.println(a.toString());
    }
}
```
```
Output:
Name:Chakri  Id:157
```
In this way, we can override the toString() to print the required attributes.

These are some of the important Java Object class methods and the ways to override them.

You have reached the end of the article😍. That's all for today😁. Happy programming people.💛





