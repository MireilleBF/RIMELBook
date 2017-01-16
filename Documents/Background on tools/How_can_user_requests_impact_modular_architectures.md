## Analysis

_**Subject:**_

After a few weeks of studies, we think about reducing the scope of this part, because there are too little documentation on it. We will focus on how the community drive the development.

_@mbf : je n'arrive pas à comprendre où vous prenez en compte la communauté \(c'est peut etre que communauté c'est pour vous les développeurs?\) ? Vous pensez vraiment qu'il y a bcp de différences entre author and commiter? Pas d'utilisations des issues? dans le temps? par exemple pour voir s'il y a une correlation entre le nombre d'issues et de commit? _

_**Methodology:**_

We run through 3 phases to analyse data from the Terasology repository \(for instance\).  
The first phase is to extract data : to do this, we use an homemade script and we extract :

* The commit hash
* The author name
* The author email
* The author date
* The committer name
* The committer email
* The committer date
* The subject 

The second phase is to transform data using Logstash to convert the CSV, product by the fisrt step and produce a JSON file. We then use this JSON to populate an Elasticsearch.

The third and last step is to exploit these data, and produce charts, stats, dashboards, ... and reason on it.

_**First results:**_

We were able to extract,  display the files per commits over the last two years. We can measure that over 1300 modifications was made between November 30th and the December 6th.

![](/assets/screen_kibana.png)

_**Major difficulties:**_

We encountered major difficulties in term of documentation. We didn't find anything on the subject.

Therefore, searching tools has also be a pain because there are too few researches about it.

_**Tools used:**_

We first thouugh of using Diggit but we realized that this tools wasn't fullfilling our needs : we don't know Ruby, and the possibilities are too limitied for our purpose. So we use homemade scripts and the ELK stack where we mainly use Elasticsearch  and Kibana.

* Github API
* Scripts
* ELK



