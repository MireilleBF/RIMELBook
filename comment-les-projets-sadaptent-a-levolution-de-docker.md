# **Comment les projets s’adaptent à l’évolution de Docker ?**

# **Authors**

Nous sommes quatre étudiants en dernière année à Polytech Nice-Sophia, spécialisé en Architecture Logicielle.

* César Collé &lt;[cesar.colle@etu.unice.fr](mailto:cesar.colle@etu.unice.fr)&gt;
* Loris Friedel &lt;[loris.friedel@etu.unice.fr](mailto:loris.friedel@etu.unice.fr)&gt;
* Loïck Mahieux &lt;[loick.mahieux@etu.unice.fr](mailto:loick.mahieux@etu.unice.fr)&gt;
* Thomas Munoz &lt;[thomas.munoz@etu.unice.fr](mailto:thomas.munoz@etu.unice.fr)&gt;

# **I. Research context /Project**

Nous aimons utiliser Docker dans nos projets au quotidien et nous constatons que Docker ajoute \(et dans une moindre mesure supprime\) régulièrement des fonctionnalités, de plus c’est une technologie jeune \(4 ans\) et souvent considéré comme “à la mode”, c’est pourquoi nous nous posons des questions concernant la légitimité des nouvelles fonctionnalités, la gestion faite par Docker de son produit ainsi que le niveau de maturité de cette technologie.

# **II. Observations/General question**

Docker est devenu un outil essentiel pour le développement et la mise en production en entreprise. Nous nous sommes posé la question de savoir comment la communauté s’adapte aux modifications de Docker. En effet, pour un outil devenu aussi essentiel dans le développement de produits en entreprise il est important de s’assurer qu’il évolue pour s’adapter aux usages qu’il en est fait.

Aussi, nous nous sommes demandés, au vu de notre expérience dans l’utilisation de cet outil si l’évolution lente que nous constations \(depuis 2 ans peu de nouveautés ont été introduites\) résultait d’un manque de besoin pour davantage de nouveauté ou d’un retard de la part de la société Docker \(et de la communauté\).

Pour résumer, les questions que nous nous sommes posées sont les suivantes :

1. **Est-ce un produit assez stable pour être utilisé en entreprise pour des projets en production ? **

2. **Quelles sont les fonctionnalitées réellement adoptées/utilisées par les utilisateurs de Docker?**

3. **Comment les Dockerfile sont-ils maintenus au cours de la durée de vie d’un projet ?**

# **III. Information gathering**

Nous avons analysé 1469 projets originaire de Github pour mener à bien notre étude.

Pour être sélectionné, un projet doit :

* contenir un Dockerfile.

* être parmi les projets avec le plus d’étoiles et de contributeurs sur Github \(dans le top 1000 à chacune de nos recherches\).

Nous avons ainsi effectué plusieurs recherches, par langage \(Java, Go, Ruby, C/C++ etc.\), en récupérant à chaque fois les 1000 premiers projets \(ordonné par nombre d’étoiles\).

Ensuite, nous avons filtré les projets contenant au moins 1 Dockerfile \(afin de ne pas essayer d’analyser des projets n’en contenant pas\).

Ensuite, nous avons trié les projets les plus importants en deux catégories : ceux qui sont fortement liés à Docker \(tel que Traefik\) et ceux qui l’utilisent simplement pour avoir une image de leur application \(tel qu’une application web standard\).

# **IV. Hypothesis & Experiences**

## **Identifier les commandes les plus utilisées**

### **Répartition des commandes**

Grâce à la répartition des commandes, il nous est possible d’identifier les commandes “indispensables” à la conception d’un Dockerfile et celles qui le sont moins.

