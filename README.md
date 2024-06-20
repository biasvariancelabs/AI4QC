# AI4QC Repository for Semantic Data Management

This repository contains the AI4QC ontology, a semantic annotation schema designed to provide detailed metadata fields and examples of semantically annotated EO (Earth Observation) datasets in JSON format.

Semantic annotation of datasets involves enriching data with meaningful metadata that explains its context, content, and relevance. This process transforms raw data into a more valuable resource by making it understandable and usable, not just for humans, but also for automated systems. It bridges the gap between data and its interpretation, allowing for more precise and efficient data utilization.

## Top-level annotation schema for AI4QC datasets 
![ontology_schema](https://github.com/biasvariancelabs/AI4QC/assets/9078206/d34fcac9-32d1-4a60-808b-03b29725113a)

In the figure above, we present a top-level structure of the AI4QC metadata schema that is aimed to be used for describing and representing the produced AI4QC datasets within the AI4QC Training data platform and the AI4QC dataset catalogue. It will enable the users to explore the characteristics of the datasets and search for specific datasets of interest.

The AI4QC metadata schema is composed of several distinctive parts that deal with capturing different characteristics of the datasets. These include DCAT data specification, Provenance, Task, Data, Quality, Ground-truth labels and EO anomalies.

DCAT data specification includes the three-level structure for representing data catalogues, datasets and distributions that was reused from the DCAT schema, which is a standard for describing data catalogs. This standard includes classes like dcat:Catalog, dcat:Dataset, dcat:Distribution, and dcat:DataService. The relationships shown in the figure indicate that a catalog has datasets, which in turn have distributions, and there are services to access these datasets.

The Provenance specification addresses the origin and history (provenance) of data labeling. Here we include the information from the OGC Training Data Markup Language for AI. It includes an AI Labeler (tds:AI_Labeler) and a Labeling Procedure (tds:AI_LabelingProcedure), suggesting a formalized process of how data is labeled for training AI models.

The Task specification is used to represent the AI task that the dataset can be used for. Here, the task is identified as tds:AI_Task, which can be a specific Earth Observation task (tds:AI_EOTask). This is linked to a tds:AI_TrainingDataset, suggesting that tasks are associated with specific datasets for training purposes.

The Data specification is the core of our metadata schema and represents data being used for AI Training (tds:AI_TrainingData). It links to the DCAT data specification, the provenance of the labels used in the dataset, the AI task as well as data quality measures, ground truth labels and EO anomaly types represented within the datasets.

The EO anomalies specific segment outlines the types of anomalies that can occur in EO imaging data, such as clouds, aerosol, and ghosting. These are specific challenges that need to be labeled and dealt within the AI4QC datasets.

The Quality segment deals with representing the data quality information. Here we include two classes from the W3C Data Quality Vocabulary (https://www.w3.org/TR/vocab-dqv/). dqv:QualityMeasurement represents a metric value providing quantitative or qualitative information about the dataset or distribution. A Quality Metric (dqv:Metric) gives a procedure for measuring a data quality dimension, which is abstract, by observing a concrete quality indicator.

For the representation of the ground truth labels, we reuse the structure from the the OGC Training Data Markup Language for AI. We distinguish ground truth labeling into three types: tds:AI_SceneLabel, tds:AI_PixelLabel, and tds:AI_ObjectLabel. This classification is crucial for training accurate AI models, as each type of label provides different levels of detail for the learning process.


## Detailed AI4QC annotation schema field list

![image](https://github.com/biasvariancelabs/AI4QC/assets/9078206/0aaa2b10-6e01-409c-a68c-b3ba23df0e72)
Here, we represent the detailed field list for the AI4QC metadata schema for each key entities from the conceptual diagram. The blue fields denote object properties (covering the relationships between different entities), the green fields denote datatype properties (covering the association with data values) and the orange fields denote annotation properties (used to provide additional information such as comments, labels, or descriptions).

All the fields are categorised into three categories: mandatory, recomented and optional. This allows flexibility of data annotation for different use cases. For the fields, we also reuse metadata terms from standard vocabularies which are represented by the prefix. The fields without a prefix are defined directly in our schema. The standard vocabularies that we reuse include:
- [DCMI Metadata Terms](https://www.dublincore.org/specifications/dublincore/dcmi-terms/)
- [Friend of a Friend (FOAF)](http://xmlns.com/foaf/spec/)
- [Open Digital Rights Language (ODRL)](https://www.w3.org/TR/odrl-vocab/)
- [Asset Description Metadata Schema (ADMS)](https://semiceu.github.io/ADMS/releases/2.00/)
- [The PROV Ontology (PROV-O)](https://www.w3.org/TR/prov-o/)
- [RDF Schema (RDFS)](https://www.w3.org/TR/rdf-schema/)
- [Data Quality Vocabulary (DQV)](https://www.w3.org/2013/dwbp/wiki/Data_Quality_Vocabulary_(DQV))


The AI4QC dataset metadata schema is designed to be interoperable with other systems since it reuses standard vocabularies. This helps in integrating with other semantic web resources, ensuring that metadata created using this model can be understood and used beyond the specific system it was created for.


