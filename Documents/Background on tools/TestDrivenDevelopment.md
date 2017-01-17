# Background on tools : What are the impacts of Test-Driven Development on code quality, code maintainability and test coverage ?

## Questions

The questions we aim to answer are :

* Can developpers using TDD methods really claim a better quality of code ?

By “quality”, we mean code smells, code duplication, cyclomatic complexity and number of bugs.

* Do TDD projects really have a higher test coverage ?

## Tooling

### SonarQube[^1]

We will use SonarQube, a tool to analyse projects and to find metrics such as **code smell**, **cyclomatic complexity** or duplicated lines of code. This tool can also show the code coverage but we don't know yet how to use this functionality.

Here is a preview of an analysis of the TDD project Fitness made by SonarQube.![](/assets/sonar.png)

We can see here a detailed preview of the analysis of the project Fitnesse with the number of code smells in particular.![](/assets/sonar2.png)

### SoftVis3D[^2]

SoftVis3D is a tool which allow to display a project in the shape of a 3D city map. Each building represents a file and each district a package. One of the strong points of this tool is that it exists as a SonarQube plugin and so is really easy to use. Moreover it is possible to choose which metrics to use to modelize the base of a building, its height and its color.

The following pictures represents an analysis of the Fitnesse project with SoftVis3D. Here, the base of a building is the cyclomatic complexity and the height is the number of lines of code.

In the first picture with orange buildings, the color is not linked to any metrics.

![](/assets/sonarcity.png)

But in this second picture the color varies according the number of code smells. This picture shows also another feature of SoftVis3D, the city is represented with streets \(which are the packages\) forming districts.![](/assets/sonarstreet.png)

### **Code Maat **

Code-Maat inspects commit logs from nearly any version control system to generate data, such as code age, number of revisions for each files, code ownership and so on. It can be interesting to compare theses metrics for test-driven and test last projects to see for which development strategy files are the most frequently modified. With the code age we can check if files keep being maintained over time, or reach a definitive state at some point of the project. We can also measure when this happens in average. The analysis can be parameterized. We can set a minimal number of revisions to reach to consider a file, we can specify a regular expression the commit message must match. This last feature will be exploited to make statistics on commits containing key-words like “fix”, “feature” or so, and understand the impacts of TDD.

## Issues

A difficult task we had to face was to find a framework generating test report that Sonar was able to use \(Surefire for example\). This kind of framework is language specific. Analyzing those reports allows Sonar to estimate the test-coverage of a project.

To analyze a project with SonarQube, one needs to collect a few parameters on the project, parameters often directly linked to the way the project was thinked and built. For example, for each project, the structure may differ, and one needs to search for files to include or exclude or where to find test reports. It is necessary to study the projects and their structure to generate a valid analysis result, which may be a difficult task in projects with thousands of lines and different technologies.

