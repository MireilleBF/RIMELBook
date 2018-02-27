# Comment les utilisateurs de Docker Compose s'adaptent-ils aux changements de version selon les spécifications de leurs projet

## Auteurs

Nous somme cinq étudiants en cinquième année de science informatique à l'école Polytech Nice-Sophia Antipolis, et nous nous spécialisons en Architecture Logicielle.

* Maxime Carlier &lt;maxime.carlier@etu.unice.fr&gt;
* Rami Ajroud &lt;rami.ajroud@etu.unice.fr&gt;
* Danial Aswad &lt;danial-aswad.bin-ahmad-fazlan@etu.unice.fr&gt;
* Ahmed Fezai &lt;ahmed.fezai@etu.unice.fr&gt;
* Thomas Suignard &lt;thomas.suignard@etu.unice.fr&gt;

## Introduction

Dans le cadre de la matière Rétro-Ingénierie, Maintenance et Évolution des Logiciels \(RIMÉL\), ce chapitre présente le travail que nous avons réalisé durant ce semestre. Ce document montre explicitement le contexte de notre travail et le problématique évoqué suivie par nos hypothèses, la démarche effectuée et les résultats. À la fin de ce document nous établissons une relation entre les résultats obtenus avec nos hypothèses.

## I. Contexte de recherche

“Docker est un logiciel libre qui automatise le déploiement d’applications des conteneurs logiciel”  
-- Wikipédia

C’est ainsi que l’encyclopédie libre à choisie de présenter ce logiciel ayant connus un boom phénoménal dans les 5 dernière années.

Ainsi, Docker est un logiciel qui permet de déployer une stack logicielle indépendamment de la plateforme, mais qui offre en plus, d’autres outils permettant d’étendre au delà les capacités de base de la plateforme. Docker-Compose permet ainsi de déployer de manière groupé un ensemble de container pour contrôler de manière centralisé, le déploiement de plusieurs stack logicielle fonctionnant ensemble ou encore Docker Swarm qui vise à répondre au problématique de d'orchestration de plusieurs machines.

A l’heure actuelle, Docker est utilisé dans environs 10.000 projets Github, à levé environs 250 Millions de Dollar de fond et effectué déjà 8 acquisition \([https://www.crunchbase.com/organization/docker\](https://www.crunchbase.com/organization/docker\)\). Son succès, plus qu’académique pour les problématiques qu’il cherche à résoudre à su atteindre le monde industriel et attirer le regard de nombreux investisseurs. L’avenir semble donc radieux pour la boîte Californienne, et pourtant, une récente affaire vient ternire le blason de la baleine bleue.

Passé le domaine des conteneur dans lequel Docker à su s’imposer comme Leader incontesté, c’est au niveau de l'orchestration multi machine que la guerre fait rage. Pendant les deux années précédentes, ce sont Docker Swarm, Kubernetes et Mesos qui se sont livré bataille pour assouvir leurs règne. Et bien que Kubernetes soit clairement plus appréciés des utilisateurs \(33k star et 11.626 fork sur github contre 5k star et 1.023 fork pour Swarm\) c’est toujours Docker qui a la main sur le produit sous jacent.

Pourtant Docker à récemment décidé de faire marche arrière face à la pression d’utilisateurs soucieux d’un éventuel “Vendor Lock” qui se profilait à l’horizon, et choisis d’intégrer Kubernetes à son logiciel de Conteneurisation.

Ce revers qui peut paraître anodin, et même bienvenu de la part de l’entreprise Américaine, laisse pourtant entrevoir un certain point d’ancrage pour une argumentation en défaveur de la politique de développement que l’entreprise a choisis pour un tout autre logiciel de sa suite.

En effet les foudres n’ont pas finit de s’abattre sur Docker Compose et ses fameuse mises à jours destructrice. L’entreprise ayant fait le pari osé de ne pas garantir de rétro compatibilité entre versions, les utilisateurs ne sont pas à l’abris de voir tout bonnement disparaître l’un des opérateur qu’ils utilisent dans leurscompose fileentraînant ainsi un version lock de leurs système de déploiement a moins d’investir un temps-homme suffisant pour remédier à cela, lorsque cela est possible.

Mais au vu du revers de la politique de Docker sur Kubernetes, qu’adviendrait-il de sa politique de mise à jours pour Compose, s’il s'avérait que les utilisateurs ne tirait pas, ou peu de de bénéfice de cette approche ? Ou bien s’il ne mettait tout simplement pas à jour leurs Compose File ? Ou encore même, si l’implémentation des nouvelles version ne se limitait qu'à un groupe restreint d’utilisateurs, peu représentatif de la balance économique \(étudiants/académiques plutôt que industriels déboursant de l’argent\) ?

Ce sont ce type de questions auxquelles nous allons tenter d’apporter une réponse.

![](/assets/docker_compose_study_project_files/docker-compose-version-release.png)

_TODO_

## II. Observations et question générale

Pour faire suite aux problématiques soulevées dans notre contexte, nous commencerons par formuler une question de haut niveau, autour de laquelle nous construirons notre étude.

**Question générale : Comments les utilisateurs s'adaptent-ils aux mise à jour de Docker Compose en fonction des caractéristiques de leurs projets ?**

L’objectifs ainsi fixé, il s’agira donc pour nous, dans la suite de ce document de chercher si oui ou non il existe des critères propres à un projet, qui permettraient d’établir un lien de causalité entre leurs présence \(ou leur absence\) valué, et le dynamisme de changement de version desCompose File.

L'intérêt étant ici, que si il existe bel est bien un lien entre un tel critère, et cette action de mettre à jour son Docker Compose, nous serions en mesure de qualifier le groupe d’utilisateurs qui bénéficie le plus \(ou pas du tout\) de la politique de mise à jour adopté par Docker.

Ce résultat intermédiaire nous permettrait ainsi de conclure si le pari fait par Docker pour son outil Compose va à l’encontre ou non de l’usage qu’en font les utilisateurs.

_TODO_

## III. Rassemblement d'informations

_TODO_

## IV. Hypothèses et expériences

_TODO_

## V. Analyse des résultats et conclusion

_TODO_

## VI. Références

_TODO_

