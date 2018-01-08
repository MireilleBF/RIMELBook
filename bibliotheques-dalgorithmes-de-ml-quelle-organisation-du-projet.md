```text
                                   
```

##                                     Bibliothèques d’algorithmes de ML 

##                                        Quelle organisation du projet ?

```text


```

## Auteurs

* FUSCO  Anthony &lt;anthony.fusco42@gmail.com&gt;

* BELHASSEN Issam &lt;issambelhassen4@gmail.com&gt;

* PASTOR Florent &lt;flopastor06@gmail.com&gt;

* LEFEBRE  Jeremy &lt;efebvre.jeremyp@gmail.com&gt;

## **Introduction & contexte:**

L'apprentissage automatique est une méthode d'analyse de données qui automatise la construction de modèles analytiques. C'est une branche de l'intelligence artificielle basée sur l'idée que les machines devraient être capables d'apprendre et de s'adapter par l'expérience. C'est un domaine de l'informatique qui donne aux ordinateurs la capacité d'apprendre sans être explicitement programmé.

Le regain d'intérêt pour l'apprentissage automatique est dû aux mêmes facteurs qui ont rendu l'exploration de données et l'analyse bayésienne plus populaires que jamais. Des choses comme des volumes croissants et des variétés de données disponibles, un traitement informatique moins coûteux et plus puissant, et un stockage de données abordable. Toutes ces choses permettent de produire rapidement et automatiquement des modèles capables d'analyser des données plus grandes et plus complexes et d'obtenir des résultats plus rapides et plus précis, même à très grande échelle. Et en construisant des modèles précis, une organisation a de meilleures chances d'identifier des opportunités rentables - ou d'éviter des risques inconnus.

Les logiciels de machine learning sont en général des logiciels open source à grande échelle, ce type de logiciel permet de collecter les algorithmes d'apprentissage automatique, contient des outils pour le pré-traitement des données, la classification, la régression, le clustering, les règles d'association et la visualisation. Et qui est également bien adapté au développement de nouveaux schémas d'apprentissage machine.

La réalisation d’un logiciel open source de bibliotheque machine learning nécessite beaucoup de considérations comme la paternité de code et le travail collaboratif, qui sont des acteurs clés dans une opensource à grande échelle systèmes.

## **Question Générale et son intérêt :**

Comment les scientifiques contribuent-ils aux différents types d'algorithmes des librairies de machine learning ? Est ce que chaque famille d'algorithme possède ses collaborateurs spécifiques ?

Nous voulons comprendre comment sont maintenue les familles d’algorithmes de machine learning dans le cadre des projet Weka et Scikit-learn. Particulièrement si nous pouvons déterminer des “spécialités” chez certains contributeurs pour certains type d’algorithmes. Nous allons pouvoir a l’aide de deux projet open-sources identifier les familles d’algorithmes présentes et leurs mainteneurs respectifs.

## **Sous Question :**

Comment s’organisent les contributeurs d’un projet “OpenSource” ? Le code produit est-il impacté ?

Nous allons pouvoir appréhender ces question sous deux points de vue différents. Tout d’abord, nous allons pouvoir nous pencher sur l’organisation d’un projet regroupant plusieurs centaines de collaborateurs différents et qui pour la plupart ne se trouve pas au même endroits, géographiquement parlant, et ont donc des difficultés à communiquer. De plus, les membres participant à ce projet ne sont pas sélectionnés en amont, cela peut vraiment être n’importe qui, est ce que cela à un impact sur le code ? la couverture de test ? De ce fait nous étudierons une méthode de travail qui permet une collaboration éloignée à grande échelle sans structure hiérarchiqueà priori.

Dans un second temps, on pourrait s'intéresser au côté architecturale du projet. Par exemple, une hypothèse pourrait être qu’une structure générale est établie en premier lieu puis les contributeurs viennent apporter leur briques en respectant la structure initiale. Ou essayer de voir si les scientifiques qui sont des contributeurs réguliers sur les différentes famille d’algorithmes établissent une structure propre à leur famille.

## ** KPI/Metrics**

* Nombre de contributeurs différents

* Nombre de contributeurs différents par famille d’algorithme

* Nombre de contributeurs ayant commiter sur plusieurs famille d’algorithme

* Nombre de contributeurs différents ayant commiter sur une seule famille

* Nombre de contributeurs par groupement de classes fortement couplées

