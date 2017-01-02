# Modularity in Video Games

> **Remarques** : @mbf à enlever après prise en compte

* **Titre du chapitre** :
  * ... je ne sais pas si la limitation aux video games est une bonne idée d'autant que je ne pense pas que l'on puisse répondre à cette question par votre étude.
* **Question générale** :
  * oui
* **Pourquoi \(fera office d'introduction\) :**
  * il y a de l'idée... on en saura un peu plus après quelques essais
* **Outils, Méthodes \(en partie dans l'introduction\) : **
  * ok
* **Codes \(au choix à présenter dans une partie méthodologie ou dans les sous parties**
  * ok
* **Pistes \(devra servir de base à un plan de chapitre, et il faut expliquer pourquoi\)**
  * trop succinct
* **Articles : serviront de référence et pourront etre discutés**

  * absents... Il faudrait chercher du côté des plugings. 
    peut etre : 
    [https://books.google.fr/books?hl=fr&lr=&id=NVaZBQAAQBAJ&oi=fnd&pg=PA177&dq=software+engineering+modularity+code+quality&ots=p2EbX7G5rr&sig=AE0Pkr-4xcjn7pqZiXugQyw8WVg&redir\_esc=y\#v=onepage&q=modularity&f=false|Investigating software modularity using class and module level metrics
M English, J Buckley, JJ Collins - Software Quality Assurance: In …, 2015 - books.google.com]

* **En vrac**

---

In this chapter, it will be discussed "_how can video games \(and more generally, software\) be modular thanks to the addition of 'mods' or 'plugins' ?_". This can be the wish of the development team, or driven by the community playing the video game \(or using the software\).

_**Questions :**_

* How can a community impact the development of some features ?
* How can the addition of mod impact the architecture ?
  > @mbf : mod? module? feature?

With these questions, we hope to retrieve and measure some information like :

* the mean time between two major updates and the number of line of code implied
* the number of user requests before a major update
  > @mbf : ... community driven sofware evolution?

_**Projects to study :**_

* [Terasology](https://github.com/MovingBlocks/Terasology)
* [Intellij Idea Community](https://github.com/JetBrains/intellij-community)

_**Methodology :**_

* Analyze connection between component and plugin interface system.
* Deduce if there is a strong connection or a loosely one.
* Attempt to find every pull request involving change in plugin interface system.

_**References used:**_

* _N/A_

_**Tools used:**_

* [Github API](https://developer.github.com/v3/)
* [Diggit](https://github.com/jrfaller/diggit)

_**Distribution of Work:**_

* MANNOCCI Adrien \(M2\)
* SARROCHE Nicolas \(SI5\)



