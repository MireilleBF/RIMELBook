# What about **Architecture & Design ?**

## How do Hibernate and Entity Framework deal with dialects? Are there any major differences?

One of the properties of ORMs is that they are database agnostic, but because of the existing differences in SQL between the various databases, ORMs have to account for it when it comes to the actual generation of the SQL code.** **

So we found it interesting to see how this property, which is very important, is dealt with in the two ORMs

**References : **

* reference here 

## **How **do **Entity Framework and Hibernate manage caching? **Are there any major differences?



Caching in ORMs is a major factor in the overall performance, it is also a very interesting concept, this is why we thought it would be worth the effort to compare the two implementations and see if there are any major differences, though it is very hard to draw any conclusions as to whether or not the differences we’ll find \(if any\) are related to performance, because of other factors outside of our scope

 **References :**

* reference here 

The tooling and methodology are common for caching and dialects

## **Tools used :**

* CodeCity

* IntelliJ UML plugin: generating UML from code and exporting it as XML

## **Methodology :**

Through this question we’ll try to take a closer look at the different caching strategies used in both frameworks, by having access to the source code, and more specifically the parts dealing with cache, we hope that, through code analysis, we will be able to find the differences \(or the similarities\) in this area.

We will also take a look at the classes responsible for generating the SQL for the different dialects 

More precisely, we will clone both hibernate and entity’s code base into IntelliJ, using its UML plugin, we will generate an UML graph, this graph will be exported an XML and will be parsed, thus giving us the possibility to look for classes by name and use keywords such as “cache” and “dialect”, when the research phase is done, we can visualize the results and analyse them

