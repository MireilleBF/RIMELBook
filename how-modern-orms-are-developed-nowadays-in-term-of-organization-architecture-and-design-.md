# **How modern ORMs are developed nowadays, in term of organization, Architecture and Design ?**

Object-relational mapping \(ORM\) is a mechanism that makes it possible to address, access and manipulate objects without having to consider how those objects relate to their data sources. it abstracts away the actual details, ORM lets programmers maintain a consistent view of objects over time, even as the sources that deliver them, the sinks that receive them and the applications that access them change.

ORMs can even take care of important aspects of the database access such as caching strategies and connection management \(pooling …\), which can have quite an effect on the overall performance of the application, so we thought it would be interesting to examine hibernate and entitymanager, from different angles : organisation which is more related to contribution and Architecture/Design which is more technical, in both parts we’ll try to extract some interesting metrics/informations

Through this question we want to take a closer look at ORMs, Hibernate and Entity Framework, the purpose of this study is not to find out which ORM is better, but rather the difference between the way the two projects are conducted \(version control, commits, branching strategies …\) and the effect it has on the final products.

**Team :**

* Buisson Kevin

* Dahmoul Salah

* El Amrani Achraf

* Tijani Yassine




