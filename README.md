#### tweakstreet-samples

Various examples for the Tweakstreet Data Integration Tool. Check it out here: https://tweakstreet.io

The base components of the Tweakstreet GUI application are: control flows, data flows, steps, hops and modules. Control flows allow serial processing of tasks; they typically contain one or multiple data flows. Data flows execute the tasks in parallel. The basic components in a data flow are steps - which encapsulate certain functionality - and the hops which are the connections between the steps. Modules allow to define configuration or additional functionality in a file (library) and config modules can be used to define configuration e.g. for different environments.

The samples are self contained. You do not need anything else except of the Tweakstreet application which can be downloaded from the above site.

Below is a list of available samples, listing the name of the folder, the name of the flow file and a short description what the flow does.

Folder: basic-01
- read-csv-01.dfl: read a CSV file
- read-csv-02.dfl: read and filter a CSV file
