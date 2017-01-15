# How can user requests impact modular architectures ?

* **Titre du chapitre** :

  * ... je ne sais pas si la limitation aux video games est une bonne idée d'autant que je ne pense pas que l'on puisse répondre à cette question par votre étude.

* **Pourquoi \(fera office d'introduction\) :**

  * il y a de l'idée... on en saura un peu plus après quelques essais

* **Pistes \(devra servir de base à un plan de chapitre, et il faut expliquer pourquoi\)**

  * trop succinct

* **Articles : serviront de référence et pourront etre discutés**

  * absents... Il faudrait chercher du côté des plugings. 
    peut etre : 



---

## Introduction

In this chapter, it will be discussed "_how can video games \(and more generally, software\) be modular thanks to the addition of 'mods' or 'plugins' ?_". This can be the wish of the development team, or driven by the community playing the video game \(or using the software\).

_**Questions :**_

* How can a community impact the development of some features ?
* How can the addition of mod impact the architecture ?

With these questions, we hope to retrieve and measure some information like :

* the mean time between two major updates and the number of line of code implied
* the number of user requests before a major update

_**Projects to study :**_

* [Terasology](https://github.com/MovingBlocks/Terasology)
* [Intellij Idea Community](https://github.com/JetBrains/intellij-community)

_**Methodology :**_

* Analyze connection between component and plugin interface system.
* Deduce if there is a strong connection or a loosely one.
* Attempt to find every pull request involving change in plugin interface system.

_**References used:**_

* _N/A_

_**Tools used:**_

* [Github API](https://developer.github.com/v3/)
* [Diggit](https://github.com/jrfaller/diggit)

_**Distribution of Work:**_

* MANNOCCI Adrien \(M2\)
* SARROCHE Nicolas \(SI5\)

_**Articles:**_

* Software modularity :  [Investigating software modularity using class and module level metrics M English, J Buckley, JJ Collins - Software Quality Assurance: In …, 2015 - books.google.com](https://www.gitbook.com/book/mireillebf/uca-students-on-software-maintenance/edit#)
* 
## Analysis

_**Subject:**_

After a few weeks of studies, we think about reducing the scope of this part, because there are too little documentation on it. We will focus on how the community drive the development.

_**Methodology:**_

We run through 3 phases to analyse data from the Terasology repository \(for instance\).  
The first phase is to extract data : to do this, we use an homemade script and we extract :

* The commit hash
* The author name
* The author email
* The author date
* The committer name
* The committer email
* The committer date
* The subject 

The second phase is to transform data using Logstash to convert the CSV, product by the fisrt step and produce a JSON file. We then use this JSON to populate an Elasticsearch.

The third and last step is to exploit these data, and produce charts, stats, dashboards, ... and reason on it.

_**First results:**_

We were able to extract,  display the files per commits over the last two years. We can measure that over 1300 modifications was made between November 30th and the December 6th.

![](/assets/screen_kibana.png)

_**Major difficulties:**_

We encountered major difficulties in term of documentation. We didn't find anything on the subject.

Therefore, searching tools has also be a pain because there are too few researches about it.

_**Tools used:**_

We first thouugh of using Diggit but we realized that this tools wasn't fullfilling our needs : we don't know Ruby, and the possibilities are too limitied for our purpose. So we use homemade scripts and the ELK stack where we mainly use Elasticsearch  and Kibana.

* Github API
* Scripts
* ELK



