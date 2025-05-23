---
title: Research product
parent: Interoperability framework
ancestor: RA-SKG
layout: default
nav_order: 2
---

# RA-SKG Research product

The RA-SKG extension introduce metrics (i.e., indicators and badges) for [Research product].

## Properties

### `ra_metrics`
*List* (recommended): A collection of metrics available for a [Research product]. 

Each element of the list is structured as follow.
- `ra_metric` *Object* (mandatory): The information about the provided metric. Metrics can be of two kinds:
  - **Scalar** indicating something countable (e.g., a citation count). In this case, `ra_metric` has the following properties:
    - `ra_measure` *Object* (mandatory): An object representing the scalar and its meaning.
      - `class` *String* (recommended): The URL of the class identifying the entity (e.g., in an ontology) describing that type.
      - `labels` *Object* (recommended): the labels describing the type (multiple for multilingualism). 
        The object is a dictionary, the keys represent language codes following [ISO 639-1]; the special key `none` is reserved whenever the information about the language is not available or cannot be shared.
      - `defined_in` *String* (optional): the URL of the schema defining the metric type used.
    - `ra_value` *String* (mandatory): the actual value of the metric.
  
  - **Badges** indicating a property or claim the [Research product] exhibits. In this case, `ra_metric` has the following properties:
    - `ra_category` *Object* (mandatory): An object representing the badge and its meaning.
      - `class` *String* (recommended): The URL of the class identifying the entity (e.g., in an ontology) describing that type.
      - `labels` *Object* (recommended): the labels describing the type (multiple for multilingualism). 
        The object is a dictionary, the keys represent language codes following [ISO 639-1]; the special key `none` is reserved whenever the information about the language is not available or cannot be shared.
      - `defined_in` *String* (optional): the URL of the schema defining the metric type used.
- `ra_provider` *String* (recommended): An [Agent] providing the metric.
- `description` *String* (optional): A description of the metric.


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
        "ra_category": {
          "labels": {
            "en": "code open",
            "it": "codice aperto"
          }
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