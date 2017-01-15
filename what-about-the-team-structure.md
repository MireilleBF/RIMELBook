# What about the team structure ?

### _Intro:_

This study tries to compare the a  model of an ideal team, based on Conway’s law, to a real company team. In this article we will expose some criterias of the Spring.io team structure.

First of all, we need to extract the team from the website project. To achieve this, we choose to develop our **own **extractor, in few word: given a webpage \(one extractor is write for one page\), we can by **parsing **the tags and make analysis catch the information needed.

Extract tool is available at [RIMEL-extractor](http://rimel.dobl.fr/) \([http://rimel.dobl.fr/\](http://rimel.dobl.fr/\)\)

With the extractor tool you can:

* Choose a project which reference a team \(e.g. [https://spring.io/team\](https://spring.io/team\)\)
* See the list of team members
* The Map will shows you their location
* The grid shows you their team position \(e.g. Developer\)
* Sort by Name, Position, Location, Github name
* View the most represented positions and locations
* View the correlation between project and location \(Coming soon\)

We can now analyse the team by considering some metrics: the projects that Spring team develop, the projects locations and the team positionning.



We need to make sense of the data we have collected.

First, the data we can collect on the spring.io/teams page is not extended and knowing that they have certainly been filled by hand, they are not very reliable.

So, we have begun to extract the geographical position of the developer, his main position, his github adress and his name.



### Locations_:_

These data are arranged on a map to allow a quick look at the scope of the project.

A project where all members work in the same building is different from a project where members can be scattered around the world \(like Spring\).   
The consequences of huge separation may be a lack of communication due to jet lag, language or culture. That will impact productivity in a negative way.

We were able to recover the latitude and longitude of each developer and thanks to the Google Map's GeoCode API we were able to retrieve geographical informations allowing to aggregate this data and to know the number of developer by country. \(in a donut chart\)

### Team projects:

By analyzing the terms of each job description, we were able to group them and thus know the number of developer in each functional module \(company's way\)

So in details :

For each job description we have retrieved words separated by spaces, removed unnecessary terms like punctuation and link words and removed the term Spring \(because it does not have any specific meaning, every developer is at Spring\)

We then counted the occurrences of each word \(after having standardized their case\), and have weighted by several functions \(log, square or n, available in the settings the size of display of the word according to its number of occurrences\).

### Project_: \(comming soon\)_











