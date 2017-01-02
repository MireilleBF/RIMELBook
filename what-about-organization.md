# What about Organization ?

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

## How can we detect highly coupled components in ORM frameworks through contributions ?

**Tools used :**

* CodeCity

* Git Maat

* GitHub API

* Jenkins

* Sonar

* Python/Groovy scripts


**Methodology :**

Here we’ll try to find out if there is a correlation between contribution \(commits …\) and highly coupled components. This will be done by analysing commits that include multiple files belonging to different components. Are two different files always committed together ?

