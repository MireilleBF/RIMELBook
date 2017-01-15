# Background on tools : What are the impacts of Test-Driven Development on code quality, code maintainability and test coverage ?

## Questions

The questions we aim to answer are :

* Can developpers using TDD methods really claim a better quality of code ?

By “quality”, we mean code smells, code duplication, cyclomatic complexity and number of bugs.

* Do TDD projects really have a higher test coverage ?

## Tooling

### SonarQube[^1]

We will use SonarQube, a tool to analyse projects and to find metrics such as code smell, cyclomatic complexity or duplicated lines of code. This tool can also show the code coverage but we don't know yet how to use this functionality.

Here is a preview of an analysis of the TDD project Fitness made by SonarQube.![](/assets/sonar.png)

We can see here a detailed preview of the analysis of the project Fitnesse with the number of code smells in particular.![](/assets/sonar2.png)

### SoftVis3D[^2]

SoftVis3D is a tool which allow to display a project in the shape of a 3D city map. Each building represents a file and each district a package. One of the strong points of this tool is that it exists as a SonarQube plugin and so is really easy to use. Moreover it is possible to choose which metrics to use to modelize the base of a building, its height and its color.

The following pictures represents an analysis of the Fitnesse project with SoftVis3D. Here, the base of a building is the cyclomatic complexity and the height is the number of lines of code.

In the first picture with orange buildings, the color is not linked to any metrics.

![](/assets/sonarcity.png)

But in this second picture the color varies according the number of code smells. This picture shows also another feature of SoftVis3D, the city is represented with streets \(which are the packages\) forming districts.![](/assets/sonarstreet.png)

## Problems faced







[^1]: [https://sonarqube.com](https://sonarqube.com)

[^2]: [http://softvis3d.com](http://softvis3d.com)

