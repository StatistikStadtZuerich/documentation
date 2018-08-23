# Linked Open Statistical Data 
This documentation covers using the linked open statistical data service provided by the [Statistics Office of the City of Zurich](https://www.stadt-zuerich.ch/statistik). 

## Getting started
You can first start with the information in this document. Further documentation is provided in a [Jupyternotebook](https://github.com/statistikstadtzuerich/documentation/blob/master/Linked_Data/Manual/LOSD_Manual_of_Statistik_Stadt_Zurich.ipynb) . You can use it to exercise working with our data if you're new to SPARQL.

For using the Jupyter notebook correctly, refer to the section about the installation of Jupyter in this context.

You can run your SPARQL query in https://ld.stadt-zuerich.ch/sparql/ and directly see the result as a table or chart. See the [official SPARQL Query Language documentation](https://www.w3.org/TR/2013/REC-sparql11-query-20130321/) for how to write your own query or modifify an existing one. 

An online version of the Jupyter notebooks is available on [binder](https://mybinder.org/v2/gh/statistikstadtzuerich/documentation/master?filepath=%2FLinked_Data%2FManual%2FLOSD_Manual_of_Statistik_Stadt_Zurich.ipynb). Currently the code blocks can't be executed, unfortunately. 

### list of available datasets
Use the following query to get a list of all datasets with their respective lables. 

```SPARQL
PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT  ?dataset (COUNT(*) AS ?count) ?label WHERE { GRAPH <https://linked.opendata.swiss/graph/zh/statistics> {

   #?obs a qb:Observation ;
   ?obs <http://purl.org/linked-data/cube#dataSet> ?dataset .

   ?dataset rdfs:label ?label .

}} GROUP BY ?dataset ?label
```
### list of all measures
Use the following query to geta  list of all available measures. Clicking on each measure will give you additional information like unit and description. 
```SPARQL
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX qb: <http://purl.org/linked-data/cube#>
SELECT * WHERE {
  ?Kennzahl a qb:MeasureProperty ;
       rdfs:label ?KennzahlLabel .
} 
ORDER BY ?KennzahlLabel
```

## Github
The relevant repositories are:
* https://github.com/statistikstadtzuerich/documentation (This documentation)
* https://github.com/statistikstadtzuerich/ld-data (The pipeline from the internal data format of SSZ to RDF)
* https://github.com/statistikstadtzuerich/ld.stadt-zuerich.ch  (the server for managing the linked data)
* https://github.com/statistikstadtzuerich/stat.stadt-zuerich.ch (the server to create the API)

## Api Reference
An API reference will be provided later on.

## Install Jupyter to use our Jupyter notebook fully
The Jupyter notebook provided by us will allow you to directly query the end-point from the notebook. For that reason the sparqlkernel and some extensions need to be installed. First you have to install python. Next, execute the following commands to install the necessary items:
```
python -m pip install --upgrade pip setuptools wheel
pip install jupyter
pip install sparqlkernel
pip install allthekernels
jupyter sparqlkernel install
pip install jupyter_contrib_nbextensions
jupyter contrib nbextension install --user
jupyter notebook
```
After downloading the notebook to your machine, move it into the folder from where you executed ```jupyter notebook``` (or do it the other way around). The kernel of the Notebook has to be set to "allthekernels" or otherwise you will not be able to use the R examples. 

**Important notice**: The Sparql kernel has some quirks within. This means you have to use the [Lindas](https://lindas-data.ch/) endpoint directly and not the one provided in the middleware for the time being. We work on this. Then it is especially useful to set the GRAPH as we have done in all examples in the jupyter notebook.

## Licensing
This documentation is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) (Statistik Stadt Zürich). 
