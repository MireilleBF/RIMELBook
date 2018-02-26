# Comment est organisé le développement d'un projet Open Source de Machine Learning ?

_Février 2018_

## Auteurs

Nous sommes quatre étudiants en dernier année à Polytech Nice-Sophia Antipolis, spécialisés en Architecture Logicielle.

* Robin Alonzo &lt;alonzo.robin@etu.unice.fr&gt;
* Antoine Aubé &lt;aube.antoine@etu.unice.fr&gt;
* Thierno Balde &lt;balde.thierno@etu.unice.fr&gt;
* Mathieu Mérino &lt;merino.mathieu@etu.unice.fr&gt;

## Introduction

Ce chapitre présente le travail de recherche produit par notre groupe dans le cadre de la matière Rétro-Ingénierie, Maintenance et Évolution des Logiciels \(RIMÉL\). Nous présenterons successivement notre contexte de recherche, la question que nous avons posé accompagnée de nos hypothèses, puis la démarche à laquelle nous avons procédé ; nous poursuivrons par une analyse des résultats obtenus en faisant le lien avec nos hypothèses, puis concluerons.

## I. Contexte : Apprentissage Automatique, une communauté grandissante

L'**apprentissage automatique** \(Machine Learning, ML\) est une science sous-jacente à l'intelligence artificielle qui définit des méthodes pour prédire des caractéristiques à partir d'un ensemble de données.

Cette discipline ne cesse d'intéresser de nouveaux adeptes, autant les entreprises qui souhaitent exploiter les très grands volumes de données qu'elles génèrent, que les chercheurs qui ne cessent de publier de nouveaux travaux à ce sujet.![](/assets/organisation_project_os_ml/machine_learning_trends.png)

_Figure 1 - Intérêt croissant pour le Machine Learning lors des cinq dernières années_

