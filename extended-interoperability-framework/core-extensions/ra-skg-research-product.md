---
title: Research product
parent: Interoperability framework
ancestor: RA-SKG
layout: default
nav_order: 2
---

# (Extended) Research product

By default, this extended core entity inherits all the properties defined in the core [Research product].
Here below, please describe the new properties and relations that the extension adds to the default [Research product].


## Properties

### `ra_metrics`
*List* (recommended): A collection of metrics available for a [Research product]. 

Each element of the list is structured as follow.
- `ra_metric` *Object* (mandatory): The information about the provided metric. Metrics can be of two kinds:
  - **Scalar** (e.g., a citation count). In this case, `ra_metric` has the following properties:
    - `class` *String* (recommended): The URL of the class identifying the entity (e.g., in an ontology) describing that type.
    - `labels` *Object* (recommended): the labels describing the type (multiple for multilingualism). 
    The object is a dictionary, the keys represent language codes following [ISO 639-1]; the special key `none` is reserved whenever the information about the language is not available or cannot be shared.
    - `defined_in` *String* (recommended): the URL of the schema of the manifestation type, e.g., a link to the vocabulary of allowed product types.
  
  - **Badges** (e.g., a property or claim the [Research product] exhibits). In this case, `ra_metric` has the following properties:
    - `labels` *Object* (recommended): the labels describing the type (multiple for multilingualism). 
    The object is a dictionary, the keys represent language codes following [ISO 639-1]; the special key `none` is reserved whenever the information about the language is not available or cannot be shared.
- `ra_provider` *String* (mandatory): An [Agent] providing the metric.
- `description` *String* (mandatory): A description of the metric.



```json
"ra_metrics": [
    {
      "ra_metric": {
        "ra_measure": {
          "class": "http://www.wikidata.org/entity/Q5122404",
          "labels": {
            "en": "publication citation count",
            "it": "conteggio delle citazioni ricevute dalla pubblicazione"
          },
          "defined_in": "http://www.wikidata.org/"
        },
        "ra_value": 125.0
      },
      "ra_provider": "agent_2",
      "description": "The total number of citations received by the article in consideration. Citations and article metadata required to calculate the particular indicator are gathered by OpenCitations Index and OpenCitations Meta."
    },
    {
      "ra_metric": {
        "labels": {
          "en": "code open",
          "it": "codice aperto"
        }
      },
      "ra_provider": "agent_3",
      "description": "Badge assessing that the code developed and used within the article is open. Information gathered from."
    }
  ]
```

----
[Research product]: {% link interoperability-framework/docs/research-product.md %}
[Agent]: {% link interoperability-framework/docs/agent.md %}
[ISO 639-1]: https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes