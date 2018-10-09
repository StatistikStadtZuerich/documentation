# DINAcon Workshop Linked Data Experience

## Table of contents

People presenting: 

| Part                  | Presenter          | Organisation                    | Topic         | 
| --------------------- | ------------------ | ------------------------------- | ------------- | 
| <a href="#10"> 1 </a> | Jean-Luc Cochard   | Schweizerisches Bundesarchiv    | Das Angebot von LINDAS (Bundesarchiv) |
| <a href="#20"> 2 </a> | Pasquale Di Donato | Swisstopo                       | Linked Data für Geoinformation (Swisstopo) |
| <a href="#30"> 3 </a> | Michael Grüebler   | Statistik Stadt Zürich          | Linked Open Statistical Data (Statistik Stadt Zürich) |
| <a href="#40"> 4 </a> | Cristina Sarasua   | Universität Zürich              | Wikidata and crowd sourced data |
| <a href="#50"> 5 </a> | Matthias Mazenauer | Statistisches Amt Kanton Zürich | Visualisation on linked data |

![Visual agenda overview](agenda-overview.png "Visual agenda overview")

<a id="10" />

## Jean-Luc Cochard



<a id="20" />

## Pasquale Di Donato



<a id="30" />

## Michael Grüebler

### Population in the City of Zurich 

Queries the population of the city, its districts and its quarters in 2017.

[code link](http://yasgui.org/short/SJ2e_SqqX)
```SPARQL
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX dataset: <https://ld.stadt-zuerich.ch/statistics/dataset/>
PREFIX measure: <https://ld.stadt-zuerich.ch/statistics/measure/>
PREFIX dimension: <https://ld.stadt-zuerich.ch/statistics/property/>
PREFIX code: <https://ld.stadt-zuerich.ch/statistics/code/>
SELECT ?RaumLabel ?Population WHERE {
  ?sub a qb:Observation ;
       qb:dataSet dataset:BEW-RAUM-ZEIT ;
       measure:BEW ?Population ;
       dimension:RAUM ?Raum ;
       dimension:ZEIT ?Date .
  ?Raum rdfs:label ?RaumLabel
  FILTER(year(?Date) = 2017)
} ORDER BY DESC(?Population)
```

### Population of quarters ready to link 

Queries the population of all the quarters of the city of Zurich in 2017.
For linking purposes the geometry and wikidata-identifiers are selected.  

[code link](http://yasgui.org/short/Byg5OH5qm)
```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
PREFIX geo: <http://www.opengis.net/ont/geosparql#>
PREFIX dataset: <https://ld.stadt-zuerich.ch/statistics/dataset/>
PREFIX measure: <https://ld.stadt-zuerich.ch/statistics/measure/>
PREFIX dimension: <https://ld.stadt-zuerich.ch/statistics/property/>
PREFIX code: <https://ld.stadt-zuerich.ch/statistics/code/>
SELECT ?Quarter ?Geometry ?WikidataUID ?QuarterLabel ?Population WHERE {
  ?sub a qb:Observation ;
       qb:dataSet dataset:BEW-RAUM-ZEIT ;
       measure:BEW ?Population ;
       dimension:RAUM ?Quarter ;
       dimension:ZEIT ?Date .
  ?Quarter owl:sameAs ?WikidataUID ;
        skos:broader code:Quartier ;
        rdfs:label ?QuarterLabel .  
  ?Quarter geo:hasGeometry ?Geometry .
  FILTER(year(?Date) = 2017)
} ORDER BY DESC(?Population)
```


<a id="40" />

## Cristina Sarasua  


<a id="50" />

## Matthias Mazenauer


