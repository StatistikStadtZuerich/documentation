# Linked Open Statistical Data 
This documentation covers using the linked open statistical data service provided by the [Statistics Office of the City of Zurich](https://www.stadt-zuerich.ch/statistik). 

## Getting started
You can first start with the information in this document or the [getting started document by Klemens Rosin](https://github.com/statistikstadtzuerich/documentation/blob/master/Linked_Data/GettingStarted/GettingStartedZurichLOSD.md). We also provide a [short video introduction](https://youtu.be/IUyzwwwIJSk) by Adrian Gschwend about querying RDF Data Cubes. 

Further documentation is provided in a [Jupyter Notebook](https://github.com/statistikstadtzuerich/documentation/blob/master/Linked_Data/Manual/LOSD_Manual_of_Statistik_Stadt_Zurich.ipynb) (for direct viewing in the browser use one of the options below). 

You can:
* use the [Markdown version](https://github.com/statistikstadtzuerich/documentation/blob/master/Linked_Data/Manual/README.md).
* use [mybinder](https://mybinder.org/v2/gh/statistikstadtzuerich/documentation/master?filepath=Linked_Data%2FManual%2FLOSD_Manual_of_Statistik_Stadt_Zurich.ipynb)  to read it (due to firewall issues the code is not executable for the time being.
* For a local installation, which works fine, refer to the section about the installation of Jupyter in this context.

## Queries, Endpoint 
You can run your SPARQL query in https://ld.stadt-zuerich.ch/sparql/ and directly see the result as a table or chart. See the [official SPARQL Query Language documentation](https://www.w3.org/TR/2013/REC-sparql11-query-20130321/) for how to write your own query or modifify an existing one.  The endpoint is https://ld.stadt-zueri.ch/query. 

### List of available datasets
Use the following query to get a list of all datasets with their respective labels. It also shows how many observations are available per dataset. 

```SPARQL
PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT  ?dataset (COUNT(*) AS ?count) ?label WHERE { GRAPH <https://linked.opendata.swiss/graph/zh/statistics> {

   ?dataset a qb:DataSet ; 
   		rdfs:label ?label . 
    
   #?obs a qb:Observation ;
   ?obs <http://purl.org/linked-data/cube#dataSet> ?dataset .

}} GROUP BY ?dataset ?label
```
### List of all measures
Use the following query to geta  list of all available measures. Clicking on each measure will give you additional information like unit and description. 
```SPARQL
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX qb: <http://purl.org/linked-data/cube#>

SELECT * WHERE { GRAPH <https://linked.opendata.swiss/graph/zh/statistics> {
  ?kennzahl a qb:MeasureProperty ;
       rdfs:label ?kennzahlLabel .
  }} 
ORDER BY ?KennzahlLabel
```

## GitHub
The relevant repositories are:
* https://github.com/statistikstadtzuerich/documentation (This documentation)
* https://github.com/statistikstadtzuerich/ld-data (The pipeline from the internal data format of SSZ to RDF)
* https://github.com/statistikstadtzuerich/ld.stadt-zuerich.ch  (the server for managing the linked data)
* https://github.com/statistikstadtzuerich/stat.stadt-zuerich.ch (the server to create the API)
* and also https://github.com/statistikstadtzuerich/sszvis (the visualization library)

## REST API and Reference
In a further step we will provide a REST-API to access the data.

## Install Jupyter to use our Jupyter Notebook
The Jupyter Notebook provided by us will allow you to directly query the end-point from the notebook. For that reason the sparqlkernel and some extensions need to be installed. First you have to install python. Next, execute the following commands to install the necessary items:
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
After downloading the notebook to your machine, move it into the folder from where you executed ```jupyter notebook``` (or do it the other way around). The kernel of the notebook has to be set to "allthekernels" or otherwise you will not be able to use the R examples. 

**Important notice**: The SPARQL Jupiter kernel has some quirks within. This means you have to use the [LINDAS](https://lindas-data.ch/) endpoint directly and not the one provided in the middleware for the time being. We will contribute patches to the SPARQL kernel to fix this and update the documentation once it works. When querying the dataset we strongly recommend to add the `GRAPH` to the `WHERE` clause. Omitting this makes the query slower as there is other data in this endpoint. All our examples  in the Jupyter Notebook do this, just copy paste it to your queries.

## License
This documentation is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) (Statistik Stadt Zürich). 
