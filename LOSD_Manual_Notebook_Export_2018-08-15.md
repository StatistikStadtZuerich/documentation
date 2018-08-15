
<h1>Table of Contents<span class="tocSkip"></span></h1>
<div class="toc"><ul class="toc-item"><li><span><a href="#Introduction" data-toc-modified-id="Introduction-1"><span class="toc-item-num">1&nbsp;&nbsp;</span>Introduction</a></span></li><li><span><a href="#Linked-Open-Data-(LOD)" data-toc-modified-id="Linked-Open-Data-(LOD)-2"><span class="toc-item-num">2&nbsp;&nbsp;</span>Linked Open Data (LOD)</a></span><ul class="toc-item"><li><span><a href="#Basics" data-toc-modified-id="Basics-2.1"><span class="toc-item-num">2.1&nbsp;&nbsp;</span>Basics</a></span><ul class="toc-item"><li><span><a href="#Open-Data-and-Linked-Data:-definition-and-benefits" data-toc-modified-id="Open-Data-and-Linked-Data:-definition-and-benefits-2.1.1"><span class="toc-item-num">2.1.1&nbsp;&nbsp;</span>Open Data and Linked Data: definition and benefits</a></span></li><li><span><a href="#Graph-Database-vs.-Relational-Database" data-toc-modified-id="Graph-Database-vs.-Relational-Database-2.1.2"><span class="toc-item-num">2.1.2&nbsp;&nbsp;</span>Graph Database vs. Relational Database</a></span></li><li><span><a href="#Basics-of-Linked-Data" data-toc-modified-id="Basics-of-Linked-Data-2.1.3"><span class="toc-item-num">2.1.3&nbsp;&nbsp;</span>Basics of Linked Data</a></span></li><li><span><a href="#Triple-Storage-and-Resource-Description-Framework-(RDF)" data-toc-modified-id="Triple-Storage-and-Resource-Description-Framework-(RDF)-2.1.4"><span class="toc-item-num">2.1.4&nbsp;&nbsp;</span>Triple Storage and Resource Description Framework (RDF)</a></span></li><li><span><a href="#RDF-vocabulary" data-toc-modified-id="RDF-vocabulary-2.1.5"><span class="toc-item-num">2.1.5&nbsp;&nbsp;</span>RDF vocabulary</a></span></li><li><span><a href="#RDF-serialization" data-toc-modified-id="RDF-serialization-2.1.6"><span class="toc-item-num">2.1.6&nbsp;&nbsp;</span>RDF serialization</a></span></li><li><span><a href="#RDF-Data-Cube-model" data-toc-modified-id="RDF-Data-Cube-model-2.1.7"><span class="toc-item-num">2.1.7&nbsp;&nbsp;</span>RDF Data Cube model</a></span></li><li><span><a href="#How-to-query-Linked-Data:-SPARQL" data-toc-modified-id="How-to-query-Linked-Data:-SPARQL-2.1.8"><span class="toc-item-num">2.1.8&nbsp;&nbsp;</span>How to query Linked Data: SPARQL</a></span></li><li><span><a href="#SPARQL-vs.-SQL" data-toc-modified-id="SPARQL-vs.-SQL-2.1.9"><span class="toc-item-num">2.1.9&nbsp;&nbsp;</span>SPARQL vs. SQL</a></span></li></ul></li></ul></li><li><span><a href="#Data-Model" data-toc-modified-id="Data-Model-3"><span class="toc-item-num">3&nbsp;&nbsp;</span>Data Model</a></span><ul class="toc-item"><li><span><a href="#Concepts-of-the-Historic-Data" data-toc-modified-id="Concepts-of-the-Historic-Data-3.1"><span class="toc-item-num">3.1&nbsp;&nbsp;</span>Concepts of the Historic Data</a></span></li><li><span><a href="#Concepts-of-the-RDF-Data-Cube" data-toc-modified-id="Concepts-of-the-RDF-Data-Cube-3.2"><span class="toc-item-num">3.2&nbsp;&nbsp;</span>Concepts of the RDF Data Cube</a></span></li><li><span><a href="#Other-important-concepts" data-toc-modified-id="Other-important-concepts-3.3"><span class="toc-item-num">3.3&nbsp;&nbsp;</span>Other important concepts</a></span></li></ul></li><li><span><a href="#SPARQL-Interface" data-toc-modified-id="SPARQL-Interface-4"><span class="toc-item-num">4&nbsp;&nbsp;</span>SPARQL-Interface</a></span><ul class="toc-item"><li><span><a href="#Example-Query:-all-DataSets" data-toc-modified-id="Example-Query:-all-DataSets-4.1"><span class="toc-item-num">4.1&nbsp;&nbsp;</span>Example Query: all DataSets</a></span><ul class="toc-item"><li><span><a href="#Explanation" data-toc-modified-id="Explanation-4.1.1"><span class="toc-item-num">4.1.1&nbsp;&nbsp;</span>Explanation</a></span></li></ul></li><li><span><a href="#Example-Query:-specific-DataSets" data-toc-modified-id="Example-Query:-specific-DataSets-4.2"><span class="toc-item-num">4.2&nbsp;&nbsp;</span>Example Query: specific DataSets</a></span><ul class="toc-item"><li><span><a href="#Explanation" data-toc-modified-id="Explanation-4.2.1"><span class="toc-item-num">4.2.1&nbsp;&nbsp;</span>Explanation</a></span></li></ul></li><li><span><a href="#Example-Query:-the-first-100-Triples" data-toc-modified-id="Example-Query:-the-first-100-Triples-4.3"><span class="toc-item-num">4.3&nbsp;&nbsp;</span>Example Query: the first 100 Triples</a></span><ul class="toc-item"><li><span><a href="#Explanation" data-toc-modified-id="Explanation-4.3.1"><span class="toc-item-num">4.3.1&nbsp;&nbsp;</span>Explanation</a></span></li></ul></li><li><span><a href="#Example-Query:-total-number-of-Triples" data-toc-modified-id="Example-Query:-total-number-of-Triples-4.4"><span class="toc-item-num">4.4&nbsp;&nbsp;</span>Example Query: total number of Triples</a></span><ul class="toc-item"><li><span><a href="#Explanation" data-toc-modified-id="Explanation-4.4.1"><span class="toc-item-num">4.4.1&nbsp;&nbsp;</span>Explanation</a></span></li></ul></li><li><span><a href="#Example-Query:-number-of-Observations-per-DataSet" data-toc-modified-id="Example-Query:-number-of-Observations-per-DataSet-4.5"><span class="toc-item-num">4.5&nbsp;&nbsp;</span>Example Query: number of Observations per DataSet</a></span><ul class="toc-item"><li><span><a href="#Explanation" data-toc-modified-id="Explanation-4.5.1"><span class="toc-item-num">4.5.1&nbsp;&nbsp;</span>Explanation</a></span></li></ul></li><li><span><a href="#Example-Query:-Filter-with-Regular-Expressions" data-toc-modified-id="Example-Query:-Filter-with-Regular-Expressions-4.6"><span class="toc-item-num">4.6&nbsp;&nbsp;</span>Example Query: Filter with Regular Expressions</a></span><ul class="toc-item"><li><span><a href="#Explanation" data-toc-modified-id="Explanation-4.6.1"><span class="toc-item-num">4.6.1&nbsp;&nbsp;</span>Explanation</a></span></li></ul></li><li><span><a href="#Example-Query:-plot-area-without-forest-in-Zurich" data-toc-modified-id="Example-Query:-plot-area-without-forest-in-Zurich-4.7"><span class="toc-item-num">4.7&nbsp;&nbsp;</span>Example Query: plot area without forest in Zurich</a></span><ul class="toc-item"><li><span><a href="#Explanation" data-toc-modified-id="Explanation-4.7.1"><span class="toc-item-num">4.7.1&nbsp;&nbsp;</span>Explanation</a></span></li></ul></li><li><span><a href="#Example-Query:-Kennzahlen-as-MeasureProperties" data-toc-modified-id="Example-Query:-Kennzahlen-as-MeasureProperties-4.8"><span class="toc-item-num">4.8&nbsp;&nbsp;</span>Example Query: Kennzahlen as MeasureProperties</a></span><ul class="toc-item"><li><span><a href="#Explanation" data-toc-modified-id="Explanation-4.8.1"><span class="toc-item-num">4.8.1&nbsp;&nbsp;</span>Explanation</a></span></li></ul></li><li><span><a href="#Example-Query:-units-of-every-Kennzahl" data-toc-modified-id="Example-Query:-units-of-every-Kennzahl-4.9"><span class="toc-item-num">4.9&nbsp;&nbsp;</span>Example Query: units of every Kennzahl</a></span><ul class="toc-item"><li><span><a href="#Explanation" data-toc-modified-id="Explanation-4.9.1"><span class="toc-item-num">4.9.1&nbsp;&nbsp;</span>Explanation</a></span></li></ul></li><li><span><a href="#Example-Query:-Groups-as-DimensionProperties" data-toc-modified-id="Example-Query:-Groups-as-DimensionProperties-4.10"><span class="toc-item-num">4.10&nbsp;&nbsp;</span>Example Query: Groups as DimensionProperties</a></span><ul class="toc-item"><li><span><a href="#Explanation" data-toc-modified-id="Explanation-4.10.1"><span class="toc-item-num">4.10.1&nbsp;&nbsp;</span>Explanation</a></span></li></ul></li><li><span><a href="#Example-Query:-Metadata-as-AttributeProperties" data-toc-modified-id="Example-Query:-Metadata-as-AttributeProperties-4.11"><span class="toc-item-num">4.11&nbsp;&nbsp;</span>Example Query: Metadata as AttributeProperties</a></span><ul class="toc-item"><li><span><a href="#Explanation" data-toc-modified-id="Explanation-4.11.1"><span class="toc-item-num">4.11.1&nbsp;&nbsp;</span>Explanation</a></span></li></ul></li><li><span><a href="#Example-Query:-Groupcodes-as-Concepts" data-toc-modified-id="Example-Query:-Groupcodes-as-Concepts-4.12"><span class="toc-item-num">4.12&nbsp;&nbsp;</span>Example Query: Groupcodes as Concepts</a></span></li><li><span><a href="#Example-Query:-Hierarchies" data-toc-modified-id="Example-Query:-Hierarchies-4.13"><span class="toc-item-num">4.13&nbsp;&nbsp;</span>Example Query: Hierarchies</a></span></li><li><span><a href="#Example-Query:-Spatial-Hierarchies" data-toc-modified-id="Example-Query:-Spatial-Hierarchies-4.14"><span class="toc-item-num">4.14&nbsp;&nbsp;</span>Example Query: Spatial Hierarchies</a></span><ul class="toc-item"><li><span><a href="#Explanation" data-toc-modified-id="Explanation-4.14.1"><span class="toc-item-num">4.14.1&nbsp;&nbsp;</span>Explanation</a></span></li></ul></li><li><span><a href="#Example-Query:-A-DataSet" data-toc-modified-id="Example-Query:-A-DataSet-4.15"><span class="toc-item-num">4.15&nbsp;&nbsp;</span>Example Query: A DataSet</a></span><ul class="toc-item"><li><span><a href="#Explanation" data-toc-modified-id="Explanation-4.15.1"><span class="toc-item-num">4.15.1&nbsp;&nbsp;</span>Explanation</a></span></li></ul></li><li><span><a href="#Example-Query:-Observations-of-a-DataSet" data-toc-modified-id="Example-Query:-Observations-of-a-DataSet-4.16"><span class="toc-item-num">4.16&nbsp;&nbsp;</span>Example Query: Observations of a DataSet</a></span></li><li><span><a href="#Example-Query:-Slices-of-a-DataSet" data-toc-modified-id="Example-Query:-Slices-of-a-DataSet-4.17"><span class="toc-item-num">4.17&nbsp;&nbsp;</span>Example Query: Slices of a DataSet</a></span></li><li><span><a href="#Example-Query:-Shapes-of-a-DataSet" data-toc-modified-id="Example-Query:-Shapes-of-a-DataSet-4.18"><span class="toc-item-num">4.18&nbsp;&nbsp;</span>Example Query: Shapes of a DataSet</a></span><ul class="toc-item"><li><span><a href="#Explanation" data-toc-modified-id="Explanation-4.18.1"><span class="toc-item-num">4.18.1&nbsp;&nbsp;</span>Explanation</a></span></li></ul></li><li><span><a href="#Example-Query:-Metadata-of-a-DataSet" data-toc-modified-id="Example-Query:-Metadata-of-a-DataSet-4.19"><span class="toc-item-num">4.19&nbsp;&nbsp;</span>Example Query: Metadata of a DataSet</a></span></li><li><span><a href="#Example-Query:-Conjunction-of-Kennzahlen" data-toc-modified-id="Example-Query:-Conjunction-of-Kennzahlen-4.20"><span class="toc-item-num">4.20&nbsp;&nbsp;</span>Example Query: Conjunction of Kennzahlen</a></span></li><li><span><a href="#Example-Query:-Time-and-Date" data-toc-modified-id="Example-Query:-Time-and-Date-4.21"><span class="toc-item-num">4.21&nbsp;&nbsp;</span>Example Query: Time and Date</a></span></li></ul></li><li><span><a href="#REST-Interface" data-toc-modified-id="REST-Interface-5"><span class="toc-item-num">5&nbsp;&nbsp;</span>REST-Interface</a></span><ul class="toc-item"><li><span><a href="#Basics" data-toc-modified-id="Basics-5.1"><span class="toc-item-num">5.1&nbsp;&nbsp;</span>Basics</a></span></li><li><span><a href="#Search-API" data-toc-modified-id="Search-API-5.2"><span class="toc-item-num">5.2&nbsp;&nbsp;</span>Search-API</a></span></li><li><span><a href="#All-Datasets" data-toc-modified-id="All-Datasets-5.3"><span class="toc-item-num">5.3&nbsp;&nbsp;</span>All Datasets</a></span></li><li><span><a href="#Dataset" data-toc-modified-id="Dataset-5.4"><span class="toc-item-num">5.4&nbsp;&nbsp;</span>Dataset</a></span></li><li><span><a href="#Slice" data-toc-modified-id="Slice-5.5"><span class="toc-item-num">5.5&nbsp;&nbsp;</span>Slice</a></span></li><li><span><a href="#Shape" data-toc-modified-id="Shape-5.6"><span class="toc-item-num">5.6&nbsp;&nbsp;</span>Shape</a></span></li><li><span><a href="#Metadata" data-toc-modified-id="Metadata-5.7"><span class="toc-item-num">5.7&nbsp;&nbsp;</span>Metadata</a></span></li><li><span><a href="#API-Tests" data-toc-modified-id="API-Tests-5.8"><span class="toc-item-num">5.8&nbsp;&nbsp;</span>API-Tests</a></span></li></ul></li><li><span><a href="#Hydra-Client" data-toc-modified-id="Hydra-Client-6"><span class="toc-item-num">6&nbsp;&nbsp;</span>Hydra-Client</a></span></li><li><span><a href="#Use-of-sszvis" data-toc-modified-id="Use-of-sszvis-7"><span class="toc-item-num">7&nbsp;&nbsp;</span>Use of sszvis</a></span></li><li><span><a href="#OpenSource-projects-about-STIP,-LOSD-and-sszvis" data-toc-modified-id="OpenSource-projects-about-STIP,-LOSD-and-sszvis-8"><span class="toc-item-num">8&nbsp;&nbsp;</span>OpenSource projects about STIP, LOSD and sszvis</a></span></li></ul></div>

