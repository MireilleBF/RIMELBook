## How do contributions of developers evolve over time?

_**Project studied:**_

The open source projects are a good study case because there is often many move, developers start to contribute to the project and other stop to contribute. We should have many data to analyse the developers attitude.

We will study the [ElasticSearch](https://github.com/elastic) project.

> @mbf : Le lien est trop haut... Sauf si vous vous intéressez à la suite.

_**Methodology:**_

We will start by getting Github data out to work on it. The Github API should make possible the extraction of these data. Depending on the data format we will use for example python for processing of data. Also with python we could make a first set of basic graph for guide the rest of our exploration.

> @mbf : Quelles data vous intéressent? Que voulez-vous identifier ? Les commits faisant référence à des bugs? Les contributeurs sur des fichiers, lignes de codes?

Depending on the things that we could reveal with data, we will choose the good graph tool for representing them. Considering the huge quantity of data that we can extract, we could use the tools of the project that we will study : ElasticSearch, and Kibana to make dashboards.

> @mbf : Explicitez d'abord les questions que vous allez posés puis votre approche \(quelles données extraire\) et ensuite comment vous allez les explorer : requêtes, visualisation, etc.

_**References used:**_

[The seven habits of highly effective GitHubbers](http://ben.balter.com/2016/09/13/seven-habits-of-highly-effective-githubbers/) by Ben Balter \(September 13, 2016\)

[A Data Set for Social Diversity Studies of GitHub Teams](/A Data Set for Social Diversity Studies of GitHub Teams) by Bogdan Vasilescu, Alexander Serebrenik, Vladimir Filkov

> @mbf : TB @inproceedings{Vasilescu:2015:DSS:2820518.2820601,  
>  author = {Vasilescu, Bogdan and Serebrenik, Alexander and Filkov, Vladimir},  
>  title = {A Data Set for Social Diversity Studies of GitHub Teams},  
>  booktitle = {Proceedings of the 12th Working Conference on Mining Software Repositories},  
>  series = {MSR '15},  
>  year = {2015},  
>  location = {Florence, Italy},  
>  pages = {514--517},  
>  numpages = {4},  
>  url = {[http://dl.acm.org/citation.cfm?id=2820518.2820601}](http://dl.acm.org/citation.cfm?id=2820518.2820601}),  
>  acmid = {2820601},  
>  publisher = {IEEE Press},  
>  address = {Piscataway, NJ, USA},  
> }

_**Tools used:**_

Github API

Python for manipulate data and make a first set of graph

> @mbf : sans la question détaillée dure de savoir, attention de ne pas "tout refaire!"



