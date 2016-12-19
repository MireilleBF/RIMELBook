# **How modern ORMs are developed nowadays, in term of organization, Architecture and Design ?**

Through this question we want to take a closer look at ORMs, Hibernate and Entity Framework, the purpose of this study is not to find out which ORM is better, but rather the difference between the way the two projects are conducted \(version control, commits, branching strategies …\) and the effect it has on the final products.

## What about Organization ?

### How do components evolve over time \(including ownership, bugs, build stability, metrics\) ?

**Tools used :**

* CodeCity
* Git Maat
* GitHub API
* Jenkins
* neo4j

**Methodology :**

Here we’ll examine the components of each ORM from different points of view :

* Ownership: are components “owned” by a contributor ?

* Size : how does size of said components vary ?

Once those questions are answered, we’ll try to find more interesting correlations between those metrics. Is the number of bugs reported on a components proportional to its size ? Does the number of bugs decrease if a big component is broken into smaller ones ?

### How can we detect highly coupled components in ORM frameworks through contributions ?

**Tools used :**

* CodeCity
* Git Maat
* GitHub API
* Jenkins
* Sonar
* Python/Groovy scripts

**Methodology :**

Here we’ll try to find out if there is a correlation between contribution \(commits …\) and highly coupled components. This will be done by analysing commits that include multiple files belonging to different components. Are two different files always committed together ?

## What about **Architecture & Design ?**

### D**oes Hibernate and Entity Framework contain anti-patterns and do they influence their performance ?**

**Tools used :**

* CodeCity

* GitHub API

* Git Maat

* Python/Groovy scripts

* Jenkins/jira

* Sonar

* static code analysis tool \(to be defined\)

**References : **

* \[0\] Tuba Kaya, [Automatically Detecting ORM Performance, Anti-Patterns on C\# Applications](http://scriptiesonline.uba.uva.nl/document/621996) - Amsterdam University

* \[1\]  Jasper Alblas, [finding Performance Issues in Hibernate Usage by Static Code Analysis](http://scriptiesonline.uba.uva.nl/document/199509) - Amsertdam University

**Methodology :**

The goal of this part is to detect anti-patterns in those ORM implementations, and impacts of those anti-patterns in term of perfomances and code quality. Do we find the sames anti-patterns in both Hibernate and Entity framework ? Did they have been fixed in the next commits, and how ?

### **How Entity Framework and Hibernate manage caching?**

**Tools used :**

* GitHub API

* Python/Groovy scripts

**Methodology :**

TODO

## 

## 



