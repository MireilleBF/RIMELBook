# How can user requests impact modular architectures ?

## Introduction

In this chapter, it will be discussed "_how can a community drive the developpement of a software \(in our case a video game and 3d engine\) or at least some features? _". This can be the achieved by the development team, or driven by the community playing the video game \(or using the software\).

_**Questions :**_

* How can a community impact the development of some features ?
* How long does it take from the idea to the first realisation ?

With these questions, we hope to retrieve and measure some information like :

* the mean time between a demand and a commit
* the number of user implied in the community 

_**Projects to study :**_

* [Terasology](https://github.com/MovingBlocks/Terasology) : Terasology is, in the first place, a clone of the well known game Minecraft. Now it is more like a 3D engine that you can use to make your own game.

_**Methodology :**_

* Analyse the community.
* Analyse the Git repository.
* Attempt to find every pull request involving change in plugin interface system.

## Analysis

_**Subject:**_

After a few weeks of studies, we think about reducing the scope of this part, because there are too little documentation on it. We will focus on how the community drive the development.

_**First Methodology:**_

We will run through 3 phases to analyse data from the Terasology repository \(for instance\).  
The first phase will be to extract data : to do this, we use an homemade script and we extract :

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

_**New Methodology:**_

An idea suggested by one of our teachers  was to going back up to the source of our community : their forum. We then implemented a crawler in order to deduce relevant information \(or even piece of information\) like :

* Who is the most talkative on the forum
* Who talks about features 
* The date when people asks for features
* The elapsed time between the day a user makes a request and the day of the first commit about this request

Here are all data we retrieved from the forum :

* Title of the message
* Pseudo of the writer
* Date of the message
* Category of the message
* Content of the message
* Content of the message without useless words \(determinants, subjects, ...\)
* URI of the page

The crawler generates data ready to be insert in ElasticSearch.

We also extracted information about pull requests and issues on Git using the Githup API, converted them into proper JSON object and placed them into our ElasticSearch.

To summarize, our elasticsearch now contains :

* All github commits
* All github issues
* All github pull requests
* All forum messages

_**New results:**_

We first extracted the messages from the forum in order to have an overview of distribution of the messages among all the users. It appears that the person named 'Cervator' produces or answering to most of messages of the forum. We found out that this person spearhead the Terasology project.

![](/assets/community_1.png)

_**Major difficulties:**_

We encountered major difficulties in term of documentation. We didn't find anything on the subject.

Therefore, searching tools has also be a pain because there are too few researches about it.

_**Tools used:**_

We first thouugh of using Diggit but we realized that this tools wasn't fullfilling our needs : we don't know Ruby, and the possibilities are too limitied for our purpose. So we use homemade scripts and the ELK stack where we mainly use Elasticsearch  and Kibana. We also implemented our own crawler for the forum.

* [Github API](https://www.gitbook.com/book/mireillebf/uca-students-on-software-maintenance/edit#)

* Scripts

* Homemade Crawler

* ELK

_**References used:**_

* Software modularity :  [Investigating software modularity using class and module level metrics M English, J Buckley, JJ Collins - Software Quality Assurance: In …, 2015 - books.google.com](https://www.gitbook.com/book/mireillebf/uca-students-on-software-maintenance/edit#)

_**Distribution of Work:**_

* MANNOCCI Adrien \(M2\)
* SARROCHE Nicolas \(SI5\)



