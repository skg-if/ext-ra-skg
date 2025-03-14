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
*List* (recommended): **add description here**. Each element of the list is structured as follow.



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