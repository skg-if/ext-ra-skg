---
title: Data model
parent: RA-SKG
layout: default
nav_order: 2
has_toc: false
---

# RA-SKG data model

The RA-SKG Data Model is the metadata model used for the data compliant with the [RA-SKG extension of the SKG-IF]({% link ext-ra-skg/extended-interoperability-framework/ra-skg-if.md %}).

The RA-SKG Data Model is used to model extends the SKG-IF Data Model with additional classes,their attributes and their relations to other entities. All these aspects are implemented using the 'language' of the Semantic Web, in particular by re-employing several existing ontological models developed to address specific modelling scenarios compatible with the aims of this extension. 

The RA-SKG Data Model, summarised in the following [Graffoo diagrams](https://essepuntato.it/graffoo), allows one to record information which are required for research assessment use cases, as well as their relationships with well-established entities of the scholarly communication domain. Examples of such entities are research performance indicators, which are used to support various research evaluation processes, and narrative CVs, which are texts presenting the overarching story of one or more research products usually related to an entity of interest.

![RA-SKG diagram]({% link ext-ra-skg/data-model/graphs/ra-skg.png %})

The SKG-IF Data Model has been also implemented as an OWL ontology, i.e., the [SKG-IF Ontology: Research Assessment extension](https://w3id.org/skg-if/extension/ra-skg/ontology/). It is not yet another bibliographic ontology, but rather a place where existing and complementary ontological entities from several other ontologies are grouped together for the purpose of providing descriptive metadata compliant with this extension.

The SKG-IF data created following the [RA-SKG extension of the SKG-IF]({% link ext-ra-skg/extended-interoperability-framework/ra-skg-if.md %}) are aligned with the *SKG-IF Ontology: Research Assessment extension* via the [SKG-IF JSON-LD context](https://w3id.org/skg-if/context/skg-if.json) extended with the [RA-SKG JSON-LD context](https://w3id.org/skg-if/extension/ra-skg/context/skg-if.json). In addition, a specific [SHACL document](https://w3id.org/skg-if/extension/ra-skg/validation/shacl) has been developed for semantically validating the data provided according to the data model of this extension.

The methodology used to produce this data model is described [here](./methodology).
