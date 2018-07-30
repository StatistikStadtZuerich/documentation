# Linked Open Statistical Data 

## Getting started
Use the following SPARQL query in http://ld.stadt-zuerich.ch/sparql/ to retrieve a full list of available datasets.

```SPARQL
PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT  ?dataset (COUNT(*) AS ?count) ?label WHERE { GRAPH <https://linked.opendata.swiss/graph/zh/statistics> {

   #?obs a qb:Observation ;
   ?obs <http://purl.org/linked-data/cube#dataSet> ?dataset .

   ?dataset rdfs:label ?label .

}} GROUP BY ?dataset ?label
```
See the [official SPARQL Query Language documentation](https://www.w3.org/TR/2013/REC-sparql11-query-20130321/) for how to modify your query according your needs. 

Our [examples](https://github.com/statistikstadtzuerich/documentation/tree/master/examples) provide a good starting point and exercise to work with our data. 

## Api Reference

## Licensing

This documentation is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) (Statistik Stadt Zürich). 
