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

Scénario

Je suis un développeur dans une entreprise, pour réaliser à bien mon projet je dois utiliser une librairie de machine learning, je me suis renseigné sur les différentes librairies et j’ai choisi d’utiliser Weka qui est une librairie de ML en Java. Je dispose donc d’un certain jeu de données et je me heurte à un problème : weka dispose de très nombreux algorithmes cependant tous ces algorithmes ne peuvent pas résoudre mon problème car leurs actions et leurs résultats dépendent du jeu de données en entrée et de certaines préconditions. Je me demande alors s’il n’existe pas un moyen d’extraire automatiquement toutes les préconditions d’un algorithme de Weka.

Cette question nous semble très importante car si un outil permettant d’extraire ces préconditions existe, il fera gagner un temps non négligeable à tous les utilisateurs “novices” de Weka. Cette question peut également être étendue à d’autres librairies \(de machine learning ou même d’autres librairies proposant des algorithmes\) cependant dans notre projet nous allons y répondre dans le cadre de Weka.  


## III. Rassemblement d'informations

Pour répondre à ce sujet, la documentation de Weka a été indispensable pour avoir des informations sur les préconditions. Nous avons également cherché dans le code source de la librairie Weka si nous pouvions trouver des préconditions.

## IV. Hypothèses et expériences

Nous avons pu observer que certaines préconditions sont liées à des objets appelés

Capabilities dans le code de Weka. Les Capabilities permettent de spécifier le type que doit avoir une donnée avant d’être utilisée par un algorithme de machine learning de la librairie Weka.

* IV.1 Nous pouvons extraire des préconditions de la classe “Capabilities”

  Suite à nos recherches, nous avons fait l’hypothèse que nous pouvons extraire certaines préconditions d’un algorithme de Weka grâce à la classe “Capabilities” vu précédemment.

  Pour réaliser à bien cette tâche, nous avons décidé de développer nous même un outil nous permettant de “tester” les algorithmes de Weka avec différents types de données en entrée en se basant sur le contenu de la classe Capabilities de chacun des algorithmes testés.

* IV.2 Il existe des préconditions non définies dans les Capabilities

  Si Weka propose le système des capabilities regroupant des préconditions, nous ne pouvons pas affirmer que toutes les préconditions sur les données sont explicitement définies dans ces capabilities. Il est possible qu’il existe des préconditions implicitement définies dans le code source, gérées par exemple par des exceptions. Pour vérifier cela, nous avons cherché dans le code source \(notamment le dossier Classifier\) les exceptions définies, et notamment si certaines n’étaient pas dûes à des conditions sur les données en entrée, autres que les capabilities.

* IV.3 Nous pouvons extraire certaines préconditions des Exceptions propagées dans le code Weka

  En analysant le code des algorithmes de Weka, nous avons remarqué qu’un certain type d’Exception avait était créer \(les WekaException\) Nous pensons que certains appels de ces exceptions peuvent correspondrent à certaines préconditions qui ne seraient pas présentes dans les Capabilities.  

## V. Analyse des résultats et conclusion

Nous avons pu développer le programme dont nous avons parlé précédemment, il arrive a extraire toutes les préconditions inscrites dans les Capabilities de chacun des algorithmes, voici un extrait du fichier de sortie que nous obtenons :

![](https://lh6.googleusercontent.com/7NyzSmD0isLuKkMHvLtSE1PuJRo6v2_78zLzR0MzALBSlrUl9p1S_zoV66wjls3tiKO7yvXw4w1H4ZIt71S5xd4xZ53IFoOGX6e1qbfyMrgGNF46Bk3ZP2Ja17E9vR3cbfSu1Krn)

Nous constatons bien que le contenu de la classe Capabilities renseigne bien sur certaines préconditions des algorithmes. Afin de vérifier ce résultat, nous avons par la suite testé les algorithmes avec des données en entrée correspondant à la classe Capabilities de chacun d’eux.

## VI. Références

À remplir.



