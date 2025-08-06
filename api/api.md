---
title: API extensions
parent: RA-SKG
layout: default
nav_order: 5
---

# API extensions

The RA-SKG extension adds new properties to the core entities [Research product] and [Agent], which means also the schemas for these entities in the SKG-IF OpenAPI specification have to be extended. To do so this extension provides an OpenAPI overlay:[https://skg-if.github.io/ext-ra-skg/api/ver/current/overlay.yaml](https://skg-if.github.io/ext-ra-skg/api/ver/current/overlay.yaml). Using [speakeasy](https://www.speakeasy.com/openapi/overlays) this overlay can be applied to [https://skg-if.github.io/api/openapi/ver/current/skg-if-openapi.yaml](https://skg-if.github.io/api/openapi/ver/current/skg-if-openapi.yaml) (which may or not have other extension overlays already applied to it):

```sh
speakeasy overlay apply -s skg-if-openapi.yaml  -o overlay.yaml
```
----
[Research product]: {% link interoperability-framework/docs/research-product.md %}
[Agent]: {% link interoperability-framework/docs/agent.md %}
[Topic]: {% link interoperability-framework/docs/topic.md %}
