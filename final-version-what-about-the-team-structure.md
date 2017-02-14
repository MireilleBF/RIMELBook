# **Extract the real team**

We wanted to extract the real team of a big organisation, and compare it to the ideal team found by Tom and Fabien, then try to discuss the Conway’s law according to our results.

First of all we need to create a model to define what is a real team according to Convoy’s law :

![](https://lh5.googleusercontent.com/Dp4OU7-zov2DpQUfG-aY5ynyxBUqxMUzlCyItzWEzGQQzwSvePWxbETZCJ75b9UXYzOUjLJ3uHxZ3TxFNRqT350hcbGwUGgIawr9_iGQgA_xr2g8oIRhIy-iQqg7VxHPNvvh73lw)

We can assume that for a given project \(Spring in our case\) there are one or more project modules \(Spring Framework, Spring Cloud, Spring Data…\). For each of this submodules there is a team of 5 to 15 developers : these numbers are not randomly chosen, it’s the ideal number of developers in an agile team based on SCRUM method. Conway’s law tell us “organizations which design systems ... are constrained to produce designs which are copies of the communication[structures](https://en.wikipedia.org/wiki/Organizational_structure)of these organizations”, the team contributors are constrained to be reachable : we consider two persons reachable if they are same timezone or have less than 1 hour of difference \(+-1\).

There is an abstraction zone to not exceed, we are doing a top to bottom approach instead of Tom and Fabien who are doing a bottom to top research : in this part we will not talk about components or code because they aro too deep in our architecture.

## Extract the real team from the spring.io webpage about the major team \(most important collaborators\)

First of all, we need to extract the team from the website project. To achieve this, we choose to develop our own extractor, in few word: given a webpage \(one extractor is write for one page\), we can by parsing the HTML tags and make analysis that catch the information needed. Then wegenerate some arrays and diagrams in order to evaluate the extracted organisations.

## How to do it

in the extractor tool you can:

* Choose a project which reference a team \(e.g.[https://spring.io/team](https://www.gitbook.com/book/mireillebf/uca-students-on-software-maintenance/edit#)\)

* See the list of team members

* The Map will shows you their location

* The grid shows you their team position \(e.g. Developer\)

* Sort by Name, Position, Location, Github name

* View the most represented positions and locations

* View the correlation between project and location

So, to extract all the team on rimel.dobl.fr, just click on this button

![](https://lh3.googleusercontent.com/OdO1j2Grncj3-haBsTvY_GYNPa8vEAbDX_w6yoI3JEu_IAEXDr2wGnMijeWiZUIZbf9fnYAEypbw-51c55qQAvbyiwn77EKLaPXb8xn58zJEDf8b544K1ET41ISn1-7BHv7LtflZ)

Then, all charts just appear below.

At the top of the page, a table and a map, showing all the contributors retrieved from the spring page.

For each, we got :

* the Name \(Surname + Lastname\)

* The description of the position \(handwrite by the collaborator\)

* A description of the location

* The precise location \(latitude and longitude, visible on the map on the right\)

* The collaborator’s github address

![](https://lh4.googleusercontent.com/XNjBt__q7qyj2oQRQYYQsms_j9f7t-jVGKYJvlooLSFkktaPU6FK_I-7hSyUkIaw-exooBIXBSD3bh0TwmlFNbzxqATB3VdD4UY3c1ttVibe0DtK41Tk_P2HYwgcTVVc859mSeEq)

So we decided to made a words analysis on the terms found on the description of each collaborator.

We create a cloud a word, where the bigger word is the most present word in all the positions.

Interest of the words cloud :

* It reveals the essential. Projects names pop, key words float to the surface.

* Word clouds can allow you to share back results from research in a way that doesn’t require an understanding of the technicalities.

![](https://lh3.googleusercontent.com/WcFoXPkRVInDtJSBld6hQYLIEi4hhcfSrJAEFkYFitvlOI1jWblhZ1LVUVq80y-Zaf9AQeDqbDFygNaTOuMvKDWnrcsb45oGkm5VlD75hNJ9MtlKgOrWGThWLqMJdlwQOlzBw_hz)

    


Then we tried to find similarities between collaborators in order to find the work relationship between them and then constitute the teams. But the position’s description are too blurred and two collaborator working in the same team describe their work so differently that we can’t find similarities.

![](https://lh6.googleusercontent.com/cEB6gUP40nmtv3YVcB7zmWaM7G5FGOKA78d0-D71qyBE3eS5Ww1m1KIjKk3EhelnobDmzM5ErBVO9_TgrVNqxaTLAvOY_U8Q6k_s2KKsx9S4fejGFSehV2kG--KETVOpf2ARzR_H)

For example the most used word in position description is “Committer”. Committer is a general work mean someone who push code into projects. But in our purpose it’s mean nothing. That’s why we decide to search into collaborators repository.

So how we proceed :

1. Collect all the spring projects's name at github.com/spring-projects using github’s developper API

2. Find the team members working in these projects

3. Determine in which time zone members are located

## Results

We obtained in the spring-framework project 18 collaborators from our initial list \(the one from spring.io\). 18 people is poor, but it’s the best we have so we listed these contributors :

![](https://lh6.googleusercontent.com/IBf99yKrnBc7O8Cot4bB6GGTzscaFanvfssTT4UY6SWQL3PcLPHzOFpaORoetqj9tkJm7OOCihrRH2N4swxHvznikyLBO-tUW896duf_vEhnitBxiaSxojKHWT78D_T-kSPXnoUP)

![](https://lh4.googleusercontent.com/H14dxxLPd4Hptpfg_rcbym0jU9EFOEsFpggZ15cNKESRhR5WVBEduIUkoKymO6wW-BEdPJp2tAStWONOENawUZOI7tlBDFIfUecy2o4hVqDNfzIIq8GTK0TGVZ2AmkYg13V1sfvO)

Then according to these data we compute the average time difference between collaborators.![](https://lh4.googleusercontent.com/3muWtfPvnGRwx4rF6qBHlWa5e87kEcJn6Pn4acOpjbdisKeiLLmcWsQCFFP1Ki8EeGcHkEtP66qNPmi864jhOgORfte0WOSE4el4NEIAQYi5EuCyxN3N1PJneIVAFRAynQOI0xrV)

And we find there is a maximum of 9 hours of time difference !This can be a problem if you want to work together.

## Difficulties encountered & Analysis of results

### Difficulties

Given the poor amount of data we have it’s quite hard to extract sense.Furthermore some data are too blurry, or even random.

Hopefully we have the github account of each collaborator. Using the github api we constitute team. But we only arrived to find sense in time difference.

### Analysis of results

As we said in a previous part all our data is based on time differences. But even though we have succeeded to find that in some project there may be a big difference in time due to the location of the collaborators. This does not allow us to find the actual composition of the team.

By digging a little more and merging this analysis of the time differences with the first one \(that which consists of analyzing the position description\) we found something interesting on smaller time slice.

For example on spring framework we had 9 hours of time shifting to the maximum.

But If we reduce this to smaller intervals of 1 or 2 hours. We realized this often represents 4 or 5 people, with only one leader.

So we can think this is a team work. But nothing proves it. However, we will discuss it in the final conclusion.

