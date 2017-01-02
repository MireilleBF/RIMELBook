# **What is the impact of the structure \(teams organisation\) on the code and vice versa ?**

> **Remarques** : @mbf à enlever après prise en compte

* **Titre du chapitre** :
* A choisir la question générale est trop longue pour faire office d'un titre \(bugs management along ..Open Source\)?
*
* **Question générale** :
* OK
* Attention, par la suite il semble que l'open source ne soit pas l'objectif mais seulement un moyen... Faîtes un choix. Si vous pensez que votre étude est plus générale alors ne mettez pas "Open source" dans le titre... Comme vous n'avez pas de code non open-source à étudier : Laisser open source et dans la question générale et dans les perspectives, élargissez la question, peut-on déduire de vos résultats des comportements similaires dans le cadre de projets présentant la même volatilité des développeurs? l'absence de dirigisme? En quoi votre étude est-elle impactée par le fait que vous vous intéressez uniquement à des projets open-source?
* **Pourquoi \(fera office d'introduction\) :**
* manque au niveau général
* devra servir de base pour introduire le plan, i.e. la décomposition en sous partie. A faire assez vite pour que vous ayez votre fil conducteur.
* **Outils, Méthodes \(en partie dans l'introduction\) : **
* Soyez plus précis.
* **Codes \(au choix à présenter dans une partie méthodologie ou dans les sous parties**

* ok mettre ce qui est ici dans la partie introduction et compléter avec les sous-parties

* **Pistes \(devra servir de base à un plan de chapitre, et il faut expliquer pourquoi\)**

* **Articles : serviront de référence et pourront etre discutés**

* **En vrac**
1. TeamCodeParser est lié à github ou git?
2. Vous devez faire le lien entre la structure et l'équipe... je ne le vois pas dans les outils...
3. j'ai du mal avec "ideal team" ... il faudrait clarfier cette question.
4. 
_**Team:**_

* Dorian BLANC
* Fabien VICENTE
* Manuel PAVONE
* Tom DALL'AGNOL

_**Tools: **_

* GitHub API
* TeamCodeParser \(Made by us, allows, given a Github repository \(ex: github.com/spring-io/sagan\), to extract the team by **code exploration**\)
* TeamParser \(Made by us, allows, given a webpage \(ex: spring.io/team\), to extract teams by **subject **and **location**\)

_**Project to study: **_

* [Spring](https://spring.io/)

_**Questions: **_

* Extract the code and analyze it to determine the perfect team. 
* Verify the suitability between the ideal teams and those extracted from the project documentation.

_**Introduction:**_

Melvin Conway introduced the idea in 1967 at the National Symposium on Modular Programming.** It states that :**

> _Organizations which design systems ... are constrained to produce designs which are copies of the communication structures of these organizations - M. Conway_

We try to verify the validity of this assumption by studying the structure of Spring project team and comparing the results to the code commits.

