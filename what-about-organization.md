# What about Organization ?

In this chapter we’ll be interested in the organizational differences between the two ORMs, to do so, we’ll examine the implementation of two features of our choosing: Caching, and dialects, the reason behind this choice is the fact the we find them interesting and also to make this study a bit more specific, given that ORMs cover a big variety of functionalities,

To do so, We will try to answer the following questions :

## How do components evolve over time \(including ownership, bugs, build stability, metrics\) ?

by components we mean structures responsible for a feature, for example, in the case of hibernate, a component is more often than not, a maven project, the study we'll only include those components

**Tools used :**

* CodeCity : to get  visualization of the codebase following size of the packages, complexity and other metrics.

* code Maat : to perform analysis on the codebase in order to detect ownership patterns, churn and the maturity of components

* GitHub API : retreive pull request, this will give us the velocity

* Jenkins : retreive the failing builds, and more precisely commist that broke the build

* [codescene.io ](https://codescene.io): visualize all the analysis of code Maat

Here we’ll examine the components of each ORM from different points of view :

* Ownership: are components “owned” by a contributor ?

* Size : how does size of said components vary ? given that the two ORMs are coded in languages that are somewhat similar in terms of verbosity \(Java and C\#\), we find it fair to compare the components in terms of lines of code, the comparison doesn't stop here, as we will also look at the evolution of size during time \(from one release to another for example\)

To answer this question we'll use first CodeCity in order to have a global picture about the codebase, then using Code Maat we'll perform several analysis \(i.e the ones listed before\), with the option -t of Code Maat, we will add the temporal dimension to our analysis.

On the other hand, the Github API will give us informations about the activity around those features, finally with Jenkins we will be able to find the commits and commiters that broke the builds and on which configurations did they broke it.

finally we will use tools in order to visualize the retreived informations in order to make it more "readable".

## Are dialects and caching highly coupled with other components  ?

Here We'll examine the coupling between the caching and dialects components and the rest of the code base

**Tools used :**

* CodeCity : perform analysis on concerned components

* Code Maat : perform analysis on the logical coupling side.

* [codescene.io](https://codescene.io) : visualize all the analysis of code Maat

**Methodology :**

Here we well try to see if dialects and caching components are tightly coupled with other components, in other terms, does adding new functionality require making changes in other areas of the code base, of course this is not necessarily something related to those features alone, and could be extended to other features, this question seems interesting because, usually, adding functionality to tightly coupled components is harder than adding it to a loosely coupled one.  
 To so we will analyse commits history using code maat and see if files from those components are often commited with files from other components.



