# Linked Open Statistical Data 
This documentation covers using the linked open statistical data service provided by the [Statistics Office of the City of Zurich](https://www.stadt-zuerich.ch/statistik). 

## Getting started
You can first start with the information in this document. As further documentation we provide a [Jupyternotebook](https://github.com/statistikstadtzuerich/documentation/blob/master/LOSD_Manual_of_Statistik_Stadt_Zurich.ipynb) . You can use it to exercise to work with our data if you're new to SPARQL.

An online Jupyter notebook will soon be provided:
[![Binder](https://mybinder.org/badge.svg)](https://mybinder.org/v2/gh/statistikstadtzuerich/documentation/master)

You can run your SPARQL query in https://ld.stadt-zuerich.ch/sparql/ and directly see the result as a table or chart. See the [official SPARQL Query Language documentation](https://www.w3.org/TR/2013/REC-sparql11-query-20130321/) for how to write your own query or modifify an existing one. 

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

## Licensing
This documentation is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) (Statistik Stadt Zürich). 
