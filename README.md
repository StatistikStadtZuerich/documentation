# Linked Open Statistical Data 

## Getting started
You can run your SPARQL query in http://ld.stadt-zuerich.ch/sparql/ and directly see the result as a table or chart. See the [official SPARQL Query Language documentation](https://www.w3.org/TR/2013/REC-sparql11-query-20130321/) for how to write your own query or modifify an existing one. 

Our [examples](https://github.com/statistikstadtzuerich/documentation/tree/master/examples) provide a good starting point and exercise to work with our data if you're new to SPARQL. 

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
Use the folloing query to geta  list of all available measures. Clicking on each measure will give you additional information like unit and description. 
```SPARQL
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX qb: <http://purl.org/linked-data/cube#>
SELECT * WHERE {
  ?Kennzahl a qb:MeasureProperty ;
       rdfs:label ?KennzahlLabel .
} 
ORDER BY ?KennzahlLabel

```
## Api Reference

## Licensing

This documentation is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) (Statistik Stadt Zürich). 
