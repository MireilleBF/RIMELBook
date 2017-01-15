# Background on tools : **How are modern ORMs developed nowadays, in term of Organization, Architecture and Design ?**

## code maat / codescene.io

we started using codescene which gave us the first insight about the lead developer about the whole framework as this diagram shows us the interactions between the developers :



![](/assets/lead.png)

we can clearly identify that Steve Ebersol is the lead of the hibernate project, but let's see if its still the same from a feature point of view, for example the dialect feature is mainly developed through the hibernate-core module, and precisely through its dialect package, here's a visualization of the knowledge and code owner :



![](/assets/ownership.png)



this confirms what we saw on a higher-level through communications between developers, it seems a bit normal, since handling dialects is a core feature hence the delegation to the most experienced developer\(s\).



