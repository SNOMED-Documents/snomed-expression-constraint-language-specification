# Appendix E - Reference Set Fields

In the SNOMED CT Release File Specification (http://snomed.org/rfs), SNOMED International specifies a set of reference set types with their own specific properties (e.g. an attribute value type reference set). Each reference set that is developed to conform to a specified type is defined as a subtype of the associated reference set type concept (e.g. 900000000000480006 | Attribute value type reference set| ). All reference sets of a given type are populated with members using the same data structure - with the same set of field names in the same order. SNOMED International uses these reference set type data structures (as defined in the [SNOMED CT Release File Specification](https://app.gitbook.com/o/h8Z6qGxuQrzM9vbx5bPT/s/irKbJsZG57nSWZA4GT0M/ "mention") ) as the release file format for all reference sets of that type.

All reference set type concepts are a subtype of [900000000000455006 | Reference set|](http://snomed.info/id/900000000000455006) , and have an associated set of reference set descriptors in the [| Reference set descriptor reference set|](http://snomed.info/id/900000000000456007) . Some reference set type concepts are organised under one or more reference set groups (e.g. [723564002 | MRCM reference set|](http://snomed.info/id/723564002) ), which represent a group of reference set types (often with different data structures).

In the Expression Constraint Language (v2.0+) reference set field names are used to indicate which field values to return, and to filter reference set members based on specific field criteria. The first (non-metadata) field in every reference set (in order '0') must always be 'referencedComponentId'. For reference sets, which are a subtype of an international reference set type, the additional field names defined in the SNOMED CT Release File Specification must be used. In all other cases, the additional field names may use any latin-script alphabetic character (a-z or A-Z) defined by the owner of the corresponding reference set type concept. Owners of a reference set type are encouraged to explicitly document these field names, keep them unchanged and publish a machine readable representation of these (following the format used below). In the absence of this, the column name from the corresponding RF2 file (with all whitespace removed) will be used.

The international reference set types and their corresponding list of field names to be used in ECL v2.0+ are shown in the table below (for information only). A normative, computable representation of this table is attached below the table. Please note that this file may be extended by implementers with national or local reference set types.

## Reference Set Types

### Content Reference Set Types

| Reference Set Type                                             | Field Names                                     |
| -------------------------------------------------------------- | ----------------------------------------------- |
| 446609009 \| Simple type reference set\|                       | referencedComponentId                           |
| 733619002 \| Ordered component type reference set\|            | referencedComponentId, order                    |
| 900000000000480006 \| Attribute value type reference set\|     | referencedComponentId, valueId                  |
| 900000000000521006 \| Association type reference set\|         | referencedComponentId, targetComponentId        |
| 733618005 \| Ordered association type reference set\|          | referencedComponentId, targetComponentId, order |
| 900000000000516008 \| Annotation type reference set\|          | referencedComponentId, annotation               |
| 900000000000512005 \| Query specification type reference set\| | referencedComponentId, query                    |
| 447258008 \| Ordered type reference set\|                      | referencedComponentId, order, linkedToId        |
| 762676003 \| OWL expression type reference set\|               | referencedComponentId, owlExpression            |
| 1119417006 \| Postcoordinated expression type reference set\|  | referencedComponentId, expression, substrate    |

### Language Reference Set Types

| Reference Set Type                                  | Field Names                            |
| --------------------------------------------------- | -------------------------------------- |
| 900000000000506000 \| Language type reference set\| | referencedComponentId, acceptabilityId |

### Map Reference Set Types

| Reference Set Type                                                                         | Field Names                                                                                               |
| ------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------- |
| 900000000000496009 \| Simple map from SNOMED CT type reference set\|                       | referencedComponentId, mapTarget                                                                          |
| 1187636009 \| Simple map to SNOMED CT type reference set\|                                 | referencedComponentId, mapSource                                                                          |
| 447250001 \| Complex map from SNOMED CT type reference set\|                               | referencedComponentId, mapGroup, mapPriority, mapRule, mapAdvice, mapTarget, correlationId                |
| 609331003 \| Extended map from SNOMED CT type reference set\|                              | referencedComponentId, mapGroup, mapPriority, mapRule, mapAdvice, mapTarget, correlationId, mapCategoryId |
| 705111002 \| Map to SNOMED CT with correlation and origin type reference set\|             | referencedComponentId, mapSource, attributeId, correlationId, contentOriginId                             |
| 705109006 \| Code to expression type reference set type reference set\|                    | referencedComponentId, mapSource, expression, definitionStatusId, correlationId, contentOriginId          |
| 1193542003 \| Simple map with correlation from SNOMED CT type reference set\|              | referencedComponentId, mapTarget, correlationId                                                           |
| 1193543008 \| Simple map with correlation to SNOMED CT type reference set\|                | referencedComponentId, mapSource, correlationId                                                           |
| 1193544002 \| Simple map with correlation from SNOMED CT to SNOMED CT type reference set\| | referencedComponentId, mapTarget, correlationId                                                           |

***

### Metadata Reference Set Types

| Reference Set Type                                                  | Field Names                                                                                                                                                                                    |
| ------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| 900000000000456007 \| Reference set descriptor type reference set\| | referencedComponentId, attributeDescription, attributeType, attributeOrder                                                                                                                     |
| 900000000000534007 \| Module dependency type reference set\|        | referencedComponentId, sourceEffectiveTime, targetEffectiveTime                                                                                                                                |
| 900000000000538005 \| Description format type reference set\|       | referencedComponentId, descriptionFormat, descriptionLength                                                                                                                                    |
| 723589008 \| MRCM domain type reference set\|                       | referencedComponentId, domainConstraint, parentDomain, proximalPrimitiveConstraint, proximalPrimitiveRefinement, domainTemplateForPrecoordination, domainTemplateForPostcoordination, guideURL |
| 723604009 \| MRCM attribute domain type reference set\|             | referencedComponentId, domainId, grouped, attributeCardinality, attributeInGroupCardinality, ruleStrengthId, contentTypeId                                                                     |
| 723592007 \| MRCM attribute range type reference set\|              | referencedComponentId, rangeConstraint, attributeRule, ruleStrengthId, contentTypeId                                                                                                           |
| 723563008 \| MRCM module scope type reference set\|                 | referencedComponentId, mrcmRuleRefsetId                                                                                                                                                        |

***

{% file src=".gitbook/assets/Field Names of International Reference Set Types - ECL 2.0.tsv" %}






<a href="https://docs.google.com/forms/d/e/1FAIpQLScTmbZIf0UEQwYDkY27EEWBkaiYkHSbR0_9DmFrMLXoQLyL7Q/viewform?usp=pp_url&entry.1767247133=ECL+Specification&entry.670899847=Appendix%20E%20-%20Reference%20Set%20Fields" class="button primary">Provide Feedback</a>
