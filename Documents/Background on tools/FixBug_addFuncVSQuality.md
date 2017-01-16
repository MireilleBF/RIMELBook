# What is the relation between adding functionality, bug fixing, and code quality

## **@mbf : Gros soucis, je ne sais pas évaluer cela.**

## **Process:**

**récupère les morceau de code dégueu**

**on regarde quel morceau correspond a quel commit**

**on lie les commits au taches jira**

**on peut ainsi noter chaque tâche jira**

**on trie les tache jira par type**

# **Question :**

**Existe-t-il une corrélation entre l'évolution de la qualité d’un code et certain type de modification ?**

**Comment évaluer un code \(quels metrics\) ?**

* **sonar**

* **code maat**

* **autre …**

**Comment extraire les zones blâmés ?**

**Comment lier ces morceaux de code blâmés à des types de modifications \(ticket jira\) ?**

* **Github**

* **Jira**

* **Script perso**

* **diggit ?**

**Beaucoup des commit ont soit des numéros de ticket jira ou de pull request dans leur commentaire. le bug et donc de retrouver à quel type de modification appartient un commit en le lien à son ticket, ce qui permet une fois une analyse de code effectuer de faire des métriques sur la qualité du code par rapport au différent type de modification. dans le cas ou un commit contient le numéro d’un ticket, la marche à suivre et plutôt simple, il suffit de prendre la simple des tickets et de faire un “grep” dans la liste des commits, ceci lira les ticket à leur commit. Dans le cas ou un commit à une référence sur une pull request le procédé est un peu plus compliqué. Nous devons d’abord les ticket à des pull request. heureusement, pour le projet choisis, Scala, les pull request sont quasiment toute reporté dans le Jira avec un taghas-pull-requestet le numéro de la pull request et mise en commentaire. nous pouvons donc grâce à ça simplement lier les commits à des pull request, que l’on peut elles-mêmes liées à des tickets Jira. Tout ceci devra être effectué avec un outil qui sera développé spécialement pour l’occasion**

## **Les metrics pour l’évaluation du code**

**Afin de pouvoir évaluer un code nous allons l’analyser pour connaître la qualité et l’évolution dans le temps du code . Pour cela nous allons utiliser deux différents outils , À savoir : SONAR et CODE MAAT.**

**    Sonar est un outil open source qui se charge du développement et du support de Sonar. Le but principal de cet outil est de fournir une analyse complète de la qualité d'une application en fournissant de nombreuses statistiques \(oumétriques\) sur ses projets. Ces données permettent ainsi d'évaluer la qualité du code, et d'en connaître l'évolution au cours du développement.**

**L’outil sonar nous permettra de :**

* **détecter un code à risque**

* **une mesure quantitative du nombre de classe et du code dupliqué**

* **pour les projets où il existe des tests unitaires , sonar nous permet d’avoir une mesure qualitative de la couverture et le taux de réussite des tests**

* **une historique pour en voir l’évolution au cours du temps**

**      
**

**Pour l’instant nous avons pas encore des résultats à présenter , ils sont en cours d’évaluation et d’analyse .**

**      
**

