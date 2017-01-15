# What about **Architecture & Design ?**

## How do Hibernate and Entity Framework deal with caching and dialects? Are there any major differences?

One of the properties of ORMs is that they are database agnostic, but because of the existing differences in SQL between the various databases, ORMs have to account for it when it comes to the actual generation of the SQL code.** **

So we found it interesting to see how this property, which is very important, is dealt with in the two ORMs

**References : **

* \[0\] Tuba Kaya, [Automatically Detecting ORM Performance, Anti-Patterns on C\# Applications](http://scriptiesonline.uba.uva.nl/document/621996) - Amsterdam University

  > @mbf :... Attention ce n'est pas une publication officielle.

* \[1\]  Jasper Alblas, [finding Performance Issues in Hibernate Usage by Static Code Analysis](http://scriptiesonline.uba.uva.nl/document/199509) - Amsertdam University

  > @mbf :... il faut choisir 1 article publié

## **How Entity Framework and Hibernate manage caching?**

**References :**

* \[2\] [http://searchwindevelopment.techtarget.com/definition/object-relational-mapping](http://searchwindevelopment.techtarget.com/definition/object-relational-mapping)

> @mbf : article web sur ORM mais rien à voir avec RIMEL

## **Tools used :**

* CodeCity

* IntelliJ UML plugin: generating UML from code and exporting it as XML

## **Methodology :**

Through this question we’ll try to take a closer look at the different caching strategies used in both frameworks, by having access to the source code, and more specifically the parts dealing with cache, we hope that, through code analysis, we will be able to find the differences \(or the similarities\) in this area.

We will also take a look at the classes responsible for generating the SQL to see way dialect management.

More precisely, we will clone both hibernate and entity’s code base into IntelliJ, using its UML plugin, we will generate an UML graph, this graph will be exported an XML and will be parsed, thus giving us the possibility to look for classes by name and use keywords such as “cache” and “dialect”, when the research phase is done, we can visualize the results and analyse them



