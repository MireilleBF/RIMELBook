## Peut-on extraire automatiquement toutes les préconditions d'algorithmes de machine learning ?

## Auteurs

Nous sommes cinq étudiants en dernière année de Master 2 à Polytech Nice-Sophia Antipolis, spécialisés en Architecture Logicielle.

* Maxime Dejeux &lt;maxime.dejeux@gmail.com&gt;

* Guillaume Faguet &lt;faguet.guillaume@gmail.com&gt;

* Mohamed Chennouf &lt;mohamed.chennouf@etu.unice.fr&gt;

* Matthieu Génovèse &lt;matthieu.genovese@gmail.com&gt;

* Michael Liechtensteger &lt;michael.liechtensteger@gmail.com&gt;

## Introduction

Ce document présente les résultats de nos recherches sur l’extraction de préconditions des algorithmes de machine learning. Pour cela, nous présentons d’abord le contexte dans lequel s’est déroulé notre recherche. Par la suite, nous rentrerons en détail sur les résultats observés et les analyses effectuées.

## I. Contexte de recherche

Weka est une librairie proposant un ensemble d’algorithmes de machine learning permettant d’effectuer des opérations de data mining. Ces algorithmes peuvent être soit directement appliqués à un jeu de données, ou bien utilisés directement dans un code Java. Weka propose des outils pour gérer les préconditions sur des données. L'intérêt de ces préconditions est de pouvoir vérifier que des jeux de données possèdent bien certaines propriétés, ou sont d’un format spécifique, pour pouvoir être utilisés par les algorithmes de la librairie Weka. Cependant, la connaissance des préconditions nécessite actuellement un travail de la part de l’utilisateur, car les préconditions ne sont pas explicitement montrés à l’utilisateur. Cela peut rendre l’utilisation des algorithmes difficile, car même si la documentation indique certaines préconditions nécessaires, toutes ne sont pas indiquées, et peuvent mener à des erreurs involontaires de l’utilisateur. Il pourrait être utile pour l’utilisateur d’avoir plus de détails sur les données utilisables, pour faciliter l’utilisation des algorithmes.

Ce sujet nous a semblé intéressant pour plusieurs raisons :

* Le machine learning est un sujet actuel

* Automatiser la récupération de préconditions peut faciliter l’utilisation d’algorithmes de machine learning de la librairie Weka par des utilisateurs

## II. Observations et question générale

Pour appréhender notre sujet, nous avons imaginé un scénario en nous mettant dans la peau d’un utilisateur d’une librairie de Machine Learning.

**Scénario**

Je suis un développeur dans une entreprise, pour réaliser à bien mon projet je dois utiliser une librairie de machine learning, je me suis renseigné sur les différentes librairies et j’ai choisi d’utiliser Weka qui est une librairie de ML en Java. Je dispose donc d’un certain jeu de données et je me heurte à un problème : weka dispose de très nombreux algorithmes cependant tous ces algorithmes ne peuvent pas résoudre mon problème car leurs actions et leurs résultats dépendent du jeu de données en entrée et de certaines préconditions. Je me demande alors s’il n’existe pas un moyen d’extraire automatiquement toutes les préconditions d’un algorithme de Weka.

Cette question nous semble très importante car si un outil permettant d’extraire ces préconditions existe, il fera gagner un temps non négligeable à tous les utilisateurs “novices” de Weka. Cette question peut également être étendue à d’autres librairies \(de machine learning ou même d’autres librairies proposant des algorithmes\) cependant dans notre projet nous allons y répondre dans le cadre de Weka.

## III. Rassemblement d'informations

Pour répondre à ce sujet, nous nous sommes appuyés principalement sur la documentation de Weka. La lecture de cette documentation a principalement pour but d’en apprendre plus sur le fonctionnement de la librairie Weka, et de trouver d’éventuelles informations sur les préconditions.

Nos recherches dans la documentation nous ont menés à des objets appelés les Capabilities.

Nous avons également cherché dans le code source de la librairie Weka si nous pouvions trouver des préconditions.

