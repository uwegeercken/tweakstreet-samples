### Tweakstreet Data Integration Tool Samples

Various examples for the Tweakstreet Data Integration Tool. Check it out here: https://tweakstreet.io

The base components of the Tweakstreet GUI application are: control flows, data flows, steps, hops and modules. Control flows allow serial processing of tasks; they typically contain one or multiple data flows. Data flows execute certain processing tasks in parallel. The basic components in a data flow are steps - which encapsulate certain functionality - and the hops which connect steps to each other. Modules allow to define variables or additional functionality (functions) in a file and config modules can be used to define configuration e.g. for development and production environments.

The samples in this repository are self contained. You do not need anything else except of the Tweakstreet application which can be downloaded from the above site.

Below is a list of available samples, listing the name of the folder, the name of the flow file and a short description what the flow does.

Folder: basic-01
- read-csv-01.dfl: read a CSV file
- read-csv-02.dfl: read and filter a CSV file
- read-csv-03.dfl: read CSV file and remove some fields from the output
- read-csv-04.dfl: read CSV file, add a calculated list field and convert elevation value to meters
