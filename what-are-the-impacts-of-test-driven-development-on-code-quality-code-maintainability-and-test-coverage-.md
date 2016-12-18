# What are the impacts of Test-Driven Development on code quality, code maintainability and test coverage ?

The Test-Driven Development \(TDD\) is a method of software development relying on writing tests before the tested code even exists. More precisely, there are five different steps. First writing the unit test, then run the test to watch it fail. If the test succeeds, there is a problem since the tested code is not yet written. When the test is written and fails, the next step is to write just enough code to see the test succeed. Then, when the new test succeeds, the fourth step is to check that all the tests still pass. If there are some failures, it is necessary to fix the issues to have all the tests passing. Then the final step is to refactor the code in order to make it better. The

The purpose of this method is to write the specifications first in the form of unit tests so the written code answers exactly to the wanted functionalities. More than that, it wants to assert that the code is always valid and more stable. It should also help the developer to avoid regression when refactoring the code.![](https://upload.wikimedia.org/wikipedia/commons/thumb/0/0b/TDD_Global_Lifecycle.png/1024px-TDD_Global_Lifecycle.png)



