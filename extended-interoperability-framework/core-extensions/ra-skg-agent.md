---
title: Agent
parent: Interoperability framework
ancestor: RA-SKG
layout: default
nav_order: 1
---

# (Extended) Agent

The RA-SKG extension introduce metrics (i.e., indicators and badges) for [Agent].

## Properties

### `ra_metrics`
*List* (recommended): A collection of metrics available for a [Agent]. 

Each element of the list is structured as follow.
- `ra_metric` *Object* (mandatory): The information about the provided metric. This property is structured as follows:
    - `ra_measure` *Object* (mandatory): An object containing representing the scalar and its meaning.
      - `class` *String* (mandatory): The URL of the class identifying the entity (e.g., in an ontology) describing that type.
      - `labels` *Object* (mandatory): the labels describing the type (multiple for multilingualism). 
    The object is a dictionary, the keys represent language codes following [ISO 639-1]; the special key `none` is reserved whenever the information about the language is not available or cannot be shared.
      - `defined_in` *String* (mandatory): the URL of the schema of the manifestation type, e.g., a link to the vocabulary of allowed product types.
    - `ra_value` *String* (mandatory): the actual value of the metric.
- `ra_provider` *String* (mandatory): An [Agent] providing the metric.
- `ra_discipline` *String* (mandatory): An [Topic] the metric is relevant to.
- `description` *String* (mandatory): A description of the metric.


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

----
[Research product]: {% link interoperability-framework/docs/research-product.md %}
[Agent]: {% link interoperability-framework/docs/agent.md %}
[Topic]: {% link interoperability-framework/docs/topic.md %}
[ISO 639-1]: https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes