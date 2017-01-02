# What about **Architecture & Design ?**

## D**oes Hibernate and Entity Framework contain anti-patterns and do they influence their performance ?**

**Tools used :**

* CodeCity

* GitHub API

* Git Maat

* Python/Groovy scripts

* Jenkins/jira

* Sonar

* static code analysis tool \(to be defined\)

>@mbf : voir l'autre chapitre

**References : **

* \[0\] Tuba Kaya, [Automatically Detecting ORM Performance, Anti-Patterns on C\# Applications](http://scriptiesonline.uba.uva.nl/document/621996) - Amsterdam University
>@mbf :... Attention ce n'est pas une publication officielle.

* \[1\]  Jasper Alblas, [finding Performance Issues in Hibernate Usage by Static Code Analysis](http://scriptiesonline.uba.uva.nl/document/199509) - Amsertdam University
>@mbf :... il faut choisir 1 article publié

**Methodology :**

The goal of this part is to detect anti-patterns in those ORM implementations, and impacts of those anti-patterns in term of perfomances and code quality. Do we find the sames anti-patterns in both Hibernate and Entity framework ? Did they have been fixed in the next commits, and how ?

>@mbf : Quels anti-patterns? liés aux ORMs? COMMENT ferez-vous le lien avec les performances? 

## **How Entity Framework and Hibernate manage caching?**

**Tools used :**

* GitHub API

* Python/Groovy scripts


**References :**

* \[2\] **http://searchwindevelopment.techtarget.com/definition/object-relational-mapping**

>@mbf : article web sur ORM mais rien à voir avec RIMEL

**Methodology :**

Through this question we’ll try to take a closer look at the different caching strategies used in both frameworks, by having access to the source code, and more specifically the parts dealing with cache, we hope that, through code analysis, we will be able to find the differences \(or the similarities\) in this area.



