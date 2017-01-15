# What about Organization ?



In this chapter we’ll be interested in the organizational differences between the two ORMs, to do so, we’ll examine the implementation of two features of our choosing: Caching, and dialects \[define caching and dialects ??\], the reason behind this choice is the fact the we find them interesting and also to make this study a bit more specific, given that ORMs cover a big variety of functionalities

To do so, We will try to answer the following questions :



## How do components evolve over time \(including ownership, bugs, build stability, metrics\) ?

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

* Size : how does size of said components vary ?

  > @mbf : relativement au temps, les uns par rapport aux autres ? dans un système? entre les systèmes?, l'architecture?

Once those questions are answered, we’ll try to find more interesting correlations between those metrics. Is the number of bugs reported on a components proportional to its size ? Does the number of bugs decrease if a big component is broken into smaller ones ?

> @mbf : ces questions sont différentes de ORMs... On n'est plus non plus sur de l'organisation... que se passe-t-il si on ajoute un "composant" .. retrouve-t-on des responsabilités similaires dans les 2 systèmes?
>
> @mbf : qui est sur cette partie?

## How can we detect highly coupled components in ORM frameworks through contributions ?

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

Here we’ll try to find out if there is a correlation between contribution \(commits …\) and highly coupled components. This will be done by analysing commits that include multiple files belonging to different components. Are two different files always committed together ?

> @mbf : en quoi cela nous intéresse?  
> Ce passage est écrit sans réflexion.



