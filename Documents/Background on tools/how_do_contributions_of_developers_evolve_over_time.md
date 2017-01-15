# **How do contributions of developers evolve over time?**

---

We want to know if the developers's works in a open source project follow the same way, every developer start by write documentations or tests before fix bugs or they have all a behavior very different in their contributions activities.

We use the simple command "git log" with a custom respons format for obtain the follow informations \(`git log --pretty="%an:$:%ad:$:%s" --date=short`\) : for every commit, the author, the date and the message associate. These data are put in text file, read by a Python program to inject these in Elastic base. After that we use Kibana to make query and visualisations. With the capabilities of Kibana and Elastic to search into a string, we hope find enough informations for define developer behavior in open source projects.

### The first results :

We have define a data format to give to the Git command "log". With that we have every informations about commits of ElasticSearch project. We stocked them into text file and maked Python program for inject all of it into Elastic base. We made a first set of visualisations that can provide some informations that we already see in Github for example but it was especially for test tools. We can see the number of commits on the time, the number of commits for each developers and when he make them.

### Difficulties encountered :

To use ElasticSearch and Kibana we used Docker image with them but it was not trivial to keep injected data and visualisations that we made with Kibana. The worst difficulty will start when we will inspect commits's messages because developers write them in differents ways and it can be complicated to obtain some useful informations considering the huge quantity of data.

