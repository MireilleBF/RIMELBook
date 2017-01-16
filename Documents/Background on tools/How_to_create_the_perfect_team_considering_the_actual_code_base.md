# How to create the perfect team considering the actual code base?

## Questions

* How to split a project into teams?
* How to link contributors of a git project to create a team?

* How to have several teams with the best amount of knowledge about the code they will work on?

## Tools

* code-maat : a tool to analyze a version control system repository \(as a git repository\)

* neo4j : to analyze, visualize and edit graphs

* python: to input the code-maat data into neo4j

## Methodology

The first thing we did is to try to model how we will represent teams and how it will map to concepts of a project. This model shown in figure 1 is the result of our work. It gives us a clearer idea on how to work on our project.

![](/assets/16118398_10207796048890112_224782135_n.png)

_Fig 1. Model of all the concepts we need for our research_

We have defined a couple of useful concepts. Our goal is to find the ideal team considering the source code. An ideal team is the union of all main contributors of a component, ie a team with all the people that have the most knowledge about the code. We define a component as the one gave by the spring-framework : all folders at the root containing a source folder. A file is a source file \(.java in the spring case\). A contributor of a file is someone who worked on a specific file \(had commit link to that file\). An owner is the contributor which has at least 50% of the code of a file. From these, we find an efficient team by component : the gathering of all owners of one file in the component. At the end, we have a team by component.

We first use code-maat to extract data from the Spring repository. It retrieves all the commits and allows us to know which files are strongly coupled together and which contributor has the most ownership on a file. The coupling give us hints about the components of the project : the folders at root that contain a source folder are component for the spring team, but if some of them are strongly coupled together, then the component can be more than just one folder. Then we export this data to a neo4j database using a python script.

This script creates nodes corresponding for now only to files and relationships corresponding for now only to coupling. We’ll also add properties to these relations corresponding to these extracted by code-maat in the future like the level of coupling.

This database will allow us to do search based on theses properties and relationships from which we could extract useful data for our research. We’ll then be able to query it to find answer to our questions and visualize our results in the form of a graph.

## Results

In the figure 2, we can see nodes which represents files \(we don’t filter configuration files for now, hence the big knot of tightly coupled files, those are pom.xml\) and links between them which represents coupling a relation of coupling between them. To reach this result, we use code-maat as described in the methodology part, and then we put the data transformed by our python script into neo4j.

This proves our knowledge on how to use the tools and allow us to know which files are strongly coupled and extract components from these. Next step is to link these components to the owners of each files in order to create a team.

![](/assets/graph.png)_Fig 2. Death Star of coupling _

## **@mbf : ;-\)**

## Difficulties

One of the main difficulties has been to define a model of the main concept of our study. What is a Team, a Component, a File, etc… We needed a clear definition of these to have a strong base for our research.

One of the bias of this study is that we only have an exterior point of view of the project. We can’t know about all the internal discussions theyhad, we only use the results of these : the commits.

A second difficulty was to find a way to use the output from code-maat which is a big CSV file with a lot of data. The solution we have found is to use it as an intermediary format to push this data in a Graph based database that we’ll be able to query. This needs a little bit of work on a per output file basis but seems to give good results. We will continue using this method in order to construct our database. The only other flaw we found in this system is how slow Neo4J can be, but that is to be expected when you have to manage graphs that can be quite big.