## IV. Hypothèses et expériences {#docs-internal-guid-be454e9c-d956-6fb9-9ddd-21f79a30421d}

Nous avons pu observer que certaines préconditions sont liées à des objets appelés

Capabilities dans le code de Weka. Les Capabilities permettent de spécifier le type que doit avoir une donnée avant d’être utilisée par un algorithme de machine learning de la librairie Weka.



**IV.1 Nous pouvons extraire des préconditions de la classe “Capabilities”**

Suite à nos recherches, nous avons fait l’hypothèse que nous pouvons extraire certaines préconditions d’un algorithme de Weka grâce à la classe “Capabilities” vu précédemment.

Pour réaliser à bien cette tâche, nous avons décidé de développer nous même un outil nous permettant de “tester” les algorithmes de Weka avec différents types de données en entrée en se basant sur le contenu de la classe Capabilities de chacun des algorithmes testés. Il a fallu également tester le fait que violer ces capability entraînait bien une erreur de la part des l’algorithmes.  


**IV.2 Il existe des préconditions non définies dans les Capabilities**

Si Weka propose le système des capabilities regroupant des préconditions, nous ne pouvons pas affirmer que toutes les préconditions sur les données sont explicitement définies dans ces capabilities. Il est possible qu’il existe des préconditions implicitement définies dans le code source, gérées par exemple par des exceptions. Pour vérifier cela, nous avons cherché dans le code source \(notamment le dossier Classifier\) les exceptions définies, et notamment si certaines n’étaient pas dues à des conditions sur les données en entrée, autres que les capabilities.



**IV.3 Nous pouvons extraire certaines préconditions des Exceptions propagées dans le code Weka**

En analysant le code des algorithmes de Weka, nous avons remarqué qu’un certain type d’Exception avait était créer \(les WekaException\) Nous pensons que certains appels de ces exceptions peuvent correspondrent à certaines préconditions qui ne seraient pas présentes dans les Capabilities.



**IV.4 Nous pouvons extraire toutes les préconditions dans le code Weka**

Il est possible que les capabilities représentent la totalité des préconditions, ou bien il existe potentiellement un moyen de récupérer toutes les préconditions dans le code.

## V. Analyse des résultats et conclusion



**V.1 les préconditions dans les Capabilities**

Nous avons pu développer le programme dont nous avons parlé précédemment, il arrive à extraire toutes les préconditions inscrites dans les Capabilities de chacun des algorithmes, voici un extrait du fichier de sortie que nous obtenons :

