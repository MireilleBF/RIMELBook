# Comment est organisé le développement d'un projet Open Source de Machine Learning ?

## Auteurs

Nous sommes quatre étudiants en dernier année à Polytech Nice-Sophia Antipolis, spécialisés en Architecture Logicielle.

* Robin Alonzo &lt;alonzo.robin@etu.unice.fr&gt;
* Antoine Aubé &lt;aube.antoine@etu.unice.fr&gt;
* Thierno Balde &lt;balde.thierno@etu.unice.fr&gt;
* Mathieu Mérino &lt;merino.mathieu@etu.unice.fr&gt;

## Introduction

Ce chapitre présente le travail de recherche produit par notre groupe dans le cadre de la matière Rétro-Ingénierie, Maintenance et Évolution des Logiciels \(RIMÉL\). Nous présenterons successivement notre contexte de recherche, la question que nous avons posé accompagnée de nos hypothèses, puis la démarche à laquelle nous avons procédé ; nous poursuivrons par une analyse des résultats obtenus en faisant le lien avec nos hypothèses, puis concluerons.

## I. Contexte : Apprentissage Automatique, une communauté qui grandit

L'apprentissage automatique \(Machine Learning, ML\) est une science sous-jacente à l'intelligence artificielle qui définit des méthodes pour prédire des caractéristiques à partir d'un ensemble de données.

Cette discipline ne cesse d'intéresser de nouveaux adeptes, autant les entreprises qui souhaitent exploiter les très grands volumes de données qu'elles génèrent, que les chercheurs qui ne cessent de publier de nouveaux travaux à ce sujet.![](/assets/organisation_project_os_ml/machine_learning_trends.png)

_Figure 1 - Intérêt croissant pour le Machine Learning lors des cinq dernières années_

_Source des données : _[_https://trends.google.fr/trends/explore?date=today%205-y&q=machine%20learning,deep%20learning,artificial%20intelligence_](https://trends.google.fr/trends/explore?date=today 5-y&q=machine learning,deep learning,artificial intelligence)

Une brève investigation révèle qu'une communauté s'est créée autour de l'apprentissage automatique, autant pour diffuser le savoir \(des sites comme _DataCamp_\), pour collaborer autour d'ensemble de données publics \(_Kaggle_\) ou pour construire des logiciels et bibliothèques qui tiennent compte de l'avancée dans le domaine \(de nombreux projets open source sur _GitHub_ comme _scikit-learn_, ...\).

## II. Questionnement

L'apprentissage automatique est un domaine de pointe, que nous imaginons encore très proche de la recherche. Nous nous étonnons que, pourtant, les outils récurrents du Machine Learning \(nous entendons souvent parler de _Tensorflow_ et ses surcouches, _numpy_, ...\) soient des logiciels Open Source.

Dans ces conditions, nous nous demandons comment est organisé le développement d'un projet open source de Machine Learning. À l'échelle d'un projet, de la réponse à cette question dépend la confiance que nous pouvons mettre en la qualité de leurs algorithmes et donc, d'une certaine manière, nous faire préférer un projet à un autre. Au niveau global, nous souhaitons déterminer s'ils existe des schémas récurrents dans l'ensemble de ces projets.

Notre intuition suggère plusieurs pistes que nous souhaitons explorer et auxquels nous nous restreindrons dans cette étude. Leur formulation ci-suit concerne bien les projets Open Source de Machine Learning :

* Ces projets sont-ils menés par des chercheurs ?
* Qui écrit les algorithmes d'apprentissage automatiques dans ces projets ?
* La qualité logicielle est-elle une préoccupation de ces projets ?

## III. Rassemblement d'informations

### Outils utilisés

Pour rassembler les informations utilisés dans cette étude, nous avons utilisé les outils suivants :

* RepoDriller[^1] pour analyser les contributions successives des projets.
* SonarQube pour analyser la qualité des projets.

Nous avons également produit une série de scripts Bash, Javascript et Python pour des tâches plus spécifiques et pour automatiser la récolte des informations, afin d'améliorer la reproductibilité de l'étude et de repérer les possibles erreurs dans le protocole que nous suivons.

### Objets de l'étude

Comme nous souhaitons observer des propriétés vraies pour les projets Open Source de Machine Learning en général, l'étude portera sur un ensemble de projets.

#### Critères de sélection

Nos critères de sélection sont arbitraires, ils nous permettent de ne pas nous disperser dans les outils d'analyse que nous produisons. Les critères sont les suivants :

* Ces projets sont des bibliothèques d'algorithmes d'apprentissage automatique.
* Ces projets sont écrits en majorité en Python. Python est en effet l'un des langages de prédilection dans ce domaine.
* Ces projets sont hébergés sur GitHub.

#### Projets retenus

Nous avons retenu trente-quatre projets qui respectent nos critères.

Les projets que nous avons sélectionné ont été trouvés sur la liste Awesome Machine Learning[^2].

Ils sont au nombre de trente-quatre : _scikit-learn_, _theano_, _keras_, _scikit-image_, _simplecv_, _nltk_, _pattern_, _auto-ml_, _pylearn_, _pybrain_, _brainstorm_, _pyevolve_, _pytorch_, _cogitare_, _featureforge_, _metric-learn_, _simpleai_, _astroML_, _lasagne_, _hebel_, _chainer_, _prophet_, _gensim_, _surprise_, _crab_, _nilearn_, _pyhsmm_, _skll_, _spearmint_, _deap_, _mlxtend_, _tpot_, _pgmpy_ et _milk_.

Ces projets sont différents entre notamment au niveau des domaines auxquels ils sont dédiés \(certains sont généralistes, d'autres spécifiques à certains domaines\) ainsi que de leur maturité \(en terme de nombre de contributions, nombre de contributeurs\).

![](/assets/organisation_project_os_ml/contributions_per_project.png)

_Figure 2 - Grandes disparités de la maturité des projets étudiés_

Nous observerons néanmoins que ces projets très actifs pour la plupart. La _Figure 3_ présente la fonction de répartition cumulative \(Cumulative Distribution Function - CDF\) des contributions apportés aux projets en 2017 et montre que, nonobstant de rares projets qui n'évoluent plus ou très peu, les projets évoluent en continu dans l'année.

![](/assets/organisation_project_os_ml/contributions_cdf.png)

_Figure 3 - Évolutions perpetuelles de la plupart des projets_

## IV. Hypothèses et expériences

_À remplir._

## V. Analyse des résultats et conclusion

_À remplir._

## VI. Références

_À remplir._



[^1]: [https://github.com/mauricioaniche/repodriller](https://github.com/mauricioaniche/repodriller)

[^2]: [https://github.com/josephmisiti/awesome-machine-learning](https://github.com/josephmisiti/awesome-machine-learning)

