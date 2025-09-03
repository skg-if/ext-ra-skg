---
title: API extensions
parent: RA-SKG
layout: default
nav_order: 5
---

# API extensions

The RA-SKG extension introduces additional properties for the core SKG-IF entities [Research product] and [Agent]. 
To support these additions, the SKG-IF API is extended, in a modular way, using an OpenAPI overlay applied to the core specification.

## Creating the RA-SKG OpenAPI specification

To generate the RA-SKG OpenAPI specification, apply the [RA-SKG overlay](https://skg-if.github.io/ext-ra-skg/api/ver/current/overlay.yaml) 
to the [SKG-IF core OpenAPI specification](https://skg-if.github.io/api/openapi/ver/current/skg-if-openapi.yaml) using [Speakeasy](https://www.speakeasy.com/openapi/overlays): 
```sh
speakeasy overlay apply -s skg-if-openapi.yaml -o overlay.yaml
```

The overlay can be used on its own or combined with other SKG-IF overlays.


## Extended query parameters

Once the overlay is applied, the RA-SKG API specification introduces additional query parameters to support filtering by RA-SKG metrics and profiles, 
as defined in the RA-SKG extension, for both [Research product] and [Agent] entities.

### Filtering by RA-SKG metrics

Supported endpoints: `/products`, `/persons`

These filters enable users to refine search results based on the presence and values of research assessment metrics, as described by the [ra_metrics] property.

These parameters enable filtering capabilities over both scalar metrics (e.g., citation counts) and badges. 
Some filters are applicable exclusively to one type (scalar or badge), while others are relevant to both.


#### Attribute filters

Query parameters for exact match filtering.

| Filter name      | Description                                                              | Applicable for |
| -------------------- | ------------------------------------------------------------------------ | -------------- |
| `ra_metrics.ra_provider`    | ID of the Agent that provided the metric.        | Scalar, Badge |
| `ra_metrics.ra_metric.ra_measure.class`       | The URL of the class identifying the entity (e.g., in an ontology) describing that type. | Scalar |
| `ra_metrics.ra_metric.ra_measure.labels`       | The label describing the type. | Scalar |
| `ra_metrics.ra_metric.ra_measure.defined_id`  | The URL of the schema of the manifestation type. | Scalar |
| `ra_metrics.ra_metric.ra_category.class`       | The URL of the class identifying the entity (e.g., in an ontology) describing that type.        | Badge |
| `ra_metrics.ra_metric.ra_category.labels`       | The label describing the type. | Badge |
| `ra_metrics.ra_metric.ra_category.defined_in`  | The URL of the schema of the manifestation type.               | Badge |


#### Convenience filters

These filters are not properties of the [RA-SKG Research product] or [RA-SKG Agent], but they are useful for some common use cases.


| Filter name      | Description                                                              | Applicable for |
| -------------------- | ------------------------------------------------------------------------ | -------------- |
| `cf.search.ra_metrics.description`    | Keyword of phrase search in the `description` of the given metrics.        | Scalar, Badge |
| `cf.min.ra_metrics.ra_metric.ra_value`   | Minimum threshold for the metric value.                     | Scalar |
| `cf.max.ra_metrics.ra_metric.ra_value`   | Maximum threshold for the metric value.                     | Scalar |

### Filtering by RA-SKG profiles

Supported endpoint: `/persons`

To support filtering based on the [ra_profiles] property of the [RA-SKG Agent], the RA-SKG API specification defines the following query parameters. 
These filters allow users to search for Persons that include specific profile information.

#### Attribute filters

Query parameters for exact match filtering.

| Filter name                | Description                                                                                                                                                                        |
| ------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `ra_profiles.ra_template`       | Filter by the URL of the template that is used to create the CV.                                                                                             |
| `ra_profiles.ra_sections.cites`       | Filter entities that cite a specific research product by its identifier. |

#### Convenience filters

These filters aren not properties of the [RA-SKG Agent], but they are useful for some common use cases.

| Filter name                | Description                                                                                                                                                                        |
| ------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `cf.search.ra_profiles.title`       | Keyword or phrase search in the titles of the `ra_profiles`.                                                                                             |
| `cf.search.ra_profiles.ra_sections.title`       | Keyword or phrase search in the section titles of the `ra_profiles`.                                                                                                   |
| `cf.search.ra_profiles.ra_sections.description` | Keyword or phrase search in the section descriptions of the `ra_profiles`, e.g., to find those with specific thematic focus.     |
| `cf.search.ra_profiles.ra_sections.ra_content`    | Keyword or phrase search in the content of all sections of the `ra_profiles`.                                                                   |


----
[Research product]: {% link interoperability-framework/docs/research-product.md %}
[Agent]: {% link interoperability-framework/docs/agent.md %}
[RA-SKG Agent]: {% link ext-ra-skg/extended-interoperability-framework/core-extensions/ra-skg-agent.md %}
[RA-SKG Research product]: {% link ext-ra-skg/extended-interoperability-framework/core-extensions/ra-skg-research-product.md %}
[ra_metrics]: {% link ext-ra-skg/extended-interoperability-framework/core-extensions/ra-skg-research-product.md %}#ra_metrics
[ra_profiles]: {% link ext-ra-skg/extended-interoperability-framework/core-extensions/ra-skg-research-product.md %}#ra_profiles