This project was developed by Samuele Bortolotti and Erich Robbi for the Knowledge Graph Engineering course of the master's degree in Computer Science at University of Trento.

# Project Description
Reusability is one of the main principles in the Knowledge Graph Engineering (KGE) process
defined by [*iTelos*](https://doi.org/10.48550/ARXIV.2105.09418). 

## Background
Through the employment of new techniques and equipment, companies are producing an unprecedented volume of data. 
Thanks to such resources it is possible to resolve complicated issues leveraging knowledge acquisition, by gaining access and reusing this data, appropriately adjusted for secondary needs.

However, the available data is frequently not easily accessible, and even when it is, it cannot be used outside of the purpose for which it was produced.

Indeed, among the resources, we can identify three categories, which are strictly connected to the relevance for the purpose itself: **Core**, **Common**, and **Contextual resources**.

- **Common resources** are not directly relevant to the user’s purpose but are fundamental to support it since they include knowledge that is shared across several domains of interest.
- **Core resources** do not convey knowledge on the most crucial aspects related to the purpose; however, without this knowledge, the service cannot be delivered.
- **Contextual resources** include particular, sometimes exclusive data pertaining to the purpose and for this reason, they are the less reusable ones.

iTelos is a general-purpose methodology that aims at providing a possible solution to the resources re-usability problem by developing independently the data level and the schema level of the resources. To fulfill its objective, iTelos uses ontologies, in order to set a standard schema for the whole application, and Knowledge Graphs, a graph-structured data model to integrate data.

To support our work in re-usability, we have relied on the [FAIR](The FAIR Guiding Principles for scientific data management and stewardship) guiding principles. FAIR aim to make data Findable, metadata, and data should be easy to find for both humans and computers; Accessible, once the data is found the user has to know how to access it; Interoperable, the data need to interoperate with applications or workflows for analysis, storage, and processing; and finally Reusable, optimize the data re-use thought well-described metadata and data in order to be replicated and/or combined in different settings. 

The goal of this work is to provide a service that will make it easier to locate schools in the Trentino area, together with information about those schools and the courses they offer, based on criteria such as city, commune, school type, course length, and instructional activity schedules.

# Purpouse
The initial, and thus informal, purpose which has been later formalized, is shown below:

<div align="center">
”A service that will facilitate the finding of schools, including details about the school
and courses offered, in the region of Trentino based on city, commune, school type,
course duration, and teaching activities schedules.”
</div>

## Domain of Interest
This research seeks to provide a complete analysis of the educational facilities in Trentino which
comprehend geospatial and temporal domains. Since it is possible to combine many domains to produce a newly composed domain that serves a specific purpose, domain composition has
become an important step that was undertaken to identify the project’s aim.

Setting the parameters under which the project’s material would be taken into consideration was crucial since Trentino’s educational system included a wide range of topics. Trentino has
a wide range of educational institutions, including public and private kindergartens, elementary schools, secondary schools, universities, and other vocational training facilities.

Moreover, the data we were able to gather spans the years 2014 through 2022. 

However, we have sufficient recent data to assert that our temporal domain refers to the last few years (2020 - 2022).

Furthermore, a crucial feature we want our system to provide is to define metrics in order to assess the quality of the education provided by an educational facility, such as the quality of the reviews, the rate of completion of compulsory schooling, the number of students who fail to pass the year per municipality.

As a result, after learning about the type of data that was already accessible, the project’s original goal was established as follows:

<div align="center">
“A service that will help parents and students to find schools, including details about
schools and courses offered, in the region of Trentino based on city, municipality,
school type, course duration, teaching activities schedules, contact information, and
education statistics”
</div>

# Datasets
This section comprehends the list of resources we have employed in order to build the final knowledge graph.
Keep in mind that all the resources were managed thoughout the entire process in order to be aligned syntatically and semantically, hence, the cleaned datasets can be found in the GitHub repository.

| Data Source                                                                                                                    	| Format 	| Organization      	| Description                                                                                                                                                                                                                                                                                                                                                                                                                                                                 	| License                                                             	|
|--------------------------------------------------------------------------------------------------------------------------------	|--------	|-------------------	|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|---------------------------------------------------------------------	|
| [Municipalities of Trentino](https://en.wikipedia.org/wiki/Municipalities_of_Trentino)                                         	| HTML   	| Wikipedia         	| This resource represents a list of municipalities of the autonomous province of Trento, Italy. In particular, it shows the [ISTAT code](https://en.wikipedia.org/wiki/Italian_National_Institute_of_Statistics), the name, the area, and the estimated population in 2001.                                                                                                                                                                                                  	| [CC Attribution v3.0](https://creativecommons.org/licenses/by/3.0/) 	|
| [Nidi di Infanzia](ttps://dati.trentino.it/dataset/nidi-dinfanzia2)                                                            	| CSV    	| OpenData Trentino 	| This resources contains the number of facilities of Nursery Schools which are present in each municipality of the autonomous province of Trento.                                                                                                                                                                                                                                                                                                                            	| [CC Attribution v4.0](https://creativecommons.org/licenses/by/4.0/) 	|
| [Scuole d'Infanzia](https://dati.trentino.it/dataset/scuole-dinfanzia2)                                                        	| CSV    	| OpenData Trentino 	| This resources contains the number of facilities of Kindergartens which are present in each municipality of the autonomous province of Trento.                                                                                                                                                                                                                                                                                                                              	| [CC Attribution v4.0](https://creativecommons.org/licenses/by/4.0/) 	|
| [Scuole Elementari](https://dati.trentino.it/dataset/scuole-elementari2)                                                       	| CSV    	| OpenData Trentino 	| This resources contains the number of facilities of Elementary Schools which are present in each municipality of the autonomous province of Trento.                                                                                                                                                                                                                                                                                                                        	| [CC Attribution v4.0](https://creativecommons.org/licenses/by/4.0/) 	  |
| [Scuole Medie superiori](https://dati.trentino.it/dataset/scuole-medie-superiori-e-centri-di-formazione-professionale2)        	| CSV    	| OpenData Trentino 	| This resources contains the number of facilities of High Schools which are present in each municipality of the autonomous province of Trento.                                                                                                                                                                                                                                                                                                                               	| [CC Attribution v4.0](https://creativecommons.org/licenses/by/4.0/) 	|
| [Scuole Medie inferiori](https://dati.trentino.it/dataset/scuole-media-inferiori2)                                             	| CSV    	| OpenData Trentino 	| This resources contains the number of facilities of Middle Schools which are present in each municipality of the autonomous province of Trento.                                                                                                                                                                                                                                                                                                                             	| [CC Attribution v4.0](https://creativecommons.org/licenses/by/4.0/) 	|
| [Insegnamenti e corsi di studio dell'Università di Trento](https://dati.trentino.it/dataset/insegnamenti-universita-di-trento) 	| JSON   	| OpenData Trentino 	| his dataset provides information about all the courses the University of Trento provides.                                                                                                                                                                                                                                                                                                                                                                                   	| [CC Attribution v4.0](https://creativecommons.org/licenses/by/4.0/) 	|
| [Istituzioni scolastiche del Trentino](https://dati.trentino.it/dataset/istituzioni-scolastiche-trentino)                      	| CSV    	| OpenData Trentino 	| The dataset contains information about all educational facilities presents in Trentino. The relevant information which are listed are the address, the name and the type.                                                                                                                                                                                                                                                                                                   	| [CC Attribution v4.0](https://creativecommons.org/licenses/by/4.0/) 	|
| [Corsi di studio scuole Trentine](https://dati.trentino.it/dataset/corsi-di-studio-delle-scuole-trentine)                      	| XML    	| OpenData Trentino 	| The resource concerns the courses each school in Trentino offers                                                                                                                                                                                                                                                                                                                                                                                                            	| [CC Attribution v4.0](https://creativecommons.org/licenses/by/4.0/) 	|
| [Invalsi Servizio Statistico Cineca](https://invalsi-serviziostatistico.cineca.it/)                                            	| CSV    	| CINECA            	| This dataset contains the average score of the [Invalsi tests](https://it.wikipedia.org/wiki/Prove_nazionali_INVALSI) per municipality. Their goal is to assess students' learning levels of Italian, Math, and English at critical points in the academic year.                                                                                                                                                                                                            	| [CC Attribution v4.0](https://creativecommons.org/licenses/by/4.0/) 	|
| [Google Reviews](https://developers.google.com/)                                                                               	| HTML   	| Google            	| This resource concerns the reviews that other people leave on points of interest around the world. They can give pretty meaningful information regarding how people have felt about a given school facility either concerning their education or the ones of others they know.                                                                                                                                                                                              	| [CC Attribution v3.0](https://creativecommons.org/licenses/by/3.0/) 	|
| [Istituto di Statistica della Provincia di Trento](https://statweb.provincia.tn.it/indicatoriStrutturaliSubPro/)               	| CSV    	| Provincia TN      	| This website contains all the resources which were collected and made available by the Statistical Institute of the Province of Trento (ISPAT). It provides several relevant information about Trentino and the cultural level of its inhabitants. In this project, we have employed this service for deepening our knowledge about the number of students per municipality and the information concerning the rate of completion of compulsory schooling per municipality. 	| [CC Attribution v4.0](https://creativecommons.org/licenses/by/4.0/) 	|
| [Unitrento Digital University](https://webapps.unitn.it/du)                                                                    	| JSON   	| Unitn             	| Information on the students, faculty, staff, and administration of the University of Trento can be found at the Digital University portal.                                                                                                                                                                                                                                                                                                                                  	| [CC Attribution v4.0](https://creativecommons.org/licenses/by/4.0/) 	|
| [Vivo Scuola](https://www.vivoscuola.it)                                                                                       	| HTML   	| Vivoscuola        	| Vivoscuola provides an integrated variety of services, information, and curiosity about schools to students, teachers, and parents                                                                                                                                                                                                                                                                                                                                          	| [CC Attribution v3.0](https://creativecommons.org/licenses/by/3.0/) 	| 

# Informal modeling

# Formal modeling

# ETG construction

# Aswer to the competency questions

# Resources
In this section, we present the list of resources which can be consulted in order to know more about the project.

## Authors
Here you can find the contact information in order to get in touch with us:

|  Name    |  Surname   | Github Username                                             |
| :------: | :--------: | :---------------------------------------------------------: |
| Samuele  | Bortolotti | [`samuelebortolotti`](https://github.com/samuelebortolotti) |
| Erich    | Robbi      | [`erich-r`](https://github.com/erich-r)                     |


## GitHub repository
All the materials, concerning the Personas, Competency Questions, Ontologies, Teleology, Teleontology, KG and GraphQL queries Teleontology, KG and GraphQL queries are listed below:

## Google Drive folder

## Project Report

## Project Presentation

