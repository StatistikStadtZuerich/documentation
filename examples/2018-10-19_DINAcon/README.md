# DINAcon Workshop Linked Data Experience

## Presenter

People presenting: 

| Part                  | Presenter          | Organisation                    | Topic         | 
| --------------------- | ------------------ | ------------------------------- | ------------- | 
| <a href="#10"> 1 </a> | Jean-Luc Cochard   | Schweizerisches Bundesarchiv    | Das Angebot von LINDAS (Bundesarchiv) |
| <a href="#20"> 2 </a> | Pasquale Di Donato | Swisstopo                       | Linked Data für Geoinformation (Swisstopo) |
| <a href="#30"> 3 </a> | Michael Grüebler   | Statistik Stadt Zürich          | Linked Open Statistical Data (Statistik Stadt Zürich) |
| <a href="#40"> 4 </a> | Cristina Sarasua   | Universität Zürich              | Wikidata and crowd sourced data |
| <a href="#50"> 5 </a> | Matthias Mazenauer | Statistisches Amt Kanton Zürich | Visualisation on linked data |

<a id="10" />

## Jean-Luc Cochard



<a id="20" />

## Pasquale Di Donato



<a id="30" />

## Michael Grüebler

### Population "City"
Queries the population of the quarter "City" from LOSD as an example

[code link](http://yasgui.org/short/r19a_z-_X)
```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
PREFIX dataset: <https://ld.stadt-zuerich.ch/statistics/dataset/>
PREFIX measure: <https://ld.stadt-zuerich.ch/statistics/measure/>
PREFIX dimension: <https://ld.stadt-zuerich.ch/statistics/property/>
PREFIX code: <https://ld.stadt-zuerich.ch/statistics/code/>
SELECT ?Raum ?RaumLabel ?Zeit ?WikidataUID ?Bevoelkerung WHERE {
  ?sub a qb:Observation ;
       qb:dataSet dataset:BEW-RAUM-ZEIT ;
       measure:BEW ?Bevoelkerung ;
       dimension:RAUM ?Raum ;
       
 	dimension:ZEIT ?Zeit .
  ?Raum owl:sameAs ?WikidataUID ;
        skos:broader code:Quartier ;
        rdfs:label ?RaumLabel .  
  FILTER (?Raum=code:R00014)
} ORDER BY ?Zeit
```

The query can be extended by removing the filter

### Percentage of Foreigners

Calculate the percentage of foreigners 

[code link](http://yasgui.org/short/ry3q1rb_Q)
```SPARQL
PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX dataset: <https://ld.stadt-zuerich.ch/statistics/dataset/>
SELECT ?RaumLabel ?WikidataUID ?Time ?PercForeign
WHERE{ 
  GRAPH <https://linked.opendata.swiss/graph/zh/statistics>{
    ?swiss a qb:Observation ;
      qb:dataSet dataset:BEW-RAUM-ZEIT-HEL ;
      <https://ld.stadt-zuerich.ch/statistics/property/RAUM> ?Location ;
      <https://ld.stadt-zuerich.ch/statistics/property/ZEIT> ?Time .
    
  ?Location owl:sameAs ?WikidataUID ;
        skos:broader <https://ld.stadt-zuerich.ch/statistics/code/Quartier> ;
        rdfs:label ?RaumLabel .     

   ?swiss   <https://ld.stadt-zuerich.ch/statistics/property/HEL> <https://ld.stadt-zuerich.ch/statistics/code/HEL1000> .
   ?swiss  <https://ld.stadt-zuerich.ch/statistics/measure/BEW> ?NbrSwiss .
 
        
    ?foreigner a qb:Observation ;
      qb:dataSet dataset:BEW-RAUM-ZEIT-HEL ;
      <https://ld.stadt-zuerich.ch/statistics/property/RAUM> ?Location ;
      <https://ld.stadt-zuerich.ch/statistics/property/ZEIT> ?Time .
    
  ?Location owl:sameAs ?WikidataUID ;
        skos:broader <https://ld.stadt-zuerich.ch/statistics/code/Quartier> ;
        rdfs:label ?RaumLabel .     

   ?foreigner   <https://ld.stadt-zuerich.ch/statistics/property/HEL> <https://ld.stadt-zuerich.ch/statistics/code/HEL2000> .
   ?foreigner  <https://ld.stadt-zuerich.ch/statistics/measure/BEW> ?NbrForeign .
 
        BIND((?NbrForeign / (?NbrSwiss + ?NbrForeign) *100) AS ?PercForeign)
        
  }}
ORDER BY ?RaumLabel ?Time ?NameOfCountry
LIMIT 100
```

<a id="40" />

## Cristina Sarasua  


<a id="50" />

## Matthias Mazenauer


