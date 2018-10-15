# DINAcon Workshop Linked Data Experience

## Table of contents

People presenting: 

| Part                               | Presenter          | Organisation                    | Topic         | 
| ---------------------------------- | ------------------ | ------------------------------- | ------------- | 
| <a href="#user-content-10"> 1 </a> | Jean-Luc Cochard   | Schweizerisches Bundesarchiv    | Das Angebot von LINDAS (Bundesarchiv) |
| <a href="#user-content-20"> 2 </a> | Pasquale Di Donato | Swisstopo                       | Linked Data für Geoinformation (Swisstopo) |
| <a href="#user-content-30"> 3 </a> | Michael Grüebler   | Statistik Stadt Zürich          | Linked Open Statistical Data (Statistik Stadt Zürich) |
| <a href="#user-content-40"> 4 </a> | Cristina Sarasua   | Universität Zürich              | Wikidata and crowd sourced data |
| <a href="#user-content-50"> 5 </a> | Michael Grüebler   | Statistik Stadt Zürich          | Federated Query |
| <a href="#user-content-60"> 6 </a> | Matthias Mazenauer | Statistisches Amt Kanton Zürich | Visualisation on linked data |

![Visual agenda overview](agenda-overview.png "Visual agenda overview")

<a id="user-content-10" />

## Jean-Luc Cochard

See Presentation: [link to be added]


<a id="user-content-20" />

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

### Bonus Query: Points in Polygon: The stops in one quarter (Zürich Altstetten)

