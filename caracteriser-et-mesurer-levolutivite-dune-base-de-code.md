# Caractériser et mesurer l'évolutivité d'une base de code

## Authors

Nous sommes 4 étudiants à Polytech' Nice-Sophia specialisés en Architecture Logicielle que voici :

* Chevalier Mathias &lt;chevalier.mathias@outlook.com&gt;
* Eroglu Yasin &lt;eroyasworkspace@gmail.com&gt;
* Gning Khadim &lt;khgning@gmail.com&gt;
* Jungbluth Günther &lt;gunther.jungbluth.poirier@gmail.com&gt;

## I. Research context /Project

### Qu'est-ce donc que PIX?

PIX est un projet public de plateforme en ligne d’évaluation et de certification des compétences numériques. C’est un projet en cours de développement qui se veut tout à fait transparent dans la manière dont il évolue. Il s’inscrit dans le cadre de modernisation et d’adaptation des offres du secteur public pour répondre à la croissance exponentielle et inexorable du numérique que l’on constate à la fois pour notre génération et pour les générations futures. Notons par ailleurs que l’acronyme PIX n’en est pas un, et ne signifie rien de particulier mais se veut évidemment évocatif.

Dans sa manière d’être, le projet PIX se présente tel que Agile avec les méthodologies des “Startups d’Etat” et implique de nombreux acteurs allant du ministère de l’Education nationale, de l’Enseignement supérieur et de la Recherche, etc… Il implique aussi différents acteurs du monde professionnel dans une démarche de co-construction. La caractéristique principale du projet, tout du moins dans sa philosophie, qui revient constamment et qui se veut être une véritable pierre angulaire de PIX: l’évolutivité.

Nous allons donc étudier et travailler autour de cette supposée évolutivité afin de pouvoir la remettre en question et de voir comment cela a été mis, ou non, en place. C’est un sujet qui est intéressant sur de nombreux points de vues et c’est pour cela que nous l’avons choisi. En effet nous pouvons discerner dans la politique gouvernementale actuelle un réel souhait de modernisation, d’ouverture, et un désir de se réaliser à travers différents outils et projets liés de près ou de loin à l’informatique, qui est finalement le cadre dans lequel on retrouve le projet PIX. Nous pouvons même associer PIX à deux catégories, la première dûe à sa nature de projet transparent dans son évolution, et la seconde liée à la promesse de réalisation d’une plateforme en ligne d’évaluation et de certification des compétences numériques. En d’autre mots, PIX souhaite aider les élèves et étudiants au niveau de leurs rapports avec l’informatique et sa prédominance dans le monde actuel en renforçant leurs différentes compétences allant de l’utilisabilité aux notions de sécurité.

## II. Observations/General question

Nous nous sommes donc demandé comment caractériser cette évolutivité dont se targue PIX. Cette notion d’évolutivité est particulièrement intéressante dans le contexte actuelle où de plus en plus de projet se disant agile et évolutif voient le jour. Les entreprises prennent conscience de la plus value qu’apporte de tels projets. Dans les grands groupes, notamment, on observe un grand nombre de projet de migration d’outil spécifique, utilisant des technologies anciennes vers de nouvelles technologies en suivant les concepts d’agilité et d’évolutivité. Le but de cette démarche étant de concevoir et développer des solutions s’adaptant, autant que faire se peut, aux évolutions des métiers pour lesquels elles sont conçues.

PIX est d’autant plus intéressant pour notre étude car il s’attaque à un domaine en perpétuelle évolution: l’informatique. De plus, il s’adresse à des profils aussi divers que variés. L’évolutivité doit donc faire partie intégrante de sa conception sans quoi ce projet est voué à l’échec. En outre, la transparence dont fait preuve l’équipe qui développe PIX quant au développement de leur produit est un atout non négligeable pour notre étude.

## III. Information Gathering

Il s’agit tout d’ abord d’étudier, avant de rentrer dans le code, la documentation et la définition de PIX ainsi que ses possibilités fonctionnelles offertes par la version beta de l'application.

### **Informations générales**

PIX se veut, comme on a déjà pu le dire, relativement transparent, et nous avons commencé par étudier le projet de manière très générale, afin de comprendre les tenants et les aboutissants du projet. Le site web du projet, et différents articles présents sur le web ont donc constitué notre source d’informations pour placer le contexte de notre étude, ainsi que d’expliciter la genèse et les objectifs du projet.

#### Timeline

PIX a réellement commencé son développement au milieu de l’année 2016, avec un objectif clair, atteindre les salles de classe pour la rentrée 2017-2018, soit l’année scolaire en cours à l’heure de la rédaction de ce document. Nous verrons par la suite que cet objectif n’a pas réellement été atteint et s’est peut-être révélé être quelques peu optimiste. Nous pouvons en effet voir sur la figure suivante que le développement ne s’est absolument pas arrêté, ni même ralenti sur cette fin d’année 2017. Nous aurions tout à fait pu voir un ralentissement, synonyme de passage de la phase de développement à nouvelle phase de maintenance, mais ce n’est pas le cas \(notons que le creux juste avant 2018 est probablement dû à la période des fêtes, comme cela avait été le cas en 2017\).

