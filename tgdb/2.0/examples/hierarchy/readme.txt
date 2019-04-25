==================================================================
 TIBCO(R) Graph Database
 Copyright (c) 20016-2018 TIBCO Software Inc. All rights reserved.
------------------------------------------------------------------ 
 House of Bonaparte
==================================================================

This example demonstrates how to build a graph with the API
and perform search and queries on objects in the graph.
Refer to hierarchy.pdf for full graph description.

==================================================================
Instructions
------------------------------------------------------------------
Navigate to directory <tgdb_home>/bin
<tgdb_home> specifies the path for home directory

For Example,
On MacOSX /home/tibco/tgdb/1.1
On Windows C:/home/tibco/tgdb/1.1

==================================================================
For Windows
==================================================================

1) Initialize database:

tgdb -i -f -c ../examples/hierarchy/initdb.conf

2) Start database

tgdb -s -c ../examples/hierarchy/tgdb.conf

3) Compile all the java classes.

Make sure that you navigate to <tgdb_home>/bin in your terminal
window or command prompt before executing following steps.

For instance,

javac -cp ../lib/tgdb-client.jar ../examples/common/*.java ../examples/hierarchy/BuildGraph.java

javac -cp ../lib/tgdb-client.jar;../lib/tgdb-gremlin-mincore.jar ../examples/common/*.java ../examples/hierarchy/GremlinQueryGraph.java

To compile all the Java classes at once use following command

javac -cp ../lib/tgdb-client.jar;../lib/tgdb-gremlin-mincore.jar ../examples/common/*.java ../examples/hierarchy/*.java

4) Build graph

java -cp ../lib/tgdb-client.jar;../examples hierarchy.BuildGraph

5) Search graph

java -cp ../lib/tgdb-client.jar;../examples hierarchy.SearchGraph -memberName "Napoleon Bonaparte"

6) Query graph. Query for members born between the start and end years. For instance

java -cp ../lib/tgdb-client.jar;../examples hierarchy.QueryGraph -startyear 1900 -endyear 2000

7) Gremlin Query. Same as #6 but Gremlin-style query

java -cp ../lib/tgdb-client.jar;../lib/tgdb-gremlin-mincore.jar;../examples hierarchy.GremlinQueryGraph -startyear 1900 -endyear 2000

8) PageRank analysis. Requires NVIDIA CUDA's graph analytics package nvGraph. See Release Notes for config

java -cp ../lib/tgdb-client.jar;../lib/tgdb-gremlin-mincore.jar;../examples hierarchy.PageRankGraph

9) Update Graph. Update a given member of the house. For instance

java -cp ../lib/tgdb-client.jar;../examples hierarchy.UpdateGraph -memberName "Napoleon Bonaparte" -crownTitle "King of USA" -yearDied null -reignEnd "31 Jan 2016"

==================================================================
For MacOSX/Linux
==================================================================

1) Initialize database:

./tgdb -i -f -c ../examples/hierarchy/initdb.conf

2) Start database

./tgdb -s -c ../examples/hierarchy/tgdb.conf

3) Compile all the java classes.

Make sure that you navigate to <tgdb_home>/bin in your terminal window
or command prompt before executing following steps.

For instance,

javac -cp ../lib/tgdb-client.jar ../examples/common/*.java ../examples/hierarchy/BuildGraph.java

javac -cp ../lib/tgdb-client.jar:../lib/tgdb-gremlin-mincore.jar ../examples/common/*.java ../examples/hierarchy/GremlinQueryGraph.java

To compile all the Java classes at once use following command

javac -cp ../lib/tgdb-client.jar:../lib/tgdb-gremlin-mincore.jar ../examples/common/*.java ../examples/hierarchy/*.java

4) Build graph

java -cp ../lib/tgdb-client.jar:../examples hierarchy.BuildGraph

5) Search graph

java -cp ../lib/tgdb-client.jar:../examples hierarchy.SearchGraph -memberName "Napoleon Bonaparte"

6) Query graph. Query for members born between the start and end years. For instance

java -cp ../lib/tgdb-client.jar:../examples hierarchy.QueryGraph -startyear 1900 -endyear 2000

7) Gremlin Query. Same as #6 but Gremlin-style query

java -cp ../lib/tgdb-client.jar:../lib/tgdb-gremlin-mincore.jar:../examples hierarchy.GremlinQueryGraph -startyear 1900 -endyear 2000

8) PageRank analysis. Requires NVIDIA CUDA's graph analytics package nvGraph. See Release Notes for config

java -cp ../lib/tgdb-client.jar:../lib/tgdb-gremlin-mincore.jar:../examples hierarchy.PageRankGraph

9) Update Graph. Update a given member of the house. For instance

java -cp ../lib/tgdb-client.jar:../examples hierarchy.UpdateGraph -memberName "Napoleon Bonaparte" -crownTitle "King of USA" -yearDied null -reignEnd "31 Jan 2016"

==================================================================
