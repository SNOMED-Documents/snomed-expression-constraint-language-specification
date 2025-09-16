# Use Cases

The SNOMED CT Expression Constraint Language enables the intensional definition of a bounded set of clinical meanings. This is important for a number of use cases, including those described in this page.

## Terminology Binding

Most Electronic Health Records (EHRs) are designed and developed using one or more information models, which describe the information that is collected, stored, communicated and displayed. Some information models are designed for a specific proprietary system, while others are based on a common health information standard (e.g. HL7 FHIR resource, HL7 CDA template, ISO 13606 archetype). Information models may also be defined using a wide variety of representations (e.g. UML class diagram, database table design, Archetype Definition Language, or XML Schema). Irrespective of the purpose, design and representation of the information models, however, the use of clinical terminology is an important part of making the models complete and useful.

Terminology binding provides the links between the information model and the terminology. These links may be used to constrain the set of possible values which can populate a given coded data element in the information model, or they may define the meaning of an information model artefact using the terminology. Terminology binding is an important part of supporting the following clinical information system functions:

* Data capture;
* Retrieval and querying;
* Information model library management; and
* Semantic interoperability.

To enable terminology binding to be defined using intensional rules, a formal language must be used. The SNOMED CT Expression Constraint Language can be used in this way to define terminology bindings which constrain the set of possible coded values within an information model.

## Intensional Reference Set Definitions

Reference sets are a flexible, extensible SNOMED CT file structure used to support a variety of requirements for the customization and enhancement of SNOMED CT content. These include the representation of subsets, language preferences, or maps to/from other code systems.

Some reference sets (using the Query Specification type) allow a serialised query to represent the membership of a subset of SNOMED CT components. A query contained in this reference set is executed against the content of SNOMED CT to produce a subset of concepts, descriptions or relationships. This query is referred to as an intensional definition of the subset. It can be run against future releases of SNOMED CT to generate a potentially different set of subset members. The members of the resulting subset may also be represented in an enumerated form as a Simple Reference Set. An enumerated representation of a subset is referred to as an extensional definition.

The SNOMED CT Expression Constraint Language can be used in this way to represent the intensional definition of a subset of SNOMED CT concepts that can be enumerated as a Simple Reference Set.

## SNOMED CT Content Queries

SNOMED CT provides both hierarchies and formal concept definitions to allow a range of advanced query techniques. SNOMED CT queries can be performed over different sets of terminology artefacts (known as the substrate of the query), including:

* The precoordinated components distributed as part of the SNOMED CT international edition;
* The precoordinated components distributed by a local release centre as part of a national or local SNOMED CT edition;
* The postcoordinated expressions stored within an expression repository; or
* The SNOMED CT expressions stored within an Electronic Health Record (EHR).

The SNOMED CT Expression Constraint Language enables queries over SNOMED CT content to be expressed. These queries may be performed for a range of purposes, including the authoring and quality assurance of new SNOMED CT content, the design and development of extensional reference sets, and the design and display of SNOMED CT subsets in clinical user interfaces. While the language itself does not support querying over the full EHR content, the SNOMED CT Expression Constraint Language could be embedded within record-based query languages (such as SQL) to represent the terminological aspects of these queries.

## SNOMED CT Concept Model

The SNOMED CT Concept Model is the set of rules that determines the permitted sets of attributes and values that may be applied to particular types of concepts. There are also additional rules on the cardinality and grouping of each type of attribute. The SNOMED CT Concept Model includes the definition of the domain and range of each attribute. The domain is the set of concepts which are permitted to be used as the source of the attribute, while the range is the set of concepts which are permitted to be used as the target of the attribute. For example, the domain of the attribute [363698007 | Finding site|](http://snomed.info/id/363698007) is the descendants and self of [404684003 | Clinical finding|](http://snomed.info/id/404684003) , while the range is the descendants and self of [442083009 | Anatomical or acquired body structure|](http://snomed.info/id/442083009) The SNOMED CT Concept Model rules are represented in a computable form in the [SNOMED CT Machine Readable Concept Model.](https://app.gitbook.com/o/h8Z6qGxuQrzM9vbx5bPT/s/wLJPOzgAQsSAYr6nhvCl/)






<a href="https://docs.google.com/forms/d/e/1FAIpQLScTmbZIf0UEQwYDkY27EEWBkaiYkHSbR0_9DmFrMLXoQLyL7Q/viewform?usp=pp_url&entry.1767247133=ECL+Specification&entry.670899847=Use%20Cases" class="button primary">Provide Feedback</a>