![](https://lh4.googleusercontent.com/jsgJAKKjPTIR_u2KOT5Y7hJNlxONJeeDFYCJ4tAeNMWCD9iENB9447efANHhXMsJEa6OOUP4090KXoCroF48wDYy_cmCeRVjZTbWURtMF7JdUblcAUscYqW6puORE8Oej8SVvz4q)

### 

### ![](/assets/name.png)

![](https://lh4.googleusercontent.com/rgVSJ-BjmS1btKgyOi5fDkR8m5v-ERLoWcf-Mq-imhgc-lcYBWkSJQaNUFo0PvqbbJofu4GCp-gKh9vFpblJFJSDCR5kC2L1INY0RHBsYBi1QL2hf3YA7TA-P3snQdIsUQr4KPCF)

![](https://lh5.googleusercontent.com/vbgKta6OF4uo3T27OG_UAcHmASPWmB1OMSzKCQIM8Zv2KEHlFxw-2kAQ9KXegVaTrSLRznxGAoYLQmPCaZg-vpbl6ABV4nVeO0VSuKT-k5ZYeXpelHk59I5FqS57XYY1PCfg9MlG)

![](https://lh5.googleusercontent.com/eOGlPvM9SlCgKEu0v54nFUdI_sYNT1XGuFFBnahQmevENNiLABJx_RhJNK-N0ec7FN--zfvbdX-W2OQVQXxDBOttwHhAQ-0KP6oNhtH5E2BWYKDQ9vk4HAsyBhmIeOnrIgoGynzM)

### **Commentaires sur les résultats**

Sur ce graphique, on peut constater qu’un noyau de commandes très utilisées, composé deFROMetRUNexiste. Aussi, les commandes les plus utilisées sont des commandes déjà disponible dès le début de Docker \(ou dans les mois qui suivent sa sortie\), il s’agit de WORKDIR, CMD, ENV, COPY, EXPOSE, ENTRYPOINT, ADD, MAINTAINER \(maintenant dépréciée\), etc. Les nouvelles commandes \(arrivées plus récemment comme ONBUILD, HEALTHCHECK ou LABEL\) sont peu utilisées.

On peut alors se demander si les nouvelles commandes proposées apportent des fonctionnalités suffisamment intéressantes pour être utilisées plus largement. Par exemple la commande MAINTAINER est plus utilisée que la commande LABEL \(alors que MAINTAINER est dépréciée au profit de LABEL\)

La forte utilisation d’une commande est un indicateur de son importance. Aussi, un noyau composé uniquement de commandes anciennes \(c’est-à-dire présentes depuis la création de Docker, comme FROM, RUN, etc.\)

# Tools

## **GitHub Javascript Client**

[**https://github.com/pksunkara/octonode**](https://github.com/pksunkara/octonode)

Afin de pouvoir automatiser le clonage des dépôts, nous avons utilisé le client Github en JavaScript \(NodeJS\) qui nous a permis de récupérer une liste de dépôts à partir d’une recherche \(sur un topic particulier, comme par exemple Java ou Go\).

## **Repo-driller**

[**https://github.com/mauricioaniche/repodriller**](https://github.com/mauricioaniche/repodriller)

Toute nos expériences sont basées essentiellement sur l’utilisation de repo-driller. Repo-driller nous a permis notamment de pouvoir filtrer les commits provenant des dépôts afin de se concentrer seulement sur ceux impactant un dockerfile.

Sur ces commits, nous avons pu récupérer toutes les modifications et à quelle date elles ont été faites. Ces données ont ensuite été traité par un module d’analyse externe.**    
**

## **V. Result Analysis and Conclusion**

En conclusion, lorsque l’on observe la répartition de l’ensemble des commandes docker, à travers les projets les plus populaires de github, on peut constater que

## **VI. References**

[**https://www.infoq.com/articles/docker-future**](https://www.infoq.com/articles/docker-future)

[**http://www.redbooks.ibm.com/redpapers/pdfs/redp5461.pdf**](http://www.redbooks.ibm.com/redpapers/pdfs/redp5461.pdf)**\(p. 55-56-57\)**

