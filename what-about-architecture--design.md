# What about **Architecture & Design ?**

The goal is to use static analysis of code to find interesting results about each feature, be it caching or dialects, and, if possible, to generalize our methods to be used in other scenarios

## **Tools used :**

* CodeCity

* IntelliJ UML plugin: generating UML from code and exporting it as XML

## **Methodology :**

Through this question we’ll try to take a closer look at the different caching strategies used in both frameworks, by having access to the source code, and more specifically the parts dealing with cache, we hope that, through code analysis, we will be able to find the differences \(or the similarities\) in this area.

We will also take a look at the classes responsible for generating the SQL for the different dialects

**References : **

* [Reverse Engineering Java Code to Class Diagram: An Experience Report](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.259.546&rep=rep1&type=pdf)

## **How **does **Entity Framework and Hibernate manage d**ialects**? **Are there any major differences? 

## Dialects

let's start with hibernate:

Let’s start with dialect: we used simple search functions, such as “find” and “grep”, to search for key words, the idea being that, by searching for those words, they will leads us to java classes that implement our features, so the search for the word dialect lead us to a package containing different classes:

* ·A mother classes containing various SQL key words and functions

* ·A more interesting result : we found classes representing different database products : postgres, MySql …  
  this is very important, as it gives an insight into dialects supported by hibernate

![](/assets/uml_postges.png)

Figure : generated UML for Dialect package

As we can see, each new version extends the older one, to alter its behavior or to add something new.

what about entity ?

![](/assets/AST.png)

## **How **does **Entity Framework and Hibernate manage caching? **Are there any major differences? 

Moving on to caching, finding interesting information was a lot harder compared to dialects. 

let's start with hibernate:

We used the same technique: searching by key word “cache”, we were able to find an interface defining various cache-related methods, but this leads us nowhere.

The next thing we tried is taking a look at the class that talks to the database:”SessionImpl”,

We used our IDE, and generated an UML to see if there are any references to cache classes:

![](/assets/UML.png)

                                                                Figure : generated UML for SessionImpl

As we can see, no references to cache

So the next thing we tried, is to examine the method that loads entities from the database, the reason being, that any cache related logic **has to be**, contained in this method. Let’s call it “the load method”

And we were not disappointed,

We found out, that en event approach was used, when the load method was called, a number of listeners are triggered, this explains why UML didn’t give us useful information, because references to those listeners are contained within methods, as opposed to a more classical OOP mechanism, such as inheritance and composition, which are more visible in UML

By examining the event listeners we found that, they also have a load method in which we can see:

![](/assets/code.png)

                                                              Figure : Calls to first & second level cache

This gives a very important insight, as we learned that hibernate has two levels of cache

Granted, the analysis of caching is more manual that it is static, but we learned that the hard way, it is very difficult to find information about a complex feature without resorting to manual work and reading the code, for various reasons, even the programming approach can affect greatly the efficiency of static analysis, as we mentioned before, the fact that an event driven approach is used, made it impossible to see references to cache classes in the generated UML

What about Entity Framework ?

![](blob:file:///7ff295cb-f130-407d-8404-28dcc79ba115)

  












