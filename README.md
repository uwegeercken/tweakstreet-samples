### Tweakstreet Data Integration Tool Samples

Various examples for the Tweakstreet Data Integration Tool. The samples offer different levels of difficulty, so that both beginners and advanced users can benefit from it. For the Tweakstreet ETL tool, check out the Tweakstreet website here: https://tweakstreet.io

The base components of the Tweakstreet GUI application are: control flows, data flows, steps, hops and modules. Control flows allow serial processing of tasks; they typically contain - amongst other components - one or multiple data flows. Data flows execute certain processing tasks in parallel. The core components in a data flow are steps - which encapsulate certain functionality - and the hops which connect steps to each other. Modules allow to define variables or additional functionality (functions) in a file and config modules can be used to define configuration e.g. for development and production environments. Besides handling flat records, Tweakstreet represents all data natively as nested data structures.

Except for the database related examples, the samples in this repository are self contained. You do not need anything else except of the Tweakstreet application which can be downloaded from the above site. The repository also contains a folder: _data_. The data files in this folder are used for the samples. For each sample there is also a screenshot available. All samples have a description on the dataflow or controlflow level, as well as descriptions for all or most of the steps.

For the samples with the SQLite database you need to download the JDBC driver from https://github.com/xerial/sqlite-jdbc or another source. Put the JDBC driver jar file into the HOME/.tweakstreet/drivers folder.

I recommend to also check the Tweakstreet forum at: https://forum.tweakstreet.io/ which contains tutorials, data challenges and more.

To get a copy of all samples clone this repository, install the Tweakstreet Data Integration Tool and run it. On the Tweakstreet homepage you find a link to the documentation. There is also an introduction tutorial video available on youtube: https://www.youtube.com/watch?v=zjduMFtbmFM.

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
| basic-03           | random-data-05.dfl           | generate random data based on distinct lists generated from a CSV file |
| basic-04           | split-01.dfl                 | split a string of multiple key/value pairs into its components and create a dictionary |
| basic-05           | diff-01.dfl                  | calculate the difference between a reference and a second data set |
| basic-05           | diff-02.dfl                  | calculate the difference between a reference and a second data set. use a decision step to route output |
| basic-06           | misc-01.dfl                  | retrieve system information and do some date calculations using the time library |
| basic-06           | serialize-01.dfl             | serialize data to a file |
| basic-06           | deserialize-01.dfl           | deserialize data to the file produced in the serialize-01 data flow |
| basic-06           | distinct-01.dfl              | determine the distinct values over a group of fields |
| basic-06           | rest-01.dfl                  | get data from a REST endpoint and split into individual rows |
| basic-06           | rest-02.dfl                  | get data from the geonames REST endpoint, split the JSON response into rows and sum up population per continent |
| basic-07           | partitioning-01.dfl          | partition data to process in parallel |
| basic-08           | database-01.dfl              | read airport data from a local SQLite database |
| basic-08           | database-02.dfl              | read airport data and lookup country data from a local SQLite database using a "SQL Input" step |
| basic-08           | database-03.dfl              | read airport data and join country data using a "Join on Condition" step |
| basic-08           | database-04.dfl              | read airport data and join country data using a "SQL Script" step and convert list to rows |
| basic-08           | database-05.dfl              | read airport and country data and output the results including JSON field |
| basic-08           | database-06.dfl              | read data stored in the database-05.dfl flow and restore the dictionary with the country data |
| basic-08           | database-07.dfl              | read data stored in the database-05.dfl flow and restore the dictionary data already in the SQL query |
| basic-09           | stateful-01.dfl              | Generate a row count and calculate the running average age using the "Stateful Calculator" step |
| basic-10           | templates-01.dfl             | Use sample data and merge it with a template using the Freemarker template engine |
| basic-11           | mainflow-01.dfl, subflow-01.dfl | usage of the subflow step |
| basic-11           | mainflow-02.dfl, mainflow-02_subflow-01, mainflow-02_subflow-02 | switching subflows depending on a variables value |
| medium-01          | cast-values-01.dfl           | Cast selected values of a list of dictionaries from string to long or double |
| medium-01          | functions-01.dfl             | Show the use of functions as a formular or using the widgets |

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
| data              | airports.json                | 7733 airports with name, codes, coordinates, elevation |
| data              | airports_cleaned.json        | 7733 airports with name, codes, coordinates, elevation. with corrected long and double data types |
| data              | countries.csv                | 241 countries with name and code |
| data              | country_continent_lookup.csv | country to continent lookup data |
| data              | continent_names_lookup.csv   | continent names lookup data |
| data/sqlite       | airports.db                  | airports and countries in a Sqlite database file |


