# What is the relation between adding functionality, bug fixing, and code quality

## Abstract

In this question we will try to highlight any relation between adding functionality, bug fixing, and degradation or improvement of code quality. We hope to highlight an overall trend in the quality of the code over timeand thus confirm or invalidate the Lehman law.

## Chosen methodology

To answer this question we will proceed in several steps. We will have to extract from a Github repository several versions of the same code. To do this we will extract the state of the code with each release or revision.

In this way we can hope to have enough difference between project version that we would have chosen to be able to consider them as relevant for our study.In addition, we can imagine that changes made during a review will contain more bug fixes than adding functionality, and vice versa. If this hypothesis is verified we will have between two revisions mainly bug corrections and between two versions we will have more features added, which could allow us to independently evaluate the impact of these two types of modification.



Once our code base has been extracted we will have to make a qualitative evaluation of the code for each selected revisions and versions, using tools. We can rely on the complexity of the code, which tools like Metrics or Sonar can give us.



Pour répondre à cette question nous allons procéder en plusieurs étapes. Nous allons devoir extraire d'un repository Github plusieur version d'un même code. Pour ce faire nous allons extraire l'état du code à chaque release ou révision.

De cette manière nous pourrons esperer avoir suffisament d'écart entre de version de projet que nous aurions choisis pour pouvoir les considérer comme pertinant pour notre étude. De plus, nous pouvons imaginer que les modification apporter lors d'une révcision tiendrons plus de la correction de bug que de l'ajout de fonctionnalité, et vice versa. Si ette hypothèse est vérifier nous aurons entre deux révisions éssentielement des corrections de bug et entre deux versions des ajout de fonctionnalité, ce qui pourrait nous permettre d'évaluer indépendament l'impact de ces deyx type de modification.

Une fois notre base de code extraite nous devrons faire une évaluation qualitative du code pour chaque révisions et version choisis, à l'aide d'outils. nous pourrons nous baser sur la complexité du code, que de outils comme Metrics ou Sonar peuvent nous donner.

