## How long do bugs remain in open-source codes?

# Context

In this part, we will study on how long do bugs remain in open-source codes by evaluating the project management.

The next step will be to compare the duration of an issue judging by whom contribute in its solving. A good thing to keep in mind is the complexity of the solved bug, does a complex bug will be last longer than a simplest one ? How many contributors do we need to solve a complex bug ?

By complex I mean, a non recurrent problem or a bug that needs a expertise on the programming language or a expert on the project itself.

> @mbf : Je me demande comment vous ferez pour qualifier les bugs.. après corrections?

_**Project studied:**_

In that case, we will be looking for active projects that being running for a while and with a large number of contributors. Such as the [ElasticSearch Project](https://github.com/elastic) or the [Atom text editor](https://github.com/atom/atom/).

> @mbf : sur quel critère pensez-vous faire le choix?

_**Methodology:**_

The first thing to do is to collect and analyse all the issues on the git repository of the project. The goal is to evaluate whether the project uses issues to report bugs and if the contributors interact in these with commit tags, comments or not.  
After that, we have to look into each issues and compare the creation date, the first commit date and the date when the issue was closed.

_**References used:**_

[Tracking the Software Quality of Android Applications  
along their Evolution](https://hal.inria.fr/hal-01178734/document) by Geoffrey Hecht, Benomar Omar, Romain Rouvoy, Naouel Moha, Laurence Duchien \(17 Sep 2015\)

[14 Ways to Contribute to Open Source without Being a Programming Genius or a Rock Star](http://blog.smartbear.com/programming/14-ways-to-contribute-to-open-source-without-being-a-programming-genius-or-a-rock-star/) by Andy Lester \(March 10, 2012\)

_**Tools used:**_

[The Github API](https://developer.github.com/v3/)

[Gitinspector : a statistical analysis tool for git repositories](https://github.com/ejwa/gitinspector)