**Steps**: Below is the list of steps and an indication in which dataflow they are used.

| Step          | Dataflow  |
| :--           | :-- |
| CSV Input		| read-csv-01.dfl, read-csv-02.dfl, read-csv-03.dfl, read-csv-04.dfl, read-csv-05.dfl, read-csv-06.dfl, read-csv-07.dfl, random-data-05.dfl |
| Filter		| read-csv-02.dfl, read-csv-04.dfl |
| Pick Fields	| read-csv-03.dfl, random-data-02.dfl, partitioning-01.dfl, database-05.dfl, random-data-05.dfl, rest-02.df |
| Calculator	| read-csv-04.dfl, read-csv-07.dfl, modules-03.dfl, random-data-02.dfl, split-01.dfl, partitioning-01.dfl, database-06.dfl, templates-01.dfl, cast-values-01.dfl, functions-01.dfl |
| Logger		| read-csv-04.dfl, modules-01.dfl, modules-02.dfl |
| Group By		| read-csv-05.dfl, read-csv-06.dfl, random-data-05.dfl, rest-02.df |
| Sort			| read-csv-05.dfl, read-csv-06.dfl |
| Stream Lookup	| read-csv-06.dfl |
| Generate Rows	| random-data-01.dfl, random-data-02.dfl, random-da,ta-03.dfl, random-data-04.dfl, diff-01.dfl, diff-02.dfl, serialize-01.dfl, partitioning-01.dfl, random-data-05.dfl, mainflow-01.dfl |
| Random Data	| random-data-01.dfl, random-data-02.dfl, random-data-03.dfl, random-data-04.dfl, serialize-01.dfl, partitioning-01.dfl, random-data-05.dfl, mainflow-01.dfl |
| Data Table	| split-01.dfl, stateful-01.dfl, distinct-01.dfl, templates-01.dfl |
| Diff on sorted Keys	| diff-01.dfl, diff-02.dfl |
| Decision		| diff-02.dfl, partitioning-01.dfl |
| Deserialize	| deserialize-01.dfl  |
| Serialize		| serialize-01.dfl |
| System Info	| misc-01.dfl |
| Clock			| misc-01.dfl, stateful-01.dfl |
| SQL Input		| database-01.dfl, database-02.dfl, database-03.dfl, database-05.dfl, database-06.dfl, database-07.dfl, mainflow-02.dfl |
| SQL Lookup	| database-02.dfl, database-05.dfl |cont
| Join on Condition	| database-03.dfl |
| SQL Script	| database-04.dfl |
| List to Rows	| database-04.dfl, rest-01.dfl, rest-02.df, cast-values-01.dfl |
| SQL Insert	| database-05.dfl |
| Stateful Calculator	| stateful-01.dfl |
| Distinct		| distinct-01.dfl |
| Freemarker  | templates-01.dfl |
| HTTP Request  | rest-01.dfl, rest-02.dfl  |
| Read File  | cast-values-01.dfl, functions-01.dfl |
| Sub Flow  | mainflow-01.dfl, mainflow-02.dfl |
| Interface Input | subflow-01.dfl, mainflow-02_subflow-01, mainflow-02_subflow-02 |
| Interface Output | subflow-01.dfl, mainflow-02_subflow-01, mainflow-02_subflow-02 |
| Value Mapper | mainflow-02.dfl |


last update: 2021-10-26
