# A.3 Cardinality - Valid Expressions

| **Expression Constraint** | **Valid Expression**[1](https://confluence.ihtsdotools.org/display/DOCECL/A.3+Cardinality+-+Valid+Expressions#Footnote1) |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| **Precoordinated**        | **Postcoordinated**                                                                                                      |

< [373873005 |Pharmaceutical / biologic product|](http://snomed.info/id/373873005) : \[1..3] [127489000 |Has active ingredient|](http://snomed.info/id/127489000) = < [105590001 |Substance|](http://snomed.info/id/105590001) | [322236009 | Paracetamol 500mg tablet|](http://snomed.info/id/322236009) | [373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005) :\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009) }\
[404826002 | Benzocaine + butamben + tetracaine hydrochloride|](http://snomed.info/id/404826002) | [373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005) :\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009) },\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[387494007 | Codeine|](http://snomed.info/id/387494007) }

< [373873005 |Pharmaceutical / biologic product|](http://snomed.info/id/373873005) : \[1..1] [127489000 |Has active ingredient|](http://snomed.info/id/127489000) = < [105590001 |Substance|](http://snomed.info/id/105590001) | [370166004 | Aspirin 325mg tablet|](http://snomed.info/id/370166004) | [373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005) :\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009) }

< [373873005 |Pharmaceutical / biologic product|](http://snomed.info/id/373873005) : \[0..1] [127489000 |Has active ingredient|](http://snomed.info/id/127489000) = < [105590001 |Substance|](http://snomed.info/id/105590001) | [279999999108 | Inert tablet|](http://snomed.org/fictid#279999999108) | [373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005) :\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009) }\
[370166004 | Aspirin 325mg tablet|](http://snomed.info/id/370166004)

< [373873005 |Pharmaceutical / biologic product|](http://snomed.info/id/373873005) : \[1.._]_ [_127489000 |Has active ingredient|_](http://snomed.info/id/127489000) _= <_ [_105590001 |Substance|_](http://snomed.info/id/105590001) _|_ [_7947003 | Aspirin|_](http://snomed.info/id/7947003) _|_ [_373873005 | Pharmaceutical / biologic product|_](http://snomed.info/id/373873005) _:_\
&#xNAN;_{_ [_127489000 | Has active ingredient|_](http://snomed.info/id/127489000) _=_\
[_412031009 | Paracetamol or derivative|_](http://snomed.info/id/412031009) _},_\
&#xNAN;_{_ [_127489000 | Has active ingredient|_](http://snomed.info/id/127489000) _=_\
[_255641001 | Caffeine|_](http://snomed.info/id/255641001) _},_\
&#xNAN;_{_ [_127489000 | Has active ingredient|_](http://snomed.info/id/127489000) _=_\
[_387458008 | Aspirin|_](http://snomed.info/id/387458008) _}_\
[_437867004 | Chlorphenamine + dextromethorphan + paracetamol + pseudoephedrine|_](http://snomed.info/id/437867004)\
&#xNAN;_<_ [_404684003 | Clinical finding|_](http://snomed.info/id/404684003) _:_\
&#xNAN;_\[1..1]_ [_363698007 | Finding site|_](http://snomed.info/id/363698007) _=_\
&#xNAN;_<_ [_91723000 | Anatomical structure|_](http://snomed.info/id/91723000) _|_ [_125596004 | Injury of elbow|_](http://snomed.info/id/125596004) _|_ [_404684003 | Clinical finding|_](http://snomed.info/id/404684003) _:_\
&#xNAN;_{_ [_116676008 | Associated morphology|_](http://snomed.info/id/116676008) _=_\
[_72704001 | Fracture|_](http://snomed.info/id/72704001) _,_\
[_363698007 | Finding site|_](http://snomed.info/id/363698007) _=_\
[_299701004 | Bone of forearm|_](http://snomed.info/id/299701004) _,_\
[_363698007 | Finding site|_](http://snomed.info/id/363698007) _=_\
[_62413002 | Bone structure of radius|_](http://snomed.info/id/62413002) _}_ [_2_](https://confluence.ihtsdotools.org/display/DOCECL/A.3+Cardinality+-+Valid+Expressions#Footnote2)\
&#xNAN;_<_ [_404684003 | Clinical finding|_](http://snomed.info/id/404684003) _:_\
&#xNAN;_\[2.._] [363698007 | Finding site|](http://snomed.info/id/363698007) =\
< [91723000 | Anatomical structure|](http://snomed.info/id/91723000) | [86299006 | Tetralogy of Fallot|](http://snomed.info/id/86299006) | [404684003 | Clinical finding|](http://snomed.info/id/404684003) :\
{ [116676008 | Associated morphology|](http://snomed.info/id/116676008) =\
[72704001 | Fracture|](http://snomed.info/id/72704001) ,\
[363698007 | Finding site|](http://snomed.info/id/363698007) =\
[299701004 | Bone of forearm|](http://snomed.info/id/299701004) },\
{ [116676008 | Associated morphology|](http://snomed.info/id/116676008) =\
[72704001 | Fracture|](http://snomed.info/id/72704001) ,\
[363698007 | Finding site|](http://snomed.info/id/363698007) =\
[702468001 | Bone structure of lower leg|](http://snomed.info/id/702468001) }\
< [404684003 | Clinical finding|](http://snomed.info/id/404684003) :\
{ \[2..\*] [363698007 | finding site|](http://snomed.info/id/363698007) =\
< [91723000 | Anatomical structure|](http://snomed.info/id/91723000) } | -| [64572001 | Disease|](http://snomed.info/id/64572001) :\
{ [116676008 | Associated morphology|](http://snomed.info/id/116676008) =\
[396351009 | Congenital septal defect|](http://snomed.info/id/396351009) ,\
[363698007 | Finding site|](http://snomed.info/id/363698007) =\
[25943004 | Structure of atrioventricular node|](http://snomed.info/id/25943004) ,\
[363698007 | Finding site|](http://snomed.info/id/363698007) =\
[113262008 | Thoracic aorta structure|](http://snomed.info/id/113262008) }\
{ [116676008 | Associated morphology|](http://snomed.info/id/116676008) =\
[90141005 | Congenital hypertrophy|](http://snomed.info/id/90141005) ,\
[363698007 | Finding site|](http://snomed.info/id/363698007) =\
[244384009 | Entire right ventricle|](http://snomed.info/id/244384009) }

< [373873005 |Pharmaceutical / biologic product|](http://snomed.info/id/373873005) : \[1..3] { \[1..\*] [127489000 |Has active ingredient|](http://snomed.info/id/127489000) = < [105590001 |Substance|](http://snomed.info/id/105590001) } | [322236009 | Paracetamol 500mg tablet|](http://snomed.info/id/322236009) | [373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005) :\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009) }\
[404826002 | Benzocaine + butamben + tetracaine hydrochloride|](http://snomed.info/id/404826002) | [373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005) :\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009) },\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[387494007 | Codeine|](http://snomed.info/id/387494007) }

< [373873005 |Pharmaceutical / biologic product|](http://snomed.info/id/373873005) : \[0..1] { [127489000 |Has active ingredient|](http://snomed.info/id/127489000) = < [105590001 |Substance|](http://snomed.info/id/105590001) } | [111115279999999108 | Inert tablet|](http://snomed.org/fictid#111115279999999108) | [373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005) :\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009) }\
[370166004 | Aspirin 325mg tablet|](http://snomed.info/id/370166004)

< [373873005 |Pharmaceutical / biologic product|](http://snomed.info/id/373873005) : \[1..\*] { [127489000 |Has active ingredient|](http://snomed.info/id/127489000) = < [105590001 |Substance|](http://snomed.info/id/105590001) } | [370166004 | Aspirin 325mg tablet|](http://snomed.info/id/370166004) | [373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005) :\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009) },\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[387494007 | Codeine|](http://snomed.info/id/387494007) }\
< [404684003 | Clinical finding|](http://snomed.info/id/404684003) :\
\[1..1] { [363698007 | Finding site|](http://snomed.info/id/363698007) =\
< [91723000 | Anatomical structure|](http://snomed.info/id/91723000) } | [125596004 | Injury of elbow|](http://snomed.info/id/125596004) | [404684003 | Clinical finding|](http://snomed.info/id/404684003) :\
{ [363698007 | Finding site|](http://snomed.info/id/363698007) =\
[299701004 | Bone of forearm|](http://snomed.info/id/299701004) },\
{ [363698007 | Finding site|](http://snomed.info/id/363698007) =\
[62413002 | Bone structure of radius|](http://snomed.info/id/62413002) }

< [404684003 |Clinical finding|](http://snomed.info/id/404684003) :\
\[0..0] { \[2..\*] [363698007 |Finding site|](http://snomed.info/id/363698007) = < [91723000 |Anatomical structure|](http://snomed.info/id/91723000) } | [86299006 | Tetralogy of Fallot|](http://snomed.info/id/86299006) | [404684003 | Clinical finding|](http://snomed.info/id/404684003) :\
[363698007 | Finding site|](http://snomed.info/id/363698007) =\
[39057004 | Pulmonary valve structure|](http://snomed.info/id/39057004) ,\
[116676008 | Associated morphology|](http://snomed.info/id/116676008) =\
[415582006 | Stenosis|](http://snomed.info/id/415582006)

***

| Footnotes Ref                                                                                                | Notes                                                                                                                                                                 |
| ------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [1](https://confluence.ihtsdotools.org/display/DOCECL/A.3+Cardinality+-+Valid+Expressions#FootnoteMarker1-0) | The SNOMED CT identifiers created with the '9999999' namespace are for example only, and should not be used in a production environment.                              |
| [2](https://confluence.ihtsdotools.org/display/DOCECL/A.3+Cardinality+-+Valid+Expressions#FootnoteMarker2-0) | As mentioned earlier, only non-redundant defining attributes are included in the cardinality count. Because \<a href="http://snomed.info/id/62413002" title="62413002 |
