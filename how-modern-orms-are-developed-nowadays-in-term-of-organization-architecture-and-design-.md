# **How modern ORMs are developed nowadays, in term of organization, Architecture and Design ?**

Through this question we want to take a closer look at ORMs, Hibernate and Entity Framework, the purpose of this study is not to find out which ORM is better, but rather the difference between the way the two projects are conducted \(version control, commits, branching strategies …\) and the effect it has on the final products.

## What about Organization ?

### How do components evolve over time \(including ownership, bugs, build stability, metrics\) ?

**Tools used :**

* CodeCity
* Git maat
* GitHub API
* Jenkins

**Methodology :**

Here we’ll examine the components of each ORM from different points of view :

* Ownership: are components “owned” by a contributor ?

* Size : how does size of said components vary ?


Once those questions are answered , we’ll try to find more interesting correlations between those metrics, is the number of bugs reported on a components proportional to its size ? does the number of bugs decrease if a big component is broken into smaller ones ?

### How can we detect highly coupled components in ORM frameworks through contributions ?

**Tools used :**

* CodeCity
* Git maat
* GitHub API
* Jenkins
* sonar
* python/groovy scripts

**Methodology :**

Here we’ll try to find out if there is a correlation between contribution \(commits …\) and highly coupled components, this will be done by analysing commits that include multiple files belonging to different components. are two different files always committed together ?



## What about **Architecture & Design ?**

### D**oes Hibernate and Entity framework contain anti-patterns and do they influence their performance ?**

**Tools used :**

* CodeCity

* Automatically Detecting ORM Performance, Anti-Patterns on C\#   Applications:[http://scriptiesonline.uba.uva.nl/document/621996](http://scriptiesonline.uba.uva.nl/document/621996)
* Finding Performance Issues in Hibernate Usage by Static Code Analysis :[http://scriptiesonline.uba.uva.nl/document/199509](http://scriptiesonline.uba.uva.nl/document/199509)
* GitHub API

* Git Maat

* python/groovy scripts

* Jenkins


* sonar

**Methodology :**

TODO

### **How Entity Framework and hibernate manage database connections?**

**Tools used :**

* GitHub API

* python/groovy scripts

**Methodology :**

TODO

##  

## 



