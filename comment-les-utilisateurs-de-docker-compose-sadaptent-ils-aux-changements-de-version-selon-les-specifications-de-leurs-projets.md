# Comment les utilisateurs de Docker Compose s'adaptent-ils aux changements de version selon les spécifications de leurs projet

## Auteurs

Nous somme cinq étudiants en cinquième année de science informatique à l'école Polytech Nice-Sophia Antipolis, et nous nous spécialisons en Architecture Logicielle.

* Maxime Carlier &lt;maxime.carlier@etu.unice.fr&gt;
* Rami Ajroud &lt;rami.ajroud@etu.unice.fr&gt;
* Danial Aswad &lt;danial-aswad.bin-ahmad-fazlan@etu.unice.fr&gt;
* Ahmed Fezai &lt;ahmed.fezai@etu.unice.fr&gt;
* Thomas Suignard &lt;thomas.suignard@etu.unice.fr&gt;

## Introduction
Dans le cadre de la matière Rétro-Ingénierie, Maintenance et Évolution des Logiciels (RIMÉL), ce chapitre présente le travail que nous avons réalisé durant ce semestre. Ce document montre explicitement le contexte de notre travail et le problématique évoqué suivie par nos hypothèses, la démarche effectuée et les résultats. À la fin de ce document nous établissons une relation entre les résultats obtenus avec nos hypothèses.

## I. Contexte de recherche

Docker Compose est un outil permettant de définir les comportements des conteneurs (écrit dans le fichier docker-compose.yml) et de lancer plusieurs conteneurs d'application docker avec une seule commande. Comme Docker ne garantit aucune manière de la rétro compatibilité d’une version à une autre, à la manière de Python entre sa version 2.X et 3.X, le résultat est donc le fichier docker-compose.yml écrit sous la syntaxe de la version 2 ne peuvent être utilisés sous la version 3 sans apporter certaines modification. 

_TODO_

## II. Observations et question générale

Nous souhaitons donc étudier la manière dont les utilisateurs de cet outil réagit face à la mise à jour du Docker. Afin d’élargir les perspectives de nos études, nous avons choisi de chercher à voir s’il était possible de définir certains comportements lors de ces mise à jours en fonction de certains critère. En nous appuyant sur un sample de dépôt sur GitHub, et en les classifiants selon leurs caractéristiques disponibles telles que : le nombre de collaborateurs, le nombre de lignes de codes, le langage source, les technologie utilisés.

_TODO_

## III. Rassemblement d'informations

_TODO_

## IV. Hypothèses et expériences

_TODO_

## V. Analyse des résultats et conclusion

_TODO_

## VI. Références

_TODO_

