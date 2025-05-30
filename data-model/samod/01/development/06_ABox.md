---
title: Sample Data
layout: default
parent: Motivating Scenario 1
nav_order: 5
---

```
@prefix : <https://example.org/skg-if/extention/01/data/> .
@prefix owl: <http://www.w3.org/2002/07/owl#> .
@prefix rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#> .
@prefix xml: <http://www.w3.org/XML/1998/namespace> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .
@prefix tbox: <https://example.org/skg-if/extention/01/schema/> .
@base <https://example.org/skg-if/extention/01/data/> .

<https://example.org/skg-if/extention/01/data/> rdf:type owl:Ontology ;
                                                        owl:imports <https://example.org/skg-if/extention/01/schema/> .

:yoyota-vuvuli a tbox:Agent ;
    tbox:name "Yoyota Vuvuli" ;
    tbox:submits :academic-profile-1 ;
    tbox:holdsBibliometricDataInTime [
            tbox:withBibliometricData [
                tbox:hasMeasure tbox:author-publication-count ;
                tbox:hasNumericValue 4 
            ] ;
            tbox:description "The total number of a researcher's articles, reflecting their productivity." ;
            tbox:wasGeneratedBy [
                tbox:used [
                    tbox:description "Article metadata required to calculate the particular indicator are gathered by the OpenAIRE Graph v9.0.0." 
                ] ;
                tbox:description "All publication records of subtype \"Article\" from the OpenAIRE Graph that are marked as authored by the researcher are counted." ;
                tbox:wasAssociatedWith [
                    tbox:hasIdentifier [
                        tbox:hasLiteralValue "https://github.com/athenarc/bip-scholar-indicators" ;
                        tbox:usesIdentifierScheme tbox:url 
                    ] 
                ] 
            ] 
        ] ,
        [
            tbox:withBibliometricData [
                tbox:hasMeasure tbox:author-publication-count ;
                tbox:hasNumericValue 2 
            ] ;
            tbox:withinContext :environmental-science ;
            tbox:description "The total number of a researcher's articles from the field of Environmental Science, reflecting their productivity." ;
            tbox:wasGeneratedBy [
                tbox:used [
                    tbox:description "Article metadata required to calculate the particular indicator are gathered by the OpenAIRE Graph v9.0.0." 
                ] ;
                tbox:description "All publication records of subtype \"Article\" from the OpenAIRE Graph that are marked as authored by the researcher and are related to the Environmental Science field are counted." ;
                tbox:wasAssociatedWith [
                    tbox:hasIdentifier [
                        tbox:hasLiteralValue "https://github.com/athenarc/bip-scholar-indicators" ;
                        tbox:usesIdentifierScheme tbox:url 
                    ] 
                ] 
            ] 
        ] ,
        [
            tbox:withBibliometricData [
                tbox:hasMeasure tbox:author-publication-count ;
                tbox:hasNumericValue 2 
            ] ;
            tbox:withinContext :machine-learning ;
            tbox:description "The total number of a researcher's articles from the field of Machine Learning, reflecting their productivity." ;
            tbox:wasGeneratedBy [
                tbox:used [
                    tbox:description "Article metadata required to calculate the particular indicator are gathered by the OpenAIRE Graph v9.0.0." 
                ] ;
                tbox:description "All publication records of subtype \"Article\" from the OpenAIRE Graph that are marked as authored by the researcher and are related to the Machine Learning field are counted." ;
                tbox:wasAssociatedWith [
                    tbox:hasIdentifier [
                        tbox:hasLiteralValue "https://github.com/athenarc/bip-scholar-indicators" ;
                        tbox:usesIdentifierScheme tbox:url 
                    ] 
                ] 
            ] 
        ] ,
        [
            tbox:withBibliometricData [
                tbox:hasMeasure tbox:author-citation-count ;
                tbox:hasNumericValue 124 
            ] ;
            tbox:description "The total number of citations received by all articles of the researcher of interest." ;
            tbox:wasGeneratedBy [
                tbox:used [
                    tbox:description "Citations and article metadata required to calculate the particular indicator are gathered by the OpenAIRE Graph v9.0.0." 
                ] ;
                tbox:description "All publication records of subtype \"Article\" from the OpenAIRE Graph that are marked as authored by the researcher were collected and their citations from other articles were counted." ;
                tbox:wasAssociatedWith [
                    tbox:hasIdentifier [
                        tbox:hasLiteralValue "https://github.com/athenarc/bip-scholar-indicators" ;
                        tbox:usesIdentifierScheme tbox:url 
                    ] 
                ] 
            ] 
        ] ,
        [
            tbox:withBibliometricData [
                tbox:hasMeasure tbox:author-citation-count ;
                tbox:hasNumericValue 52 
            ] ;
            tbox:withinContext :environmental-science ;
            tbox:description "The total number of citations received by all articles of the researcher of interest from the field of Environmental Science." ;
            tbox:wasGeneratedBy [
                tbox:used [
                    tbox:description "Citations and article metadata required to calculate the particular indicator are gathered by the OpenAIRE Graph v9.0.0." 
                ] ;
                tbox:description "All publication records of subtype \"Article\" from the OpenAIRE Graph that are marked as authored by the researcher and are related to the Environmental Science field were collected and their citations from other articles were counted." ;
                tbox:wasAssociatedWith [
                    tbox:hasIdentifier [
                        tbox:hasLiteralValue "https://github.com/athenarc/bip-scholar-indicators" ;
                        tbox:usesIdentifierScheme tbox:url 
                    ] 
                ] 
            ] 
        ] ,
        [
            tbox:withBibliometricData [
                tbox:hasMeasure tbox:author-citation-count ;
                tbox:hasNumericValue 106 
            ] ;
            tbox:withinContext :machine-learning ;
            tbox:description "The total number of citations received by all articles of the researcher of interest from the field of Machine Learning." ;
            tbox:wasGeneratedBy [
                tbox:used [
                    tbox:description "Citations and article metadata required to calculate the particular indicator are gathered by the OpenAIRE Graph v9.0.0." 
                ] ;
                tbox:description "All publication records of subtype \"Article\" from the OpenAIRE Graph that are marked as authored by the researcher and are related to the Machine Learning field were collected and their citations from other articles were counted." ;
                tbox:wasAssociatedWith [
                    tbox:hasIdentifier [
                        tbox:hasLiteralValue "https://github.com/athenarc/bip-scholar-indicators" ;
                        tbox:usesIdentifierScheme tbox:url 
                    ] 
                ] 
            ] 
        ] ,
        [
            tbox:withBibliometricData [
                tbox:hasMeasure tbox:author-download-count ;
                tbox:hasNumericValue 5600 
            ] ;
            tbox:description "The total number of downloads received by all articles of the researcher of interest." ;
            tbox:wasGeneratedBy [
                tbox:used [
                    tbox:description "Usage data and article metadata required to calculate the particular indicator are gathered by the OpenAIRE Graph v9.0.0." 
                ] ;
                tbox:description "All publication records of subtype \"Article\" from the OpenAIRE Graph that are marked as authored by the researcher were collected and their downloads were counted." ;
                tbox:wasAssociatedWith [
                    tbox:hasIdentifier [
                        tbox:hasLiteralValue "https://github.com/athenarc/bip-scholar-indicators" ;
                        tbox:usesIdentifierScheme tbox:url 
                    ] 
                ] 
            ] 
        ] .

:academic-profile-1 a tbox:Expression .
    

:article-1 a tbox:ScholarlyWork ;
    tbox:title "Enhancing Sustainable Agriculture through AI-Driven Soil Monitoring" ;
    tbox:hasIdentifier [
        tbox:hasLiteralValue "10.1234/envinf.2022.001" ;
        tbox:usesIdentifierScheme tbox:doi 
    ] ;
    tbox:realization [
        tbox:issued "2024-01-01T00:00:00+00:00"^^xsd:dateTime ;
        tbox:partOf [
            tbox:title "Journal of Environmental Informatics" 
        ]
    ] ;
    tbox:isRelatedToRoleInTime [
        tbox:withContribution tbox:conceptualization ;
        tbox:isHeldBy :yoyota-vuvuli 
    ] ,
    [
        tbox:withContribution tbox:methodology ;
        tbox:isHeldBy :yoyota-vuvuli 
    ] ,
    [
        tbox:withContribution tbox:writing-lead ;
        tbox:isHeldBy :yoyota-vuvuli 
    ] ,
    [
        tbox:withContribution tbox:data-analysis ;
        tbox:isHeldBy :ahmed-el-zein 
    ] ,
    [
        tbox:withContribution tbox:software-development ;
        tbox:isHeldBy :ahmed-el-zein 
    ] ,
    [
        tbox:withContribution tbox:fieldwork ;
        tbox:isHeldBy :clara-green 
    ] ,
    [
        tbox:withContribution tbox:writing-review ;
        tbox:isHeldBy :clara-green 
    ] ,
    [
        tbox:withRole tbox:author ;
        tbox:isHeldBy :yoyota-vuvuli ;
        tbox:relatesToOrganization :university-of-bologna 
    ] ,
    [
        tbox:withRole tbox:author ;
        tbox:relatesToOrganization :university-of-bologna ;
        tbox:isHeldBy :ahmed-el-zein 
    ] ,
    [
        tbox:withRole tbox:author ;
        tbox:relatesToOrganization :university-of-bologna ;
        tbox:isHeldBy :clara-green 
    ] ;
    
    tbox:holdsBibliometricDataInTime [
        tbox:withBibliometricData :environmental-science ,
            :machine-learning ,
            :precision-agriculture 
    ] ,
    [
        tbox:withBibliometricData [
            tbox:hasMeasure tbox:publication-citation-count ;
            tbox:hasNumericValue 34 
        ] ;
        tbox:description "The total number of citations received by the article of interest." ;
        tbox:wasGeneratedBy [
            tbox:used [
                tbox:description "Citations and article metadata required to calculate the particular indicator are gathered by the OpenAIRE Graph v9.0.0." 
            ] ;
            tbox:description "All citations from other articles pointing to the article of interest were counted." ;
            tbox:wasAssociatedWith [
                tbox:hasIdentifier [
                    tbox:hasLiteralValue "https://github.com/athenarc/Bip-Ranker" ;
                    tbox:usesIdentifierScheme tbox:url 
                ] 
            ] 
        ] 
    ] ,
    [
        tbox:withBibliometricData [
            tbox:hasMeasure tbox:publication-download-count ;
            tbox:hasNumericValue 1200 
        ] ;
        tbox:description "The total number of downloads received by the article of interest." ;
        tbox:wasGeneratedBy [
            tbox:used [
                tbox:description "Usage data and article metadata required to calculate the particular indicator are gathered by the OpenAIRE Graph v9.0.0." 
            ] ;
            tbox:description "All publication records of subtype \"Article\" from the OpenAIRE Graph that are marked as authored by the researcher were collected and their downloads were counted." 
        ] 
    ] ,
    [
        tbox:withBibliometricData [
            a tbox:CategorialBibliometricData ;
            tbox:prefLabel "Data Open" ;
            tbox:withinContext [
                tbox:hasIdentifier [
                    tbox:hasLiteralValue "10.1234/agri2022data" ;
                    tbox:usesIdentifierScheme tbox:doi 
                ] 
            ] 
        ] 
    ] .

:article-2 a tbox:ScholarlyWork ;
    tbox:title "A Novel Framework for Interpretable Deep Learning in Biomedical Imaging" ;
    tbox:hasIdentifier [
        tbox:hasLiteralValue "10.5678/ieeetmi.2020.045" ;
        tbox:usesIdentifierScheme tbox:doi 
    ] ;
    tbox:realization [
        tbox:issued "2021-01-01T00:00:00+00:00"^^xsd:dateTime ;
        tbox:partOf [
            tbox:title "IEEE Transactions on Medical Imaging" 
        ]
    ] ;
    tbox:isRelatedToRoleInTime [
        tbox:withContribution tbox:conceptualization ;
        tbox:isHeldBy :yoyota-vuvuli 
    ] ,
    [
        tbox:withContribution tbox:algorithm-design ;
        tbox:isHeldBy :yoyota-vuvuli 
    ] ,
    [
        tbox:withContribution tbox:supervision ;
        tbox:isHeldBy :yoyota-vuvuli 
    ] ,
    [
        tbox:withContribution tbox:software-implementation ;
        tbox:isHeldBy :james-patterson 
    ] ,
    [
        tbox:withContribution tbox:data-curation ;
        tbox:isHeldBy :james-patterson 
    ] ,
    [
        tbox:withContribution tbox:validation ;
        tbox:isHeldBy :rina-huang 
    ] ,
    [
        tbox:withContribution tbox:experimentation ;
        tbox:isHeldBy :rina-huang 
    ] ,
    [
        tbox:withRole tbox:author ;
        tbox:relatesToOrganization :university-of-bologna ;
        tbox:isHeldBy :yoyota-vuvuli 
    ] ,
    [
        tbox:withRole tbox:author ;
        tbox:relatesToOrganization :university-of-bologna ;
        tbox:isHeldBy :james-patterson 
    ] ,
    [
        tbox:withRole tbox:author ;
        tbox:relatesToOrganization :university-of-bologna ;
        tbox:isHeldBy :rina-huang 
    ] ;
    tbox:relatesToOrganization :university-of-bologna ;
    tbox:holdsBibliometricDataInTime [
        tbox:withBibliometricData :machine-learning ,
            :biomedical-imaging 
    ] ,
    [
        tbox:withBibliometricData [
            tbox:hasMeasure tbox:publication-citation-count ;
            tbox:hasNumericValue 42 
        ] ;
        tbox:description "The total number of citations received by the article of interest." ;
        tbox:wasGeneratedBy [
            tbox:used [
                tbox:description "Citations and article metadata required to calculate the particular indicator are gathered by the OpenAIRE Graph v9.0.0." 
            ] ;
            tbox:description "All citations from other articles pointing to the article of interest were counted." ;
            tbox:wasAssociatedWith [
                tbox:hasIdentifier [
                    tbox:hasLiteralValue "https://github.com/athenarc/Bip-Ranker" ;
                    tbox:usesIdentifierScheme tbox:url 
                ] 
            ] 
        ] 
    ] ,
    [
        tbox:withBibliometricData [
            tbox:hasMeasure tbox:publication-download-count ;
            tbox:hasNumericValue 1500 
        ] ;
        tbox:description "The total number of downloads received by the article of interest." ;
        tbox:wasGeneratedBy [
            tbox:used [
                tbox:description "Usage data and article metadata required to calculate the particular indicator are gathered by the OpenAIRE Graph v9.0.0." 
            ] ;
            tbox:description "All publication records of subtype \"Article\" from the OpenAIRE Graph that are marked as authored by the researcher were collected and their downloads were counted." 
        ] 
    ] ,
    [
        tbox:withBibliometricData [
            a tbox:CategorialBibliometricData ;
            tbox:prefLabel "Code Open" ;
            tbox:withinContext [
                tbox:hasIdentifier [
                    tbox:hasLiteralValue "github.com/vuvuli2020-framework" ;
                    tbox:usesIdentifierScheme tbox:github 
                ] 
            ] 
        ] 
    ] .

:article-3 a tbox:ScholarlyWork ;
    tbox:title "Towards a Comprehensive Ontology for Climate Data Sharing" ;
    tbox:hasIdentifier [
        tbox:hasLiteralValue "10.9101/dscc.2021.002" ;
        tbox:usesIdentifierScheme tbox:doi 
    ] ;
    tbox:realization [
        tbox:issued "2023-01-01T00:00:00+00:00"^^xsd:dateTime ;
        tbox:partOf [
            tbox:title "Data Science for Climate Change" 
        ]
    ] ;
    tbox:isRelatedToRoleInTime [
        tbox:withContribution tbox:conceptualization ;
        tbox:isHeldBy :yoyota-vuvuli 
    ] ,
    [
        tbox:withContribution tbox:ontology-design ;
        tbox:isHeldBy :yoyota-vuvuli 
    ] ,
    [
        tbox:withContribution tbox:writing-lead ;
        tbox:isHeldBy :yoyota-vuvuli 
    ] ,
    [
        tbox:withContribution tbox:data-integration ;
        tbox:isHeldBy :marie-dupont 
    ] ,
    [
        tbox:withContribution tbox:writing-review ;
        tbox:isHeldBy :marie-dupont 
    ] ,
    [
        tbox:withContribution tbox:validation ;
        tbox:isHeldBy :hiroshi-nakamura 
    ] ,
    [
        tbox:withContribution tbox:technical-infrastructure ;
        tbox:isHeldBy :hiroshi-nakamura 
    ] ,
    [
        tbox:withRole tbox:author ;
        tbox:relatesToOrganization :university-of-bologna ;
        tbox:isHeldBy :yoyota-vuvuli 
    ] ,
    [
        tbox:withRole tbox:author ;
        tbox:relatesToOrganization :university-of-bologna ;
        tbox:isHeldBy :marie-dupont 
    ] ,
    [
        tbox:withRole tbox:author ;
        tbox:relatesToOrganization :university-of-bologna ;
        tbox:isHeldBy :hiroshi-nakamura 
    ] ;
    tbox:holdsBibliometricDataInTime [
        tbox:withBibliometricData :environmental-science ,
            :biomedical-imaging 
    ] ,
    [
        tbox:withBibliometricData [
            tbox:hasMeasure tbox:publication-citation-count ;
            tbox:hasNumericValue 18 
        ] ;
        tbox:description "The total number of citations received by the article of interest." ;
        tbox:wasGeneratedBy [
            tbox:used [
                tbox:description "Citations and article metadata required to calculate the particular indicator are gathered by the OpenAIRE Graph v9.0.0." 
            ] ;
            tbox:description "All citations from other articles pointing to the article of interest were counted." ;
            tbox:wasAssociatedWith [
                tbox:hasIdentifier [
                    tbox:hasLiteralValue "https://github.com/athenarc/Bip-Ranker" ;
                    tbox:usesIdentifierScheme tbox:url 
                ] 
            ] 
        ] 
    ] ,
    [
        tbox:withBibliometricData [
            tbox:hasMeasure tbox:publication-download-count ;
            tbox:hasNumericValue 950 
        ] ;
        tbox:description "The total number of downloads received by the article of interest." ;
        tbox:wasGeneratedBy [
            tbox:used [
                tbox:description "Usage data and article metadata required to calculate the particular indicator are gathered by the OpenAIRE Graph v9.0.0." 
            ] ;
            tbox:description "All publication records of subtype \"Article\" from the OpenAIRE Graph that are marked as authored by the researcher were collected and their downloads were counted." 
        ] 
    ] ,
    [
        tbox:withBibliometricData [
            a tbox:CategorialBibliometricData ;
            tbox:prefLabel "FAIR Data" ;
            tbox:withinContext [
                tbox:hasValue "85%" 
            ] 
        ] 
    ] .

:article-4 a tbox:ScholarlyWork ;
    tbox:title "Ethical AI for Equitable Healthcare Diagnostics" ;
    tbox:hasIdentifier [
        tbox:hasLiteralValue "10.3456/jrai.2019.014" ;
        tbox:usesIdentifierScheme tbox:doi 
    ] ;
    tbox:realization [
        tbox:issued "2019-01-01T00:00:00+00:00"^^xsd:dateTime ;
        tbox:partOf [
            tbox:title "Journal of Responsible AI Applications" 
        ]
    ] ;
    tbox:isRelatedToRoleInTime [
        tbox:withContribution tbox:framework-design ;
        tbox:isHeldBy :yoyota-vuvuli 
    ] ,
    [
        tbox:withContribution tbox:case-studies ;
        tbox:isHeldBy :yoyota-vuvuli 
    ] ,
    [
        tbox:withContribution tbox:writing-lead ;
        tbox:isHeldBy :yoyota-vuvuli 
    ] ,
    [
        tbox:withContribution tbox:literature-review ;
        tbox:isHeldBy :sarah-michaels 
    ] ,
    [
        tbox:withContribution tbox:ethical-analysis ;
        tbox:isHeldBy :sarah-michaels 
    ] ,
    [
        tbox:withRole tbox:author ;
        tbox:relatesToOrganization :university-of-bologna ;
        tbox:isHeldBy :yoyota-vuvuli 
    ] ,
    [
        tbox:withRole tbox:author ;
        tbox:relatesToOrganization :university-of-bologna ;
        tbox:isHeldBy :sarah-michaels 
    ] ;
    tbox:relatesToOrganization :university-of-bologna ;
    tbox:holdsBibliometricDataInTime [
        tbox:withBibliometricData :machine-learning ,
            :ethics-in-ai 
    ] ,
    [
        tbox:withBibliometricData [
            tbox:hasMeasure tbox:publication-citation-count ;
            tbox:hasNumericValue 30 
        ] ;
        tbox:description "The total number of citations received by the article of interest." ;
        tbox:wasGeneratedBy [
            tbox:used [
                tbox:description "Citations and article metadata required to calculate the particular indicator are gathered by the OpenAIRE Graph v9.0.0." 
            ] ;
            tbox:description "All citations from other articles pointing to the article of interest were counted." ;
            tbox:wasAssociatedWith [
                tbox:hasIdentifier [
                    tbox:hasLiteralValue "https://github.com/athenarc/Bip-Ranker" ;
                    tbox:usesIdentifierScheme tbox:url 
                ] 
            ] 
        ] 
    ] ,
    [
        tbox:withBibliometricData [
            tbox:hasMeasure tbox:publication-download-count ;
            tbox:hasNumericValue 1950 
        ] ;
        tbox:description "The total number of downloads received by the article of interest." ;
        tbox:wasGeneratedBy [
            tbox:used [
                tbox:description "Usage data and article metadata required to calculate the particular indicator are gathered by the OpenAIRE Graph v9.0.0." 
            ] ;
            tbox:description "All publication records of subtype \"Article\" from the OpenAIRE Graph that are marked as authored by the researcher were collected and their downloads were counted." 
        ] 
    ] ,
    [
        tbox:withBibliometricData [
            a tbox:CategorialBibliometricData ;
            tbox:prefLabel "Transparent Algorithms" ;
            tbox:withinContext [
                tbox:hasIdentifier [
                    tbox:hasLiteralValue "10.5678/ethicalai2019" ;
                    tbox:usesIdentifierScheme tbox:doi 
                ] 
            ] 
        ] 
    ] .

:university-of-bologna a tbox:Organization ;
    tbox:name "University of Bologna" .

:ahmed-el-zein a tbox:Agent ;
    tbox:name "Ahmed El-Zein" .

:clara-green a tbox:Agent ;
    tbox:name "Clara Green" .

:james-patterson a tbox:Agent ;
    tbox:name "James Patterson" .

:rina-huang a tbox:Agent ;
    tbox:name "Rina Huang" .

:marie-dupont a tbox:Agent ;
    tbox:name "Marie Dupont" .

:hiroshi-nakamura a tbox:Agent ;
    tbox:name "Hiroshi Nakamura" .

:sarah-michaels a tbox:Agent ;
    tbox:name "Sarah Michaels" .

:machine-learning a tbox:SubjectTerm ;
    tbox:prefLabel "Machine Learning" .

:environmental-science a tbox:SubjectTerm ;
    tbox:prefLabel "Environmental Science" .

:precision-agriculture a tbox:SubjectTerm ;
    tbox:prefLabel "Precision Agriculture" .

:biomedical-imaging a tbox:SubjectTerm ;
    tbox:prefLabel "Biomedical Imaging" .

:ethics-in-ai a tbox:SubjectTerm ;
    tbox:prefLabel "Ethics in AI" .

:john-doe a tbox:Agent ;
    tbox:name "John Doe" ;
    tbox:submits :academic-profile-2 ;
    tbox:holdsRoleInTime [
        tbox:withRole tbox:principal-researcher ;
        tbox:relatesToOrganization :university-of-bologna 
    ] ;
    tbox:hasEmail "j.doe@narniauni.edu" .

:academic-profile-2 a tbox:Expression ;
    tbox:hasPart [
        tbox:title "Personal statement" ;
        tbox:hasContent "I am a passionate and driven materials scientist dedicated to advancing sustainable solutions to global environmental challenges. My research focuses on the development of biodegradable polymers, aiming to reduce plastic waste and its impact on ecosystems. With over a decade of experience in academic and collaborative industry projects, I have cultivated a multidisciplinary approach, integrating chemistry, materials science, and environmental studies to drive innovation in sustainable materials. Throughout my career, I have been committed to fostering an inclusive and collaborative research environment. By mentoring early-career researchers, supervising diverse teams, and organizing training programs, I have supported others in achieving their potential while ensuring knowledge transfer across generations of scientists. Beyond my research contributions, I actively engage with the wider scientific and public communities to amplify the impact of my work. Whether through advising policymakers on sustainable packaging legislation or participating in outreach programs to inspire young minds, I strive to bridge the gap between science and society." 
    ] ,
    [
        tbox:title "Contributions to General Knowledge" ;
        tbox:hasContent "I have dedicated my career to advancing the understanding of sustainable materials science, focusing on the development of biodegradable polymers for packaging applications. My work has led to the publication of 25 peer-reviewed journal articles, including high-impact papers in Nature Materials and Advanced Functional Materials. I led the “Sustainable Polymers Initiative,” a collaborative research project funded by the European Research Council, which developed a novel polymer blend with 50% lower environmental impact compared to traditional plastics. This research has been widely cited and has attracted industrial interest, leading to a joint patent with GreenPack Ltd. Supervising a diverse group of PhD students and postdoctoral researchers, I have fostered innovation and collaboration, resulting in four students winning national awards for their research excellence." 
    ] ,
    [
        tbox:title "Contributions to the Development of Individuals" ;
        tbox:hasContent "I am deeply committed to mentoring and supporting the next generation of researchers. Over the past five years, I have served as a mentor for the Royal Society’s “Future Leaders Program,” guiding early-career scientists in grant writing, career development, and balancing academic and personal responsibilities. I have organized annual training workshops on advanced polymer synthesis techniques, attracting participants from academic and industrial backgrounds. These workshops have been instrumental in equipping attendees with practical skills and fostering industry-academia collaborations. Additionally, I co-developed an undergraduate internship program within my department, which has provided hands-on research opportunities to over 30 students, many of whom have progressed to postgraduate studies." 
    ] ,
    [
        tbox:title "Contributions to Society" ;
        tbox:hasContent "My research has directly contributed to addressing global environmental challenges. The biodegradable polymer developed in the Sustainable Polymers Initiative is now being scaled up by GreenPack Ltd., with the potential to replace traditional plastics in 20% of European food packaging markets by 2030. To raise public awareness, I have participated in science communication initiatives such as the BBC series Future Materials, explaining the role of sustainable materials in tackling climate change. I also contribute regularly to outreach programs in local schools, inspiring young students to pursue careers in STEM fields. In 2022, I collaborated with policymakers to draft recommendations for sustainable packaging legislation, which influenced the European Union’s “Green Materials Directive." 
    ] .

:henry-jekyll a tbox:Agent ;
    tbox:name "Henry Jenkyll" ;
    tbox:submits :academic-profile-3 .

:academic-profile-3 a tbox:Expression ;
    tbox:hasPart [
        tbox:title "Exploring the Duality of Molecular Systems for Drug Design" ;
        tbox:hasContent "The complexity of molecular behavior in biological systems presents a significant challenge for drug design. My research aims to understand and leverage the dual nature of certain molecular systems, which can exhibit distinct functional states depending on environmental or structural conditions. This work addresses the need for more precise and adaptable pharmaceutical agents that minimize side effects while maximizing therapeutic efficacy. This line of research focuses on characterizing “switchable” biomolecules—compounds that can toggle between active and inactive states in response to stimuli like pH, light, or enzymatic interactions. By employing computational chemistry, structural biology, and experimental validation, I explore how these molecules interact with cellular pathways to enable targeted and dynamic drug delivery systems. This research has improved the understanding of molecular duality, paving the way for next-generation drugs that respond dynamically to the body’s needs. These findings have influenced early-stage pharmaceutical development and contributed to interdisciplinary collaborations between biophysics and pharmacology." ;
        tbox:cites :publication-1 ,
            :publication-2 ,
            :dataset-1 ,
            :dataset-2 
    ] ,
    [
        tbox:title "Ethical AI Models in Biochemical Research" ;
        tbox:hasContent "As artificial intelligence (AI) becomes integral to biochemical research, there is a growing need to ensure that these technologies operate transparently and equitably. My research investigates how AI models can be designed to prioritize ethical considerations, such as bias reduction, explainability, and equitable data representation, while maintaining scientific rigor and innovation. This work focuses on creating ethical frameworks for the development and application of AI in biochemical data analysis. It involves training neural networks on curated datasets, developing algorithms that emphasize interpretability, and implementing safeguards to prevent biased or unreliable predictions in drug discovery and diagnostics. This research has enhanced the reliability and trustworthiness of AI in biochemical applications, fostering more widespread adoption of these tools across academia and industry. It has also influenced discussions around the ethical implications of AI, contributing to the formulation of policy recommendations for its use in life sciences." ;
        tbox:cites :publication-3 ,
            :publication-4 ,
            :dataset-3 ,
            :dataset-4 
    ] .

:publication-1 a tbox:Expression ;
    tbox:realizationOf [
        a tbox:ScholarlyWork 
    ] ;
    tbox:bibliographicCitation "Jekyll, H., & Hyde, E. (2020). Structural insights into pH-sensitive molecular switches for targeted drug delivery. Journal of Molecular Systems, 45(3), 567–582." .

:publication-2 a tbox:Expression ;
    tbox:realizationOf [
        a tbox:ScholarlyWork 
    ] ;
    tbox:bibliographicCitation "Jekyll, H. et al. (2021). Computational and experimental evaluation of light-activated biomolecules for precision therapeutics. Biophysical Advances, 12(4), 123–138." .

:publication-3 a tbox:Expression ;
    tbox:realizationOf [
        a tbox:ScholarlyWork 
    ] ;
    tbox:bibliographicCitation "Jekyll, H., & Smith, A. (2022). Ethical AI frameworks for protein-ligand interaction predictions. Computational Chemistry Ethics, 8(1), 45–63." .

:publication-4 a tbox:Expression ;
    tbox:realizationOf [
        a tbox:ScholarlyWork 
    ] ;
    tbox:bibliographicCitation "Jekyll, H., & Patel, R. (2023). Bias reduction in AI-driven biochemical research: A case study on data curation. Journal of Ethical AI in Science, 2(3), 98–112." .

:dataset-1 a tbox:Expression ;
    tbox:realizationOf [
        a tbox:Dataset 
    ] ;
    tbox:bibliographicCitation "Molecular Switch Simulation Data for pH-Sensitive Systems” (DOI: 10.1234/molswitch2020)" .

:dataset-2 a tbox:Expression ;
    tbox:realizationOf [
        a tbox:Dataset 
    ] ;
    tbox:bibliographicCitation "Experimental Data on Light-Responsive Drug Delivery Molecules (DOI: 10.5678/lightdrugdata2021)" .

:dataset-3 a tbox:Expression ;
    tbox:realizationOf [
        a tbox:Dataset 
    ] ;
    tbox:bibliographicCitation "Curated Protein-Ligand Interaction Data for AI Training (DOI: 10.9101/proteinai2022)" .

:dataset-4 a tbox:Expression ;
    tbox:realizationOf [
        a tbox:Dataset 
    ] ;
    tbox:bibliographicCitation "Benchmark Data for Evaluating Ethical AI Models in Biochemistry (DOI: 10.8765/benchmarkbioai2023)" .

tbox:conceptualization a tbox:Contribution ;
    tbox:prefLabel "Conceptualization" .

tbox:methodology a tbox:Contribution ;
    tbox:prefLabel "Methodology" .

tbox:writing-lead a tbox:Contribution ;
    tbox:prefLabel "Writing (Lead)" .

tbox:data-analysis a tbox:Contribution ;
    tbox:prefLabel "Data Analysis" .

tbox:software-development a tbox:Contribution ;
    tbox:prefLabel "Software Development" .

tbox:fieldwork a tbox:Contribution ;
    tbox:prefLabel "Fieldwork" .

tbox:writing-review a tbox:Contribution ;
    tbox:prefLabel "Writing (Review)" .

tbox:algorithm-design a tbox:Contribution ;
    tbox:prefLabel "Algorithm Design" .

tbox:supervision a tbox:Contribution ;
    tbox:prefLabel "Supervision" .

tbox:software-implementation a tbox:Contribution ;
    tbox:prefLabel "Software Implementation" .

tbox:data-curation a tbox:Contribution ;
    tbox:prefLabel "Data Curation" .

tbox:validation a tbox:Contribution ;
    tbox:prefLabel "Validation" .

tbox:experimentation a tbox:Contribution ;
    tbox:prefLabel "Experimentation" .

tbox:ontology-design a tbox:Contribution ;
    tbox:prefLabel "Ontology Design" .

tbox:data-integration a tbox:Contribution ;
    tbox:prefLabel "Data Integration" .

tbox:technical-infrastructure a tbox:Contribution ;
    tbox:prefLabel "Technical Infrastructure" .

tbox:framework-design a tbox:Contribution ;
    tbox:prefLabel "Framework Design" .

tbox:case-studies a tbox:Contribution ;
    tbox:prefLabel "Case Studies" .

tbox:literature-review a tbox:Contribution ;
    tbox:prefLabel "Literature Review" .

tbox:ethical-analysis a tbox:Contribution ;
    tbox:prefLabel "Ethical Analysis" .
```