==================================================================
 TIBCO(R) Graph Database
 Copyright (c) 20016-2018 TIBCO Software Inc. All rights reserved.
------------------------------------------------------------------ 
 Openflights Routes
==================================================================

This example demonstrates how to import openflights data into the 
database and then find routes between two airports

1) Navigate to <tgdb_home>/bin in your terminal
window or command prompt before executing following steps.

2) Init database and import flights data:

Windows:
tgdb -i -f -c ../examples/routes/initdb.conf

MacOSX/linux:
./tgdb -i -f -c ../examples/routes/initdb.conf

3) Start database

Windows:
tgdb -s -c ../examples/routes/tgdb.conf

MacOSX/linux:
./tgdb -s -c ../examples/routes/tgdb.conf

4) Launch an Admin console and connect to the server

Navigate to <tgdb_home>/bin in a new command prompt window and execute following

Windows:
tgdb-admin

MacOSX/linux:
./tgdb-admin

Execute a 'show types' command and make sure entries are present
admin@localhost:8222> show types
 T  SysId     Name                  #Entries
 N  9225      airlineType           6162
 N  9227      airportType           7184
 E  1041      routeType             65600
3 type(s) returned.

5) Compile: javac -cp ../lib/tgdb-client.jar ../examples/common/*.java ../examples/routes/OpenFlightsQuery.java

6) Execute OpenFlightsQuery program and follow the instructions on prompt :

Windows:
java -cp ../lib/tgdb-client.jar;../examples routes.OpenFlightsQuery [-noprint]

MacOSX/linux:
java -cp ../lib/tgdb-client.jar:../examples routes.OpenFlightsQuery [-noprint]

option 'noprint' just prints the summary instead of all routes.
Use only if number of routes is high (stops > 2)


