---
title: Agent
parent: Interoperability framework
ancestor: RA-SKG
layout: default
nav_order: 1
---

# RA-SKG Agent

The RA-SKG extension introduce metrics (i.e., indicators and badges) for [Agent].

## Properties

### `ra_metrics`
*List* (recommended): A collection of metrics available for a [Agent]. 

Each element of the list is structured as follow.
- `ra_metric` *Object* (mandatory): The information about the provided metric. Metrics can be of two kinds:
  - **Scalar** indicating something countable (e.g., a citation count). In this case, `ra_metric` has the following properties:
    - `ra_measure` *Object* (mandatory): An object representing the scalar and its meaning.
      - `class` *String* (recommended): The URL of the class identifying the entity (e.g., in an ontology) describing that type.
      - `labels` *Object* (recommended): the labels describing the type (multiple for multilingualism). 
        The object is a dictionary, the keys represent language codes following [ISO 639-1]; the special key `none` is reserved whenever the information about the language is not available or cannot be shared.
      - `defined_in` *String* (optional): the URL of the schema defining the metric type used.
    - `ra_value` *String* (mandatory): the actual value of the metric.
  
  - **Badges** indicating a property or claim the [Agent] exhibits. In this case, `ra_metric` has the following properties:
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
          "class": "http://purl.org/spar/bido/author-citation-count",
          "labels": {
            "en": "author citation count",
            "it": "conteggio delle citazioni ricevute dall'autore"
          },
          "defined_in": "http://purl.org/spar/bido-standard-bibliometric-measures"
        },
        "ra_value": 3125.0
      },
      "ra_provider": "agent_1",
      "ra_discipline": "topic_1",
      "description": "The total number of citations received by all articles of a specific discipline of the researcher of interest. All publication records of subtype 'Article' from the OpenAIRE Graph that are marked as authored by the researcher were collected and their citations from other articles were counted. Citations and article metadata required to calculate the particular indicator are gathered by the OpenAIRE Graph v9.0.0."
    }
  ]
```


### `ra_profiles`
*List* (recommended): A collection of narrative profiles for an [Agent] (applies only if the `entity_type` of an  [Agent] is `person`) that can support an evaluation. 

Each element of the list is structured as follows:
- `ra_title` *String* (recommended): the title of the narrative profile.
- `ra_sections` *List* (recommended): Sections composing the narrative. Each section has the following properties:
    - `ra_title` *String* (recommended): Title of the section
    - `description` *String* (optional): Description, e.g. containing guidelines, of what is expected as content of the section
    - `ra_content` *String* (optional): Content of the section
    - `cites` *List* (optional): [Research products] the section is referring to.
- `ra_template` *String* (optional): the URL of the template that is used to create the CV.


```json
"ra_profiles" : [
  {
    "title": "John Doe CV",
    "ra_sections": [
      {
        "title": "Ethical AI Models in Biochemical Research",
        "description": "Maximum 1000 words",
        "ra_content": "As artificial intelligence (AI) becomes integral to ...",
        "cites": ["product_1", "product_2"]	
      },
      {
        "title": "Exploring the Duality of Molecular Systems for Drug Design",
        "description": "Maximum 1000 words",
        "ra_content": "The complexity of molecular behavior in biological ...",
        "cites": ["product_3", "product_4"]	
      }
    ]
  }
]
```
----
[Research product]: {% link interoperability-framework/docs/research-product.md %}
[Research products]: {% link interoperability-framework/docs/research-product.md %}
[Agent]: {% link interoperability-framework/docs/agent.md %}
[Topic]: {% link interoperability-framework/docs/topic.md %}
[ISO 639-1]: https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes