### Tweakstreet Data Integration Tool Samples

Various examples for the Tweakstreet Data Integration Tool. The idea is to provide samples for challenges in the design of data flows or when solving specific problems and offering different levels of difficulty, so that both beginners and advanced users can benefit from it. Check out the Tweakstreet website here: https://tweakstreet.io

The base components of the Tweakstreet GUI application are: control flows, data flows, steps, hops and modules. Control flows allow serial processing of tasks; they typically contain - amongst other components - one or multiple data flows. Data flows execute certain processing tasks in parallel. The core components in a data flow are steps - which encapsulate certain functionality - and the hops which connect steps to each other. Modules allow to define variables or additional functionality (functions) in a file and config modules can be used to define configuration e.g. for development and production environments. Besides handling flat records, Tweakstreet represents all data natively as nestable data structures

The samples in this repository are self contained. You do not need anything else except of the Tweakstreet application which can be downloaded from the above site. The repository also contains a folder: _data_. The data files in this folder are used for the samples.

Below is a list of available samples, listing the name of the folder, the name of the flow file and a short description what the flow does.

Folder: basic-01
- read-csv-01.dfl: read a CSV file
- read-csv-02.dfl: read and filter a CSV file
- read-csv-03.dfl: read CSV file and remove some fields from the output
- read-csv-04.dfl: read CSV file, add a calculated list field and convert elevation value to meters
- read-csv-05.dfl: read CSV file, group by country and sort by highest number of airports
