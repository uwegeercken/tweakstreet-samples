### Tweakstreet Data Integration Tool Samples

Various examples for the Tweakstreet Data Integration Tool. The idea is to provide samples for challenges in the design of data flows or when solving specific problems and offering different levels of difficulty, so that both beginners and advanced users can benefit from it. Check out the Tweakstreet website here: https://tweakstreet.io

The base components of the Tweakstreet GUI application are: control flows, data flows, steps, hops and modules. Control flows allow serial processing of tasks; they typically contain - amongst other components - one or multiple data flows. Data flows execute certain processing tasks in parallel. The core components in a data flow are steps - which encapsulate certain functionality - and the hops which connect steps to each other. Modules allow to define variables or additional functionality (functions) in a file and config modules can be used to define configuration e.g. for development and production environments. Besides handling flat records, Tweakstreet represents all data natively as nestable data structures.

Except for the database related examples, the samples in this repository are self contained. You do not need anything else except of the Tweakstreet application which can be downloaded from the above site. The repository also contains a folder: _data_. The data files in this folder are used for the samples. For each sample there is also a screenshot available.

For the samples with the SQLite database you need to download the JDBC driver from https://github.com/xerial/sqlite-jdbc. Put the JDBC driver jar file into the folder HOME/.tweakstreet/drivers.

I recommend to also check the Tweakstreet forum at: https://forum.tweakstreet.io/ which contains tutorials, data challenges and more.

Clone this repository, install the Tweakstreet Data Integration Tool and run it. On the Tweakstreet homepage you find a link to the documentation. There is also an introduction tutorial video available on youtube: https://www.youtube.com/watch?v=zjduMFtbmFM.

