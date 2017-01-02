# How is managed Node.js evolution over time?

Remarques : @mbf à enlever après prise en compte
Titre du chapitre :
A choisir la question générale est trop longue pour faire office d'un titre (bugs management along ..Open Source)?
Question générale :
OK
Attention, par la suite il semble que l'open source ne soit pas l'objectif mais seulement un moyen... Faîtes un choix. Si vous pensez que votre étude est plus générale alors ne mettez pas "Open source" dans le titre... Comme vous n'avez pas de code non open-source à étudier : Laisser open source et dans la question générale et dans les perspectives, élargissez la question, peut-on déduire de vos résultats des comportements similaires dans le cadre de projets présentant la même volatilité des développeurs? l'absence de dirigisme? En quoi votre étude est-elle impactée par le fait que vous vous intéressez uniquement à des projets open-source?
Pourquoi (fera office d'introduction) :
manque au niveau général
devra servir de base pour introduire le plan, i.e. la décomposition en sous partie. A faire assez vite pour que vous ayez votre fil conducteur.
Outils, Méthodes (en partie dans l'introduction) :
Soyez plus précis.
Codes (au choix à présenter dans une partie méthodologie ou dans les sous parties

ok mettre ce qui est ici dans la partie introduction et compléter avec les sous-parties
Pistes (devra servir de base à un plan de chapitre, et il faut expliquer pourquoi)

Articles : serviront de référence et pourront etre discutés

En vrac
personne ne semble répondre à la 1e question, même si elle mérite d'être affinée, comme dans la suite c'est intéressant)

La question du chapitre doit être revue, elle ne correspond pas vraiment à ce que vous avez prévu...
Il faut identifier
des références... ??? euh ... en fait dans les sous-rubriques
des projets à étudier aussi... cela devient urgent.
des outils !!

## Case Study

In the world of software management, dependency management is a hell. The system evolves more it integrates components, most system management is becoming increasingly complex.

Nodejs experienced strong growth in recent years. This includes the number of modules published the number of contributors. Node is a platform with many dependencies, publish a new version of a component can be a nightmare very quickly.

​​![](/assets/Capture.PNG)

In this chapter, we will focus on the development of nodejs philosophy

## Methodology

We will start by watching commits over a given period, identify which modules evolve together over time and different contributors to these modules.

Then we will analyze:

* the dependency rules between these correlated modules

* * are they strict / loose ?
* the version of a module changes

* The contributions from developers on a module

* * Who is working on such a module

  * Which developer commit the most lines

  * What are contributors to module X Version X.Y.Z

## References

[NodeJS ​Foundation](https://nodejs.org/en/foundation/)

​[Registry npm](https://www.npmjs.com/package/npm-registry)​

​[Semantic versioning​](http://semver.org/lang/fr/)

​[A Unified Framework for the Comprehension of Software's time Dimension​](https://papyrus.bib.umontreal.ca/xmlui/bitstream/handle/1866/11998/Benomar_Omar_2015_these.pdf?sequence=2&isAllowed=y)

## Tools

​[CodeCity​](https://wettel.github.io/codecity.html)

​[Github ap​](https://developer.github.com/v3/)

​[Gitinspector](https://github.com/ejwa/gitinspector)​

## Distribution of work in the team

* Balde Thierno

  * Commits analysis over a given period

  * Identification modules and correlated these contributors

* Diallo Mahmoud

  * Versions Analysis of Module

  * Contributions Analys is different developers on a given module



