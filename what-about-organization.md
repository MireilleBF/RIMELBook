# What about Organization ?

In this chapter we’ll be interested in the organizational differences between the two ORMs, to do so, we’ll examine the implementation of two features of our choosing: Caching, and dialects, the reason behind this choice is the fact the we find them interesting and also to make this study a bit more specific, given that ORMs cover a big variety of functionalities,

To do so, We will try to answer the following questions :

## General organization of hibernate and Entity Framework core

First of all we'll present the two communities working on the projects, Hibernate is an open source framework led by a core team that works on Red hat, the following picture shows the interactions between developpers on the hibernate project :

![](/assets/lead.png)

As we can see from the highlighted paths, there's one project lead on hibernate, and two big contributors, this gives to the project a clear direction, as the vision is not shared across severals, but on the other hand if the lead \(i.e Steve Ebersole in our case.\) leaves the project, there will  a knowledge loss \(uless there's a transition period\).

on the Entity Framework side, things are a bit different, the framework is a part of .NET core stack \(newly open sourced\) which is maintained by Microsoft, the following picture shows the interactions between developpers on the project :

![](/assets/leadEntity.png)

Here we can see that there's no established lead on entity framework as the half on the right is made of leads, in this case we have a knowledge sharing, but different visions as each one of them may have a different point of vue about where the product is heading.

## Organization around dialects and caching on hibernate and Entity Framework core

when doing feature driven comparison, it might be interesting to look closely to the team organization around the targeted features, as sometimes it may give you insights about feature importance to the team, stability and maintenance.



### Dialect organization on Hibernate

![](/assets/ownership.png)

we can see that Hibernate support variety of SQL dialects, also, we can see that color circles tend to be steve ebersole's one, which is normal since dialects are a core feature developed from the first day, managing them is critical, so it's normal the lead as an owner of this feature

### Dialect organization on Entity Framework

![](/assets/dialect_entityFramework.png)

in contrast with hibernate, we can see that \(like the general team organization\) ownership of the dialect feature is dispatched through the team, which may slow the developpement since it will increase interactions and coupling between developpements.



### Caching organization on Hibernate

![](/assets/cache_feature_h.png)

here we have the general cache structure package, which owned again by hibernate's lead, we can assume that this behaviour may be a pattern that is reproduced on all features.

### Caching organization on Entity Framework

![](/assets/cache_feature_en.png)

On Entity side, we can see also repartition between the leads, which leads to the same conclusion on hibernate.



## Conclusion