![](https://lh6.googleusercontent.com/7NyzSmD0isLuKkMHvLtSE1PuJRo6v2_78zLzR0MzALBSlrUl9p1S_zoV66wjls3tiKO7yvXw4w1H4ZIt71S5xd4xZ53IFoOGX6e1qbfyMrgGNF46Bk3ZP2Ja17E9vR3cbfSu1Krn)



Nous constatons que le contenu de la classe Capabilities renseigne bien sur certaines préconditions des algorithmes. Afin de vérifier ce résultat, nous avons par la suite testé les algorithmes avec des données en entrée correspondant à la classe Capabilities de chacun d’eux.

Pour tester les préconditions définies par les capabilities, nous avons créé différents jeux de données représentants les différents types de données possibles, et avons testés les algorithmes de Weka avec ces données.

Les préconditions définies dans les capabilités sont les suivantes :

* Nominal class

* Missing class values

* Binary class

* Date class

* Numeric class

* Unary class

* String class

* Relational class

* Empty nominal class

Une fois la création de jeux de tests représentants ces types de données, nous avons exécuté des algorithmes possédant des préconditions que les jeux de données respectent.

Nous avons observé que tous les algorithmes s'exécutent bien avec les bons jeux de données. Cela rejoint notre hypothèse numéro 1.

Cependant, même si les capabilities de Weka indiquent des préconditions, nous ne pouvons pas être certain que toutes les préconditions sont incluses dans ces capabilities.

Pour pouvoir vérifier notre hypothèse numéro 2, il nous faut pouvoir tester les préconditions d’une autre façon, car il est possible qu’il existe des préconditions autres que les capabilities.

Pour cela, nous avons développé un programme en Java permettant d’analyser le code source et d’y ressortir des exceptions et de ressortir des statistiques dessus.. Dans le cadre du projet, nous nous sommes concentrés sur les classes contenues dans le dossier Classifier de la librairie Weka.  


**V.2 les préconditions non définies dans les Capabilities**

Pour les préconditions non définies par les Capabilities , nous avons récupérer les exceptions des algorithmes de Weka afin de pouvoir les catalogué à un type de précondition. Nous avons donc créé un algorithme capable de parcourir les répertoires de Weka et en extraire les exceptions. Ce programme stocke dans un fichier JSON tous les fichiers qu’il parcourt avec le nombre exception par fichier et le contenu de ces exceptions :

![](https://lh4.googleusercontent.com/_VFApIhGvLVJrbLsog2ebm70-mn7aIrKZzoCg0RweQym2dXVZBG-THSkj45hTdRMVjwQBHahPnXuhQHW3ADrNHqk2xL6sMYx_7oKGop63-LTd431-EmlfXagsjM6d9WHUOdpqXZK)

**Json File : Données extraite dans le répertoire classifiers**



Ces exceptions sont ensuite exploitées par un logiciel Javascript avec un serveur NodeJs qui lit ce fichier Json , catégorise ces exceptions et les affichent sous forme de graphique.

Par exemple l’ erreur : 

ArithmeticException est catégorisé en une précondition de type Arithmetic. C’est une exception qui intervient lors d’une opération arithmetic impossible \(un entier divisé par zéro…\).

Le résultat de cette catégorisation est la suivant :



![](https://lh6.googleusercontent.com/M1uotmRfeagrnzm0vMa6oGJsxLL_Fs6JRovwHLAHuGl7p2ehxzhOdyjAVgxFlqIrea53P9FZMgkrhiw8VtxejMB4JqTYB9cpL_7GUrBrkAwBV7WnfV2EYxQtZIUyyeEoW7jxXKcu)

## **Résultat des préconditions dans le répertoire classifiers**

Dans classifiers , nous avons 238 exceptions, dont 11 viennent des class Weka et 227 dont des erreurs Java. Parmi ces erreurs nous avons pu catégorisé certaine d’entre elles :

-Préconditions Arithmetic : 5 erreurs : soit 2.2% des erreurs

-Préconditions sur le Format : 18 erreurs : soit 7.9% des erreurs

-Argument illegal : 15 erreurs : soit 6.6% des erreurs

-préconditions sur la taille des données : 20 erreurs : soit 8.8% des erreurs

En ce qui concerne le reste des erreurs , nous n’avons pas réussi à les catégorisés. Nous avons donc réussi à catégoriser environ 25% des erreurs lié au exception grâce à notre logiciel. Les 75 % restant sont des exceptions inexploitable car ce sont des exceptions beaucoup trop génériques pour pouvoir les catégoriser.

**V.3 Conclusion**

Nous pouvons en conclure que notre hypothèse numéro 2 est valide, car nous sommes parvenus à trouver des préconditions non définies dans les capabilities.

L’hypothèse numéro 3 est également validée car pour répondre à l’hypothèse numéro 2, nous avons dû extraire des préconditions directement dans le code Weka.

Pour conclure, nous sommes parvenus à valider nos hypothèses concernant l’extraction des préconditions. Cependant, nous ne sommes pas en mesure de valider l’hypothèse numéro 4, qui est : Est-il possible d’extraire toutes les préconditions des algorithmes.

## VI. Références

[https://www.cs.waikato.ac.nz/ml/weka/documentation.html](https://www.cs.waikato.ac.nz/ml/weka/documentation.html)

[http://weka.sourceforge.net/doc.dev/weka/core/Capabilities.html](http://weka.sourceforge.net/doc.dev/weka/core/Capabilities.html)