# Introduction
Statistik Stadt Zürich is replacing its statistical yearbook with a web-based solution (stat.stadt-zuerich.ch). The content can be accessed directly or programmatically:
* through a REST-interface
* through a SPARQL-interface

This document describes the available data and how it is queried by interested parties.


# Linked Open Data (LOD)
The data is provided in the form of Linked Open Data (LOD), or more precisely in the form of a RDF Data Cube. The data is queried by means of the SPARQL Protocol And RDF Query Language or SPARQL in short.

The [Linked Data crash course](http://www.linkeddatatools.com/semantic-web-basics) offers a short introduction for users new to graph databases and triple storages (in contrast to relational databases). The RDF Data Cube model in particular, is intorudced in section 3.2.

## Basics
Linked data is a topic far too big to be completely covered here. Likewise, a complete SPARQL tutorial would go far beyond the scope of this document (and was already done plenty of times). However, the most important concepts shall be mentioned and linked with their specification or other useful sources. 

### Open Data and Linked Data: definition and benefits
* The European Commission offers a nice [presentation](https://joinup.ec.europa.eu/sites/default/files/document/2015-05/d2.1.2_training_module_1.2_introduction_to_linked_data_v1.00_en.pdf) on the topic

### Graph Database vs. Relational Database
* See [this section](http://www.linkeddatatools.com/introducing-rdf) of the Linked Data crash course
* or [this RDF/OWL lecture](https://www.scss.tcd.ie/Owen.Conlan/CS7063/06%20Introduction%20to%20OWL%20(1%20Lecture).ppt.pdf) for a nice introduction to the subject
* [This site](https://lod-cloud.net/) provides an interactive graph of the LOD cloud with a plethora of datasets and SPARQL endpoints

### Basics of Linked Data
* URIs for the designation, RDF for the description and SPARQL for the querying of data
* See the aforementioned [this RDF/OWL lecture](https://www.scss.tcd.ie/Owen.Conlan/CS7063/06%20Introduction%20to%20OWL%20(1%20Lecture).ppt.pdf)

### Triple Storage and Resource Description Framework (RDF)
* Triple structure: **Subject** -> **Predicate** -> **Object**
* [RDF Specification](http://www.w3.org/TR/2014/REC-rdf11-concepts-20140225/Overview.html)
* Again, [the RDF/OWL lecture](https://www.scss.tcd.ie/Owen.Conlan/CS7063/06%20Introduction%20to%20OWL%20(1%20Lecture).ppt.pdf) offers one of the best introductions to the subject

### RDF vocabulary
* RDFS (RDF Scheme), OWL (Web Ontology Language) and many more
* See [this introduction]() to semantic modelling and why we need vocabularies
* This document uses primarily the following vocabularies:

| Vocabulary | Namespace |
| :--------- | :-------- |
| [xsd](https://www.w3.org/XML/Schema) | $<http://www.w3.org/2001/XMLSchema#>$ |
| [rdf](https://www.w3.org/TR/rdf11-concepts/) | $<http://www.w3.org/1999/02/22-rdf-syntax-ns#>$ |
| [rdfs](https://www.w3.org/TR/rdf-schema/) | $<http://www.w3.org/2000/01/rdf-schema#>$ |
| [owl](https://www.w3.org/TR/owl2-overview/) | $<http://www.w3.org/2002/07/owl#>$ |
| [skos](https://www.w3.org/TR/swbp-skos-core-guide/) | $<http://www.w3.org/2004/02/skos/core#>$ |
| [foaf](http://xmlns.com/foaf/spec/) | $<http://xmlns.com/foaf/0.1/>$ |
| [qb](https://www.w3.org/TR/vocab-data-cube/) | $<http://purl.org/linked-data/cube#>$ |
| [dcterms](http://dublincore.org/documents/dc-rdf/) | $<http://purl.org/dc/terms/>$ |
| [qudt](http://www.qudt.org/release2/qudt-catalog.html) | $<http://qudt.org/schema/qudt#unit>$ |

### RDF serialization
* [JSON](https://www.w3.org/TR/json-ld/) is a common format for data serialization and messaging
* [TURTLE](https://www.w3.org/TR/turtle/) is especially useful because it conforms with the SPARQL syntax

### RDF Data Cube model
* See the [Specification](https://www.w3.org/TR/vocab-data-cube/) or section 3.2 of this document.

### How to query Linked Data: SPARQL 
* See the [Specification](https://www.w3.org/TR/sparql11-query/),
* the [cheat-sheet](http://www.iro.umontreal.ca/~lapalme/ift6281/sparql-1_1-cheat-sheet.pdf) for a summary of the syntax
* and the [wikibook](https://en.wikibooks.org/wiki/SPARQL) for more examples

### SPARQL vs. SQL
* See [this comparison](https://www.cambridgesemantics.com/blog/semantic-university/learn-sparql/sparql-vs-sql/)

# Data Model

## Concepts of the Historic Data
**Observation**: As the basis of the historic data, observations are the individual measurements of the statistics with a code structure of the form:
```
ZddmmyyyyRrrrrrKENGR10000GR20000GR30000GR40000GR50000
```
where the format(length) is equal to Char(53).

**Kennzahl**:
The Kennzahl represents the dimension that is measured by an observation in dependance of other dimensions. If we look at an observation as a function, then the Kennzahl serves as its output (all other dimensions as input). Examples of Kennzahlen are: 
* "BEW" for population
* "STF" for plot area (in *m^2^*)
* "ZUZ" for in-migration 
* "WSS" for water pollutant (in *mg/l*) 
* etc. 

The format(length) is Char(3). "KEN" serves as the placeholder in the observation code. For an observation reading "residential population in dependance of homeland, sex and urban district in the year 2016", the Kennzahl would correspond to "BEW" for residential population:
```
Z31122016R00012BEWHEL1000SEX0001XXX0000XXX0000XXX0000 
with a value of BEW = 206 persons
Z31122016R00011BEWHEL2000SEX0002XXX0000XXX0000XXX0000 
with a value of BEW = 414 persons
```
are two examples with their respective measurements.

**Groups**: 
Groups are equivalent to dimensions and describe how a Kennzahl is divided into subsets. In other words, groups correspond to the input parameters in the function analogy. They also determine the hierarchy of an observation or measurement. Group examples are: 
* "BEW" for residence permit (not to be confused with the Kennzahl!)
* "HEL" for homeland
* "SEX" for sex 
* "ALT" for age
* "TIG" for animal species 
* etc. 

The format(length) is also Char(3) and "GR1",...,"GR5" serve as the placeholders in the observation code. An observation may comprise a maximum of 5 groups where missing groups are denoted with "XXX" (see the examples above). It is important to note that, despite being dimensions as well, "Zeit" and "Raum" are regarded separately. Both are fixed parts of each and every observation with their own format(length). 

**Zeit**: 
A special type of dimension with identifier "Z" and groupcode of format(length) Char(9). Missing or unknown groupvalues are denoted with "X". Examples are "ZXXXX2016" for the year 2016 or "Z24121950" for the 24th Dec. in 1950.

**Raum**: 
A special type of dimension with identifier "R" and groupcode of format(length) Char(6). Examples are "R30000" for Zurich or "R00011" for the urban district "Rathaus" in Zurich.

**Groupcodes**: 
A groupcode is a group identifier paired with its respective value or measurement. A groupvalue has format(length) Char(4) which adds up to a total of Char(7) for the groupcode. In the observation code "0000" corresponds to missing or unknown groupvalues. 

The following figures show excerpts of the statistical yearbooks from the year 1941 and 2016 (taken from the [Statistik Stadt Zurich page](https://www.stadt-zuerich.ch/content/prd/de/index/statistik/publikationen-angebote/publikationen/ssz-magazin/2018-07-17_Das-Ende-der-Jahrbuch-Aera.html)). Such data is first of all mapped to the aforementioned observations, then equipped with metadata (version, source, glossary etc.) and subsequently collected in DataSets of the RDF Data Cube model. 

<img src="attachment:1941.png" style="width:500px" align="left"><img src="attachment:2016.png" style="width:550px" align="left">

## Concepts of the RDF Data Cube

> A statistical data set comprises a collection of observations made at some points across some logical space. The collection can be characterized by a set of dimensions that define what the observation applies to (e.g. time, area, gender) along with metadata describing what has been measured (e.g. economic activity, population), how it was measured and how the observations are expressed (e.g. units, multipliers, status). We can think of the statistical data set as a multi-dimensional space, or hyper-cube, indexed by those dimensions.

The model describes such a data cube, in terms of the Resource Description Framework, primarily with the following concepts:

**qb:DataSet**: A DataSet is a collection of statistical data, most notably observations, that corresponds to a defined structure.   
* Observations of the historic data are collected in DataSets according to the following rule:
```
ZddmmyyyyRrrrrrKENGR10000GR20000GR30000GR40000GR50000 
corresponds to the DataSet 
KEN-RAUM-ZEIT-GR1-GR2-GR3-GR4-GR5
```
where missing groups/dimensions ("XXX") are omitted in the DataSet notation. 
* DataSets are accessed through the node https://ld.stadt-zuerich.ch/statistics/dataset/.

**qb:Observation**: This is the actual data, the measured values. In a statistical table (as in the statistical yearbooks), the observations would be the values in the table cells.
* Observations of the historic data are modified according to the following rule:
```
ZddmmyyyyRrrrrrKENGR10000GR20000GR30000GR40000GR50000 
corresponds to the observation 
KEN/Rrrrrr/Zddmmyyyy/GR10000/GR20000/GR30000/GR40000/GR50000 
in the Data Cube
```
where missing groups/dimensions ("XXX") are omitted in the qb:Observation notation. 
* Observations are accessed through the node https://ld.stadt-zuerich.ch/statistics/observation/.

**qb:MeasureProperty**: The measure components represent the phenomenon being observed.
* Kennzahlen of the historic data are mapped to MeasureProperties.
* Measures are accessed through the node https://ld.stadt-zuerich.ch/statistics/measure/.

**qb:DimensionProperty**: The dimension components serve to identify the observations. A set of values for all the dimension components is sufficient to identify a single observation. Examples of dimensions include the time to which the observation applies, or a geographic region which the observation covers etc. 
* Groups of the historic data are mapped to DimensionProperties.
* Groups are accessed through the node https://ld.stadt-zuerich.ch/statistics/property/.

**qb:AttributeProperty**: The attribute components allow us to qualify and interpret the observed value(s). They enable specification of the units of measure, any scaling factors and metadata such as the status of the observation (e.g. estimated, provisional).
* Only meta and system attributes of the historic data are mapped to AttributeProperties! 
* Attributes are accessed through the node https://ld.stadt-zuerich.ch/statistics/attribute/.
* Units of the MeasureProperties, for instance, are mapped to an independent concept "unit" (namespace $<http://qudt.org/schema/qudt#unit>$).

**qb:Slice**: A subset of observations within a DataSet. Produced by fixing one or more dimensions and refer to all observations with those dimension values as a single entity, a slice. In statistical applications it is common to work with slices in which a single dimension is left unspecified. In particular, to refer to such slices, in which the single free dimension is time, as "Time Series". Within the Data Cube vocabulary however, arbitrary dimensionality slices are allowed and particular types of slice are not denoted differently.
* Slices of a dataset are accessed through the nodes https://ld.stadt-zuerich.ch/statistics/dataset/.../.../slice where the points are placeholders for the DataSet name and SliceKey.

A diagram of the RDF Data Cube model is provided in the following figure. In addition to the official [Data Cube Documentation](https://www.w3.org/TR/vocab-data-cube/) a very informative presentation can be downloaded [here](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=11&ved=0ahUKEwjN68WrvprcAhVC8RQKHd50D2M4ChAWCDMwAA&url=https%3A%2F%2Fweb.imsi.athenarc.gr%2Fredmine%2Fattachments%2Fdownload%2F1018%2FData%2520Cube%2520Vocabulary%2520Overview%2520and%2520Example.pdf&usg=AOvVaw3ujILUzk2T1dLd9ebo2hYW).

<img src="https://www.w3.org/TR/vocab-data-cube/images/qb-fig1.png" style="width:700px" align="left">

## Other important concepts

**Shapes**: Shape expressions (written in RDF) are used to declare various  constraints for the components of a RDF graph (or Data Cube). Informally, a shape is a set of conditions that determine how to validate a node (of a graph), based on the values of properties and other characteristics of the node, with the Shapes Constraint Language (SHACL). Shapes and SHACL represent a validation mechanism. Examples of such constraints are:
* Observations must be linked to a Raum and Zeit
* Observations must be linked to a measure
* Observations measure a double value
* Observations comprise 5 groups at most
* DataSets contain several slices and slices contain several observations
* etc.

More information on shapes can be found in the official [SHACL Documentation](https://www.w3.org/TR/shacl/).

* Shapes of a DataSet are accessed through the nodes https://ld.stadt-zuerich.ch/statistics/dataset/.../shape where the points are a placeholder for the DataSet name.

**qudt:unit**: Specification of the units of measurement of an observation. 
* Units are accessed through the node https://ld.stadt-zuerich.ch/statistics/unit/.

**skos:Concept**: Groupcodes of the historic data are mapped to skos:Concepts and accessed through the node https://ld.stadt-zuerich.ch/statistics/code/.

# SPARQL-Interface
The SPARQL interface is accessed through https://ld.stadt-zuerich.ch/sparql/.

The actual queries are done via https://ld.stadt-zuerich.ch/query which is de facto the SPARQL endpoint. 

The integration environment is accessed through https://ld.integ.stadt-zuerich.ch/sparql/, but it is to be noted that the URIs tend to point back to the production environment. While testing, the ".integ" has to be inserted by hand or programmatically.

## Example Query: all DataSets


```sparql
%endpoint https://ld.stadt-zuerich.ch/query
%format JSON
%display table
```


<div class="krn-spql"><div class="magic">Endpoint set to: https://ld.stadt-zuerich.ch/query</div><div class="magic">Return format: JSON</div><div class="magic">Display: table</div></div>



```sparql
PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT ?dataset ?label WHERE{
    ?dataset a qb:DataSet;
        rdfs:label ?label.
}
```


<div class="krn-spql"><div class="krn-error"><span class="title">Error:</span> Unexpected response format: None</div></div>


### Explanation
Alle verschiedenen DataSet (gemäss RDF Data Cube Definition) und ihre label werden angezeigt. Diese Abfrage ist hilfreich um sich einen Überblick über die angebotenen Daten zu verschaffen und deren Aufteilung. Man könnte die Abfrage z.B. ergänzen mit einem FILTER um alle möglichen DataSets einer bestimmten Kennzahl (MeasureProperty) oder mit bestimmten Dimensionen (DimensionProperty) zu erhalten.

## Example Query: specific DataSets


```sparql
PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT ?dataset ?label WHERE{
    ?dataset a qb:DataSet;
        rdfs:label ?label.
    FILTER REGEX(STR(?label), "^Zuz").
}
```


<div class="krn-spql"><div class="krn-error"><span class="title">Error:</span> Unexpected response format: None</div></div>


### Explanation
Hier wurden all diese DataSets abgefragt, welche als Kennzahl bzw. MeasureProperty «Zuzüge» enthalten. Details zu den regular expressions oder REGEX sind hier zu finden. Auf dieselbe Weise kann man auch nach anderen Eigenschaften filtern wie z.B. Dimensionen oder Attribute.

## Example Query: the first 100 Triples


```sparql
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT * WHERE {
    ?sub ?pred ?obj.
} 
LIMIT 100
```

### Explanation
In fast jedem praktischen Sinn macht diese Abfrage keinen Sinn, aber sie vermittelt ein Gefühl für die Triples bzw. für das Mapping. Man erkennt z.B., dass «property» aus den statistischen Daten auf «DimensionProperty» des RDF Data Cube Modells abgebildet wurde. Oder, dass «code» aus den statistischen Daten im SKOS Modell einem «Concept» entspricht etc. Das LIMIT statement am Schluss der Abfrage ist selbstverständlich optional und dient nur dazu, die Anzahl Resultate zu beschränken.

## Example Query: total number of Triples


```sparql
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT (COUNT(*) AS ?count) WHERE{
    ?sub ?pred ?obj.
}
```

### Explanation
In fast jedem praktischen Sinn macht diese Abfrage keinen Sinn.

## Example Query: number of Observations per DataSet
Mit der folgenden Abfrage wird festgestellt, welche Datasets wie gross sind.


```sparql
BASE <https://ld.stadt-zuerich.ch/statistics/>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX qb: <http://purl.org/linked-data/cube#>

SELECT ?dataset (COUNT(DISTINCT ?observationIRI) AS ?observationcount) ?label WHERE{
    #Alle Observationen eines DataSets
    ?observationIRI a qb:Observation;
        qb:dataSet ?datasetIRI.
  
    ?datasetIRI rdfs:label ?label.
  
    #Der Anschaulichkeit halber werden die PREFIXes nicht angezeigt
    BIND(STRAFTER(STR(?datasetIRI), STR(<dataset/>)) AS ?dataset).
}
GROUP BY ?dataset ?label
ORDER BY DESC(?observationcount)
```


<div class="krn-spql"><div class="krn-error"><span class="title">Error:</span> Unexpected response format: None</div></div>


### Explanation
Die Darstellung zeigt, dass es für viele Anwendungen keine gute Idee ist, das Dataset GEB-RAUM-ZEIT-NAF-NAM-SEX direkt zu laden.

## Example Query: Filter with Regular Expressions
Wenn gesucht werden soll, wo welche Begriffe vorkommen, so kann dies mit der untenstehenden Abfrage erfolgen. Wildcards werden mit "*" im REGEX statement unterstützt. Zum Suchen wird das Label der jeweiligen Observation verwendet.


```sparql
PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

SELECT * WHERE{ 
    GRAPH <https://linked.opendata.swiss/graph/zh/statistics> 
    {
    ?obs rdfs:label ?label.
    
    # Wo "*Tiere*" steht, Suchbegriff eingeben. * lassen.
    FILTER REGEX(?label, "Tiere*")
    }
}
LIMIT 100
```

### Explanation
Es gibt verschiedene Typen von Antworten:
* Topic (z.B. http://stat.stadt-zuerich.ch/topic/WIR009 Tierhaltung der Landwirtschaftsbetriebe)
* Dataset (z.B. http://ld.stadt-zuerich.ch/statistics/dataset/AST-RAUM-ZEIT-BTA-TIG/ASTBTA9200TIG9000/slice Anzahl Ladwirtschaftsbetriebe mit übrigen Tierarten)
* Measure (z.B. http://ld.stadt-zuerich.ch/statistics/measure/TII Tierindividuen)
* Code (z.B. http://ld.stadt-zuerich.ch/statistics/code/PAT1200 Tierpartei Schweiz (TPS))
* Property (z.B. http://ld.stadt-zuerich.ch/statistics/property/TIG Tiergattung)
* Application  externe Applikationen 
* Glossar

## Example Query: plot area without forest in Zurich
Bei dieser etwas komplexeren Abfrage soll die Enwicklung der Grundstücksfläche ohne Wald grafisch dargestellt werden. Dazu wird das entsprechende Dataset „Grundstückfläche nach Bodenbedeckungsart, Raum und Zeit“ ausgewählt. Dieses hat die Kennzahl bzw. MeasureProperty STF und die Dimensionen RAUM, ZEIT und BBA. Dann werden von den Observationen jeweils die Dimensionen ausgewählt, für welche die Bodenbedeckungsart «ohne Wald» entspricht und RAUM ganz Zürich. Um das ganze sauber in einer Google Chart darzustellen muss noch die Jahreszahl vom Datum extrahiert werden.


```sparql
BASE <https://ld.stadt-zuerich.ch/statistics/>
PREFIX qb: <http://purl.org/linked-data/cube#>                                                                                                                   
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>                                                              
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>                   

SELECT ?jahr ?flaeche WHERE{ 
    #Das fragliche Dataset auswählen
    ?observation qb:dataSet <dataset/STF-RAUM-ZEIT-BBA>;
        <measure/STF> ?flaeche;
        <property/ZEIT> ?datum;
        <property/BBA>/skos:notation ?bodenbedeckungsart;
        <property/RAUM>/skos:notation ?raum.
    
    #Datum präparieren für die Darstellung mit Google Chart
    BIND(SUBSTR(STR(?datum),1,4) AS ?jahr).  
    
    #Filtern nach Landflaeche ohne Wald in ganz Zürich
    FILTER(?raum IN ("R10000")).                                                                         
    FILTER(?bodenbedeckungsart IN ("BBA1000")).                                                                                                                                                                                                                                                                                                      
} 
ORDER BY ?jahr
```

### Explanation
* R10000 – ganz Zürich
* BBA: Bodenbedeckungsart (http://ld.stadt-zuerich.ch/statistics/property/BBA )
* BBA1000 – Landfläche ohne Wald (http://ld.stadt-zuerich.ch/statistics/code/BBA1000)
* Ha – Hektar (Alle Masse werden auf Basisdefinitionen zurückgeführt. In diesem Fall über xxx)
* Die Zeit muss jeweils auf saubere Jahre zurückgebunden werden für diesen Fall.

## Example Query: Kennzahlen as MeasureProperties
Mit dieser Abfrage sollen alle möglichen Kennzahlen gefunden werden. Da diese im RDF Data Cube auf MeasureProperties abgebildet wurden, lassen sie entsprechend einfach finden. Zusätzlich werden die Einheiten und Kommentare ausgegeben.


```sparql
BASE <https://ld.stadt-zuerich.ch/statistics/>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX qb: <http://purl.org/linked-data/cube#>

SELECT ?measure ?label ?range ?comment WHERE {
    ?measureIRI a qb:MeasureProperty;
        rdfs:label ?label;
        rdfs:range ?rangeIRI;
        rdfs:comment ?comment.
  
    #Der Anschaulichkeit halber werden die PREFIXes nicht angezeigt
    BIND(STRAFTER(STR(?measureIRI), STR(<measure/>)) AS ?measure).
    BIND(STRAFTER(STR(?rangeIRI), STR(<http://www.w3.org/2001/XMLSchema#>)) AS ?range).
} 
ORDER BY ?measure
```

### Explanation


## Example Query: units of every Kennzahl


```sparql
PREFIX qb: <http://purl.org/linked-data/cube#>                                                                                                                   
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>                                                              
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>                   
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>

SELECT ?sub ?obj WHERE{  
    ?sub <http://qudt.org/schema/qudt#unit> ?obj;
        #rdfs:label ?label.
}
ORDER BY ?sub
```

### Explanation

## Example Query: Groups as DimensionProperties


```sparql
BASE <https://ld.stadt-zuerich.ch/statistics/>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX qb: <http://purl.org/linked-data/cube#>

SELECT ?dimIRI ?label WHERE {
    ?dimIRI a qb:DimensionProperty;
        rdfs:label ?label;
} 
ORDER BY ?dimIRI
```

### Explanation

## Example Query: Metadata as AttributeProperties


```sparql
BASE <https://ld.stadt-zuerich.ch/statistics/>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX qb: <http://purl.org/linked-data/cube#>

SELECT ?attr ?label WHERE {
    ?attr a qb:AttributeProperty;
        rdfs:label ?label;
} 
ORDER BY ?attr
```

### Explanation

## Example Query: Groupcodes as Concepts


```sparql
BASE <https://ld.stadt-zuerich.ch/statistics/>
PREFIX qb: <http://purl.org/linked-data/cube#>                                                                                                                   
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>                                                              
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>                   
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>

SELECT ?code ?label WHERE{  
    #Die Codes haben den Typ "Concept" des RFD Data Cube Modells
    ?codeIRI a skos:Concept;
        rdfs:label ?label.
  
    #Der Anschaulichkeit halber werden die PREFIXes nicht angezeigt
    BIND(STRAFTER(STR(?codeIRI), STR(<code/>)) AS ?code).
    
    #Für Vergleich mit http://ld.stadt-zuerich.ch/statistics/code/
    #FILTER(REGEX(?code, "BTA1742") || REGEX(?code, "VOR1006")).
}
ORDER BY ?codeIRI
```

## Example Query: Hierarchies


```sparql
BASE <https://ld.stadt-zuerich.ch/statistics/>
PREFIX qb: <http://purl.org/linked-data/cube#>                                                                                                                   
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>                                                              
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>                   
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>

SELECT ?hierarchy ?code ?label WHERE{  
    #Die Codes haben den Typ "Concept" des RFD Data Cube Modells
    ?codeIRI a skos:Concept;
        rdfs:label ?label;
        skos:broader ?hierarchyIRI.
  
    #Der Anschaulichkeit halber werden die PREFIXes nicht angezeigt
    BIND(STRAFTER(STR(?codeIRI), STR(<code/>)) AS ?code).
    BIND(STRAFTER(STR(?hierarchyIRI), STR(<code/>)) AS ?hierarchy).
}
GROUP BY ?hierarchy ?code ?label
ORDER BY ?code
```

## Example Query: Spatial Hierarchies
Die Codes sind nach Schema aufgeteilt. Das heisst, um z.B. alle Raum Codes zu finden, muss man zusätzlich das Schema eingrenzen.


```sparql
BASE <https://ld.stadt-zuerich.ch/statistics/>
PREFIX qb: <http://purl.org/linked-data/cube#>                                                                                                                   
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>                                                              
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>                   
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>

SELECT ?hierarchy ?code ?label WHERE{  
    #Die Codes haben den Typ "Concept" des RFD Data Cube Modells
    ?codeIRI a skos:Concept;
        rdfs:label ?label;
        skos:broader ?hierarchyIRI.
  
    #Alle Raum Codes
    ?codeIRI skos:inScheme <scheme/Raum>.
  
    #Der Anschaulichkeit halber werden die PREFIXes nicht angezeigt
    BIND(STRAFTER(STR(?codeIRI), STR(<code/>)) AS ?code).
    BIND(STRAFTER(STR(?hierarchyIRI), STR(<code/>)) AS ?hierarchy).
  
    #Für Vergleich mit http://ld.stadt-zuerich.ch/statistics/code/R00012
    #FILTER REGEX(?code, "R00012").
}
GROUP BY ?hierarchy ?code ?label
ORDER BY ?code
```

### Explanation
Raum ist komplex organisiert. Es gibt mehrere Roots:
* R10000 – Kreis 1
* R20000 – Stadt nach 1. Eingemeindung 1893
* R30000 -  Stadt Zürich 

## Example Query: A DataSet
Mit folgender Abfrage lassen sich alle Dimensionen, Attribute und Measures eines DataSets anzeigen. Da die DataSets benannt sind nach dem Schema “Kennzahl-Dimension1-Dimension2.. “, liefert diese Abfrage die erwarteten dimensions und das erwartete measure. Die Kennzahl wird ja auf die qb:MeasureProperty des RFD Data Cube Modells abgebildet. Die Attribute sind jeweils Metadaten wie z.B. Fussnote, Quelle und Aktualisierungsdatum.


```sparql
BASE <https://ld.stadt-zuerich.ch/statistics/>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX owl: <http://www.w3.org/2002/07/owl#>

#Ein einzelnes DataSet auswählen mit seinen Eigenschaften
SELECT ?dataset ?dimension ?attribute ?measure WHERE{
    #Es soll nur ein DataSets ausgewählt werden von Zeile "OFFSET"
    {
    SELECT ?datasetIRI WHERE{
        ?datasetIRI a qb:DataSet.
        }
    ORDER BY ?datasetIRI
    OFFSET 1
    LIMIT 1
    }
    
    #Von dem ausgewählten DataSet werden die Eigenschaften gesucht
    ?datasetIRI qb:structure/qb:component [qb:dimension ?dimensionIRI; qb:attribute ?attributeIRI; qb:measure ?measureIRI].
    
    #Der Anschaulichkeit halber werden die PREFIXes nicht angezeigt
    BIND(STRAFTER(STR(?datasetIRI), STR(<dataset/>)) AS ?dataset).
    BIND(STRAFTER(STR(?dimensionIRI), STR(<property/>)) AS ?dimension).
    BIND(STRAFTER(STR(?attributeIRI), STR(<attribute/>)) AS ?attribute).
    BIND(STRAFTER(STR(?measureIRI), STR(<measure/>)) AS ?measure).
}
ORDER BY ?dimension
```

### Explanation

## Example Query: Observations of a DataSet


```sparql
BASE <https://ld.stadt-zuerich.ch/statistics/>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX qb: <http://purl.org/linked-data/cube#>

SELECT ?dataset ?observation WHERE{
    {
    SELECT ?datasetIRI WHERE{
        ?datasetIRI a qb:DataSet.
        }
    ORDER BY ?datasetIRI
    OFFSET 1
    LIMIT 1
    }
    ?observationIRI qb:dataSet ?datasetIRI.
  
    #Der Anschaulichkeit halber werden die PREFIXes nicht angezeigt
    BIND(STRAFTER(STR(?datasetIRI), STR(<dataset/>)) AS ?dataset).
    BIND(STRAFTER(STR(?observationIRI), STR(<observation/>)) AS ?observation).
}
LIMIT 100
```

## Example Query: Slices of a DataSet


```sparql
BASE <https://ld.stadt-zuerich.ch/statistics/>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX qb: <http://purl.org/linked-data/cube#>

SELECT ?slice WHERE{
    ?dataset qb:slice ?slice.
}
```

## Example Query: Shapes of a DataSet


```sparql
BASE <https://ld.stadt-zuerich.ch/statistics/>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX qb: <http://purl.org/linked-data/cube#>

SELECT ?shapes WHERE{
    ?shapes a <http://www.w3.org/ns/shacl#NodeShape>.
}
```

### Explanation

## Example Query: Metadata of a DataSet


```sparql
BASE <https://ld.stadt-zuerich.ch/statistics/>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX qb: <http://purl.org/linked-data/cube#>

SELECT ?dataset ?metadata WHERE{
	?dataset a qb:DataSet.
  	?metadata a qb:AttributeProperty.
}
ORDER BY ?dataset
```


```sparql
BASE <https://ld.stadt-zuerich.ch/statistics/attribute/>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX qb: <http://purl.org/linked-data/cube#>

SELECT ?dataset ?praed ?obj WHERE{
  # ANT-RAUM-ZEIT-GGH-HEL (mit Glossar, Lizenz und Quelle)
  # BEW-RAUM-ZEIT-HEL-WSI
  # ANT-RAUM-ZEIT-ALF-ALM-GGH
  # EHE-RAUM-ZEIT-ZVF-ZVM (mit Fussnote)
  # BEW-RAUM-ZEIT-AUA-HEL-SEX (mit Glossar)
  # BEW-RAUM-ZEIT-ALT-KON-WSI (mit Fussnote, Quelle, Lizenzt)
  
  ?dataset <http://www.w3.org/2004/02/skos/core#notation> "BEW-RAUM-ZEIT-ALT-KON-WSI".
  {
    {
    #Unit
    ?dataset <http://purl.org/linked-data/sdmx/2009/attribute#unitMeasure> ?obj.
    ?dataset ?praed ?obj.
    } 

    UNION

    {
    #Lizenz
    ?dataset <http://purl.org/dc/terms/license> ?obj.
    ?dataset ?praed ?obj.
    }

    UNION

    {
    #Fussnoten
    SELECT DISTINCT ?dataset ?praed ?obj WHERE{
        ?obs a qb:Observation;
            <FUSSNOTE> ?obj;
            ?praed ?obj;
            qb:dataSet ?dataset.
      }
    }

    UNION

    {
    # Glossar
    SELECT DISTINCT ?dataset ?praed ?obj WHERE{
        ?obs a qb:Observation;
            <GLOSSAR> ?obj;
            ?praed ?obj;
            qb:dataSet ?dataset.
      }   
    }  

    UNION

    {
    # Quelle
    SELECT DISTINCT ?dataset ?praed ?obj WHERE{
        ?obs a qb:Observation;
            <QUELLE> ?obj;
            ?praed ?obj;
            qb:dataSet ?dataset.
      }   
    }   

    UNION

    {
    # Erwartetes Aktualisierungsdatum
    SELECT DISTINCT ?dataset ?praed ?obj WHERE{
        ?obs a qb:Observation;
            <ERWARTETE_AKTUALISIERUNG> ?obj;
            ?praed ?obj;
            qb:dataSet ?dataset.
      }   
    }     

    UNION

    {
    # Letztes Aktualisierungsdatum
    SELECT DISTINCT ?dataset ?praed ?obj WHERE{
        ?obs a qb:Observation;
            <DATENSTAND> ?obj;
            ?praed ?obj;
            qb:dataSet ?dataset.
      }   
    }     

    UNION

    {
    # Korrektur
    SELECT DISTINCT ?dataset ?praed ?obj WHERE{
        ?obs a qb:Observation;
            <KORREKTUR> ?obj;
            ?praed ?obj;
            qb:dataSet ?dataset.
      }   
    }        
  }
}
```

## Example Query: Conjunction of Kennzahlen
Dank der Datenharmonisierung wird die Verknüpfbarkeit der Daten wesentlich vereinfacht. Als Beispiel soll hier die Differenz aus Geburten und Sterbefällen berechnet werden.


```sparql
PREFIX qb: <http://purl.org/linked-data/cube#>
PREFIX dataset: <https://ld.stadt-zuerich.ch/statistics/dataset/>
PREFIX measure: <https://ld.stadt-zuerich.ch/statistics/measure/>
PREFIX property: <https://ld.stadt-zuerich.ch/statistics/property/>
PREFIX code: <https://ld.stadt-zuerich.ch/statistics/code/>

SELECT ?Jahr (SUM(?Geburten) AS ?Geburten) (SUM(?Sterbefaelle) AS ?Sterbefaelle) (SUM(?Differenz) AS ?Differenz) WHERE {
    ?observation a qb:Observation; 
        property:RAUM ?Raum;
        property:ZEIT ?Zeit.
  
    #Geburten extrahieren aus entsprechendem Dataset
    {
    ?observation qb:dataSet dataset:GEB-RAUM-ZEIT;
    measure:GEB ?Geburten.
    BIND(?Geburten AS ?Differenz)
    }
  
    UNION
  
    #Sterbefälle extrahieren aus entsprechendem Dataset
    {
    ?observation qb:dataSet dataset:GES-RAUM-ZEIT;
    measure:GES ?Sterbefaelle.
    BIND(?Sterbefaelle*-1 AS ?Differenz)
    }
    
    #RAUM soll ganze Stadt umfassen
    FILTER(?Raum = code:R30000)
  
    #Datum präparieren für Google Chart
    BIND(STR(?Zeit) AS ?Jahr)
}
GROUP BY ?Jahr
ORDER BY ?Jahr
```

## Example Query: Time and Date
Es gibt Datensätze, die monatlich sind und solche, die jährlich sind.

TODO

# REST-Interface

## Basics

## Search-API

## All Datasets

## Dataset

## Slice

## Shape

## Metadata

## API-Tests
API-Tests finden sich auf:

https://sszvis-components.netlify.com/#/api-test

# Hydra-Client
<span class="mark">LATER</span>

# Use of sszvis
* https://www.npmjs.com/package/sszvis
* https://github.com/statistikstadtzuerich/sszvis-components
* https://github.com/statistikstadtzuerich/stip-frontend
* http://stip-frontend-docs.interactivethings.io/
* 
* http://www.catalog.style/
* Die Datenstrukturen sind hier definiert: https://sszvis-components.netlify.com/#/chart-system


# OpenSource projects about STIP, LOSD and sszvis
<span class="mark">LATER</span>
