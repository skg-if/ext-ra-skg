# Formal Competency Questions

## MS1
Provide a list of all Open Access Publications for 2023 for Journal Articles (Gold (APC Driven), Green, Diamond) published by authors affiliated with University of Bologna using the OpenAIRE Graph.

```SPARQL
PREFIX tbox: <https://example.org/skg-if/extention/02/schema/>
PREFIX : <https://example.org/skg-if/extention/02/data/>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>

SELECT ?ror_id ?org_name ?article_title ?article_doi ?open_access_type ?year
WHERE {
    ?article a tbox:Work ;
        tbox:title ?article_title ;
        tbox:hasIdentifier ?article_identifier ;
        tbox:isRelatedToRoleInTIme ?role_in_time ;
        tbox:realization ?article_expression .

    ?identifier tbox:hasLiteralValue ?article_doi ;
        tbox:usesIdentifierScheme tbox:doi .

    ?role_in_time tbox:withRole tbox:affiliate ;
        tbox:relatesToOrganization :university-of-bologna .

    :university-of-bologna tbox:name ?org_name ;
        tbox:has_identifier ?unibo_identifier .

    ?unibo_identifier tbox:hasLiteralValue ?ror_id ;
        tbox:usesIdentifierScheme tbox:ror .

    ?article_expression a tbox:JournalArticle ;
        tbox:holdsStatusInTime ?status_in_time ;
        tbox:issued ?issued_date .

    ?status_in_time tbox:withStatus tbox:gold-open-access .

    FILTER (
        ?issued_date >= "2023-01-01T00:00:00+00:00"^^xsd:dateTime 
        && 
        ?issued_date <= "2023-12-31T23:59:59+00:00"^^xsd:dateTime
    )
}
```

***

## MS2

Provide a list of all datasets identified in OpenAIRE that are affiliated with University of Bologna, in any year between 2014-2024.

```SPARQL
PREFIX tbox: <https://example.org/skg-if/extention/02/schema/>
PREFIX : <https://example.org/skg-if/extention/02/data/>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>

SELECT DISTINCT ?ror_id ?org_name ?dataset_title (GROUP_CONCAT(DISTINCT ?dataset_doi; separator=", ") AS ?dataset_dois) (YEAR(?issued_date) AS ?year)
WHERE {
    ?dataset a tbox:Dataset ;
        tbox:title ?dataset_title ;
        tbox:hasIdentifier ?dataset_identifier ;
        tbox:isRelatedToRoleInTime ?role_in_time ;
        tbox:realization ?dataset_expression .

    ?dataset_identifier tbox:hasLiteralValue ?dataset_doi ;
        tbox:usesIdentifierScheme tbox:doi .

    ?role_in_time tbox:withRole tbox:affiliate ;
        tbox:relatesToOrganization :university-of-bologna .

    :university-of-bologna tbox:name ?org_name ;
        tbox:hasIdentifier ?unibo_identifier .

    ?unibo_identifier tbox:hasLiteralValue ?ror_id ;
        tbox:usesIdentifierScheme tbox:ror .

    ?dataset_expression tbox:issued ?issued_date .

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
PREFIX tbox: <https://example.org/skg-if/extention/02/schema/>
PREFIX : <https://example.org/skg-if/extention/02/data/>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>

SELECT DISTINCT ?ror_id ?org_name ?article_title (GROUP_CONCAT(DISTINCT ?article_doi; separator=", ") AS ?article_dois) ?type_label (YEAR(?issued_date) AS ?year)
WHERE {
    ?article a tbox:Work ;
        tbox:title ?article_title ;
        tbox:hasIdentifier ?article_identifier ;
        tbox:isRelatedToRoleInTime ?role_in_time ;
        tbox:realization ?article_expression .

    ?article_identifier tbox:hasLiteralValue ?article_doi ;
        tbox:usesIdentifierScheme tbox:doi .

    ?role_in_time tbox:withRole tbox:affiliate ;
        tbox:relatesToOrganization :university-of-bologna .

    :university-of-bologna tbox:name ?org_name ;
        tbox:hasIdentifier ?unibo_identifier .

    ?unibo_identifier tbox:hasLiteralValue ?ror_id ;
        tbox:usesIdentifierScheme tbox:ror .

    ?article_expression a ?type ;
        tbox:issued ?issued_date .

    ?type tbox:prefLabel ?type_label .

    FILTER (
        ?type = tbox:Preprint
        &&
        ?issued_date >= "2014-01-01T00:00:00+00:00"^^xsd:dateTime 
        &&
        ?issued_date <= "2024-12-31T23:59:59+00:00"^^xsd:dateTime
    )
}
GROUP BY ?article
```
