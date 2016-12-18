# What are the impacts of Test-Driven Development on code quality, code maintainability and test coverage ?

## Introduction

To present our study, we need first to explain what is our research context. Then, in a second section we deep into the description of our study and on which project it will be based.

### Research context

The **Test-Driven Development** \(TDD\) is a method of software development relying on writing tests **before** the tested code even exists. More precisely, there are five different steps. First **writing** **the unit test**, then **run** the test to watch it fail. If the test succeeds, there is a problem since the tested code is not yet written. When the test is written and fails, the next step is to write just enough code to see the **test succeed**. Then, when the new test succeeds, the fourth step is to **check** that all the tests still pass. If there are some failures, it is necessary to fix the issues to have all the tests passing. Then the final step is to **refactor** the code in order to make it better. The Figure below illustrates the developpment process using the TDD method.![](https://upload.wikimedia.org/wikipedia/commons/thumb/0/0b/TDD_Global_Lifecycle.png/1024px-TDD_Global_Lifecycle.png)Figure 1 : TDD developement process

The purpose of this method is to write the specifications first in the form of unit tests so the written code answers exactly to the wanted functionalities. More than that, it wants to assert that the code is always valid and more stable. It should also help the developer to avoid regression when refactoring the code.



In this sub-chapter, we will study the impacts of the TDD on code quality, code maintainability and test coverage. The study will be splitted in three sub-questions :

1. Does TDD reduce the number of issues to fix during the development ?
2. Does TDD reduce the overall complexity of a project ?
3. Does TDD projects always have a high test coverage ?

Test-Driven Development promotes the fact of producing a code of better quality and always valid. This study aim to verify if this assertion is real or not and in which way. There is not yet an answer to this question which divides the developer community. We think that it could be interesting to compare this method to a more common way of developing, which is to develop functionalities first, then write the tests, to bring an answer to this question with concrete arguments. Also, many companies does not approve this method thinking that testing first cost more than having something which works first. It would be interesting to see if it is true or not by comparing maintenance cost \(i.e, number of issues, fixes ...\) and productivity \(i.e, number of lines added and deleted\) in test-first method \(TDD\) with test-last method.


### References

In order to find a concrete answer, we had to find first many projects built using a TDD approach and of thousands of commits :

* FitNesse[^1]is a project from Robert C. Martin, also known as Uncle Bob,  who wrote many famous books[^2] about agile principles, code quality and best practices. It has more than 5000 commits.

* Madagascar[^3] is an open-source software package for multidimensional data analysis and reproducible computational experiments. It has more than 13 000 commits.

* JUnit[^4] was written by Kent Beck and Erich Gamma using TDD throughout. We will study JUnit4 and JUnit5.

* 




[^1]: [https://github.com/unclebob/fitnesse](https://github.com/unclebob/fitnesse)

[^2]: [https://sites.google.com/site/unclebobconsultingllc/books](https://sites.google.com/site/unclebobconsultingllc/books "https://sites.google.com/site/unclebobconsultingllc/books")

[^3]: [https://github.com/ahay/src](https://github.com/ahay/src "https://github.com/ahay/src")

[^4]: [https://github.com/junit-team/junit5](https://github.com/junit-team/junit5 "https://github.com/junit-team/junit5")

