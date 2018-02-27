
---

# Machine Learning algorithms libraries

## Is it possible to automatically detect the location of algorithm families in a machine learning project ? {#docs-internal-guid-a600e294-d88e-72f7-9e75-2aa43b92bb25}

## Authors {#docs-internal-guid-2ccf0085-d88e-9c64-5151-0e0d88c5ac35}

The code of the the scripts are available on Github by following this link : [https://github.com/earendil06/Rimel-team-ML.git](https://github.com/earendil06/Rimel-team-ML.git)

* FUSCO Anthony &lt;[anthony.fusco42@gmail.com](mailto:anthony.fusco42@gmail.com)&gt;

* BELHASSEN Issam &lt;[issambelhassen4@gmail.com](mailto:issambelhassen4@gmail.com)&gt;

* PASTOR Florent &lt;[flopastor06@gmail.com](mailto:flopastor06@gmail.com)&gt;

* LEFEBVRE Jeremy &lt;[lefebvre.jeremyp@gmail.com](mailto:lefebvre.jeremyp@gmail.com)&gt;

## I. Introduction {#docs-internal-guid-dafa870e-d890-ce14-9ccb-c01eaed7a9ca}

As part of the RIMEL module, our group realized this study which is interested in machines learning. Firstly, we will present our research context, then our general question, then our hypothesis and the experiences that we made, finally we conclude.

## II. Research context {#docs-internal-guid-ab546d41-d891-03dd-3c8b-3178318695d6}

Machine learning is the principle of using big volumes of data to train machines to perform certain tasks like image recognition.

It is possible to categorized machine learning tasks by looking at the desired output, we will call them “algorithm families” and focus on those 4 families:

* Regression

  * The output is continuous

* Clusterers

  * The output is multiple data groups not know beforehand

* Classifiers

  * The output is multiple data groups that was know beforehand

* Classifiers-regression

  * Some algorithm can be used for multiple purposes

## III. General question {#docs-internal-guid-ab546d41-d892-2be3-7763-7fd77f47fad4}

We are trying to understand the mechanism of machine learning without having to look directly at the code or the mathematics behind.

We won’t look into the details of the algorithms but we will look at the way they are structured. We will look at the general structure of a machine learning project and specify the scope until we can detect the algorithm families and find specificities to those families or to the project in general.

We would like to know if** it’s possible to automatically detect the location of algorithm families in a machine learning project ?**

We are going to study two open source machine learning libraries, the Weka project and Scikit-learn.

The Weka project is written in java and is seemingly well structured. The structure of Scikit-learn is less obvious.

## IV. Hypothesis & Experiences

Our hypothesis is that we can map the structure of the Weka project to Scikit-learn using multiple dimensions:

* Correlating the names of the files/file structure.

  * The names of machine learning algorithm is recurrent.

  * The file location of machine learning algorithm is recurrent.

* Correlating some functional metrics like the overall complexity of the algorithms between the two projects.

  * The algorithms of the same family uses the same data in input and output.

  * The Complexity of a machine learning algorithm is always similar.

* Correlating the authorship models of the algorithms of the two projects.

  * The authors of machine learning algorithms are specialized in one family and only commit on that family.

We hope that the results of those three metrics will comfort the fact that the algorithm we find are indeed the right mapping between Weka and Scikit.

### 1- Correlating the names of the files/file structure

#### a\) naming \(files, variables, functions\)

We chose some of the main algorithm of machine learning inside the 4 families that we have defined:

* Linear regression

* Logistic regression

* Decision tree

* Naive bayes

* K-means

* Random forest

By looking in both projects using those algorithm names, we have been able to find some files and packages for each of them

Given that Weka is written in Java and that it has a naming convention \(class name = file name\), there is no need to look inside the files.

In contrary for the project Scikit-learn written in Python, there is no naming convention of that sort. We had to look for algorithm inside of the files.

We wrote two Python scripts available on Github:

* **retrieve\_init\_scikit.py**

  * Allow to read the Python files named \_\_init\_\_.py of Scikit and retrieve all the algorithms declared in those files. Indeed we have noticed that Scikit centralise the export of their algorithm in those files.
  * Running this script creates a file results.txt with all the algorithms exported from Scikit.

* **match\_weka\_scikit.py**

  * Which allow to match the algorithms names of Sikit with those of Weka. It contains a list of algorithms names and uses the results found in Weka to search for the equivalent in Scikit.

  * Example for the algorithm Linear Regression:

    1. We look for the files that matches the glob “\*linear\*regression\*.java” in Weka.

    2. For each file found, we get its the name of the Java file.

       * LinearRegression.java

       * SimpleLinearRegression.java

    3. For each file we construct a regular expression for Python and we search it starting by the file names of the projects and then with the algorithm names contained in “results.txt” made before.

|  | Weka | Scikit extern | Scikit intern |
| :--- | :--- | :--- | :--- |
| Linear Regression | 2 | 0 | 1 |
| Logistic Regression | 3 | 1 | 4 |
| Decision Tree | 19 | 2 | 5 |
| Naive Bayes | 6 | 1 | 1 |
| K-Means | 2 | 0 | 0 |
| Random Forest | 1 | 0 | 2 |

Table 1 :Résults of match\_weka\_scikit.py

From those results, we can see that many algorithms have been found in Weka using simple algorithms names. This shows that this machine learning library seems complete and can be used as a reference for the research in Scikit.![](https://lh6.googleusercontent.com/20yJm7LRS1HaDKVIZGEyCYDP_PIfIrB_gvnqy_f2AQeGm6vS9Bnyf1ZEaBBKH1mnI072WAgkQOy9XZFducQ7yrjfgFjyo5AeNwbRuN28a3hCRLrvo-YthDAoCJ1WaCsbBkp9C9kc)Figure 1 : Number of algorithms found on Weka and Scikit extern

From the algorithms found in Weka, we started by making a research in Scikit by only looking at the files and packages names.

We noticed that the number of algorithm found was very low, null in some cases.

It seems that the Scikit developers didn’t have a naming and structural convention. We then have to look inside the files to see if we can get more results or if their is really no correspondence with the algorithms of Weka.

![](https://lh3.googleusercontent.com/8wVUnwy6EGyFrmp5gAK_O6Dy7haIpw83KU7XD3oUAlvwmS1Qf9csUyZdQQNHwPklXyHtyTVH9x--MY2HhaKFzRkeOEReUPNZszekrPrbJbmXsUoIQo8jO51VidRb_RPNfIU2aDL0)

Figure 2 : Number of algorithms found on Weka and Scikit intern

We looked inside the files and this graph shows the results.

It seems that we have a lot more results by taking a look inside the files.

The graph below shows the difference of results for the two strategies of research in Scikit. We found more results for each algorithms by looking inside the files.

We noticed that many results are close between Scikit and Weka.

![](https://lh4.googleusercontent.com/EA_O_JlLHNLZ7vnCCs1YdQzd5vF5AwnWu43B9pCaUpulRlX_TIOO42OEiLHIz6LCgtaGDhzcyHTljxcMeRt1vIagYOmVqNzDTrQeK-QnN7CEN6d4NU-aXBUmexFxMoWAGHhOzzNK)Figure 3 : Number of algorithms by comparing Scikit extern and intern

We can see that with the exception of K-Means, the results are good for the file research. Most of the Weka algorithms has been found in Scikit. The exception of K-Mean might mean that it has not been implemented in Scikit…

We can, with these results, confirm that the algorithm names are recurrents from one project to another.

### 2- Correlating functional metrics

#### a\) Test study

For the functional point of view, our hypothesis is that the algorithms of the same families support the same data in inputs and outputs \(pre-conditions / post-conditions\).

To answer this hypothesis we must delve into the tests, seeking to find a correlation of steps before each test launch.

Once we found families of algorithms in the best structured project Weka, we look at the other project Scikit to see if there is an identical correlation too.

We made a script that allows for grep searches on family names in tests.

We could find results in weka, for each algorithm test, we call a default constructor that initializes an instance of this algorithm by inheriting the family that belongs to it.

![](https://lh5.googleusercontent.com/054PtnOpqnU7o2_tD4fV-ASH7fgxZLsS6Sflmk68JgSmP7EGq4SCGulNd40Hx_1JmuwqA2PhADCTA3PeVRxlG01wN_3dw4R-Wjia98zF9Z0n5y75BU8rB2B57-aass3lzcSD5VlH)

![](https://lh6.googleusercontent.com/o9Ohz_44mf_K15wDe0ZqXKabBdOKZkpU-kUXoB_JflmmXQEYy2c5JR4EYnWST7FJt5VTgrNpWQAckgyThDqIXbxK_e5pFA-GG2lBs-HGlPuQ66q48QJndu0YBiAewoThksiFvTYo)

Figure 4 : Results of algorithms dependences

We tried the same steps for the scikit project but we could not find any important results.

#### b\) Study of code metrics

Our second hypothesis for the functional part is that the algorithms of the same families have a bijection of complexity, in another way there is an almost constant difference of their cyclomatic complexity and cognitive complexity.

To answer this hypothesis, we will analyze the complexities of different algorithms and compare their results between the two projects weka and scikit.

For the analysis of the complexity we have used Sonarqube which is is a tool which centralizes a whole range of measures of quality of code in a single web site.

the complexity term definition according to sonarQube is :

* Complexity: How simple or complicated the control flow of the application is.

* Cyclomatic Complexity measures the minimum number of test cases required for full test coverage.

* Cognitive Complexity is a measure of how difficult the application is to understand.

The first step was to launch a complete analysis of the two projects weka et sckit learn, Here is the result of sonar analysis which shows the set of measurements, we are interested in the complexity

![](https://lh4.googleusercontent.com/E3xXACqlFntQ_iX8XmGKiQgjPVqKZ_poTenXpC7D8RV_e-ntRJxfrxiWkxLfe5Wn-9IZs-8QMsNZRrqp36G6DkMxteSyx5OfTx4WPHqnyjJUknaGkaufx_GNHWWNbJtAhex9fpP4) ![](https://lh4.googleusercontent.com/Taofvr6TMF8WgDD7uUGQ0gzFs8no06euUedXosbfBue5ttKBkHQ5d1LKgKsfUgqigUavKNL8kOlv_StJwRew59RuNRrIjlIkCGwTpoD-Leh9tfHgt8E0ECbaPYvtKtQ9bvyQ-TSr)

Figure 5 & 6 : SonarQube analysis for Weka\(5\) and Scikit\(6\)

To extract the complexity value of each algorithm we did a search by their names.

Here are the raw results we obtained after analysing the projects.

* Comparaison Cyclomatic Complexity

|  | Cyclomatic Complexity weka | Cyclomatic Complexity scikit |
| :--- | :--- | :--- |
| Naive Bayes | 844 | 66 |
| Decision Tree | 141 | 0 |
| Random Forest | 227 | 56 |
| Linear Regression | 133 | 0 |
| Logistic Regression | 120 | 30 |

Table 2 : table of comparison cyclomatic complexity weka vs Scikit

![](https://lh6.googleusercontent.com/pXEqdYh72Wibf1JqM68wC2HtsniDXehFx_1SqEFMw8zO1_wD3umsToDkQ_8uaO4fIqY_yqbGr5-uZXZfMoWC5Avy6344q2qL25XBDlU-d3nOkeYtBiVfAlm4mZ-rl0Kb0qLoSzkI)

Figure 7 : Courbes of cyclomatic complexity weka vs scikit

Looking at the two cyclomatic complexity curves of the weka and scikit project algorithms, we notice that there is always a kind of correlation for each common algorithm, with a well-defined gap.

* Comparaison Cognitive Complexity

|  | Cognitive Complexity weka | Cognitive Complexity |
| :--- | :--- | :--- |
| Naive Bayes | 1837 | 0 |
| Decision Tree | 232 | 0 |
| Random Forest | 373 | 0 |
| Linear Regression | 0 | 0 |
| Logisitic Regression | 0 | 0 |

Table 3 : table of comparison congnitive complexity weka vs scikit

![](https://lh4.googleusercontent.com/2prsbJAezw9y3RwEsyH_UBnrK4jHe3136EtnaV7cREhkLrXHiTsUhze9bysnppzrEbWqCYRYXBjj5YwXiKG0reFqY6_TPGW6ifrqpSI8_Py1N5HT9St59IQZWwbdHdsdyCRC50Oy)

Figure 8 : Courbes of cognitive complexity weka vs scikit

For cognitive complexity, we can not notice a correlation between the two curves, this is due to language difference between weka which is developed in java and scikit which is developed in python. The latter has a clear syntax and uses a simpler approach what allows a facility of understanding.

### 3- Correlating the authorship models of the algorithms of the two projects

In this section, our aim will be to find some “big” contributors in order to know how the knowledge is spread among contributors. So that we could assume that some people might be specialised or not, the knowledge might be too dilute to find any specialised one. Then we want to find contributors that are “specialised” in a certain field, by contributing in their own area of knowledge from those who contributed in multiple domain which would help us to isolate some specific knowledge so called “families”.

#### a\) Using CVS

We first take a look to the respectives CVS of Weka \(which is SVN\) and Scikit \(which is git\) in order to collect informations like the total number of contributors, how many commit each contributors have done etc…

Here are what we obtain using SVNStats on the Weka’svn :

![](https://lh6.googleusercontent.com/_IT0CC3i4wJJV09hjN7qdK9Vohbhy0RLR2GnuxOJ0juwarvHBtUBOgp9jaW_vUI1a728dgdl9aIIX9QKoABsnjtEN-eA9hI1aWHmZfce8dizekzt3jo_n0MW7VMFvkAFrGofM_b6)

Figure 9 : Number of LOC by contributors

As we can see, there are only 4 contributors to the official SVN for all lines of code. After a few research we find out that all those four peoples are teacher or researcher at the waikato University. We assumes that they were using some kind of centralized organisation to add new modules to the weka’s library. Indeed, after few investigations all contributions \(those made by wakaito’s people or anyone around the world\) must be reviewed by a weka’s admin before being integrated to the whole project. At this point we knew that the SVN can’t provide us temporal informations about authorship.

Let’s take a look at the Scikit’s git, and the distribution of commit among all contributors:

![](https://lh5.googleusercontent.com/HVGmPT33bU7eLw4jEIvD3D42rCXvjYXcUQa3MMQd-k94--d0oGWXztbhlLAGWWfqf9cMwXJ05OOnMHAqHt5U4aXZQkY46H_T8IUABBqLA2f9nVz6WiQM7TL5QvCjPGgvVHnXGjES)

Figure 10 : Commits repartition among all contributors of scikit

We found a total of 1159 contributors splitted like above. We can observe 3 distincts parts : the first one \(dark blue\) represents the proportion of contributors with less than 200 commits, the second one \(green\) represents contributors who have more than 200 commits and less than 1000 commits, and finally the third part represent the part of commit of the 5 biggest project’s contributors. We can assume that the knowledge isn’t heavily spread because 17 peoples \(green + big fives\) have done ⅔ of all the commits. From here, we make the hypothesis that it will be easier to find specialised people among the people in the dark blue part because we assume that the fewer commits are made by a contributor the more precise and specialised they are.

Next we want to observe files that were modified by the least authors possible in order to find a relation between the contributors who did few commits and files with few authors to restrain our area of research.

![](https://lh3.googleusercontent.com/ccAm9PHp4QRoJ5nmmC7lTGlPaV6UwaDbwHy6af4Hu0zqne5rOjxjfQRWCfWDFiQYxh3awEEN_mKX7zoPLUqOeh4l0lRURvg8xGZ2P5D07KzrIlF81Sk7-pHJUvq6XwpeyxjJYHzM)Figure 11 : Number of authors for each file in scikit

Here we can observe that more than ⅔ of files have been modified by less than 4 authors. It could be because some files are too domain-specific for being modified by non-specialised people.

Both VCS give us differents informations but never the same one, this implies that it can’t be automated and we have to observe, understand and make hypothesis among informations that we grab from different library VCS.

So our next question is : Can we find people that contribute only to a specific area of the project in order to group their own files into packages that we would like to call families ?

#### b\) Take a deep look into files

Here we want to drill a bit deeper into the structures and take a look to the files content. But each library have too many files to check by hand. We thought that in such big project, we could find some patterns concerning authorship of files within the comment or in a dedicated index. Indeed, we find out after reviewing some files that a comment section indicated the author with a tag “@author”.

Then, we wanted to collect all those authors names in a single file in order to do some observations. More than that we would like to collect all authors at a given height of the directory structures so we can compare authors between directories and packages. We scripted the following process : From each leaf of the project structures, find in files the line marked as “author” and collect it in a dedicated file “AllAuthor.txt”, then go back up. Copy all authors from the bottom “AllAuthors.txt” into your “AllAuthor.txt” then repeat last step.

Here are our results :

![](https://lh6.googleusercontent.com/91x3OQn76fDDPthpjPkX-VzPh6Y9rol95o3EqESfVTFpEY1ep9uG9nJrC5RHa26GoWFjOfPZ4IkQ9V8lCKnj1SaUYf7_7Pk2P229NKddXiAblBfiETk4zF26SRd6KtcHYj-rty-r)Figure 12 : Repartition of specialized authors among all authors found

Our script find out 42 different authors in Weka and 45 differents authors in Scikit. All of those authors contributed to more than one package, so there are no “specialist”.

More than that, authors that we retrieve the most occurrences from Weka were FracPete, Mark Hall and Eibe which are parts of project’s admin. From Scikit, the authors with the most occurrences are Varoquaux, Mueller and Grisel which are parts of the “big five” contributors.

Those results are quite lower than we expected. We thought, that we could find hundreds of different authors drilling those large project with at least some specialized people.

However, multiples facts can explain those results.

First, we are collecting only authors that created the file and fill the field “author”, this means that we are looking only people who created files regardless of people who modify it over time. Second, there are no conventions about multiple authors contributions, that’s where our parser reach its limit, we only collect the first author and lose multiple lines mentions. Third, our approach is static due to the different CVS informations so we knew that those scripted operations would bring us partial informations.

Even so, we found that almost 5% of authors misspelled their own name or mail addresses, that means they were writing those informations each time they created files and among the most recurrent names we met the major part of “Big contributors” mentioned earlier. That statement show that they created a lot of files among the project that means they are those who are the most impacting on the project’s structure so by concentring the greater part of the knowledge and orienting the project’s structure they prevent the project to go wrong.

It is impossible to status with our results if we can or cannot retrieve specialized structural informations about code, looking at the autorship of the two libraries because statical informations are partial and non-directly comparable informations from CVS make the dynamical approach hard. We think a deeper look to each commit manually could come complete our informations about code ownership over time and may see arise some specialized people.

## V. Conclusion {#docs-internal-guid-ab546d41-d8e5-5ad4-38c6-42e3fae36099}

In this study we wanted to find a way to automate the process of discovering machine learning algorithm families.

To do so, our first step was to spot a bijection between our two libraries otherwise, we wouldn’t have any kind of comparable informations.

This bijection exists, algorithms names told us that both libraries shared some identical algorithms. The cyclomatic complexity show that complexity peak are depending on which family those algorithms belong and same curves behavior were observed over the two libraries. More than that we observed that both libraries contains families that we found over internet but K-means, algorithms of this family only appear in weka. Which had reduced our field of research.

Once we found a bijection, we wanted to automatically arise a project’s structure using names convention, complexity of algorithms and specialised authorship of files. Names convention were collected at different levels from each libraries which implies that our tools were tailor-made for a certain kind of files/project’s structure so as the authorship study. That last study bring us some project’s organisational informations such as project’s admin, repartition of knowledge, profession of main authors, but despite the fact that the major part of contributors or researcher or machine learning scientists none of them restrain themselves to a single family from a static point of view.

To conclude, it seems very difficult to automate the process of finding machines learning algorithms families due to the countless way to lead this kind of project or convention that organisation decide to apply to it. Yet, this study shows that we can retrieve major parts of families in a non-structured project by hand research or tailor-made scripting if we have a well structured project as reference, if the reference is big-enough to contains a wide spectrum of domain-specific knowledge.

## VI. Tools {#docs-internal-guid-b1b174c1-d8e5-8c09-50a0-cbae80bde47f}

* SonarQube

* Python scripts using linux commands “find” and “grep”

* Code-maat

* SvnStats

## VII. Articles {#docs-internal-guid-ab546d41-d8e5-b0ba-5f97-b862224267aa}

* Alain Abran, James W Moore, Pierre Bourque, Robert Dupuis, Leonard L Tripp. \(2004\). Guide to the software engineering body of knowledge: 2004 version SWEBOK \(chapter software Maintenance

* Andrew Meneely, Laurie Williams. 52009\). Conférence Proceedings of the 16th ACM conference on Computer and communications security. Conférence Proceedings of the 16th ACM conference on Computer and communications security. Secure Open Source Collaboration: An Empirical Study of Linus’ Law

* Mark Hall Eibe Frank, Geoffrey Holmes, Bernhard Pfahringer, Peter Reutemann, Ian H. Witten. \(2009\). The WEKA Data Mining Software: An Update.

* Lars Buitinck \(ILPS\), Gilles Louppe, Mathieu Blondel, Fabian Pedregosa \(INRIA Saclay - Ile de France\), Andreas Mueller, Olivier Grisel, Vlad Niculae, Peter Prettenhofer, Alexandre Gramfort \(INRIA Saclay - Ile de France, LTCI\), Jaques Grobler \(INRIA Saclay - Ile de France\), Robert Layton, Jake Vanderplas, Arnaud Joly, Brian Holt, Gaël Varoquaux \(INRIA Saclay - Ile de France\). \(2013\). API design for machine learning software: experiences from the scikit-learn project.

