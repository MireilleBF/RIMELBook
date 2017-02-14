# What are the impacts of Test-Driven Development on code quality, code maintainability and test coverage ?

## Authors

We are four students in last year of Polytech' Nice-Sophia specialized in Software Architecture :

* Alexandre Cazala &lt;alexandre.cazala@gmail.com&gt;
* Nicolas Lecourtois &lt;lecourtoisn@gmail.com&gt;
* Lisa Joanno &lt;lisa.joanno@gmail.com&gt;
* Pierre Massanès &lt;pierre.massanes@gmail.com&gt;

## Introduction

This document presents the results of our researches on the Test-Driven Development method. In order to concretly present them, we present in a first section the context of our research. In the second section, we deep into the description of our study and on which project it is based.

### Research context

The **Test-Driven Development** \(TDD\) is a method of software development relying on **writing tests before the tested code** even exists and more importantly relying on refactoring code. More precisely, there are five different steps. First writing the unit test, then run the test to watch it fail. If the test succeeds, there is a problem since the tested code is not yet written. When the test is written and fails, the next step is to write just enough code to see the test succeed. Then, when the new test succeeds, the fourth step is to check that all the tests still pass. If there are some failures, it is necessary to fix the issues to have all the tests passing. Then the final step is to **refactor** the code in order to make it better. The Figure below illustrates the development process using the TDD method.![](https://upload.wikimedia.org/wikipedia/commons/thumb/0/0b/TDD_Global_Lifecycle.png/1024px-TDD_Global_Lifecycle.png)Figure 1 : TDD method process

The purpose of this method is to write the specifications first in the form of **unit tests** so the written code answers exactly to the wanted functionalities. More than that, it wants to assert that the code is always valid and more stable. It should also help the developer to avoid regression when refactoring the code.  
In this sub-chapter, we present our study of the impacts of the TDD method on code quality, code maintainability and test coverage. The study is splitted in three sub-questions:

1. Does TDD reduce the number of issues to fix during the development ?
2. Does TDD reduce the overall complexity of a project compared to the common Test Last \(TL\) method ?
3. Does TDD projects always have a high test coverage ?

Test-Driven Development promotes the fact of producing a code of better quality and always valid. This study aims to verify if this assertion is real or not and in which way. There is not yet an answer to this question which divides the developer community. We think that it could be interesting to compare this method to a more common way of developing, which is to develop functionalities first, then write the tests, to bring an answer to this question with concrete arguments. This common method is also known as the Test-Last \(TL\) method. Also, many companies does not approve this method thinking that testing first cost more than having something which works first. It would be interesting to see if it is true or not by comparing maintenance cost \(i.e, number of issues, fixes ...\) and productivity \(i.e, number of lines added and deleted\) in test-first method \(TDD\) with test-last method.

### Scope

In this study, we compare TDD projects and TL projects only. Any other development method is not part of this study, we made this choice in order to narrow our field of research. As our main question is about code quality, we don’t study the impacts of TDD on development time compared to TL. We have restricted our analyses to some metrics defining the code quality of a project and described in the partProject Evaluation. So external factors as team size, team experience or language used are not part of our scope. Even if these factors can have impacts on code quality and code coverage, we lacked time and resources to take them into account, they are part of the limits of this study.

Other concepts linked to the TDD method, like emerging software architecture, are not studied either, still in order to focus on answering our questions.

The projects studied here are either TDD or TL but how can we now the development method used in a project ? To choose the projects, we do not have an automated tool capable of detecting the development method used. We rely on the project team and the developer community. Developing following the test-driven method is not a common choice, so usually the project team clearly state that the project is test-driven. In addition to this, we also checked manually if the commits of the TDD projects seems to follow the pattern test first, then code. But this is just a partial verification, the best would be a tool analysing the commits and finding this pattern.

### Projects Studied

In order to find a concrete answer, we had to find many projects built using a TDD approach and of at least thousands of commits:

* [FitNesse](https://github.com/unclebob/fitnesse) is a project from Robert C. Martin, also known as Uncle Bob, who wrote many famous books about agile principles, code quality and best practices. It has more than 5000 commits.

* [JUnit](https://github.com/junit-team/junit4) was written by Kent Beck and Erich Gamma using TDD throughout. We study JUnit4 \(around 2,000 commits\).

* [JFreeChart](http://www.jfree.org/jfreechart/) is a 2D chart library for Java applications \(around 3,000 commits\).

* [OpenCover](https://github.com/OpenCover/opencover) is a code coverage tool for .NET \(around 1,200 commits\).

There are other projects using TDD but those are the most interesting for our works. We are limited in time by our studies.

We found the following TL projects which are approximately of the same size as the previous TDD projects.

* [Google Gson](https://github.com/google/gson) is a Java serialization/deserialization library that can convert Java Objects into JSON and back \(around 1,300 commits\)
* [JaCoCo](http://www.eclemma.org/jacoco/) is a Java code coverage library \(around 1,400 commits\)

* [Spoon](https://github.com/INRIA/spoon) is an open-source library to analyze, rewrite, transform, transpile Java source code \(around 1,800 commits\)

We compared TDD method projects with TL method projects based on:

* Cyclomatic complexity
* Many common code smells 
* Code coverage
* Issues
* Number of lines added per commit or per week
* Number of commits per week

### Expectations

As Test-Driven Development is really driven by the tests, we expect TDD projects to have a high code coverage, of at least 80% and higher than TL projects. This method involve an important refactoring phase, so cleaning the code is an important part of it. Because of this, we expect a better code quality but also more commits about refactoring and less about fixing or patching bugs.

## Project Evaluation

The previous section described our research context, our goal and the red string for our project. In this section we present how to evaluate those project samples \(i.e, in what and how we are evaluating those projects\).

### Metrics, a way to evaluate projects

In order to answer our three sub-questions we used many metrics. All of our TDD and Test-Last projects are evaluated using the same metrics to compare them.

#### Code age

The code age measures in month the last time a file has been modified. Because some of the projects are older than others, the real metric measured here is the average code age of each file relative to the project age. For example if a file hasn’t been modified for 10 months and the project is 12 month old, we can say it’s a pretty much stable file. If most of the project contains files that are currently being modified it means that the developers have a lot of file to maintain. In the opposite case, it means that the developers just have to focus on a few files which is a sign of good maintainability.

#### Code coverage

The code coverage measures how much of a project has been tested.

#### Cyclomatic complexity

The cyclomatic complexity measures the number of paths through a function. Ideally there should be at least as much unit test as the cyclomatic complexity which should be as little as possible.

#### Code smells

Code smells are issues detected in the source code that can lead to a deeper problem. For example, Duplicated code, long methods and large class are code smells. The more code smells spotted in the source code, the more likely the project to be difficult to maintain.

### Evaluation process

During our projects, we applied the same process on seven different projects. We used four test-driven development projects and three test-last projects, as described before. We chose those seven projects of their likeliness in terms of commits and lines of code.

TDD projects :

* FitNess : 5 401 commits, 21 236 lines of code \(LOC\)

* JUnit4 : 2 160 commits, 4 682 LOC

* jFreeChart : 3 405 commits, 54 713 LOC

* Open Cover : 1 196 commits, 11 518 LOC

Test-last projects :

* spoon : 1 709 commits, 18 305 LOC

* GSON : 1 320 commits, 4 318 LOC

* JaCoCo : 1 365 commits, 11 740 LOC

For each project, we tried to obtain the data about the metrics we defined in the first part of the report.

#### JaCoCo

The first thing we did was configuring the JaCoCo \(Java code coverage\) for each project.

JaCoCo is a free code coverage library for Java. The advantage of using JaCoCo was the uniformity of generated reports, and its compatibility with Maven and Gradle. All of our studied projects use either Maven or Gradle. We configured the plugin for each project.

```
<plugin>
   <groupId>org.jacoco</groupId>
   <artifactId>jacoco-maven-plugin</artifactId>
   <version>0.7.5.201505241946</version>
   <executions>
       <execution>
           <goals>
               <goal>prepare-agent</goal>
           </goals>
       </execution>
       <execution>
           <id>report</id>
           <phase>prepare-package</phase>
           <goals>
               <goal>report</goal>
           </goals>
           </execution>
   </executions>
</plugin>
```


### Articles

Beck, K. \(2003\).Test-driven development: by example. Addison-Wesley Professional.

Dave Astels. \(2003\).Test Driven Development: A Practical Guide. Prentice Hall Professional Technical Reference.

M. Pancur, M. Ciglaric. \(2011\).Impact of test-driven development on productivity, code and tests: A controlled experiment. In Information and Software Technology 53 \(pp. 557–573\)

Bhat, T., & Nagappan, N. \(2006, September\). Evaluating the efficacy of test-driven development: industrial case studies. InProceedings of the 2006 ACM/IEEE international symposium on Empirical software engineering\(pp. 356-363\). ACM.

Martin, R. C. \(2008\).Clean Code: A Handbook of Agile Software Craftsmanship. Pearson Education.

Kaufmann R. & Janzen D. \(2003, October\). Implications of test-driven development: a pilot study. In Companion of the 18th annual ACM SIGPLAN conference on Object-oriented programming, systems, languages, and applications \(pp. 298-299\). ACM.

### Contributors

Our Team is splited in two groups. The first one composed by Alexandre Cazala and Lisa Joanno studied TDD projects and the second one composed by Nicolas Lecourtois and Pierre Massanès studied Test-Last projects.

