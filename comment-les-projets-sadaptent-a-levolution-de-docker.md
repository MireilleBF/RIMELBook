# **Comment les projets s’adaptent à l’évolution de Docker ?**

## **Authors**

Nous sommes quatre étudiants en dernière année à Polytech Nice-Sophia, spécialisé en Architecture Logicielle.

* César Collé &lt;[cesar.colle@etu.unice.fr](mailto:cesar.colle@etu.unice.fr)&gt;
* Loris Friedel &lt;[loris.friedel@etu.unice.fr](mailto:loris.friedel@etu.unice.fr)&gt;
* Loïck Mahieux &lt;[loick.mahieux@etu.unice.fr](mailto:loick.mahieux@etu.unice.fr)&gt;
* Thomas Munoz &lt;[thomas.munoz@etu.unice.fr](mailto:thomas.munoz@etu.unice.fr)&gt;

## **I. Research context /Project**

Nous aimons utiliser Docker dans nos projets au quotidien et nous constatons que Docker ajoute \(et dans une moindre mesure supprime\) régulièrement des fonctionnalités, de plus c’est une technologie jeune \(4 ans\) et souvent considéré comme “à la mode”, c’est pourquoi nous nous posons des questions concernant la légitimité des nouvelles fonctionnalités, la gestion faite par Docker de son produit ainsi que le niveau de maturité de cette technologie.

## **II. Observations/General question**

Docker est devenu un outil essentiel pour le développement et la mise en production en entreprise. Nous nous sommes posé la question de savoir comment la communauté s’adapte aux modifications de Docker. En effet, pour un outil devenu aussi essentiel dans le développement de produits en entreprise il est important de s’assurer qu’il évolue pour s’adapter aux usages qu’il en est fait.

Aussi, nous nous sommes demandés, au vu de notre expérience dans l’utilisation de cet outil si l’évolution lente que nous constations \(depuis 2 ans peu de nouveautés ont été introduites\) résultait d’un manque de besoin pour davantage de nouveauté ou d’un retard de la part de la société Docker \(et de la communauté\).

Pour résumer, les questions que nous nous sommes posées sont les suivantes :

1. **Est-ce un produit assez stable pour être utilisé en entreprise pour des projets en production ? **

2. **Quelles sont les fonctionnalitées réellement adoptées/utilisées par les utilisateurs de Docker?**

3. **Comment les Dockerfile sont-ils maintenus au cours de la durée de vie d’un projet ?**

## **III. information gathering**

Nous allons analyser un certain nombre de projet originaire de Github pour mener à bien notre étude. Pour être sélectionné, un projet doit :

* contenir un Dockerfile.

* être parmi les projets avec le plus d’étoiles et de contributeurs sur Github.

Nous allons premièrement récupérer les 1000 premiers projets Github ayant le topic “docker” ordonnés par “stars”. Ensuite, il faudra filtrer les dépôts ayant un fichier Dockerfile dans le repo.

Nous allons également faire un passage manuel sur les 50 premiers dépot de Github \(potentiellement les plus importants\) afin de s’assurer que le Dockerfile n’est pas dans un autre dépôt dédié à Docker.

Ensuite, nous allons trier les projets les plus importants en deux catégories : ceux qui sont fortement liées à Docker \(tel que Traefik\) et ceux qui l’utilisent simplement pour avoir une image de leur application \(tel qu’une application web standard\).

  




