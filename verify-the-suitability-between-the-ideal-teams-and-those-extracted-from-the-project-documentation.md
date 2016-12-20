# Verify the suitability between the ideal teams and those extracted from the project documentation.

### _**Why ?**_

This study tries to compare the Spring’s teams with some metrics that qualify a good team from a bad team, based on Conway’s law. It is a sociological based predicate, deduced by observations but that seems to be true in most of cases. He said for **example **:

> _If you have four groups working on a compiler, you'll get a 4-pass compiler_

Bigger an organization is, more social boundaries are produced: majors are caused by communication problem.

Developers are not robots and they can’t work together perfectly because humans can’t share their mind: that’s why there is a conception phase before developing something. Working on the same code part means that you spend time on integrations and ensuring that the integration will be good enough, developers need to speak together. Sometimes the project are so big that we need a **big team**, dispatched all around the world and communication can be hard.

### _**The Goal ?**_

![](/assets/ConwaysLaw.png)

If companies tries to split the work between developers by adding some rules based on that Conway’s , we can imagine the job can be done **better and faster**.

When you ask to a team of three developers to solve an easy problem such as creating a simple website: The first says “I know Node.js, you can simple add a server.ts file to route all requests”, while the second will say “Java allows you to create simple http-servlets to create a server” and the third will say “I’m not aware with backend programming, but there are a lot of online hoster to create a simple http server”. Each specialist find the way to answer to the question as it own, but with several ways.

To avoid comprehension problems between team members, software architects are setted up to clarify which way to take in development. If the architect is far from the his team \(eg. 2-3 hours jet lag\) that can slow up the subject comprehension. Generally, the developers who shares the same module editing, must talk each other to clarify in which way progress: as you can see, proximity is the key and call reachability is essential.

Spring’s team is well dispatched around the world, we want to determine if we can use the Conway’s law to deduce the ideal team and compare it to get a better coding performance.

### _**How to ?**_

First of all, we need to extract the team from the website project. To achieve this, we choose to develop our **own **extractor, in few word: given a webpage, we can by **parsing **the tags catch the information needed.

Extact tool is available at [RIMEL-extractor](http://rimel.dobl.fr/) \([http://rimel.dobl.fr/\](http://rimel.dobl.fr/\)\)

With that tool \(alpha version at the moment\) you can:

* Enter a webpage which reference a team \(e.g. [https://spring.io/team\](https://spring.io/team\)\)
* See the list of team members
* The Map will shows you their location
* The grid shows you their team position \(e.g. Developer\)
* Sort by Name, Position, Location, Github name

Now, we need to imagine an ideal team for the project. However, how do we find it?

The ideal team is a team where all the members of the project are gathered in the same place.

And if several geographical groups are formed, then the best thing is for each geographic group, to work on an independent part of the project. In order to limit problems due to remote communication.

So we will try to analyze the distribution of members.

Then we will try to assess whether it is satisfactory, and see if people working on the same subjects are geographically close or not.

We know that that law is based on how developers communicate between each other. Therefore we can imagine that committers to one project module or the same project, needs to be communication dependent.

### _**References :**_

* Allan Kelly \(2013\) Conway's law v software architecture Published at DZone with permission of Allan Kelly, DZone MVB.

* N. Nagappan, B. Murphy, and V. Basili. International Conference on Software Engineering, Proceedings \[online\] \(visited on 18/12/2016\). [The Influence of Organizational Structure on Software Quality](https://www.gitbook.com/book/mireillebf/uca-students-on-software-maintenance/edit#)

* Frank Philip Seth. The Influence of Organizational Structure On Software Quality: An Empirical Case Study \[online\]. \(visited on 18/12/2016\). [https://www.microsoft.com/en-us/research/publication/the-influence-of-organizational-structure-on-software-quality-an-empirical-case-study](https://www.microsoft.com/en-us/research/publication/the-influence-of-organizational-structure-on-software-quality-an-empirical-case-study/ "https://www.microsoft.com/en-us/research/publication/the-influence-of-organizational-structure-on-software-quality-an-empirical-case-study/")

* Lappeenranta University of Technology, LUT. "Human and organizational factors influence software quality." ScienceDaily. ScienceDaily, 11 August 2015. \[online\]. \(visited on 18/12/2016\). [www.sciencedaily.com/releases/2015/08/150811091913.htm](http://www.sciencedaily.com/releases/2015/08/150811091913.htm)

### Authors _**:**_

* Manuel PAVONE, SI5 \(5th year in Computer Science\) at the engineering school Polytech Nice-Sophia.

* Dorian BLANC, SI5 \(5th year in Computer Science\) at the engineering school Polytech Nice-Sophia.



