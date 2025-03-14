---
title: Methodology
parent: Data model
ancestor: RA-SKG
layout: default
nav_order: 1
---

# Methodology used while developing RA-SKG

The **_SAMOD_** methodology was adopted in developing RA-SKG. SAMOD is an abbreviation for **_Simplified Agile Methodology for Ontology Development_**, 
and it represents a novel agile methodology for the development of ontologies by means of small steps of an iterative workflow that focuses 
on creating well-developed and documented models starting from exemplar domain descriptions. More details about this methodology can be found 
[at this web page](https://essepuntato.it/samod/). 

In the case of this project, the team was split into two groups. The first group was created by domain experts, i.e. people with some experience
in the research assessment process. The second group was created by model engineers. The task assigned to the first group was to write motivating scenarios. 
After a couple of meetings and discussion about motivating scenarios, the team decided to create two motivating scenarios:
- Academic profiles for researchers
- Indicators for monitoring Research Performing Organisations

Basic **_description_** of those scenarios including **_examples_** has been provided by the first group (domain experts), as well as **_informal competency questions_** for those scenarios. 
The second group (model engineers) created **_glossaries_** based on scenarios descriptions and linked informal competency questions, **_diagrams_**, **_formal model as a TBOX expressed in the turtle notation_**, 
**_sample data as an ABOX expressed in the turtle notation_**, **_formal representation of competency queries_**, and **_conducted tests_** whether created model is capable to provide responses on queries. 

Links to all resources produced in the process mentioned in the previous paragraph for two scenarios are listed below:
- Academic profiles for researchers
  - [Description and examples](./samod/01/development/01_motivating-scenario)
  - [Informal competency questions](./samod/01/development/02_informal-competency-questions)
  - [Glossary](./samod/01/development/03_glossary)
  - [Diagram](./samod/01/development/04_diagram)
  - [Formal model](./samod/01/development/05_TBox)
  - [Sample data](./samod/01/development/06_ABox)
  - [Formal competency questions](./samod/01/development/07_formal_competency_questions)
  - [Test](./samod/01/development/08_formal_testing)
- Indicators for monitoring Research Performing Organisations
  - [Description and examples](./samod/02/development/01_motivating-scenario)
  - [Informal competency questions](./samod/02/development/02_informal-competency-questions)
  - [Glossary](./samod/02/development/03_glossary)
  - [Diagram](./samod/02/development/04_diagram)
  - [Formal model](./samod/02/development/05_TBox)
  - [Sample data](./samod/02/development/06_ABox)
  - [Formal competency questions](./samod/02/development/07_formal_competency_questions)
  - [Test](./samod/02/development/08_formal_testing)

By creation of all resources listed above a **_modelet_** has been created for each motivating scenario.
A modelet is a stand-alone model supporting a particular motivating scenario. By definition, a modelet does not include entities from other parts of the final model (RA-SKG-IF).
Model engineers after creation of modelet for each motivating scenario, conducted merging of modelet with SKG-IF model and producing RA-SKG-IF. At the end, model engineers refactored and optimized the final [RA-SKG-IF model](./samod/final-model/index-en.html).  
