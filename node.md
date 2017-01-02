```
How is managed Node.js evolution over time?
```

> **Remarques** : @mbf à enlever après prise en compte

* **Titre du chapitre** : 
  * Il faut un titre qui interesse. 
* **Question générale** : 
  * La question est trop précise, que cherchez-vous plus généralement? Peu de personnes s'intéressent à la manière dont Node.js évolue dans le temps.
* **Pourquoi \(fera office d'introduction\) :**
  * dependencies? mettre en place des outils pour analyser les dépendances? 
* **Outils, Méthodes \(en partie dans l'introduction\) : **
  \* sans une question plus précise, on ne sait pas répondre.
* **Codes \(au choix à présenter dans une partie méthodologie ou dans les sous parties**
  * ok
* **Pistes \(devra servir de base à un plan de chapitre, et il faut expliquer pourquoi\)**
  * trop confus
* **Articles : serviront de référence et pourront etre discutés**

## Case Study

In the world of software management, dependency management is a hell. The system evolves more it integrates components, most system management is becoming increasingly complex.

Nodejs experienced strong growth in recent years. This includes the number of modules published the number of contributors. Node is a platform with many dependencies, publish a new version of a component can be a nightmare very quickly.

​​![](/assets/Capture.PNG)

In this chapter, we will focus on the development of nodejs philosophy

> @mbf : mais quel est le problème étudié? Pourquoi cette étude de cas?

## Methodology

We will start by watching commits over a given period, identify which modules evolve together over time and different contributors to these modules.

Then we will analyze:

* the dependency rules between these correlated modules

* * are they strict / loose ?

  > @mbf : OK pourquoi vous posez la question ?
* the version of a module changes

> @mbf : OK pourquoi vous posez la question ?

* The contributions from developers on a module

* * Who is working on such a module

  * Which developer commit the most lines

  * What are contributors to module X Version X.Y.Z

  > @mbf : OK pourquoi vous posez la question ?

## References

[NodeJS ​Foundation](https://nodejs.org/en/foundation/)

​[Registry npm](https://www.npmjs.com/package/npm-registry)​
> @mbf outil que vous compter utiliser?

​[Semantic versioning​](http://semver.org/lang/fr/)

> @mbf Pourquoi ? Où voulez-vous en venir?


​[A Unified Framework for the Comprehension of Software's time Dimension​](https://papyrus.bib.umontreal.ca/xmlui/bitstream/handle/1866/11998/Benomar_Omar_2015_these.pdf?sequence=2&isAllowed=y)

> @mbf outil que vous compter utiliser? c'est une thèse... pourquoi celui-ci?





## Tools

​[CodeCity​](https://wettel.github.io/codecity.html)
> @mbf Avez-vous vérifier les compatibilités de langage ?


​[Github ap​](https://developer.github.com/v3/)

​[Gitinspector](https://github.com/ejwa/gitinspector)​

## Distribution of work in the team

* Balde Thierno

  * Commits analysis over a given period
> @mbf : pourquoi faire?
  * Identification modules and correlated these contributors
  > @mbf : Il y a des idées mais soyez un peu plus "clair"

* Diallo Mahmoud

  * Versions Analysis of Module

  * Contributions Analys is different developers on a given module
  > @mbf : ????



