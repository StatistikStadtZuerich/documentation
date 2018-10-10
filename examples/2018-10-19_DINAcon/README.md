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

### All municipality boundaries in Canton

[code link](http://yasgui.org/short/ryX8ZPicX)
```SPARQL
PREFIX schema: <http://schema.org/>
PREFIX gn: <http://www.geonames.org/ontology#>
PREFIX geo: <http://www.opengis.net/ont/geosparql#>
PREFIX dct: <http://purl.org/dc/terms/>
select ?Municipality ?Name ?WKT
where
{
?Municipality a gn:A.ADM3 .
?Municipality schema:name ?Name .
?Municipality dct:issued ?Date .
?Municipality gn:parentADM1 ?InCanton .
?InCanton schema:name ?CantonName .
?Municipality geo:hasGeometry ?Geometry .
?Geometry geo:asWKT ?WKT .
FILTER (?Date = "2018-01-01"^^xsd:date)
FILTER (?CantonName = "Zürich")  
}
```

### Boundary of the City of Zurich

[code link](http://yasgui.org/short/BJlKbwjcX)
```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
SELECT * WHERE {
  <https://ld.geo.admin.ch/boundaries/municipality/261:2018> <http://www.opengis.net/ont/geosparql#hasGeometry> ?geometry .
   ?geometry <http://www.opengis.net/ont/geosparql#asWKT> ?wkt .  
}
```

### Public Transport Stops in Zürich with city boundary

[code link](http://yasgui.org/short/H1ixGvscX)
```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT * WHERE {
  <https://ld.geo.admin.ch/boundaries/municipality/261:2018> <http://www.opengis.net/ont/geosparql#hasGeometry> ?geometry .
   ?geometry <http://www.opengis.net/ont/geosparql#asWKT> ?wkt .                                                      
  
  ?stop rdf:type  <http://vocab.gtfs.org/terms#Stop> ;
   <http://www.w3.org/2003/01/geo/wgs84_pos#lat> ?lat ;
   <http://www.w3.org/2003/01/geo/wgs84_pos#long> ?long ;
   <http://schema.org/containedInPlace> ?municipality.

  Filter (?municipality = <https://ld.geo.admin.ch/boundaries/municipality/261>)  
  BIND(CONCAT('POINT(' , STR(?long), ' ', STR(?lat) , ')')  as ?Coords ) .
} 
```

### Public Transport Stops in Zürich without city boundary

[code link](http://yasgui.org/short/r1ZGMvocX)
```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT * WHERE {                                                      
  
  ?stop rdf:type  <http://vocab.gtfs.org/terms#Stop> ;
   <http://www.w3.org/2003/01/geo/wgs84_pos#lat> ?lat ;
   <http://www.w3.org/2003/01/geo/wgs84_pos#long> ?long ;
   <http://schema.org/containedInPlace> ?municipality.

  Filter (?municipality = <https://ld.geo.admin.ch/boundaries/municipality/261>)  
  BIND(CONCAT('POINT(' , STR(?long), ' ', STR(?lat) , ')')  as ?Coords ) .
} 
```


<a id="30" />

## Michael Grüebler

### Population of the City of Zurich 

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