_Source des données : _[_Google Trends_](https://trends.google.fr/trends/explore?date=today 5-y&q=machine learning,deep learning,artificial intelligence)

Une brève investigation révèle qu'une communauté s'est créée autour de l'apprentissage automatique, autant pour diffuser le savoir \(des sites comme _DataCamp_\), pour collaborer autour d'ensemble de données publics \(_Kaggle_\) ou pour construire des logiciels et bibliothèques qui tiennent compte de l'avancée dans le domaine \(de nombreux projets open source sur _GitHub_ comme _scikit-learn_, ...\).

## II. Questionnement

### II.1. Observations et question générale

L'apprentissage automatique est un domaine de pointe, que nous imaginons encore très proche de la recherche. Nous nous étonnons que, pourtant, les outils récurrents du Machine Learning \(nous entendons souvent parler de _Tensorflow_ et ses surcouches, _numpy_, ...\) soient des logiciels Open Source.

Dans ces conditions, nous nous demandons comment est organisé le développement d'un projet open source de Machine Learning. À l'échelle d'un projet, de la réponse à cette question dépend la confiance que nous pouvons mettre en la qualité de leurs algorithmes et donc, d'une certaine manière, diriger notre choix quand nous en aurons besoin. Au niveau global, nous souhaitons déterminer s'ils existe des schémas récurrents dans l'ensemble de ces projets.

### II.2. Sous-questions

Notre intuition suggère plusieurs pistes que nous souhaitons explorer et auxquels nous nous restreindrons dans cette étude. Leur formulation ci-suit concerne bien les projets Open Source de Machine Learning :

1. **Ces projets sont-ils menés par des chercheurs ?**
2. **Qui écrit les algorithmes d'apprentissage automatiques dans ces projets ?**
3. **La qualité logicielle est-elle une préoccupation de ces projets ?**

### II.3. Objet de l'étude

Comme nous souhaitons observer des propriétés vraies pour les projets Open Source de Machine Learning en général, l'étude portera sur un ensemble de projets.

Nos critères de sélection sont arbitraires, ils nous permettent de ne pas nous disperser dans les outils d'analyse que nous produisons. Les critères sont les suivants :

* Ces projets sont des bibliothèques d'algorithmes d'apprentissage automatique.
* Ces projets sont écrits en majorité en Python. Python est en effet l'un des langages de prédilection dans ce domaine.
* Ces projets sont hébergés sur GitHub.

## III. Rassemblement d'informations

### III.1. Outils utilisés

Pour rassembler les informations utilisés dans cette étude, nous avons utilisé les outils suivants :

* [RepoDriller](https://github.com/mauricioaniche/repodriller) pour analyser les contributions successives des projets.
* [SonarQube](https://www.sonarqube.org/) pour analyser la qualité des projets.

Nous avons également produit une série de scripts Bash, Javascript et Python pour des tâches plus spécifiques et pour automatiser la récolte des informations, afin d'améliorer la reproductibilité de l'étude et de repérer les possibles erreurs dans le protocole que nous suivons.

Nous utilisons également des bibliothèques comme [scholarly](https://github.com/percolator/scholarly), qui nous permettent d'écrire des outils plus simples pour récolter nos données.

Les figures présentes dans le document ont été produites par nos soins, la plupart avec la bibliothèque [Pygal](http://pygal.org/en/stable/).

### III.2. Projets retenus

Nous avons retenu trente-quatre projets qui respectent nos critères.

Les projets que nous avons sélectionné ont été trouvés sur la liste [Awesome Machine Learning](https://github.com/josephmisiti/awesome-machine-learning).

Ils sont au nombre de trente-quatre : _scikit-learn_, _theano_, _keras_, _scikit-image_, _simplecv_, _nltk_, _pattern_, _auto-ml_, _pylearn_, _pybrain_, _brainstorm_, _pyevolve_, _pytorch_, _cogitare_, _featureforge_, _metric-learn_, _simpleai_, _astroML_, _lasagne_, _hebel_, _chainer_, _prophet_, _gensim_, _surprise_, _crab_, _nilearn_, _pyhsmm_, _skll_, _spearmint_, _deap_, _mlxtend_, _tpot_, _pgmpy_ et _milk_.

Ces projets sont différents entre eux notamment au niveau des domaines auxquels ils sont dédiés \(certains sont généralistes, d'autres spécifiques à certains domaines\) ainsi que de leur maturité \(en terme de nombre de contributions, nombre de contributeurs\).

![](/assets/organisation_project_os_ml/contributions_per_project.png)

_Figure 2 - Grandes disparités de la maturité des projets étudiés_

Nous observerons néanmoins que ces projets très actifs pour la plupart. La _Figure 3_ présente la fonction de répartition cumulative \(Cumulative Distribution Function - CDF\) des contributions apportés aux projets en 2017 et montre que, nonobstant de rares projets qui n'évoluent plus ou très peu, les projets évoluent en continu dans l'année.

![](/assets/organisation_project_os_ml/contributions_cdf.png)

_Figure 3 - Évolution perpetuelle de la plupart des projets_

Nous pensons que cette diversité apparente entre les projets nous permettra d'obtenir des résultats moins biaisés, et donc nous faisons l'hypothèse que les résultats obtenus sur cet échantillon de projets Open Source de Machine Learning seront généralisables à tous les projets similaires. Le fait qu'ils soient en changement perpétuel donne son intérêt à l'étude qui s'intéresse à l'évolution des projets.

## IV. Hypothèses et expériences

Nous avons décomposé notre question générale en sous-questions qui fixent les limites que nous souhaitons étudier. Dans cette partie, nous détaillons pour chaque sous-questions nos hypothèses et la méthode que nous allons employer pour les vérifier ou les invalider.

Nos hypothèses de travail communes à l'ensemble de l'étude est que les contributeurs sont de bonne foi :

* Ils sont auteur du code qu'ils ont mis en ligne.
* Le nom, prénom et l'adresse mail spécifiés dans les contributions leur appartiennent.

### IV.1. Ces projets sont-ils menés par des chercheurs ?

Nous avons l'intuition que les projets de Machine Learning sont le fruit du travail des chercheurs, soit parce qu'ils sont des réalisations produites à l'aboutissement de leurs travaux, soit parce qu'ils sont les mieux à même de contribuer sur ces projets.

Nous souhaitons évaluer trois hypothèses :

1. **Les contributeurs sont majoritairement des chercheurs.**
2. **Les contributions viennent majoritairement de chercheurs.**
3. **Les chercheurs contribuent plus individuellement que les autres contributeurs.**

Chaque hypothèse traite une façon de représenter l'importance des chercheurs dans ces projets : en nombre de contributeurs, en nombre de contributions, en qualité de maintenance. Si les chercheurs sont significativement importants pour la tenue du projet, nous estimons raisonnable de conclure que ces projets sont le fruit du travail des chercheurs.

Pour répondre à ces trois hypothèses, nous avons récolté des informations pour chaque _commit_ de chaque dépôt : auteur \(nom et adresse mail\), nombre de fichiers modifiés, lignes ajoutées et retirées. Pour cette question, nous avons étudié l'ensemble des projets sélectionnés.

Dans un premier temps, il convient de définir comment nous avons déterminé qu'un contributeur est un chercheur.

#### Comment reconnaître un contributeur-chercheur ?

Il s'agit dans un premier temps de lister les contributeurs des projets étudiés \(par le nom\), puis pour chacun lister les adresses mail qu'il a utilisé.

Nous avons développé deux approches qui chacune fournit des résultats partiels :

* **Un chercheur possède une adresse mail dont le domaine appartient à une académie ou à un établissement de recherche. **Cette approche présente comme biais de potentiellement considérer comme chercheur un étudiant universita%ire. Elle est très peu exhaustive car la majorité des utilisateurs contribuent avec une adresse _@gmail_ de laquelle nous ne pouvons pas conclure.
* **Un chercheur possède un profil de chercheur sur Google Scholar.** Cette approche a comme désavantage la non-complétude de Google Scholar, qui ne contient pas tous les articles de recherche et qui ne crée pas systématiquement un profil pour chaque chercheur.

Chaque approche détermine si, oui ou non, un contributeur est un chercheur à son sens \(pas de position intermédiaire\).

En définitive, nous considérons qu'un contributeur est un chercheur si au moins une des approches conclut qu'il en est un.

#### IV.1.1. _Les contributeurs sont majoritairement des chercheurs._

Il s'agit de voir l'importance des chercheurs en quantité de contributeurs.

Nous considérons que cette hypothèse serait réfutée si la part des chercheurs dans l'ensemble des contributeurs représentait moins de 50%.

#### IV.1.2. _Les contributions viennent majoritairement de chercheurs._

Il s'agit de voir l'importance des chercheurs en nombre de contributions.

Nous considérons que cette hypothèse serait réfutée si la part des chercheurs dans l'ensemble des contributions, en termes de _commits_ ou de lignes de codes modifiées, représentait moins de 50%.

#### IV.1.3. _Les chercheurs contribuent plus individuellement que les autres contributeurs._

Il s'agit de voir l'importance des chercheurs par la place de mainteneurs du projet qu'ils pourraient éventuellement avoir.

Nous considérons que cette hypothèse serait réfutée si, en termes de _commits_ ou de lignes de code modifiées, la majorité des contributeurs-chercheurs s'investit moins que les autres contributeurs.

La contribution en termes de _commits_ serait plutôt un indicateur de contribution sur le long terme tandis que la contribution en termes de lignes de code modifiées indiquerait l'appartenance du projet au contributeur.

### IV.2. **Qui écrit les algorithmes automatiques dans ces projets ?**

Sur cette partie nous allons essayé de répondre s'il existe des algorithmes avec un contributeurs principal.

Pour y arrivé nous avons défini des hypothèses et des métriques .

#### Hypothèses :

En ayant constaté que  dans le cadre des projets machine learning la plus part des temps qu'un fichier possède un seul algorithme\(machine learning\), alors nous avons posé ces différents hypothèses qui sont :

1. **Tous les algorithmes sont majoritairement maintenus par une seule personne**
2. L**es algorithmes maintenus par un contributeur majeur sont majoritaire**

Ces deux hypothèses nous permet de montrer l'importance d'avoir sur un projet machine learning des algorithmes avec plus de  contributeurs majeurs, pour pouvoir conclure ou pas de niveau de bug sur ces algorithmes de machine learning.

En partant de l'hypothèse propriété et bug sur le cours de Monsieur Xavier Blanc

* un composant\(un algorithme de machine learning dans notre cas\) avec essentiellement des contributeurs majeurs a moins de bug.
* Un composant avec beaucoup de contributeurs mineurs a plus de bug.

Si dans les projets que nous allons etudier il y'a un grand nombre de contributeurs majeurs sur les algorithme , alors nous pouvons deduire que ce projet contient des algorithmes avec moins de bugs.

Afin de repondre a ces deux hypothèses, nous nous somme focalisé sur la notion d'ownerShip de chaque fichier, le nombre de ligne par contributeur dans un fichier , et le calcul de pourcentage de chaque contributeur dans un fichier.

#### **Comment determiner qu'un algorithme a un contributeur majeur ? **

En général dans les projets de machine learning , chaque algorithme est dévéloppé dans un seul fichier .

Pour la prémière hypothèse, nous considerons que toute fichier qui n'a qu'un seul contributeur, alors nous pourrons conclure que cet algorithme à un seul contributeur qui est donc majeur . \( Dans notre étude nous écartons toute les fichiers de tests,de documentations,de benchmarks\).

Pour la seconde hypothèse , nous regardons toute les fichiers avec deux ou plusieurs contributeurs , on calcule leurs pourcentage de contributions sur chacun de fichier afin de pouvoir conclure s'il existe ou pas un contributeur majeur sur ces algorithmes corespondant au fichiers.

Nous considerons qu'un contributeur est majeur sur un algorithme si et seulement il repond à l'une de ces deux approches.

#### IV.2.1. **Tous les algorithmes sont majoritairement maintenus par une seule personne**

Si un fichier a été développé par un seul contributeur alors ce contributeur est l'unique proprètaire\(contributeur majeur\) de cet algorithme.

#### IV.2.2. L**es algorithmes maintenus par un contributeur majeur sont majoritaire**

Nous avons défini l'hypothèse que si dans un fichier , il existe deux ou plusieurs contributeurs, de regarder le pourcentage de             contribution de chacun d'eux et de dire s'il existe un contributeur avec un pourcentage  superieur à 95% alors ce contributeur est majeur pour cet algorithme.

**NB : ** Nous avons établi cette deuxième hypothèse après avoir constaté que dans les projets opens sources en générale , il peut existe plusieurs contributeurs dans un fichier, mais si on regarde en profondeur on peut y trouver que la grande majorité du fichier est faite par une seul personne , et que les autres contributeurs ont fixé des bugs, modifier ou supprimer une ligne,etc..

#### Métriques :

* **Le nombre de lignes par auteur**

* ** Le pourcentage de contributions par auteur**

#### Projets :

Pour cette questions nous avons étudier trois projets qui sont :

1. Keras \(256 fichiers\)
2. Scikit-learn \(1180 fichiers\)
3. Tensorflow \(10136 fichiers\)

#### Démarches :

Afin de répondre à la question, nous avons fait un programe nous permettant de parcourir un projet avec git blame, et nous produire à la sortie:

1. File : Nom du fichier
2. Othor\[i\] : Nom de l'auteur i \(i représente le numero de l'auteur\)
3. LineOthor\[i\] : Nombre de ligne de l'auteur i
4. Contribution\[i\] : Pourcentage de contribution de l'auteur i
5. File Lines : Nombre total de lignes du fichier
6. Learning : Est ce un algorithme d'apprentissage \(Cette colonne est verifié que pour le projet Scikit-learn\)
7. NbOthors : Nombre total de contributeur du fichier

## V. Analyse des résultats et conclusion

_À remplir._

### V.1. Ces projets sont-ils menés par des chercheurs ?

#### Discriminer les chercheurs

Les trente-quatre projets cumulent 4376 contributeurs uniques \(uniques par leur nom\).

L'approche avec les adresses mails a conclu que 527 contributeurs étaient des chercheurs, soit 3849 ne l'étaient pas. L'approche qui utilise Google Scholar a conclu que 1537 contributeurs étaient des chercheurs, soit 2839 ne l'étaient pas. Seuls 251 contributeurs ont été considérés chercheurs par les deux approches à la fois, ce qui corrobore ce que nous attendions : il y a de nombreux faux négatifs pour les deux approches.

#### V.1.1. _Les contributeurs sont majoritairement des chercheurs._ {#contrib}

![](/assets/organisation_project_os_ml/researchers_per_project.png)

_Figure 4 - Une minorité de projets compte une majorité de chercheurs_

La _Figure 4_ montre que, d'après notre critère, notre hypothèse était fausse : **dans la majorité des projets Open Source de Machine Learning, les chercheurs sont minoritaires**.

Nous portons notre attention sur les deux groupes suivants :

* Un projet ne compte aucun contributeur-chercheur : _auto-ml_, ce qui est étonnant car tous les autres projets étudiés comptent au moins 20% de contributeurs-chercheurs.

Un aperçu du dépôt de _auto-ml_ sur GitHub montre que le projet _auto-ml_ est maintenu par une seule personne, Preston Parry \(qui n'est pas chercheur\), qui cumule 90% des _commits_, et accompagné de dix autres contributeurs qui, vus au cas par cas, ne semble eux non plus pas être des chercheurs. Il semble que nos résultats pour ce projet ne soient donc pas dûs aux biais de notre discrimination des chercheurs, mais plutôt que _auto-ml_ soit une exception.

* Les projets qui comptent une majorité de chercheurs sont _scikit-image_, _pylearn_, _spearmint_, _simpleai_, _metric-learn_, _nilearn_, _pyhsmm_, _skll_, _astroML_ et _cogitare_.

Pour une partie de ces projets \(_spearmint_, _simpleai_, _metric-learn_, _astroML_, _cogitare_\), ils font partie des projets étudiés les plus petits. Ajouté à l'observation sur la proportion de chercheurs qui les développent, une hypothèse à tester serait que ces projets sont maintenus uniquement par une seule personne ou par une équipe d'un laboratoire de recherche, travaillant dans un cercle fermé donc peu accessible pour un non-chercheur. Par exemple, il s'avère que _cogitare_ est maintenu par une seule personne mais qui a _commité_ sous deux noms, le troisième contributeur a produit un unique _commit_ massif et est un outil d'intégration continue \(suggérant que le projet sur GitHub est peut-être un miroir\).

#### V.1.2. _Les contributions viennent majoritairement de chercheurs._

![](/assets/organisation_project_os_ml/researchers_commits.png)

_Figure 5 - Une majorité de \_commits_ proviennent de chercheurs dans la majorité des projets étudiés\_

La _Figure 5_ montre que, malgré la minorité de chercheurs dans ces projets établie en [V.1.1](#contrib), ils produisent la majorité des _commits_ qui constituent les projets de Machine Learning étudiés.

![](/assets/organisation_project_os_ml/researchers_modified_lines.png)

_Figure 6 - Les chercheurs produisent également la majorité des ajouts et retraits de lignes dans la majorité des projets_

La Figure 6 corrobore les observations de la Figure 5.

Compte tenu du critère d'invalidation que nous avons de l'hypothèse, nous la considérons valide et observons : **les contributions proviennent majoritairement de chercheurs**.

#### V.1.3. _Les chercheurs contribuent plus individuellement que les autres contributeurs._

#### Conclusion partielle

### V.2. **Qui écrit les algorithmes d'apprentissage automatique dans ces projets ?**

Pour chacun de ces trois projets nous avons étudier les fichiers qui ont de 1 à 10 contributeurs, donc pour les resultats nous prendrons par nombre de contributeurs . Ces resultats se trouve dans le dossier DataResult dans notre repo [github](https://github.com/AntoineAube/reace-study/tree/master/ownership-algorithm/DataResult).

Malgrès que nous avons fais de 1 à 10 contributeurs pour chaque projet , nous allons vous exposer 5 cas pour chacun des trois projets.

Les tableaux sont triés par les fichiers qui ont plus de lignes de codes et après par le pourcentage de contributions le plus élévé \(ordre d'affichage décroissant\)

Pour voir les détails de cette étude avec l'affichage des dataset veuillez cliquer[ ici](https://github.com/AntoineAube/reace-study/blob/master/ownership-algorithm/find-ownership-algorithm.ipynb)

#### Première cas - Fichier avec un seul contributeur

###### Keras \(629 contributors, 4372 commits,256 fichiers \)

![](/assets/Keras.png)

Nous constatons que dans les 256 fichiers du projet, il y'a seulement que 3 fichier avec uxn seul auteur qui d'ailleurs le même pour les trois à savoir **François Chollet** \(à part les tests,documentations,benchmarks\).

###### ScikitLearn \(1023 contributeurs , 22 605 commits,1180 fichiers\)

![](/assets/Scikit-learn.png)

Sur ce projet on en trouve 8 fichiers sur 1180 au total pour exactement 6 contributeurs sur le 1023 contributeurs.

###### Tensorflow \(1346 contributeurs , 29 096 commits,10136 fichiers\)![](/assets/tensor.png)

#### Deuxième cas - Fichier avec trois contributeurs

###### Keras \(629 contributors, 4372 commits,256 fichiers \)

###### ScikitLearn \(1023 contributeurs , 22 605 commits,1180 fichiers\)

###### Tensorflow \(1346 contributeurs , 29 096 commits,10136 fichiers\)

#### Troisième cas - Fichier avec cinq contributeurs

###### Keras \(629 contributors, 4372 commits,256 fichiers \)

###### ScikitLearn \(1023 contributeurs , 22 605 commits,1180 fichiers\)

###### Tensorflow \(1346 contributeurs , 29 096 commits,10136 fichiers\)

#### Quatrième cas - Fichier avec huit contributeurs

###### Keras \(629 contributors, 4372 commits,256 fichiers \)

###### ScikitLearn \(1023 contributeurs , 22 605 commits,1180 fichiers\)

###### Tensorflow \(1346 contributeurs , 29 096 commits,10136 fichiers\)

#### Cinquième cas - Fichier avec 10 contributeurs

###### Keras \(629 contributors, 4372 commits,256 fichiers \)

###### ScikitLearn \(1023 contributeurs , 22 605 commits,1180 fichiers\)

###### Tensorflow \(1346 contributeurs , 29 096 commits,10136 fichiers\)

## VI. Références

_À remplir._

