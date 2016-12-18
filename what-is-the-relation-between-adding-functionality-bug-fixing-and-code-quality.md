# What is the relation between adding functionality, bug fixing, and code quality

## Abstract

In this question we will try to highlight any relation between adding functionality, bug fixing, and degradation or improvement of code quality. We hope to highlight an overall trend in the quality of the code over timeand thus confirm or invalidate the Lehman law.

The idea is that we take several criteria on the quality of the code that we are going to determine and we look at the evolution over time.We are looking for a correlation between the addition of functionalities or the correction of bugs and the quality of the code and looks at several curves if the evolution of the quality corresponds or not to the correction of beug or the addition of functionnalities, Etc ...

## Chosen methodology

To answer this question we will proceed in several steps. We will have to extract from a Github repository several versions of the same code. To do this we will extract the state of the code with each release or revision.

In this way we can hope to have enough difference between project version that we would have chosen to be able to consider them as relevant for our study.In addition, we can imagine that changes made during a review will contain more bug fixes than adding functionality, and vice versa. If this hypothesis is verified we will have between two revisions mainly bug corrections and between two versions we will have more features added, which could allow us to independently evaluate the impact of these two types of modification.

Once our code base has been extracted we will have to make a qualitative evaluation of the code for each selected revisions and versions, using tools. We can rely on the complexity of the code, which tools like Metrics or Sonar can give us.

Then we will have to extract for each revisions and version of the metrics on the number of added functionality and bug fix. We will then have all the necessary information and metrics and we will have only to correlate them and see if we can extract a significant tendency on the evolution of the quality of the code according to the additions of functionalities and Bug fixes.

Pour répondre à cette question nous allons procéder en plusieurs étapes. Nous allons devoir extraire d'un repository Github plusieur version d'un même code. Pour ce faire nous allons extraire l'état du code à chaque release ou révision.

De cette manière nous pourrons esperer avoir suffisament d'écart entre de version de projet que nous aurions choisis pour pouvoir les considérer comme pertinant pour notre étude. De plus, nous pouvons imaginer que les modification apporter lors d'une révcision tiendrons plus de la correction de bug que de l'ajout de fonctionnalité, et vice versa. Si ette hypothèse est vérifier nous aurons entre deux révisions éssentielement des corrections de bug et entre deux versions des ajout de fonctionnalité, ce qui pourrait nous permettre d'évaluer indépendament l'impact de ces deyx type de modification.

Une fois notre base de code extraite nous devrons faire une évaluation qualitative du code pour chaque révisions et version choisis, à l'aide d'outils. nous pourrons nous baser sur la complexité du code, que de outils comme Metrics ou Sonar peuvent nous donner.

Ensuite nous aurons à extraire pour chaque révisons et version des métriques sur le nombre d'ajout de fonctionnalité et de correction de bug. Nous aurons alors toutes les informations et métriques nécéssaire et nous n'aurons plus qu'a les mettre en corrélation et voir si nous pourrons en extraire une tendence significative sur l'évolution de la qualité du code en fonction de l'ajouts de fonctionnalités et des corrections de bug.

## References

\[0\] Meir M. Lehman - Programs, Life Cycles, and Laws of Software Evolution - [http://www.ifi.uzh.ch/seal/teaching/courses/archive/FS13/SWEvo13/lehman-IEEE-80.pdf](http://www.ifi.uzh.ch/seal/teaching/courses/archive/FS13/SWEvo13/lehman-IEEE-80.pdf)  - 1980

\[1\] Lehman, M. M.; J. F. Ramil; P. D. Wernick; D. E. Perry; W. M. Turski - Metrics and laws of software evolution—the nineties view [http://users.ece.utexas.edu/~perry/work/papers/feast1.pdf](http://users.ece.utexas.edu/~perry/work/papers/feast1.pdf)  -  1997

## Target project

The project on which we will base ourselves has not yet been chosen. We need a rather active project with, if possible, the same contributors throughout its evolution to limit external factors to those targeted.

Le projet sur lequel nous nous baserons n'a pas encore était choisis. nous avons besoin d'un projet assez active avec si possible les mêmes contributeurs tout du long de son évolution pour limiter les facteurs extérieurs à ceux ciblé.

