# appendix-d-ecl-quick-reference

## Appendix D - ECL Quick Reference

This section provides a quick reference to the key syntax features of the Expression Constraint Language.

## Syntax Overview

The following table summarises the key symbols used in the Expression Constraint Language's brief syntax, with the ECL version in which each symbol was introduced. For more information about the version history of ECL, please refer to the 'History' section in [1. Introduction](../1.-Introduction_28739382.html).

| **Symbol**      | **Name**                         | Version | Notes                                                                                                                                                               |
| --------------- | -------------------------------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| \*\*            | \*\*                             | Pipe    | 1.0                                                                                                                                                                 |
| \*\*\*\*\*      | Any                              | 1.0     | Retrieves all concepts in the substrate                                                                                                                             |
| **^**           | Member of                        | 1.0     | Retrieves the referencedComponentId of all (active) members of a reference set (or set of reference sets)                                                           |
| **^ \[ A, B]**  | Member of (with field selection) | 2.0     | Retrieves the values of fields A and B of all (active) members of a reference set (or set of reference sets) that match the included Member filters (if applicable) |
| **<**           | Descendant of                    | 1.0     | Retrieves all descendants (subtypes) of the specified concept _excluding_ the concept itself                                                                        |
| **< <**         | Descendant or self of            | 1.0     | Retrieves all descendants (subtypes) of the specified concept _including_ the concept itself                                                                        |
| **\<!**         | Child of                         | 1.1     | Retrieves all children (immediate subtypes) of the specified concept _excluding_ the concept itself                                                                 |
| **< \<!**       | Child or self of                 | 1.4     | Retrieves all children (immediate subtypes) of the specified concept _including_ the concept itself                                                                 |
| **>**           | Ancestor of                      | 1.0     | Retrieves all ancestors (supertypes) of the specified concept _excluding_ the concept itself                                                                        |
| **> >**         | Ancestor or self of              | 1.0     | Retrieves all ancestors (supertypes) of the specified concept _including_ the concept itself                                                                        |
| **>!**          | Parent of                        | 1.1     | Retrieves all parents (immediate supertypes) of the specified concept _excluding_ the concept itself                                                                |
| **> >!**        | Parent or self of                | 1.4     | Retrieves all parents (immediate supertypes) of the specified concept _including_ the concept itself                                                                |
| \*\*!! >        |                                  |         |                                                                                                                                                                     |
| \*\*            | Top of set                       | 2.2     | Filters the results set, by matching only on concepts that have no ancestors within the set                                                                         |
| \*\*!! <        |                                  |         |                                                                                                                                                                     |
| \*\*            | Bottom of set                    | 2.2     | Filters the results set, by matching only on concepts that have no descendants within the set                                                                       |
| **A#B**         | Alternate identifier             | 2.2     | Retrieves a single concept based on an alternate identifier, where A is the identifier scheme alias and B is the identifier code                                    |
| **AND**         | Conjunction                      | 1.0     | Retrieves the intersection of the results of each sub-expressions                                                                                                   |
| **OR**          | Disjunction                      | 1.0     | Retrieves the union of the results of each sub-expressions                                                                                                          |
| **MINUS**       | Exclusion                        | 1.0     | Retrieves the members of the first expression and excludes the members returned by the second expression                                                            |
| **:**           | Refinement                       | 1.0     | Used before one or more attribute-value pairs to refine the set of concepts retrieved                                                                               |
| **\[1..3]**     | Cardinality                      | 1.0     | Used to indicate the minimum and maximum number of occurrences of attributes or relationship groups                                                                 |
| **R**           | Reverse flag                     | 1.0     | Retrieves the set of attribute values (i.e. destination concepts) of a specified attribute for a specified set of concepts                                          |
| **.**           | Dot notation                     | 1.2     | Retrieves the set of attribute values (i.e. destination concepts) of a specified attribute for a specified set of concepts                                          |
| /\* \*/         | Comment                          | 1.1     | Allows comments to be added within the text of an expression constraint                                                                                             |
| \{{ \}}         | Description filter               | 1.5     | Filters the result set, by matching only on concepts which have a description with a matching term, language, type, dialect and/or acceptability                    |
| \{{ D \}}       | Description filter               | 1.6     | Filters the result set, by matching only on concepts which have a description with a matching term, language, type, dialect and/or acceptability                    |
| \{{ C \}}       | Concept filter                   | 1.6     | Filters the result set based on the definition status, module, effectiveTime and active status of each concept                                                      |
| \{{ M \}}       | Member filter                    | 2.0     | Filters the result set based on the value of specific fields in a reference set.                                                                                    |
| \{{+ HISTORY\}} | History supplement               | 2.0     | Supplements the results with relevant inactive concepts                                                                                                             |

