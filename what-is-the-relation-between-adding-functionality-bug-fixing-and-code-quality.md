# What is the relation between adding functionality, bug fixing, and code quality ?

## **auteurs**

> **Remarques** : @mbf à enlever après prise en compte

* **Titre du chapitre** :
  * oK... on verra plus tard pour etre un peu plus percutant
* **Question générale** :
  * OK
* **Pourquoi \(fera office d'introduction\) :**
  * manque au niveau général
* **Outils, Méthodes \(en partie dans l'introduction\) : **
  \* 
* **Codes \(au choix à présenter dans une partie méthodologie ou dans les sous parties**
  \* 
* **Pistes \(devra servir de base à un plan de chapitre, et il faut expliquer pourquoi\)**
* **Articles : serviront de référence et pourront etre discutés**
* **En vrac**

---

## Abstract

In this question we will try to highlight any relation between adding functionality, bug fixing, and degradation or improvement of code quality. We hope to highlight an overall trend in the quality of the code over time and thus confirm or invalidate the Lehman law.

> @mbf : préciser laquelle

The idea is that we take several criteria on the quality of the code that we are going to determine and we look at the evolution over time.We are looking for a correlation between the addition of functionalities or the correction of bugs and the quality of the code and looks at several curves if the evolution of the quality corresponds or not to the correction of bugs or the addition of functionalities, etc.

## Problematic

The importance of our question comes from the relation between the code changes and its quality; there is a perception that when new features are added to a system that the added and modified portions of the source code are more prone to Fault. Many argued that the new code and features are prone to defects due to immaturity, lack of testing, as well as unstable requirements.

> @mbf : vous ne pouvez pas vous baser sur des rumeurs, il vous faut des références qui étayent vos propos. Ou bien vérifiez autour de vous par un mini sondage ou bien contentez vous de faire référence à Lehman.

We find that  improvements to existing features reduces bugs, improvements to code quality should reduce defect proneness an major improvements, on the other hand, can cause bugs: if we change too much code, we have too much defect prone immature code.

> @mbf : j'ai du mal à vous suivre.

But are these beliefs well-founded?Is there evidence to support the belief that bug fixes, additions, and feature enhancements can increase or abbreviate code quality?

> @mbf : OK ici.

## Chosen methodology

To answer this question we will proceed in several steps. We will have to extract from a Github repository several versions of the same code. To do this we will extract the state of the code with each release or revision.

In this way we can hope to have enough gap between two versions of project that we would have chosen to be able to consider them as relevant for our study. In addition, we can imagine that changes made during a revision will keep more bug fixes than adding functionality, and vice versa. If this assumption is verified we will have between two revisions mainly bug fixes and between two versions of feature additions, which could allow us to independently evaluate the impact of these two types of modification.

Once our code base has been extracted we will have to make a qualitative evaluation of the code for each selected revisions and versions, using tools. We can rely on the complexity of the code, which tools like Metrics or Sonar can give us.

Then we will have to extract for each revisions and version of the metrics on the number of added functionality and bug fix. We will then have all the necessary information and metrics and we will have only to correlate them and see if we can extract a significant tendency on the evolution of the quality of the code according to the additions of functionalities and Bug fixes.

> @mbf : OK

## Tools used

-github

-metrics

-sonar

> @mbf : j'aurais pensé \) code-maat...

## References

\[0\] Meir M. Lehman - Programs, Life Cycles, and Laws of Software Evolution - [http://www.ifi.uzh.ch/seal/teaching/courses/archive/FS13/SWEvo13/lehman-IEEE-80.pdf](http://www.ifi.uzh.ch/seal/teaching/courses/archive/FS13/SWEvo13/lehman-IEEE-80.pdf)  - 1980

\[1\] Lehman, M. M.; J. F. Ramil; P. D. Wernick; D. E. Perry; W. M. Turski - Metrics and laws of software evolution—the nineties view [http://users.ece.utexas.edu/~perry/work/papers/feast1.pdf](http://users.ece.utexas.edu/~perry/work/papers/feast1.pdf)  -  1997

> @mbf : Mettez en un plus moderne comme : Herraiz I, Rodriguez D, Robles G, Gonzalez-Barahona JM \(2013\) The Evolution of the Laws of Software Evolution: A Discussion Based on a Systematic Literature Review. ACM Comput Surv 46:28:1--28:28. Excellent !

## Target project

The project on which we will base ourselves has not yet been chosen. We need a rather active project with, if possible, the same contributors throughout its evolution to limit external factors to those targeted.

> @ mbf : j'ai besoin d'une séparation en plusieurs sous partie en précisant qui fait quoi.

## Contributors

BELHASSEN Issam

DENNE Djoe

DESTORS Max

MOULAYEELY Bezeid

