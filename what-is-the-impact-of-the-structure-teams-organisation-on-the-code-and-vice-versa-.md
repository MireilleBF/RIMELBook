# **What is the impact of the structure \(teams organisation\) on the code and vice versa ?**

## **auteurs**

> **Remarques** : @mbf à enlever après prise en compte

* **Titre du chapitre** :
  * OK... on verra plus tard pour etre un peu plus percutant
* **Question générale** :
  * OK
* **Pourquoi \(fera office d'introduction\) :**
  * manque au niveau général
* **Outils, Méthodes \(en partie dans l'introduction\) : **
  \* 
* **Codes \(au choix à présenter dans une partie méthodologie ou dans les sous parties**
  * explicitez en global le choix de Spring.
* **Pistes \(devra servir de base à un plan de chapitre, et il faut expliquer pourquoi\)**
  * J'ai du mal à comprendre l'articulation entre les 2 sous parties. Essayez de l'écrire en fin de votre introduction cela aidera.
* **Articles : serviront de référence et pourront etre discutés**
* **En vrac**
  1. TeamCodeParser est lié à github ou git?
  2. Vous devez faire le lien entre la structure et l'équipe... je ne le vois pas dans les outils...
  3. j'ai du mal avec "ideal team" ... il faudrait clarfier cette question.

---

_**Team:**_

* Dorian BLANC
* Fabien VICENTE
* Manuel PAVONE
* Tom DALL'AGNOL

_**Tools: **_

* GitHub API
* TeamCodeParser \(Made by us, allows, given a Github repository \(ex: github.com/spring-io/sagan\), to extract the team by **code exploration**\)
* TeamParser \(Made by us, allows, given a webpage \(ex: spring.io/team\), to extract teams by **subject **and **location**\)
  > @mbf :n'importe quelle page web ? Vraiment vous ne pensez pas à utiliser des outils extérieurs? Votre contribution serait alors aussi les outils que vous mettez en place, mais dans ce cas, j'aimerais bien que pour "TeamCodeParser" vous vérifiiez que Maat ne fait pas ce que vous faîtes et pour l'autre qu'il n'existe pas déjà des formats pour définir des équipes...

_**Project to study: **_

* [Spring](https://spring.io/)
  > @mbf : donnez des arguments par écrit pour ce choix

_**Questions: **_

* Extract the code and analyze it to determine the perfect team. 
  > @mbf :perfect, je ne comprends pas..
* Verify the suitability between the ideal teams and those extracted from the project documentation.
  > @mbf : pareil... je ne comprends pas.

_**Introduction:**_

Melvin Conway introduced the idea in 1967 at the National Symposium on Modular Programming.** It states that :**

> _Organizations which design systems ... are constrained to produce designs which are copies of the communication structures of these organizations - M. Conway_

We try to verify the validity of this assumption by studying the structure of Spring project team and comparing the results to the code commits.

## Introduction

 

In 1967, Melvin Conway introduced at the National Symposium on Modular Programming the idea that “Organizations which design systems \[...\] are constrained to produce designs which are copies of the communication structures of these organizations”. A rule that was true at this time, but with the propagation of open source philosophy, we want to know if it’s respected.

Open-source projects are a quite recent evolution in informatic with the propagation of free repository hosting like github \(launched the 10th April of 2008\). In big open-source projects, there is a mix of external contributors and a core internal team both contributing, that doesn’t know each other, something far from what could have imagined Conway at his era when there was only static teams.

We want to know if the current teams of open sources projects have the same organization than the one we could extract from the code. Looking at the code and the commits of a Version Control System \(VCS\), we could extract a design that, according to Conway, should be a copy of the real team.

If we find that the team created using the organizations informations and the team created using the code source is the same, we could conclude that Conway’s Law is valid.

We chose Spring because it’s a set of Open Source projects on which we have informations on the current teams. We can also link from their website the team members to their github account to have more informations. That’s why these projects are perfect for our study.

