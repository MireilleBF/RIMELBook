# What about Organization ?

In this chapter we’ll be interested in the organizational differences between the two ORMs, to do so, we’ll examine the implementation of two features of our choosing: Caching, and dialects \[define caching and dialects ??\], the reason behind this choice is the fact the we find them interesting and also to make this study a bit more specific, given that ORMs cover a big variety of functionalities,

To do so, We will try to answer the following questions :

## How do components evolve over time \(including ownership, bugs, build stability, metrics\) ?

by components we mean structures responsible for a feature, for example, in the case of hibernate, a component is more often than not, a maven project, the study we'll only include those components

**Tools used :**

* CodeCity

* Git Maat

* GitHub API

* Jenkins

* neo4j

**Methodology :**

> @mbf : essayez de préciser ce que vous appelerez "component"

Here we’ll examine the components of each ORM from different points of view :

* Ownership: are components “owned” by a contributor ?

* Size : how does size of said components vary ? given that the two ORMs are coded in languages that are somewhat similar in terms of verbosity \(Java and C\#\), we find it fair to compare the components in terms of lines of code, the comparison doesn't stop here, as we will also look at the evolution of size during time \(from one release to another for example\)

  > @mbf : relativement au temps, les uns par rapport aux autres ? dans un système? entre les systèmes?, l'architecture?

## Are dialects and caching highly coupled with other components  ?

Here We'll examine the coupling between the caching and dialects components and the rest of the code base

> @mbf : pourquoi pas un fichier à part?

**Tools used :**

* CodeCity

* Git Maat

* GitHub API

* Jenkins

* Sonar

* Python/Groovy scripts

> @mbf : pas clair du tout... vous avez mis tout ce que vous aviez en magasin? Expliquez moi pourquoi ces outils. Jenkins?

**Methodology :**

Here we well try to see if dialects and caching components are tightly coupled with other components, in other terms, does adding new functionality require making changes in other areas of the code base, of course this is not necessarily something related to those features alone, and could be extended to other features, this question seems interesting because, usually, adding functionality to tightly coupled components is harder than adding it to a loosely coupled one.  
 To so we will analyse commits history and see if files from those components are often commited with files from other components.

> @mbf : en quoi cela nous intéresse?  
> Ce passage est écrit sans réflexion.