**Attention**: After starting Tweakstreet, select the folder of the cloned repository as your workspace folder ('File' menu). And then please make sure that you use the config module: 'conf-module-samples.tsm'. It contains some variables which the samples rely on: in the sidebar on the left which shows the file and directory tree (Strg+B to activate it if you don't see it), click on the file 'conf-module-samples.tsm' to open it. Then right-click on the tab which carries the name of the file and select 'Set as config module'. Alternatively right-click on '$none' in the blue toolbar at the bottom, select 'Choose config module' and navigate to this file and select it.

**Flows**: Below is the list of available samples, listing the name of the folder, the name of the flow file and a short description what the flow does.

| Folder             | Filename                     | Description                      |
| :--                | :--                          | :--                              |
| basic-01           | read-csv-01.dfl              | read a CSV file |
| basic-01           | read-csv-02.dfl              | read and filter a CSV file |
| basic-01           | read-csv-03.dfl              | read CSV file and remove some fields from the output |
| basic-01           | read-csv-04.dfl              | read CSV file, add a calculated list field, convert elevationto meters and write to log |
| basic-01           | read-csv-05.dfl              | read CSV file, group by country and sort by highest number of airports |
| basic-01           | read-csv-06.dfl              | read CSV file, lookup country details, group by country and sort by highest number of airports |
| basic-01           | read-csv-07.dfl              | read fixed-length ASCII file and split each row into its individual fields |
| basic-02           | modules-01.dfl               | simply output variables from a config module to the log |
| basic-02           | modules-02.dfl               | import config variables to the data flow |
| basic-02           | modules-03.dfl               | call function from a global module |
| basic-03           | random-data-01.dfl           | generate random data using generators |
| basic-03           | random-data-02.dfl           | generate random data using generators, merge results |
| basic-03           | random-data-03.dfl           | generate random data using generators, merge results directly in random data step |
| basic-03           | random-data-04.dfl           | generate random data using list and dict generators |
| basic-04           | split-01.dfl                 | split a string of multiple key/value pairs into its components and create a dictionary |
| basic-05           | diff-01.dfl                  | calculate the difference between a reference and a second data set |
| basic-05           | diff-02.dfl                  | calculate the difference between a reference and a second data set. use a decision step to route output |
| basic-06           | misc-01.dfl                  | retrieve system information and do some date calculations using the time library |
| basic-06           | serialize-01.dfl             | serialize data to a file |
| basic-06           | deserialize-01.dfl           | deserialize data to the file produced in the serialize-01 data flow |
| basic-06           | distinct-01.dfl              | determine the distinct values over a group of fields |
| basic-07           | partitioning-01.dfl          | partition data to process in parallel |
| basic-08           | database-01.dfl              | read airport data from a local SQLite database |
| basic-08           | database-02.dfl              | read airport data and lookup country data from a local SQLite database using a "SQL Input" step |
| basic-08           | database-03.dfl              | read airport data and join country data using a "Join on Condition" step |
| basic-08           | database-04.dfl              | read airport data and join country data using a "SQL Script" step and convert list to rows |
| basic-08           | database-05.dfl              | read airport and country data and output the results including JSON field |
| basic-08           | database-06.dfl              | read data stored in the database-05.dfl flow and restore the dictionary with the country data |
| basic-08           | database-07.dfl              | read data stored in the database-05.dfl flow and restore the dictionary data already in the SQL query |
| basic-09           | stateful-01.dfl              | Generate a row count and calculate the running aerage age using the "Stateful Calculator" step |
| basic-10           | templates-01.dfl             | Use sample data and merge it with a template using the Freemarker template engine |

**Available modules**:

| Filename                     | Description                                                                  |
| :--                          | :--                                                                          | 
| conf-module-samples.tsm      | config module with variables for the data files                              |
| global-module-samples.tsm    | global module with variables for re-use across flows                         |
| random-data-lists.tsm        | various lists with random data. used with the "generate from list" generator |


**Data Files**:

| Folder            | Filename                     | Description                                            |
| :--               | :--                          | :--                                                    |
| data              | airports.csv                 | 7733 airports with name, codes, coordinates, elevation |
| data              | airports_fixed_length.csv    | 7733 airports with name, codes, coordinates, elevation. fields have fixed start/end positions |
| data              | countries.csv                | 241 countries with name and code |
| data              | country_continent_lookup.csv | country to continent lookup data |
| data              | continent_names_lookup.csv   | continent names lookup data |
| data/sqlite       | airports.db                  | airports and countries in a Sqlite database file |


**Steps**: Below is the list of steps and an indication in which dataflow they are used.

| Step                  | Dataflow  |
| :--                   | :-- |
| CSV Input		| read-csv-01.dfl, read-csv-02.dfl, read-csv-03.dfl, read-csv-04.dfl, read-csv-05.dfl, read-csv-06.dfl, read-csv-07.dfl |
| Filter		| read-csv-02.dfl, read-csv-04.dfl |
| Pick Fields		| read-csv-03.dfl, random-data-02.dfl, partitioning-01.dfl, database-05.dfl |
| Calculator		| read-csv-04.dfl, read-csv-07.dfl, modules-03.dfl, random-data-02.dfl, split-01.dfl, partitioning-01.dfl, database-06.dfl |
| Logger		| read-csv-04.dfl, modules-01.dfl, modules-02.dfl |
| Group By		| read-csv-05.dfl, read-csv-06.dfl |
| Sort			| read-csv-05.dfl, read-csv-06.dfl |
| Stream Lookup		| read-csv-06.dfl |
| Generate Rows		| random-data-01.dfl, random-data-02.dfl, random-da,ta-03.dfl, random-data-04.dfl, diff-01.dfl, diff-02.dfl, serialize-01.dfl, partitioning-01.dfl |
| Random Data		| random-data-01.dfl, random-data-02.dfl, random-data-03.dfl, random-data-04.dfl, serialize-01.dfl, partitioning-01.dfl |
| Data Table		| split-01.dfl, stateful-01.dfl, distinct-01.dfl |
| Diff on sorted Keys	| diff-01.dfl, diff-02.dfl |
| Decision		| diff-02.dfl, partitioning-01.dfl |
| Deserialize		| deserialize-01.dfl  |
| Serialize		| serialize-01.dfl |
| System Info		| misc-01.dfl |
| Clock			| misc-01.dfl, stateful-01.dfl |
| SQL Input		| database-01.dfl, database-02.dfl, database-03.dfl, database-05.dfl, database-06.dfl, database-07.dfl |
| SQL Lookup		| database-02.dfl, database-05.dfl |
| Join on Condition	| database-03.dfl |
| SQL Script		| database-04.dfl |
| List to Rows		| database-04.dfl |
| SQL Insert		| database-05.dfl |
| Stateful Calculator	| stateful-01.dfl |
| Distinct		| distinct-01.dfl |


last update: 2021-02-01