![](https://lh6.googleusercontent.com/IamAQG5t6dcEIiBX_lrMZrJ3jN8cbK6xjBA44AN8YsjeKaIomMe7zv_isO52paK4fH9ABZCvgPFE0eqx2I0iRx0s-uc61qe2Y_0_0HXbbV4kvjs99HffQtsoFyCntVknxoHSWraB)

_Figure 1 - Contributions sur le repository Github, en terme de commits, depuis le 10 juillet 2016._

Notons tout de même qu’une version beta est disponible et que certains établissement commencent à proposer à des élèves ou étudiants de différentes formation un premier contact avec la plateforme. PIX a revu ses objectifs et vise désormais une généralisation pour la rentrée 2018-2019, avec on peut se permettre de le supposer, une poussée ministérielle et probablement des moyens de mise en production et de mise en place accrus.

#### Méthode de conception

De par sa méthode de conceptionAgile, PIX a été rapidement utilisable à travers unMinimum Viable Productqui a su évoluer. Nous sommes ici en plein coeur de cette méthode de conception qui consiste à livrer de la valeur continuellement, en évitant au maximum les rétrogradations, PIX a donc rapidement été testable par des utilisateurs. Et c’est ici aussi que nous retrouvons la démarche de co-conception vantée par le projet, PIX s’est confronté à des utilisateurs tests toutes les 2 semaines \(ce qui correspond probablement à la période supposée desprint agile\) afin d’intégrer ces derniers au coeur du processus et livrer quelque chose correspondant, au moins sur l’expérience utilisateur, aux attentes.

Le deuxième point à aborder est évidemment le côté co-construction, mais du côté code cette fois ci, bien évidemment c’est un point que nous approfondirons plus en détails au fil de cette étude. Ce projet est donc ouvert sur Github et a été élaboré par 16 contributeurs différents. Ces contributions sont cependant bien différentes, et malgré un ordonnancement et une norme précise au niveau des descriptions des commits, les apports sont assez hétérogènes et tous n’ont très clairement pas participé à la même auteur. C’est cependant une caractéristique tout à fait normal dans un projet ouvert. Il est néanmoins difficile de comparer ce projet à des projets tout à fait Open Source qui regroupent eux plusieurs dizaines, voire centaines, de contributeurs \(avec évidemment aussi des contributions hétéroclytes\). Il est finalement assez complexe de classer la méthode de conception, car elle n’est pas réellement Open Source, nous ne pouvons en effet contribuer facilement au projet, mais n’est pas non plus réellement privée, puisque le code est en accès libre, et chacun peut l’utiliser \(ou le forker\).

#### Obligations liées au cadre

Malgré tout, ce projet est soumis aux desideratas d’entités hiérarchiquement supérieures aux développeurs, puisque le mandataire n’est évidemment autre que le ministère de l’enseignement, et ce malgré les revendications contraires qui cherchent parfois à potentiellement masquer ceci. L’objectif étant comme on a pu le dire, de remplacer les B2I, C2I, et autres certifications légales informatiques qui n’ont plus de réelle valeur dans le monde volatil d’aujourd’hui, et même si cette fois la finalité ne sera pas “certification ou non-certification” mais sera un score ou une grille de score pour échelonner les résultats, les contraintes “légales” sont quand même là. Les Français doivent en effet pouvoir répondre aux attentes, et ces attentes doivent aussi être suffisamment élevées pour qu’elles fassent sens par rapport à l’informatique de nos jours.

## IV. Hypothesis & Experiences

L'évolutivité est la capacité d'un système à grandir pour répondre à des demandes à venir. Cette évolutivité peut être décrite sous différents aspects pour différents buts. Tout d’abord, l'architecture doit pouvoir gérer et indiquer comment le système prendra en compte une augmentation des exigences en termes de débit et à répondre aux besoins de réduire les temps d'attente par exemple. Cette capacité à monter en charge est une première définition d’évolutivité pour un logiciel.

L'évolutivité peut aussi désigner la capacité d’une application à subir des évolutions fonctionnelles rapidement, au moindre coût, de manière rapide et fiable, c'est-à-dire sans régression des fonctionnalités déjà présentes aussi bien au niveau de leurs fiabilités que de leurs performances.

Afin de répondre à notre problématique, pour notre cas, nous avons décidé de définir l'évolutivité comme suite : s'assurer que l'architecture et l'implémentation sont en concordance l'un avec l'autre tout en leur permettant d'évoluer indépendamment est un critère qui définit si un projet est évolutif.

Nous sommes donc partie sur cette hypothèse pour faire l'analyse et en tirer une conclusion sur si oui PIX respecte ce critère, et dans le cas contraire, si non, pourquoi il ne le respecte pas.

## V. Result Analysis and Conclusion



## VI. Tools

## VI. References



