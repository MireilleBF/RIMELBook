# Background on tools : **How are modern ORMs developed nowadays, in term of Organization, Architecture and Design ?**

## code maat / codescene.io

we started using codescene which gave us the first insight about the lead developer about the whole framework as this diagram shows us the interactions between the developers :

![](/assets/lead.png)

we can clearly identify that Steve Ebersol is the lead of the hibernate project, but let's see if its still the same from a feature point of view, for example the dialect feature is mainly developed through the hibernate-core module, and precisely through its dialect package, here's a visualization of the knowledge and code owner :

![](/assets/ownership.png)

this confirms what we saw on a higher-level through communications between developers, it seems a bit normal, since handling dialects is a core feature hence the delegation to the most experienced developer\(s\).



now let's have a look to logical coupling inside the dialect package, with codescene.io \(which uses code Maat under the hood, and some extra features\) we can have nice view about the coupling  :



![](/assets/logicalcoupling-dialect.png)





this is part of the logical-coupling digram \(we used here a part, since the original one is quiet huge, and will only be used on the book\).

as we can see, the Oracledb 9 Dialect is coupled to the Oracledb 8 Dialect \(since its an update, it must inherit most of its behaviour\), the SchemaUpdate and SchemaValidator are coupled too, but the interesting information is that Schema validation/update is not coupled to the implementation of the Dialects \(which is, by the way, a good news.\)





