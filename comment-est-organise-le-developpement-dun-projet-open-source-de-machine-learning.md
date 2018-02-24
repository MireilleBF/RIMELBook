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

Dans ces conditions, nous nous demandons comment est organisé le développement d'un projet open source de Machine Learning. À l'échelle d'un projet, de la réponse à cette question dépend la confiance que nous pouvons mettre en la qualité de leurs algorithmes et donc, d'une certaine manière, nous faire préférer un projet à un autre. Au niveau global, nous souhaitons déterminer s'ils existe des schémas récurrents dans l'ensemble de ces projets.

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

Les figures présentes dans le document ont été produites par nos soins, la plupart avec la bibliothèque [Pygal](http://pygal.org/en/stable/).

### III.2. Projets retenus

Nous avons retenu trente-quatre projets qui respectent nos critères.

Les projets que nous avons sélectionné ont été trouvés sur la liste [Awesome Machine Learning](https://github.com/josephmisiti/awesome-machine-learning).

Ils sont au nombre de trente-quatre : _scikit-learn_, _theano_, _keras_, _scikit-image_, _simplecv_, _nltk_, _pattern_, _auto-ml_, _pylearn_, _pybrain_, _brainstorm_, _pyevolve_, _pytorch_, _cogitare_, _featureforge_, _metric-learn_, _simpleai_, _astroML_, _lasagne_, _hebel_, _chainer_, _prophet_, _gensim_, _surprise_, _crab_, _nilearn_, _pyhsmm_, _skll_, _spearmint_, _deap_, _mlxtend_, _tpot_, _pgmpy_ et _milk_.

Ces projets sont différents entre notamment au niveau des domaines auxquels ils sont dédiés \(certains sont généralistes, d'autres spécifiques à certains domaines\) ainsi que de leur maturité \(en terme de nombre de contributions, nombre de contributeurs\).

![](/assets/organisation_project_os_ml/contributions_per_project.png)

_Figure 2 - Grandes disparités de la maturité des projets étudiés_

Nous observerons néanmoins que ces projets très actifs pour la plupart. La _Figure 3_ présente la fonction de répartition cumulative \(Cumulative Distribution Function - CDF\) des contributions apportés aux projets en 2017 et montre que, nonobstant de rares projets qui n'évoluent plus ou très peu, les projets évoluent en continu dans l'année.

![](/assets/organisation_project_os_ml/contributions_cdf.png)

_Figure 3 - Évolution perpetuelle de la plupart des projets_

Nous pensons que cette diversité apparente entre les projets nous permettra d'obtenir des résultats moins biaisés. Le fait qu'ils soient en changement perpétuel donne son intérêt à l'étude qui s'intéresse à l'évolution des projets.

## IV. Hypothèses et expériences

_À remplir._

Nous avons décomposé notre question générale en sous-questions qui fixent les limites que nous souhaitons étudier. Dans cette partie, nous détaillons pour chaque sous-questions nos hypothèses et la méthode que nous allons employer pour les vérifier ou les invalider.

Nos hypothèses de travail communes à l'ensemble de l'étude est que les contributeurs sont de bonne foi :

* Ils sont auteur du code qu'ils ont mis en ligne.
* Le nom, prénom et l'adresse mail spécifiés dans les contributions leur appartiennent.

### IV.1. Ces projets sont-ils menés par des chercheurs ?

Nous avons l'intuition que les projets de Machine Learning sont le fruit du travail des chercheurs, soit parce qu'ils sont des réalisations produites à l'aboutissement de leurs travaux, soit parce qu'ils sont les mieux à même de contribuer sur ces projets.

Nous souhaitons évaluer trois hypothèses :

1. **Les contributeurs sont majoritairement des chercheurs.**
2. **Les contributions viennent majoritairement de chercheurs.**
3. **Un chercheur qui contribue s'investit sur le long terme.**

Chaque hypothèse traite une façon de représenter l'importance des chercheurs dans ces projets : en nombre de contributeurs, en nombre de contributions, en qualité de maintenance. Si les chercheurs sont significativement importants pour la tenue du projet, nous estimons raisonnable de conclure que ces projets sont le fruit du travail des chercheurs.

Pour répondre à ces trois hypothèses, nous avons récolté des informations pour chaque _commit_ de chaque dépôt : auteur \(nom et adresse mail\), nombre de fichiers modifiés, lignes ajoutées et retirées.

Dans un premier temps, il convient de définir comment nous avons déterminé qu'un contributeur est un chercheur.

#### Comment reconnaître un contributeur-chercheur ?

Nous avons développé deux approches qui chacune fournit des résultats partiels :

* **Un chercheur possède une adresse mail dont le domaine appartient à une académie ou à un établissement de recherche. **Cette approche présente comme biais de potentiellement considérer comme chercheur un étudiant universitaire. Elle est très peu exhaustive car la majorité des utilisateurs contribuent avec une adresse _@gmail_ de laquelle nous ne pouvons pas conclure.
* **Un chercheur possède un profil de chercheur sur Google Scholar.** Cette approche a comme désavantage la non-complétude de Google Scholar, qui ne contient pas tous les articles de recherche et qui ne crée pas systématiquement un profil pour chaque chercheur.

Chaque approche détermine si, oui ou non, un contributeur est un chercheur à son sens \(pas de position intermédiaire\).

En définitive, nous considérons qu'un contributeur est un chercheur si au moins une des approches conclut qu'il en est un.

#### Les contributeurs sont majoritairement des chercheurs.

Il s'agit de voir l'importance des chercheurs en quantité de contributeur

Nous considérons que cette hypothèse serait réfutée si la part des chercheurs dans l'ensemble des contributeurs représente moins de 50%.

## V. Analyse des résultats et conclusion

_À remplir._

## VI. Références

_À remplir._

