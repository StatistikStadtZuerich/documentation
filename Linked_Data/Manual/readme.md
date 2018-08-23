
# Documentation for LOSD
This folder contains the Jupyter Notebook for LOSD - Linked Open Statistical Data - from Statistik Stadt Zürich.

> **The Table of Contents as well as all code examples do not work in the Github preview!**

# Table of Contents
[1 Introduction](#1-Introduction)<br>
[2 Linked Open Data](#2-Linked-Open-Data)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[2.1 The Semantic Web](#2.1-The-Semantic-Web)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[2.2 Open Data and Linked Data](#2.2-Open-Data-and-Linked-Data)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[2.3 Graph Database vs. Relational Database](#2.3-Graph-Database-vs.-Relational-Database)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[2.4 Triple Storage and Resource Description Framework](#2.4-Triple-Storage-and-Resource-Description-Framework)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[2.5 RDF Vocabulary](#2.5-RDF-Vocabulary)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[2.6 RDF Serialization](#2.6-RDF-Serialization)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[2.7 RDF Data Cube model](#2.7-RDF-Data-Cube-model)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[2.8 SPARQL and how to query Linked Data](#2.8-SPARQL-and-how-to-query-Linked-Data)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[2.9 SPARQL vs. SQL](#2.9-SPARQL-vs.-SQL)<br>
[3 Data Models](#Data-Models)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[3.1 The SDMX Standard](#3.1-The-SDMX-Standard)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[3.2 Concepts of the Historic Data](#3.2-Concepts-of-the-Historic-Data)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[3.3 Concepts of the RDF Data Cube](#3.3-Concepts-of-the-RDF-Data-Cube)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[3.4 Other important Concepts](#3.4-Other-important-Concepts)<br>
[4 SPARQL](#SPARQL)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.1 SPARQL in this notebook](#4.1-SPARQL-in-this-notebook)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.2 Example Query&#58; all DataSets](#4.2-Example-Query--all-DataSets)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.2.1 Explanation](#4.2.1-Explanation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.3 Example Query&#58; the first 100 Triples](#4.3-Example-Query&#58;-the-first-100-Triples)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.3.1 Explanation](#4.3.1-Explanation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.4 Example Query&#58; total number of Triples](#4.4-Example-Query&#58;-total-number-of-Triples)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.4.1 Explanation](#4.4.1-Explanation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.5 Example Query&#58; number of Observations per DataSet](#4.5-Example-Query&#58;-number-of-Observations-per-DataSet)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.5.1 Explanation](#4.5.1-Explanation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.6 Example Query&#58; filter with regular expressions](#4.6-Example-Query&#58;-filter-with-regular-expressions)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.6.1 Explanation](#4.6.1-Explanation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.7 Example Query&#58; Kennzahlen and measures](#4.7-Example-Query&#58;-Kennzahlen-and-measures)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.7.1 Explanation](#4.7.1-Explanation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.8 Example Query&#58; Groups and dimensions](#4.8-Example-Query&#58;-Groups-and-dimensions)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.8.1 Explanation](#4.8.1-Explanation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.9 Example Query&#58; DataSets of specific dimensions](#4.9-Example-Query&#58;-DataSets-of-specific-dimensions)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.9.1 Explanation](#4.9.1-Explanation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.10 Example Query&#58; Metadata and attributes](#4.10-Example-Query&#58;-Metadata-and-attributes)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.10.1 Explanation](#4.10.1-Explanation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.11 Example Query&#58; Groupcodes](#4.11-Example-Query&#58;-Groupcodes)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.11.1 Explanation](#4.11.1-Explanation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.12 Example Query&#58; Hierarchy of Groupcodes](#4.12-Example-Query&#58;-Hierarchy-of-Groupcodes)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.12.1 Explanation](#4.12.1-Explanation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.13 Example Query&#58; spatial Hierarchies](#4.13-Example-Query&#58;-spatial-Hierarchies)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.13.1 Explanation](#4.13.1-Explanation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.14 Example Query&#58; links to other Databases](#4.14-Example-Query&#58;-links-to-other-Databases)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.14.1 Explanation](#4.14.1-Explanation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.15 Example Query&#58; Slices of DataSets](#4.15-Example-Query&#58;-Slices-of-DataSets)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.15.1 Explanation](#4.15.1-Explanation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.16 Example Query&#58; Shapes](#4.16-Example-Query&#58;-Shapes)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.16.1 Explanation](#4.16.1-Explanation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.17 Example Query&#58; Metadata of Observations](#4.17-Example-Query&#58;-Metadata-of-Observations)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.17.1 Explanation](#4.17.1-Explanation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.18 Example Query&#58; more Metadata of Observations](#4.18-Example-Query&#58;-more-Metadata-of-Observations)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.18.1 Explanation](#4.18.1-Explanation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.19 Example Query&#58; relations of a DataSet](#4.19-Example-Query&#58;-relations-of-a-DataSet)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.19.1 Explanation](#4.19.1-Explanation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.20 Example Query&#58; relations of an Observation](#4.20-Example-Query&#58;-relations-of-an-Observation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.20.1 Explanation](#4.20.1-Explanation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.21 Example Query&#58; evolution of the plot area without forest](#Example-Query&#58;-evolution-of-the-plot-area-without-forest)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.21.1 Explanation](#4.21.1-Explanation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.22 Example Query&#58; females of swiss origin in 2016](#4.22-Example-Query&#58;-females-of-swiss-origin-in-2016)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.22.1 Explanation](#4.22.1-Explanation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.23 Example Query&#58; evolution of the number of unemployed](#4.23-Example-Query&#58;-evolution-of-the-number-of-unemployed)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.23.1 Explanation](#4.23.1-Explanation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.24 Example Query&#58; conjunction of Kennzahlen](#4.24-Example-Query&#58;-conjunction-of-Kennzahlen)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.24.1 Explanation](#4.24.1-Explanation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.25 Example Query&#58; differences in population numbers](#4.25-Example-Query&#58;-differences-in-population-numbers)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.25.1 Explanation](#4.25.1-Explanation)<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[4.26 Example Query&#58; DataSets and BEZUGSZEIT](#4.26-Example-Query&#58;-DataSets-and-BEZUGSZEIT)<br>
[5 SSZVIS](#5-SSZVIS)<br>
[6 OpenSource and Repositories](#6-OpenSource-and-Repositories)<br>
