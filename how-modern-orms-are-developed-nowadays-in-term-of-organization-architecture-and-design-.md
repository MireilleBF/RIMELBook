# **How are modern ORMs developed nowadays, in term of Organization, Architecture and Design ?**

> **Remarques** : @mbf à enlever après prise en compte

* **Titre du chapitre** :
  * ...
* **Question générale** :
  * OK... Si on ne parvient pas à généraliser la question, alors il faut expliciter pourquoi on se pose la question sur les ORMs, en quoi répondre à cette question fait avancer nos connaissances de manière générale.
* **Pourquoi \(fera office d'introduction\) :**
  * a REVOIR
* **Outils, Méthodes \(en partie dans l'introduction\) : **
  \* 
* **Codes \(au choix à présenter dans une partie méthodologie ou dans les sous parties**
  \* 
* **Pistes \(devra servir de base à un plan de chapitre, et il faut expliquer pourquoi\)**
* **Articles : serviront de référence et pourront etre discutés**
* **En vrac**
  * Souci d'organisation avec des mauvais niveaux de titres. 
  * qui contribue à quoi?

---

Object-relational mapping \(ORM\) is a mechanism that makes it possible to address, access and manipulate objects without having to consider how those objects relate to their data sources. It abstracts away the actual details, ORM lets programmers maintain a consistent view of objects over time, even as the sources that deliver them, the sinks that receive them and the applications that access them change.

ORMs can even take care of important aspects of the database access such as caching strategies and connection management \(pooling …\), which can have quite an effect on the overall performance of the application, so we thought it would be interesting to examine hibernate and entitymanager, from different angles : organisation which is more related to contribution and Architecture/Design which is more technical, in both parts we’ll try to extract some interesting metrics/informations.

Through this question we want to take a closer look at ORMs, Hibernate and Entity Framework, the purpose of this study is not to find out which ORM is better, but rather the difference between the way the two projects are conducted \(version control, commits, branching strategies …\) and the effect it has on the final products.

> @mbf : il faut que l'on essaie de montrer pourquoi la question est intéressante : même type de projet, des architectures différentes, ... on verra plus tard en fonction des résultats... Mais il faudrait quand même mieux savoir ce que l'on cherche à savoir.

**Team :**

* Buisson Kevin

* Dahmoul Salah

* El Amrani Achraf

* Tijani Yassine



