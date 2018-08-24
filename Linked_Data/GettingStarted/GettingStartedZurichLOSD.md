# Contents
- <a href="#10"> 1 Getting started </a>
- <a href="#20"> 2 Available datasets </a>
- <a href="#30"> 3 Follow your nose </a>
  - <a href="#31"> 3.1 Narrow down a query: population example </a>
  - <a href="#32"> 3.2 Spatial units in Zurich: filter on time </a>
  - <a href="#33"> 3.3 Population over time: filter on space </a>
- <a href="#40"> 4 Assess variable levels: instrument example </a>
- <a href="#50"> 5 Combine datasets </a> 
  - <a href="#51"> 5.1 birth and death example </a>
  - <a href="#52"> 5.2 population density example </a>
- <a href="#60"> 6 Maps </a>

<a id="10" />

# 1 Getting started 
The City of Zurich provides linked open statistical data (LOSD). How can the data be analyzed? This document shows a few basic applications using the programming language SPARQL. Additional information on SPARQL and LOSD can be found here:

- SPARQL: [tutorial](https://docs.data.world/tutorials/sparql/), [slides](http://linked-data-training.zazuko.com/SPARQL/index.html#1), [video](https://youtu.be/IUyzwwwIJSk)
- LOSD: [City of Zurich linked data manual](https://github.com/statistikstadtzuerich/documentation/blob/master/Linked_Data/Manual/LOSD_Manual_of_Statistik_Stadt_Zurich.ipynb)
 
The data analyses should be executed on the following webpage, called **SPARQL endpoint** of the City of Zurich: [https://ld.stadt-zuerich.ch/sparql/](https://ld.stadt-zuerich.ch/sparql/).

<a id="20" />

# 2 Available datasets
Which datasets are available on the linked data platform by the City of Zurich? This can be assessed with the following code; copy the code below to the [SPARQL endpoint](https://ld.stadt-zuerich.ch/sparql/) and run the play button in the right upper corner. The core of this query means: find subjects that are of class *DataSet*. Prefixes are used to improve the readability of the code.
```SPARQL
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX qb: <http://purl.org/linked-data/cube#>
SELECT * 
WHERE
  {GRAPH <https://linked.opendata.swiss/graph/zh/statistics> {
    ?DataSet a qb:DataSet ;
      rdfs:label ?DataSetLabel .
  }}
```

The query can be narrowed down by **dataset measure**, for example limited to **datasets with people** (i.e. the dataset measure is people and not kilograms, workplaces, or cars):
```SPARQL
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX unit: <https://ld.stadt-zuerich.ch/statistics/unit/>
PREFIX attr: <http://purl.org/linked-data/sdmx/2009/attribute#>
SELECT * 
WHERE
  {GRAPH <https://linked.opendata.swiss/graph/zh/statistics> {
    ?DataSet a qb:DataSet ;
      rdfs:label ?DataSetLabel ;   
   attr:unitMeasure unit:personen .
  }}
```

Datasets can be listed **by topic**:
```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
PREFIX qb: <http://purl.org/linked-data/cube#>
SELECT ?topicLabel ?datasetLabel 
WHERE 
  {GRAPH <https://linked.opendata.swiss/graph/zh/statistics> {
    ?topic a <https://ld.stadt-zuerich.ch/schema/Category> ;
      rdfs:label ?topicLabel ;
      skos:narrower* ?dataset .
    ?dataset a qb:DataSet ;
      rdfs:label ?datasetLabel .
  }} 
 ORDER BY ?topicLabel ?datasetLabel
```

![topic list](images/1_topic.PNG)

Sometimes it is helpful to search for **text patterns in dataset labels** (e.g. bev for Bevölkerung/population)
```SPARQL
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX unit: <https://ld.stadt-zuerich.ch/statistics/unit/>
PREFIX attr: <http://purl.org/linked-data/sdmx/2009/attribute#>
SELECT * 
WHERE
  {GRAPH <https://linked.opendata.swiss/graph/zh/statistics> {
    ?DataSet a qb:DataSet ;
      rdfs:label ?DataSetLabel ;   
   attr:unitMeasure unit:personen .
    FILTER REGEX(LCASE(STR(?DataSetLabel)), "bev") .
  }}
```

![text pattern](images/2_regex.PNG)

<a id="30" />

# 3 Follow your nose

<a id="31" />

## 3.1 Narrow down a query: population example
It is more helpful to assess data at **observation** than at dataset level. If we are interested in the development of the population in City of Zurich the dataset BEW-RAUM-ZEIT contains all information needed; this dataset could be found with searching by topic or text pattern. The core the following code means: which subjects have a class *observation* and belong to the **dataset BEW-RAUM-ZEIT**. The output is limited to 10 elements, since the dataset might consist of numerous elements.
```SPARQL
PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX dataset: <https://ld.stadt-zuerich.ch/statistics/dataset/>
SELECT *
WHERE{ 
  GRAPH <https://linked.opendata.swiss/graph/zh/statistics>{
    ?obser a qb:Observation ;
      qb:dataSet dataset:BEW-RAUM-ZEIT .
  }}
LIMIT 10
```

Linked data analysis is intuitive: look at the output of the code to develop further steps; simply follow your nose! With the 'follow your nose' approach the query can be narrowed down. For example you can click this output element:
[https://ld.stadt-zuerich.ch/statistics/observation/BEW/R00024/Z31122017](https://ld.stadt-zuerich.ch/statistics/observation/BEW/R00024/Z31122017)
The components BEW, RAUM, ZEIT are of particular interest. By clicking on them, you see that BEW is of type **MeasureProperty**, RAUM and ZEIT are of type **DimensionProperty**.
This information is used to define variables for population, time, and space. For the variable ?space labels are needed, since the its variable name is not self-explanatory.
```SPARQL
PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX dataset: <https://ld.stadt-zuerich.ch/statistics/dataset/>
PREFIX measure: <https://ld.stadt-zuerich.ch/statistics/measure/>
PREFIX dimension: <https://ld.stadt-zuerich.ch/statistics/property/>
SELECT *
WHERE{ 
  GRAPH <https://linked.opendata.swiss/graph/zh/statistics>{
    ?obser a qb:Observation ;
      qb:dataSet dataset:BEW-RAUM-ZEIT ;     
      measure:BEW ?population ;
      dimension:RAUM ?space ;
      dimension:ZEIT ?time . 
   ?space rdfs:label ?spaceLabel.  
  }}
LIMIT 10
```

<a id="32" />

## 3.2 Spatial units in Zurich: filter on time
To assess spatial units in Zurich a **point in time is filtered** (e.g. December 31, 2017). This provides an overview over **spatial units** available for December 31, 2017.
```SPARQL
PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX dataset: <https://ld.stadt-zuerich.ch/statistics/dataset/>
PREFIX measure: <https://ld.stadt-zuerich.ch/statistics/measure/>
PREFIX dimension: <https://ld.stadt-zuerich.ch/statistics/property/>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
SELECT ?obser ?spaceLabel ?population
WHERE{ 
  GRAPH <https://linked.opendata.swiss/graph/zh/statistics>{
    ?obser a qb:Observation ;
      qb:dataSet dataset:BEW-RAUM-ZEIT ;     
      measure:BEW ?population ;
      dimension:RAUM ?space ;
      dimension:ZEIT ?time .
    ?space rdfs:label ?spaceLabel.
    FILTER(?time = "2017-12-31"^^xsd:date) 
  }}
ORDER BY ?space
```

<a id="33" />

## 3.3 Population over time: filter on space
If you scroll down in the output of the previous query, you can find the observation of the [entire City of Zurich](https://ld.stadt-zuerich.ch/statistics/observation/BEW/R30000/Z31122017). Its spatial dimension is R30000. In the code below the filter is set to the entire city to assess the **population over time**. For plotting the ?time variable a converted to a string. The plot is made with the pivot tool below the output.
```SPARQL
PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX dataset: <https://ld.stadt-zuerich.ch/statistics/dataset/>
PREFIX measure: <https://ld.stadt-zuerich.ch/statistics/measure/>
PREFIX dimension: <https://ld.stadt-zuerich.ch/statistics/property/>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
PREFIX code: <https://ld.stadt-zuerich.ch/statistics/code/>
SELECT ?year ?population
WHERE{ 
  GRAPH <https://linked.opendata.swiss/graph/zh/statistics>{
    ?obser a qb:Observation ;
      qb:dataSet dataset:BEW-RAUM-ZEIT ;     
      measure:BEW ?population ;
      dimension:RAUM ?space ;
      dimension:ZEIT ?time .
    ?space rdfs:label ?spaceLabel.
    FILTER(?space = code:R30000) 
    BIND (STR(?time) AS ?year)
  }}
ORDER BY ?year
```
![population](images/3_population.PNG)

<a id="40" />

# 4 Assess variable levels: instrument example
In linked data analyis it is crucial to understand the data structure; that means to know the **values per variable**. This is demonstrated with an example from a music school (Musikschule Konservatorium Zürich MKZ) and the question which instrument is played by how many students? How are the trends over time?
First, all dataset variables are assessed to **fix variables at specific values**, here the music school and the space (fixed to the entire City of Zurich). Second, the measures over the remaining (not fixed) values are summarized; here the sum is taken over instrument and time:
```SPARQL
PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX dataset: <https://ld.stadt-zuerich.ch/statistics/dataset/>
PREFIX measure: <https://ld.stadt-zuerich.ch/statistics/measure/>
PREFIX dimension: <https://ld.stadt-zuerich.ch/statistics/property/>
PREFIX code: <https://ld.stadt-zuerich.ch/statistics/code/>
SELECT ?instruLabel ?year (SUM(?students) AS ?students)
WHERE{ 
  GRAPH <https://linked.opendata.swiss/graph/zh/statistics>{
    ?obser a qb:Observation ;
      qb:dataSet dataset:SCH-RAUM-ZEIT-BTA-SST ; 
      measure:SCH ?students ;
      dimension:ZEIT ?time ; 
      dimension:BTA code:BTA7701 ; #music school            
      dimension:RAUM code:R30000; #entire city               
      dimension:SST ?instru . 
    ?instru rdfs:label ?instruLabel.
    BIND (STR(?time) AS ?year)
  }}
GROUP BY ?instruLabel ?year  
ORDER BY ?instruLabel ?year 
```
In this music school piano is the most popular instrument, followed by guitar and violin. The data can be plotted with the pivot tool again:
![instruments](images/4_instruments.PNG)

<a id="50" />

# 5 Combine datasets 

<a id="51" />

## 5.1 Birth and death example
Linked data analysis becomes particularly helpful, if different datasets are combined. In the following example births and deaths over time are combined, and natural change (births minus deaths) is calculated. Bringing datasets together is [different in SPARQL](http://www.cs.utexas.edu/~cannata/cs345/New%20Class%20Notes/15%20JoinsinSPARQL%20(3).pdf) than in convetional table analysis: the two datasets are **simply linked by additional triples**. 
```SPARQL
PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX dataset: <https://ld.stadt-zuerich.ch/statistics/dataset/>
PREFIX measure: <https://ld.stadt-zuerich.ch/statistics/measure/>
PREFIX dimension: <https://ld.stadt-zuerich.ch/statistics/property/>
PREFIX code: <https://ld.stadt-zuerich.ch/statistics/code/>
SELECT ?year ?birth ?death ?natChange
WHERE {
  GRAPH <https://linked.opendata.swiss/graph/zh/statistics>{
    ?obsbirth a qb:Observation ;
      qb:dataSet dataset:GEB-RAUM-ZEIT ;  
      measure:GEB ?birth ;  
      dimension:RAUM ?space ; 
      dimension:ZEIT ?time .
    ?obsdeath a qb:Observation ;
      qb:dataSet dataset:GES-RAUM-ZEIT ; 
      measure:GES ?death ;        
      dimension:RAUM ?space ; 
      dimension:ZEIT ?time .    
 FILTER (?space = code:R30000)
    BIND((?birth - ?death) AS ?natChange)
 BIND (STR(?time) AS ?year)
 }}
ORDER BY ?year
```

![birth and death](images/5_birth-death.PNG)

<a id="52" />

## 5.2 Population density example
The combination of the two datasets **population and area** statistics allows calculation **population density**. As in the birth and death example the dataset linkage is based on additional triples. 
The population density is calculated as people per hectare; however only land without forest and no waterbodies. Therefore, a land cover filter is used (BBA1000: land without forest, no water).
```SPARQL
PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX dataset: <https://ld.stadt-zuerich.ch/statistics/dataset/>
PREFIX measure: <https://ld.stadt-zuerich.ch/statistics/measure/>
PREFIX dimension: <https://ld.stadt-zuerich.ch/statistics/property/>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
PREFIX code: <https://ld.stadt-zuerich.ch/statistics/code/>
SELECT ?year ?population ?area ?density
WHERE{
  GRAPH <https://linked.opendata.swiss/graph/zh/statistics>{
    ?obspop a qb:Observation ;
      qb:dataSet dataset:BEW-RAUM-ZEIT ;     
      measure:BEW ?population ;
      dimension:RAUM ?space ;
      dimension:ZEIT ?time .
    ?obsarea a qb:Observation ;
      qb:dataSet dataset:STF-RAUM-ZEIT-BBA ; 
      measure:STF ?area ;
      dimension:BBA ?cover ; 
      dimension:RAUM ?space ; 
      dimension:ZEIT ?time .
    FILTER ((?space = code:R30000) && (?cover = code:BBA1000)) 
    BIND((?population/?area) AS ?density)
    BIND(STR(?time) AS ?year)
  }}
ORDER BY ?year
```
![population density](images/6_population-density.PNG)

<a id="60" />

# 6 Maps
Perimeter geometries within the City of Zurich (e.g. district/Stadtkreis) can be used to generate maps. By clicking on map symbols the district population is displayed.
```SPARQL
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX dataset: <https://ld.stadt-zuerich.ch/statistics/dataset/>
PREFIX measure: <https://ld.stadt-zuerich.ch/statistics/measure/>
PREFIX dimension: <https://ld.stadt-zuerich.ch/statistics/property/>
PREFIX code: <https://ld.stadt-zuerich.ch/statistics/code/>
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
PREFIX geo: <http://www.opengis.net/ont/geosparql#>
SELECT * 
WHERE {GRAPH <https://linked.opendata.swiss/graph/zh/statistics> {
  ?obs a qb:Observation ;
    qb:dataSet dataset:BEW-RAUM-ZEIT ; 
    dimension:RAUM ?space ; 
    dimension:ZEIT "2000-12-31"^^xsd:date ;
    measure:BEW ?population .                                      
  ?space rdfs:label ?spaceLabel ;
    skos:broader code:Kreis ;          
    geo:hasGeometry/geo:asWKT ?shape .
  BIND(CONCAT(STR(?spaceLabel), ": ", STR(?population)) AS ?shapeLabel)
  }} 
```

![map](images/7_map.PNG)
