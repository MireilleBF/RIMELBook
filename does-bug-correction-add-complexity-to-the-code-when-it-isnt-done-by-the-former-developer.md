## Does bug correction add complexity to the code when it isn't done by the former developer?

### Problematic

_**Why?**_

This study is done to compare performances and qualities of debugging in different contexts.

Companies may use those results to know if they should always assign the coder that designed a feature to any debugging task related to this feature or if they can also safely attribute other coders or even newcomers to this task.

They may also be able to reproduce our methodology in their own environment in order to get their conclusions.

It could also help them to analyze the performances of their coders in order to deduct the tasks they can attribute them.

_**Criterias**_

The results of this study may tell if it’s a good idea to give debugging tasks to other coders or not and how it affects the code quality.

We may deduct patterns such as:

“Attributing debugging tasks to the same coder makes the debugging phase shorter but brings more complexity to the code”

“Attributing newcomers to debugging permits adding a new point of view to a feature and makes the code way easier to maintain / less complex even if it takes more time to debug this feature”

Or their total opposites.

Using our methodology, companies should also be able to deduct patterns for their own team, such as:

“ XXXXX generally debugs its own features very fast and even removes complexity from its code but when it comes to someone else's feature it is the total opposite”



### Project studied:

Several projects that have a large number of contributors on a long time period.

We will also be looking for projects that have a free access ticketing in order to have more precise data.

###  Methodology:

The way to do this is to first analysis the git of the project and check if debugs are marked with special annotations.

Access to a ticketing system may also help us to improve this study.

If it is the case we then need to compare the complexity of the corrected elements before and after the corrections were done.

Those comparisons will be done in three cases:

1. When the bug corrector is the one who formerly coded the feature.

2. When the bug corrector is a different person from the coder of the feature but has some experience on the project.

3. When the bug corrector is a newcomer in the project




The elements that we will be comparing includes:

1. Cyclomatic Complexity

2. Number of dependencies

3. Number of lines of code




### References used:

Hassan AE \(2009\)[Predicting faults using the complexity of code changes](https://www.researchgate.net/publication/221554415_Predicting_faults_using_the_complexity_of_code_changes). Proc. - Int. Conf. Softw. Eng. pp 78–88

Foucault M, Palyart M, Blanc X, Murphy GC, Falleri J-R \(2015\)[Impact of Developer Turnover on Quality in Open-source Software.](http://www.cs.ubc.ca/%7Empalyart/paper/2015_FSE_Impact_Turnover_Quality.pdf)Proc. 2015 10th Jt. Meet. Found. Softw. Eng. ACM, New York, NY, USA, pp 829–841

[A Unified Framework for the Comprehension of Software’s Time Dimension](https://papyrus.bib.umontreal.ca/xmlui/bitstream/handle/1866/11998/Benomar_Omar_2015_these.pdf?sequence=2&isAllowed=y)

### Tools used:

[Code Maat is a command line tool used to mine and analyze data from version-control systems \(VCS\).](https://github.com/adamtornhill/code-maat)

[The Evolution Radar](http://reveal.inf.usi.ch/web/dambros/tools/evoradar.php#)

[A ruby tool to analyze Git repositories](https://github.com/jrfaller/diggit)

