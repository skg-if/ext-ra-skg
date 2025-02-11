# Formal Competency Questions

## MS1
Provide a list of all Open Access Publications for 2023 for Journal Articles (Gold (APC Driven), Green, Diamond) published by authors affiliated with University of Bologna using the OpenAIRE Graph.

```SPARQL
PREFIX : <https://w3id.org/skg-if/ontology/data/02/>
PREFIX datacite: <http://purl.org/spar/datacite/>
PREFIX dcat: <http://www.w3.org/ns/dcat#>
PREFIX dcterms: <http://purl.org/dc/terms/>
PREFIX fabio: <http://purl.org/spar/fabio/>
PREFIX foaf: <http://xmlns.com/foaf/0.1/>
PREFIX frbr: <http://purl.org/vocab/frbr/core#>
PREFIX literal: <http://purl.org/spar/literal/>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX pro: <http://purl.org/spar/pro/>
PREFIX pso: <http://purl.org/spar/pso/>
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>

SELECT DISTINCT ?ror_id ?org_name ?article_title (GROUP_CONCAT(DISTINCT ?article_doi; separator=", ") AS ?article_dois) ?open_access_type (YEAR(?issued_date) AS ?year)
WHERE {
    
    ?article a fabio:Work ;
        dcterms:title ?article_title ;
        datacite:hasIdentifier [ literal:hasLiteralValue ?article_doi ; datacite:usesIdentifierScheme datacite:doi ] ;
        pro:isRelatedToRoleInTime [ pro:withRole scoro:affiliate ; pro:relatesToOrganization :university-of-bologna ] ;
        frbr:realization [ 
            a ?type ;
            dcterms:issued ?issued_date ;
            pso:holdsStatusInTime [ pso:withStatus ?open_access_type ] 
        ] .
    
    :university-of-bologna foaf:name ?org_name ;
        datacite:hasIdentifier [ literal:hasLiteralValue ?ror_id ; datacite:usesIdentifierScheme datacite:ror ] .
    
    FILTER (
        ?type = fabio:JournalArticle
        &&
        ?issued_date >= "2023-01-01T00:00:00+00:00"^^xsd:dateTime 
        &&
        ?issued_date <= "2023-12-31T23:59:59+00:00"^^xsd:dateTime
    )

}
GROUP BY ?article
```

***

## MS2

Provide a list of all datasets identified in OpenAIRE that are affiliated with University of Bologna, in any year between 2014-2024.

```SPARQL
PREFIX : <https://w3id.org/skg-if/ontology/data/02/>
PREFIX datacite: <http://purl.org/spar/datacite/>
PREFIX dcat: <http://www.w3.org/ns/dcat#>
PREFIX dcterms: <http://purl.org/dc/terms/>
PREFIX fabio: <http://purl.org/spar/fabio/>
PREFIX foaf: <http://xmlns.com/foaf/0.1/>
PREFIX frbr: <http://purl.org/vocab/frbr/core#>
PREFIX literal: <http://purl.org/spar/literal/>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX pro: <http://purl.org/spar/pro/>
PREFIX pso: <http://purl.org/spar/pso/>
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>

SELECT DISTINCT ?ror_id ?org_name ?dataset_title (GROUP_CONCAT(DISTINCT ?dataset_doi; separator=", ") AS ?dataset_dois) (YEAR(?issued_date) AS ?year)
WHERE {
    
    ?dataset a fabio:Dataset ;
        dcterms:title ?dataset_title ;
        datacite:hasIdentifier [ literal:hasLiteralValue ?dataset_doi ; datacite:usesIdentifierScheme datacite:doi ] ;
        pro:isRelatedToRoleInTime [ pro:withRole scoro:affiliate ; pro:relatesToOrganization :university-of-bologna ] ;
        frbr:realization [ dcterms:issued ?issued_date ] .
    
    :university-of-bologna foaf:name ?org_name ;
        datacite:hasIdentifier [ literal:hasLiteralValue ?ror_id ; datacite:usesIdentifierScheme datacite:ror ] .
    
    FILTER (
        ?issued_date >= "2014-01-01T00:00:00+00:00"^^xsd:dateTime 
        &&
        ?issued_date <= "2024-12-31T23:59:59+00:00"^^xsd:dateTime
    )

}
GROUP BY ?dataset
```

***

## MS3

Provide a list of all Preprints identified in OpenAIRE that are affiliated with University of Bologna, in any year between 2014-2024.

```SPARQL
PREFIX : <https://w3id.org/skg-if/ontology/data/02/>
PREFIX datacite: <http://purl.org/spar/datacite/>
PREFIX dcat: <http://www.w3.org/ns/dcat#>
PREFIX dcterms: <http://purl.org/dc/terms/>
PREFIX fabio: <http://purl.org/spar/fabio/>
PREFIX foaf: <http://xmlns.com/foaf/0.1/>
PREFIX frbr: <http://purl.org/vocab/frbr/core#>
PREFIX literal: <http://purl.org/spar/literal/>
PREFIX owl: <http://www.w3.org/2002/07/owl#>
PREFIX pro: <http://purl.org/spar/pro/>
PREFIX pso: <http://purl.org/spar/pso/>
PREFIX skos: <http://www.w3.org/2004/02/skos/core#>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>

SELECT DISTINCT ?ror_id ?org_name ?article_title (GROUP_CONCAT(DISTINCT ?article_doi; separator=", ") AS ?article_dois) ?type_label (YEAR(?issued_date) AS ?year) ?repository_name
WHERE {

    ?article a fabio:Work ;
        dcterms:title ?article_title ;
        datacite:hasIdentifier [ literal:hasLiteralValue ?article_doi ; datacite:usesIdentifierScheme datacite:doi ] ;
        pro:isRelatedToRoleInTime [ pro:withRole scoro:affiliate ; pro:relatesToOrganization :university-of-bologna ] ;
        frbr:realization [ 
            a ?type ;
            dcterms:issued ?issued_date ;
            dcat:accessService [
                foaf:name ?repository_name
            ]
        ] .

    :university-of-bologna foaf:name ?org_name ;
        datacite:hasIdentifier [ literal:hasLiteralValue ?ror_id ; datacite:usesIdentifierScheme datacite:ror ] .
    
    ?type skos:prefLabel ?type_label .
    
    FILTER (
        ?type = fabio:Preprint
        &&
        ?issued_date >= "2014-01-01T00:00:00+00:00"^^xsd:dateTime 
        &&
        ?issued_date <= "2024-12-31T23:59:59+00:00"^^xsd:dateTime
    )
    
}
GROUP BY ?article
```
