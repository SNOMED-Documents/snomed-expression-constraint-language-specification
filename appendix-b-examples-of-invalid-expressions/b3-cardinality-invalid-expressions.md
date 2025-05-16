# B.3 Cardinality - Invalid Expressions

| **Expression Constraint** | **INVALID Expression**[1](https://confluence.ihtsdotools.org/display/DOCECL/B.3+Cardinality+-+Invalid+Expressions#Footnote1) |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
| **Precoordinated**        | **Postcoordinated**                                                                                                          |
| < \[ 373873005            | Pharmaceutical / biologic product                                                                                            |
| \[1..3] \[ 127489000      | Has active ingredient                                                                                                        |

```
                          ingredient |") =   
```

< [105590001 | Substance|](http://snomed.info/id/105590001) | [279999999108 | Inert tablet|](http://snomed.org/fictid#279999999108) | [373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005) :\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009) },\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[387494007 | Codeine|](http://snomed.info/id/387494007) },\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[255641001 | Caffeine|](http://snomed.info/id/255641001) },\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[44068004 | Doxylamine|](http://snomed.info/id/44068004) }\
[437867004 | Chlorphenamine + dextromethorphan + paracetamol + pseudoephedrine|](http://snomed.info/id/437867004)\
< [373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005) :\
\[1..1] [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
< [105590001 | Substance|](http://snomed.info/id/105590001) | [279999999108 | Inert tablet|](http://snomed.org/fictid#279999999108) | [373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005) :\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009) },\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[387494007 | Codeine|](http://snomed.info/id/387494007) }\
[412556009 | Paracetamol + codeine|](http://snomed.info/id/412556009)\
< [373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005) :\
\[0..1] [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
< [105590001 | Substance|](http://snomed.info/id/105590001) | [412556009 | Paracetamol + codeine|](http://snomed.info/id/412556009) | [373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005) :\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009) },\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[387494007 | Codeine|](http://snomed.info/id/387494007) }\
< [373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005) :\
\[1.._]_ [_127489000 | Has active ingredient|_](http://snomed.info/id/127489000) _=_\
&#xNAN;_<_ [_105590001 | Substance|_](http://snomed.info/id/105590001) _|_ [_279999999108 | Inert tablet|_](http://snomed.org/fictid#279999999108) _|_ [_373873005 | Pharmaceutical / biologic product|_](http://snomed.info/id/373873005) _:_\
[_411116001 | Has dose form|_](http://snomed.info/id/411116001) _=_\
[_385055001 | Tablet|_](http://snomed.info/id/385055001)\
&#xNAN;_<_ [_404684003 | Clinical finding|_](http://snomed.info/id/404684003) _:_\
&#xNAN;_\[1..1]_ [_363698007 | Finding site|_](http://snomed.info/id/363698007) _=_\
&#xNAN;_<_ [_91723000 | Anatomical structure|_](http://snomed.info/id/91723000) _|_ [_75857000 | Fracture of radius and ulna|_](http://snomed.info/id/75857000) _|_ [_404684003 | Clinical finding|_](http://snomed.info/id/404684003) _:_\
&#xNAN;_{_ [_116676008 | Associated morphology|_](http://snomed.info/id/116676008) _=_\
[_72704001 | Fracture|_](http://snomed.info/id/72704001) _,_\
[_363698007 | Finding site|_](http://snomed.info/id/363698007) _=_\
[_62413002 | Bone structure of radius|_](http://snomed.info/id/62413002) _,_\
[_363698007 | Finding site|_](http://snomed.info/id/363698007) _=_\
[_23416004 | Bone structure of ulna|_](http://snomed.info/id/23416004) _}_\
[_40733004 | Infectious disease|_](http://snomed.info/id/40733004)\
&#xNAN;_<_ [_404684003 | Clinical finding|_](http://snomed.info/id/404684003) _:_\
&#xNAN;_\[2.._] [363698007 | Finding site|](http://snomed.info/id/363698007) =\
< [91723000 | Anatomical structure|](http://snomed.info/id/91723000) | [23406007 | Arm fracture|](http://snomed.info/id/23406007) | [404684003 | Clinical finding|](http://snomed.info/id/404684003) :\
{ [116676008 | Associated morphology|](http://snomed.info/id/116676008) =\
[72704001 | Fracture|](http://snomed.info/id/72704001) ,\
[363698007 | Finding site|](http://snomed.info/id/363698007) =\
[702468001 | Bone structure of lower leg|](http://snomed.info/id/702468001) }\
[40733004 | Infectious disease|](http://snomed.info/id/40733004)\
< [404684003 | Clinical finding|](http://snomed.info/id/404684003) :\
{ \[2.._]_ [_363698007 | Finding site|_](http://snomed.info/id/363698007) _=_\
&#xNAN;_<_ [_91723000 | Anatomical structure|_](http://snomed.info/id/91723000) _} |_ [_75857000 | Fracture of radius and ulna|_](http://snomed.info/id/75857000) _|_ [_64572001 | Disease|_](http://snomed.info/id/64572001) _:_\
&#xNAN;_{_ [_116676008 | Associated morphology|_](http://snomed.info/id/116676008) _=_\
[_396351009 | Congenital septal defect|_](http://snomed.info/id/396351009) _,_\
[_363698007 | Finding site|_](http://snomed.info/id/363698007) _=_\
[_113262008 | Thoracic aorta structure|_](http://snomed.info/id/113262008) _}_\
&#xNAN;_{_ [_116676008 | Associated morphology|_](http://snomed.info/id/116676008) _=_\
[_90141005 | Congenital hypertrophy|_](http://snomed.info/id/90141005) _,_\
[_363698007 | Finding site|_](http://snomed.info/id/363698007) _=_\
[_244384009 | Entire right ventricle|_](http://snomed.info/id/244384009) _}_\
&#xNAN;_<_ [_373873005 | Pharmaceutical / biologic product|_](http://snomed.info/id/373873005) _:_\
&#xNAN;_\[1..3] { \[1.._] [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
< [105590001 | Substance|](http://snomed.info/id/105590001) } | [279999999108 | Inert tablet|](http://snomed.org/fictid#279999999108) | [373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005) :\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009) },\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[387494007 | Codeine|](http://snomed.info/id/387494007) },\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[255641001 | Caffeine|](http://snomed.info/id/255641001) },\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[44068004 | Doxylamine|](http://snomed.info/id/44068004) }\
[437867004 | Chlorphenamine + dextromethorphan + paracetamol + pseudoephedrine|](http://snomed.info/id/437867004)\
< [373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005) :\
\[0..1] { [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
< [105590001 | Substance|](http://snomed.info/id/105590001) } | [412556009 | Paracetamol + codeine|](http://snomed.info/id/412556009) | [373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005) :\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009) },\
{ [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
[387494007 | Codeine|](http://snomed.info/id/387494007) }\
< [373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005) :\
\[1.._] {_ [_127489000 | Has active ingredient|_](http://snomed.info/id/127489000) _=_\
&#xNAN;_<_ [_105590001 | Substance|_](http://snomed.info/id/105590001) _} |_ [_279999999108 | Inert tablet|_](http://snomed.org/fictid#279999999108) _|_ [_373873005 | Pharmaceutical / biologic product|_](http://snomed.info/id/373873005) _:_\
[_411116001 | Has dose form|_](http://snomed.info/id/411116001) _=_\
[_385055001 | Tablet|_](http://snomed.info/id/385055001)\
&#xNAN;_<_ [_404684003 | Clinical finding|_](http://snomed.info/id/404684003) _:_\
&#xNAN;_\[1..1] {_ [_363698007 | Finding site|_](http://snomed.info/id/363698007) _=_\
&#xNAN;_<_ [_91723000 | Anatomical structure|_](http://snomed.info/id/91723000) _} |_ [_75857000 | Fracture of radius and ulna|_](http://snomed.info/id/75857000) _|_ [_404684003 | Clinical finding|_](http://snomed.info/id/404684003) _:_\
&#xNAN;_{_ [_116676008 | Associated morphology|_](http://snomed.info/id/116676008) _=_\
[_72704001 | Fracture|_](http://snomed.info/id/72704001) _,_\
[_363698007 | Finding site|_](http://snomed.info/id/363698007) _=_\
[_62413002 | Bone structure of radius|_](http://snomed.info/id/62413002) _},_\
&#xNAN;_{_ [_116676008 | Associated morphology|_](http://snomed.info/id/116676008) _=_\
[_72704001 | Fracture|_](http://snomed.info/id/72704001) _,_\
[_363698007 | Finding site|_](http://snomed.info/id/363698007) _=_\
[_23416004 | Bone structure of ulna|_](http://snomed.info/id/23416004) _}_\
[_40733004 | Infectious disease|_](http://snomed.info/id/40733004)\
&#xNAN;_<_ [_404684003 | Clinical finding|_](http://snomed.info/id/404684003) _:_\
&#xNAN;_\[0..0] { \[2.._] [363698007 | Finding site|](http://snomed.info/id/363698007) =\
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
[244384009 | entire right ventricle|](http://snomed.info/id/244384009) }

| Footnotes Ref                                                                                                  | Notes                                                                                                                                    |
| -------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| [1](https://confluence.ihtsdotools.org/display/DOCECL/B.3+Cardinality+-+Invalid+Expressions#FootnoteMarker1-0) | The SNOMED CT identifiers created with the '9999999' namespace are for example only, and should not be used in a production environment. |