[code link](http://yasgui.org/short/r1e0elC97)
```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX geo: <http://www.opengis.net/ont/geosparql#>
PREFIX geof: <http://www.opengis.net/def/function/geosparql/>
#PREFIX geof: <http://www.opengis.net/def/geosparql/function/> 
PREFIX code: <https://ld.stadt-zuerich.ch/statistics/code/>

SELECT * WHERE {
   ?stop rdf:type  <http://vocab.gtfs.org/terms#Stop> ;
   <http://www.w3.org/2003/01/geo/wgs84_pos#lat> ?lat ;
   <http://www.w3.org/2003/01/geo/wgs84_pos#long> ?long .
  BIND(STRDT(CONCAT('POINT(', ?long, ' ', ?lat, ')'), 'http://www.openlinksw.com/schemas/virtrdf#Geometry') AS ?Stopwkt).
  
  SERVICE <https://ld.stadt-zuerich.ch/query> {
    SELECT * WHERE { 
      code:R00092 geo:hasGeometry ?GeoQuarter .
      ?GeoQuarter geo:asWKT ?GeoWKT
    } 
  }

  #?testDrin geo:sfWithin ?GeoQuarter .
  FILTER (bif:st_within(?Stopwkt, ?GeoWKT)) 
} 
limit 10
```

<a id="user-content-30" />

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


<a id="user-content-40" />

## Cristina Sarasua  


### Fountains of Wasserversorgung Zürich on Wikidata

[code link] (http://tinyurl.com/y76e9awd)

```SPARQL
#Fountains in Zürich
#defaultView:Map
SELECT ?item ?Bild ?geographische_Koordinaten WHERE {
  ?item p:P528 ?statement.
  ?statement pq:P972 wd:Q53629101.
  ?item wdt:P18 ?Bild.
  ?item wdt:P625 ?geographische_Koordinaten. 
}
```

### Fountains, Rivers, Brides and Swimmingpools in Zurich on Wikidata

[code link] (http://tinyurl.com/y954qvgx)

```SPARQL
#Fountains in Zürich
#defaultView:Map
SELECT ?item  ?Bild ?coord ?coordColor WHERE {
    
  {?item p:P528 ?statement.
        ?statement pq:P972 wd:Q53629101.   ?item wdt:P625 ?coord .
       
} UNION
  {    
    {?item wdt:P31/wdt:P279* wd:Q4022} UNION {?item wdt:P31/wdt:P279* wd:Q12280} UNION {?item wdt:P31/wdt:P279* wd:Q1501}
        ?item wdt:P131 wd:Q72
    }
        
      OPTIONAL {?item wdt:P18 ?Bild.}
      OPTIONAL{   ?article schema:about ?item .
    ?article schema:isPartOf <https://en.wikipedia.org/>.
     ?articlev schema:about ?item .
    ?articlev schema:isPartOf <https://en.wikivoyage.org/>.}
  ?item wdt:P625 ?coord. 
      BIND("#00FF00" AS ?coordColor) .
         
} 
```


### Bonus Query: Number of rivers per canton in Wikidata 

[code link](https://tinyurl.com/ybyxjxsx)

```SPARQL
SELECT  ?canton ?cantonLabel (COUNT(?river) AS ?count) #?loc ?distance #?thing ?thingLabel 

WHERE {
      
  ?river wdt:P31/wdt:P279* wd:Q4022 .
  ?river wdt:P131 ?canton .
  ?canton wdt:P31 wd:Q23058 .
     
  SERVICE wikibase:label { bd:serviceParam wikibase:language "[AUTO_LANGUAGE],en". }
} GROUP BY ?canton ?cantonLabel
```


<a id="user-content-50" />

## Federated Query (Michael Grüebler)

### All in one

[code link](http://yasgui.org/short/Up6hzNRtU)
```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX schema: <http://schema.org/>
PREFIX gn: <http://www.geonames.org/ontology#>
PREFIX geo: <http://www.opengis.net/ont/geosparql#>
PREFIX dct: <http://purl.org/dc/terms/>

PREFIX wdt: <http://www.wikidata.org/prop/direct/>
PREFIX wd: <http://www.wikidata.org/entity/>
PREFIX pq: <http://www.wikidata.org/prop/qualifier/>
PREFIX ps: <http://www.wikidata.org/prop/statement/>
PREFIX p: <http://www.wikidata.org/prop/>
PREFIX wikibase: <http://wikiba.se/ontology#>
PREFIX bd: <http://www.bigdata.com/rdf#>

PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
PREFIX dataset: <https://ld.stadt-zuerich.ch/statistics/dataset/>
PREFIX measure: <https://ld.stadt-zuerich.ch/statistics/measure/>
PREFIX dimension: <https://ld.stadt-zuerich.ch/statistics/property/>
PREFIX code: <https://ld.stadt-zuerich.ch/statistics/code/>

SELECT ?item ?Bild ?fountainCoord ?fountainCoordColor ?WKT ?Coords ?WKTColor ?CoordsColor ?QuarterLabel ?Population ?WKTQuarter ?WKTQuarterColor
WHERE {
  	SERVICE <https://ld.geo.admin.ch/query> {

SELECT ?WKT ?Coords ?WKTColor ?CoordsColor WHERE {
?Municipality a gn:A.ADM3 ;
  dct:isVersionOf ?Mainmun ;
  schema:name ?Name ;
  dct:issued ?Date ;
  gn:parentADM1 <https://ld.geo.admin.ch/boundaries/canton/1:2018> ;
  geo:hasGeometry ?Geometry .
#?InCanton schema:name ?CantonName .
?Geometry geo:asWKT ?WKT .
 #FILTER (?Name IN ("Zürich", "Uster"))                                                       
 #FILTER (?CantonName = "Bern")     
  
  ?stop rdf:type  <http://vocab.gtfs.org/terms#Stop> ;
   <http://www.w3.org/2003/01/geo/wgs84_pos#lat> ?lat ;
   <http://www.w3.org/2003/01/geo/wgs84_pos#long> ?long ;
   <http://schema.org/containedInPlace> ?Mainmun ;
   <https://ld.geo.admin.ch/def/transportation/meansOfTransportation> <https://ld.geo.admin.ch/codelist/MeansOfTransportation/8> .

  #Filter (?muni = <https://ld.geo.admin.ch/boundaries/municipality/261>)  
  BIND(CONCAT('POINT(' , STR(?long), ' ', STR(?lat) , ')')  as ?Coords ) .
      BIND("#999999" AS ?WKTColor)
      BIND("#0000FF" AS ?CoordsColor)
}       

     }

  SERVICE <https://query.wikidata.org/bigdata/namespace/wdq/sparql> {

SELECT ?item  ?Bild ?coord ?coordColor WHERE {
    
  {?item p:P528 ?statement.
        ?statement pq:P972 wd:Q53629101.   ?item wdt:P625 ?coord .
       
} UNION
  {    
    {?item wdt:P31/wdt:P279* wd:Q4022} UNION {?item wdt:P31/wdt:P279* wd:Q12280} UNION {?item wdt:P31/wdt:P279* wd:Q1501}
        ?item wdt:P131 wd:Q72
    }
        
      OPTIONAL {?item wdt:P18 ?Bild.}
      OPTIONAL{   ?article schema:about ?item .
    ?article schema:isPartOf <https://en.wikipedia.org/>.
     ?articlev schema:about ?item .
    ?articlev schema:isPartOf <https://en.wikivoyage.org/>.}
  ?item wdt:P625 ?coord. 
      BIND("#00FF00" AS ?coordColor) .
     
      
   
      
} 

} 


  ?sub a qb:Observation ;
       qb:dataSet dataset:BEW-RAUM-ZEIT ;
       measure:BEW ?Population ;
       dimension:RAUM ?Quarter ;
       dimension:ZEIT ?Zeit .
  ?Quarter owl:sameAs ?WikidataUID ;
        skos:broader code:Quartier ;
        rdfs:label ?QuarterLabel .  
  ?Quarter geo:hasGeometry ?GeoQuarter .
  ?GeoQuarter geo:asWKT ?WKTQuarter .
  FILTER(year(?Zeit) = 2017) .
  BIND("#FF0000" AS ?WKTQuarterColor) .
  
  } LIMIT 300
```

<a id="user-content-60" />

## Matthias Mazenauer

### Linked Data Visualization with D3js

[Link to Observable Notebook](https://beta.observablehq.com/@mmznrstat/a-thriving-data-ecosystem)