* Percentiles des contributeurs pour certaines quantité de commits

* Gros Contributeurs

* Identification de groupe de contributeurs avec des commits liés

* % de contributeur unique \(ayant 1 commit\)

* Tentative d’identification “d’administrateurs” du projet

* Nombre de classes couplées explicitement au sein d’une famille d’algorithme

* Nombre de classes couplées entre plusieurs famille d’algorithme

## **Outils utilisés :**

**StatSVN :** permet de récupérer des informations depuis un repository SVN et génère différentes charts graphiques comme par exemple :

* [Timeline](http://statsvn.org/statsvn/loc.html)for the lines of code

* Lines of code for each[developer](http://statsvn.org/statsvn/developers.html)

* Activity by[Clock time](http://statsvn.org/statsvn/developers.html#Activity_by_Clock_Time)

* [Authors Activity](http://statsvn.org/statsvn/developers.html#Author_Activity)

* Author activity per[Module](http://statsvn.org/statsvn/user_jkealey.html#Modules)

* Author[Most Recent Commits](http://statsvn.org/statsvn/user_jkealey.html#Most_Recent_Commits)with links to ViewVc

* Stats per[directory](http://statsvn.org/statsvn/dir_src_net_sf_statsvn_output.html)

* [File count](http://statsvn.org/statsvn/file_sizes.html#File_Count)

* [Average file size](http://statsvn.org/statsvn/file_sizes.html#Average_File_Size)

* [Largest files](http://statsvn.org/statsvn/file_sizes.html#Largest_Files)

* [Files with most revisions](http://statsvn.org/statsvn/file_sizes.html#Files_With_Most_Revisions)

* [Directory Sizes](http://statsvn.org/statsvn/dir_sizes.html#Directory_Sizes)

* [Repository Tags](http://statsvn.org/statsvn/index.html#Repository_Tags)Number of LOC per version.

* [Repository tree](http://statsvn.org/statsvn/index.html#Directories)with file count and lines of code

* [LOC and Churn](http://statsvn.org/statsvn/churn.html)the evolution of LOC and the amount of change per day

* [Repo Map](http://statsvn.org/statsvn/repomap.html)the dynamic hierarchical view of your repo for the last 30 days

**CodeCity **: permet de faire ressortir les dépendances entre les classes.

## ** Démarche prévue**

1. Nous allons tout d’abord nous intéresser à l’architecture du projet Weka afin d’essayer de dégager les grosses familles d’algorithmes de machine learning.

2. Nous allons ensuite essayer d’extrapoler les dépendances entre les différentes parties du code et étudier leur logique de structuration.

3. A la suite des deux parties précédentes nous allons mettre en correspondance les algorithmes et les auteurs du code pour voir comment les auteurs contribuent aux différents types d’algorithmes.

4. Nous allons ensuite essayer de faire de même avec le deuxième projet Scikit-learn pour voir si des contributeurs commun interviennent. Ceci nous permettra de voir s’ils sont chargés de l’écriture des mêmes algorithmes, ou de mêmes familles d’algorithme.

5. Nous allons ensuite pour les parties ciblées du code, essayer de mesurer leur évolution temporelle pour voir comment le code se complexifie selon les commits et est ce que de gros commits ont été effectués en même temps dans les deux librairies. Ceci nous permettra de discuter sur les différentes gestions des deux projets opensource. Le premier ayant un repository SVN dans lequel les contributeurs publient puis une personne se charge de fusionner le tout, et le deuxième ayant directement tous les contributeurs qui fusionnent le projet.

## **Références**

**General :**[**SWEBOK, Chap 5 Maintenance**](http://mireilleblayfornarino.i3s.unice.fr/lib/exe/fetch.php?media=teaching:reverse:swebokv3_-_chap5_-_code_maintenance.pdf)

**Etude :**

[**The WEKA Data Mining Software: An Update**](https://www.researchgate.net/profile/Mark_Hall6/publication/221900777_The_WEKA_data_mining_software_An_update/links/09e41507f01ad2a029000000.pdf)

[**Are developers aware of the architectural impact of their changes?**](http://www0.cs.ucl.ac.uk/staff/j.krinke/publications/ase17.pdf)

[**Secure Open Source Collaboration : An Empirical Study of Linux' Law**](http://mireilleblayfornarino.i3s.unice.fr/lib/exe/fetch.php?media=teaching:reverse:ccs221-meneely.pdf)

