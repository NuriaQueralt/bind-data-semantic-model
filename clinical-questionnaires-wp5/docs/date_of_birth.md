## Date of Birth

### Semantic model figure
This module describes the data elements in the KHTQ. It specifically covers the data element in the table _Date of Birth_. This module is based on the EJP RD CDE semantic model module for _Personal Information_ group [CDE-semantic-model/personal_information](https://github.com/ejp-rd-vp/CDE-semantic-model/blob/980b1125222f1654c03da605835cbfd987d7970e/docs/personal_information.md).

### Example RDF (turtle)
```ttl
@prefix : <http://w3id.org/bind/data/v1/example-rdf/> .
@prefix obo: <http://purl.obolibrary.org/obo/> .
@prefix sio: <http://semanticscience.org/resource/> .
@prefix xsd: <http://www.w3.org/2001/XMLSchema#> .
@prefix rdfs: <http://www.w3.org/2000/01/rdf-schema#> .

:identifier_ a sio:SIO_000115 ;
    sio:SIO_000020 :birthdate_role_ ;
    sio:SIO_000300 "uid_000001"^^xsd:string .

:person_ a sio:SIO_000498;
    sio:SIO_000228 :birthdate_role_ ;
    sio:SIO_000008 :birthdate_attribute_ .

:birthdate_role_  a obo:OBI_0000093, sio:SIO_000016 ;
    rdfs:label "Role: Patient for age assessment"^^xsd:string ;
    sio:SIO_000356 :birthdate_process_ .

:birthdate_process_ a sio:SIO_000006 ;
    rdfs:label "Process: Age measuring process"^^xsd:string ;
    sio:SIO_000229 :birthdate_output_ .

:birthdate_output_ a sio:SIO_000015 ;
    rdfs:label "Output Type: Birth date"^^xsd:string ;
    sio:SIO_000300 "2013-12-11"^^xsd:date ;
    sio:SIO_000628 :birthdate_attribute_ .

:birthdate_attribute_ a sio:SIO_000614, obo:NCIT_C68615 ;
    rdfs:label "Attribute Type: Birth date"^^xsd:string .
```

***
### Validation artifacts
##### ShEx figure


***
##### ShEx
``` ShEx
PREFIX : <http://w3id.org/bind/data/v1/shex/>
PREFIX obo: <http://purl.obolibrary.org/obo/> 
PREFIX sio: <http://semanticscience.org/resource/>
PREFIX xsd: <http://www.w3.org/2001/XMLSchema#>
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>

:identifierShape IRI {
    a [sio:SIO_000115];
    rdfs:label xsd:string? ;
    sio:SIO_000020 @:birthdateRoleShape ;
    sio:SIO_000020 @:sexRoleShape ;
    sio:SIO_000300 xsd:string
}

:personShape IRI { 
    a [sio:SIO_000498] ;
    rdfs:label xsd:string? ;
    sio:SIO_000228 @:birthdateRoleShape ;
    sio:SIO_000008 @:birthdateAttributeShape ;
    sio:SIO_000228 @:sexRoleShape ;
    sio:SIO_000008 @:sexAttributeShape
}

:birthdateRoleShape IRI {
    a [obo:OBI_0000093] ;
    a [sio:SIO_000016] ;
    rdfs:label xsd:string? ;
    sio:SIO_000356 @:birthdateProcessShape
}

:birthdateProcessShape IRI {
    a [sio:SIO_000006] ;
    rdfs:label xsd:string? ;
    sio:SIO_000229 @:birthdateOutputShape
}

:birthdateOutputShape IRI {
    a [sio:SIO_000015] ;
    rdfs:label xsd:string? ;
    sio:SIO_000300 xsd:date ;
    sio:SIO_000628 @:birthdateAttributeShape
}

:birthdateAttributeShape IRI {
    a [sio:SIO_000614] ;
    a [obo:NCIT_C68615] ;
    rdfs:label xsd:string?
}
```