## Examples

The following table provides some examples of each of the key syntax features of the Expression Constraint Language.

**Notes** :

1. In the table above:
   * '**id** ' represents a single SNOMED CT concept identifier,
   * '**term** ' represents a term associated with the concept identified by '**id** ',
   * '**x** ', '**y** ' and '**v** ' each represent either a single concept or a set of concepts defined using an expression constraint,
   * '**z** ' represents either a single concept or a set of concepts that are a subtype of [900000000000455006 | Reference set|](http://snomed.info/id/900000000000455006) ,
   * '**a** ' and '**b** ' each represent either a single concept or a set of concepts that are a subtype of [410662002 | Concept model attribute|](http://snomed.info/id/410662002) , and
   * '**min** ' and '**max** ' are two numeric values that represent the minimum and maximum cardinality allowed.
2. The default substrate, to which expression constraints are applied, includes all concepts, active relationships, active descriptions and active reference set members of a chosen SNOMED CT versioned edition.

**Simple expression constraints**\
Syntax| Evaluation Notes| Example| Example Expansion Concepts\
**id** | term |\
\| Only the concept with the identifier 'id'| [128477000 |Abscess|](http://snomed.info/id/128477000) | [128477000 |Abscess|](http://snomed.info/id/128477000)\
\*\*\*\*\*| All concepts in the given substrate| \* | _Any concept in the given substrate_\
&#xNAN;**^** z| The set of concepts which are members of the reference sets in z| ^ [723264001 |Lateralizable body structure reference set|](http://snomed.info/id/723264001) | [181216001 |Entire lung|](http://snomed.info/id/181216001)

[65784005 |Structure of fundus of eye|](http://snomed.info/id/65784005)\
\*\*< \*\*x| The set of all descendants (both direct and indirect) of x| < [73211009 |Diabetes mellitus|](http://snomed.info/id/73211009) < 73211009 |Diabetes mellitus)|| [46635009 |Diabetes mellitus type 1|](http://snomed.info/id/46635009)

[8801005 |Secondary diabetes mellitus|](http://snomed.info/id/8801005)\
\*\*< < \*\*x| The set of all descendants (both direct and indirect) of x, plus x itself| << [73211009 |Diabetes mellitus|](http://snomed.info/id/73211009) | [73211009 |Diabetes mellitus|](http://snomed.info/id/73211009)

[46635009 |Diabetes mellitus type 1|](http://snomed.info/id/46635009)

[8801005 |Secondary diabetes mellitus|](http://snomed.info/id/8801005)\
\*\*\<! \*\*x\
\| The set of all immediate children of x| \<! [362965005 |Disorder of body system|](http://snomed.info/id/362965005) | [49601007 |Disorder of cardiovascular system|](http://snomed.info/id/49601007)

[362969004 |Disorder of endocrine system|](http://snomed.info/id/362969004)\
\*\*< \<! \*\*x\
\| The set of all immediate children of x, plus x itself| <\<! [362965005 |Disorder of body system|](http://snomed.info/id/362965005) | [362965005 |Disorder of body system|](http://snomed.info/id/362965005)

[49601007 |Disorder of cardiovascular system|](http://snomed.info/id/49601007)

[362969004 |Disorder of endocrine system|](http://snomed.info/id/362969004)\
\*\*> \*\*x\
\| The set of all ancestors (both direct and indirect) of x| > [279420009 |Hematoma of skin|](http://snomed.info/id/279420009) | [106076001 |Skin finding|](http://snomed.info/id/106076001)

[297968009 |Bleeding skin|](http://snomed.info/id/297968009)\
&#xNAN;**> >** x| The set of all ancestors (both direct and indirect) of x, plus x itself| >> [279420009 |Hematoma of skin|](http://snomed.info/id/279420009) | [106076001 |Skin finding|](http://snomed.info/id/106076001)

[297968009 |Bleeding skin|](http://snomed.info/id/297968009)

[279420009 |Hematoma of skin|](http://snomed.info/id/279420009)\
\*\*>! \*\*x| The set of all immediate parents of x| >! [22298006 |Myocardial infarction|](http://snomed.info/id/22298006) | [57809008 |Myocardial disease|](http://snomed.info/id/57809008)

[251061000 |Myocardial necrosis|](http://snomed.info/id/251061000)\
\*\*> >! \*\*x| The set of all immediate parents of x, plus x itself| >>! [22298006 |Myocardial infarction|](http://snomed.info/id/22298006) | [22298006 |Myocardial infarction|](http://snomed.info/id/22298006)

[57809008 |Myocardial disease|](http://snomed.info/id/57809008)

[251061000 |Myocardial necrosis|](http://snomed.info/id/251061000)\
**Conjunction, Disjunction and Exclusion**\
Syntax| Evaluation Notes| Example| Example Expansion Concepts\
x**AND** y\
\| The set of concepts that are both in x and in y (i.e. the intersection of x and y)| < [19829001 |Disorder of lung|](http://snomed.info/id/19829001) AND < [87628006 |Bacterial infectious disease|](http://snomed.info/id/87628006) | [430395005 |Pneumonia caused by Gram negative bacteria|](http://snomed.info/id/430395005)

[154283005 |Pulmonary tuberculosis|](http://snomed.info/id/154283005)\
x**OR** y| The set of concepts that are either in x or in y (i.e. the union of x and y)| < [73452002 |Abscess of lung|](http://snomed.info/id/73452002) OR < [275504005 |Cyst of lung|](http://snomed.info/id/275504005) | [446543007 |Tuberculous abscess of lung|](http://snomed.info/id/446543007)

[87119009 |Congenital cystic lung|](http://snomed.info/id/87119009)\
x**MINUS** y| The set of concepts that are in x but are not in y (i.e. x excluding concepts in y)| < [29303009 |Electrocardiographic procedure|](http://snomed.info/id/29303009) MINUS < [75444003 |Fetal electrocardiogram|](http://snomed.info/id/75444003) | [447114004 |12 lead electrocardiogram during exercise|](http://snomed.info/id/447114004)

[252417001 |24 Hour electrocardiogram|](http://snomed.info/id/252417001)\
**Refinement**\
Syntax| Evaluation Notes| Example| Example Expansion Concepts\
x **:** a **=** y| The set of concepts in **x** , which have a necessary relationship with an attribute in **a** and a value in **y**| < [385494008 |Hematoma|](http://snomed.info/id/385494008) :\
<< [370135005 |Pathological process|](http://snomed.info/id/370135005) = << [441862004 |Infectious process|](http://snomed.info/id/441862004) | [698573001 |Infected hematoma|](http://snomed.info/id/698573001)

[444109008 |Infection of wound hematoma|](http://snomed.info/id/444109008)\
x **:** a **=** y\*\*,\*\* b **=** v| The set of concepts in **x** , which have both a necessary relationship with an attribute in **a** and a value in **y** , and also have a necessary relationship (either the same one or a different one) with an attribute in **b** and a value in **v**| < [71388002 |Procedure|](http://snomed.info/id/71388002) :\
<< [363704007 |Procedure site|](http://snomed.info/id/363704007) = << [69695003 |Stomach structure|](http://snomed.info/id/69695003) ,\
<< [405815000 |Procedure device|](http://snomed.info/id/405815000) = << [86174004 |Laparoscope|](http://snomed.info/id/86174004) | [708987006 |Laparoscopic total gastrectomy|](http://snomed.info/id/708987006)

[57922004 |Laparoscopic pyloromyotomy|](http://snomed.info/id/57922004)\
x **: {** a **=** y\*\*,\*\* b **=** v **}**| The set of concepts in **x** , which have a role group that contains both a necessary relationship with an attribute in **a** and a value in **y** , and also have a necessary relationship (either the same one or a different one) with an attribute in **b** and a value in **v**| < [71388002 |Procedure (procedure)|](http://snomed.info/id/71388002) : { [405813007 |Procedure site - Direct|](http://snomed.info/id/405813007) = << [10200004 |Liver structure|](http://snomed.info/id/10200004) , [260686004 |Method|](http://snomed.info/id/260686004) = << [129433002 |Inspection - action|](http://snomed.info/id/129433002) } | [773252007 |Diagnostic laparoscopy of liver|](http://snomed.info/id/773252007)

[20933000 |Endoscopy of liver|](http://snomed.info/id/20933000)\
**Cardinality**\
Syntax| Evaluation Notes| Example| Example Expansion Concepts\
x **: \[min .. max]** a **=** y| The set of concepts in **x** , which have between **min** and **max** necessary relationships with an attribute in **a** and a value in **y**| < [373873005 |Pharmaceutical / biologic product|](http://snomed.info/id/373873005) :\
\[3..\*] [127489000 |Has active ingredient|](http://snomed.info/id/127489000) = < [105590001 |Substance|](http://snomed.info/id/105590001) | [786732006 |Product containing only brompheniramine and codeine and phenylpropanolamine|](http://snomed.info/id/786732006)

[787979009 |Product containing cyanocobalamin and folic acid and pyridoxine|](http://snomed.info/id/787979009)\
x **: \[min .. max] {** a **=** y **}**| The set of concepts in **x** , which have between **min** and **max** role groups that contain a necessary relationship with an attribute in **a** and a value in **y**| < [404684003 |Clinical finding|](http://snomed.info/id/404684003) :\
\[2..3]{ [363698007 |Finding site|](http://snomed.info/id/363698007) = \*,\
[116676008 |Associated morphology|](http://snomed.info/id/116676008) = [72704001 |Fracture|](http://snomed.info/id/72704001) }\
\| [271577005 |Fracture of shaft of tibia and fibula|](http://snomed.info/id/271577005)

[75857000 |Fracture of radius AND ulna|](http://snomed.info/id/75857000)\
**Reversed Attributes**\
Syntax| Evaluation Notes| Example| Example Expansion Concepts\
y **: R** a **=** x| The set of concepts in y, which are the destination (ie attribute value) of a necessary relationship on a source concept in **x** with an attribute in **a**| < [91723000 |Anatomical structure|](http://snomed.info/id/91723000) : R [363698007 |Finding site|](http://snomed.info/id/363698007) = < [445945000 |Infectious disease associated with acquired immune deficiency syndrome|](http://snomed.info/id/445945000) | [280369009 |Brain tissue structure|](http://snomed.info/id/280369009)

[39607008 |Lung structure|](http://snomed.info/id/39607008) 395939008 |Clavulanic acid (substance)|\
x **.** a| The set of attribute values (ie destination concepts) of all necessary relationships on a source concept in **x** with an attribute in **a**| < [27658006 |Product containing amoxicillin|](http://snomed.info/id/27658006) . [127489000 |Has active ingredient|](http://snomed.info/id/127489000) | [372687004 |Amoxicillin|](http://snomed.info/id/372687004)

[395939008 |Clavulanic acid|](http://snomed.info/id/395939008)
