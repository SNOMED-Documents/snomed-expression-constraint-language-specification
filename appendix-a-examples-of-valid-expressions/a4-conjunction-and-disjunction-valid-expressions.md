# A.4 Conjunction and Disjunction - Valid Expressions

| **Expression Constraint** | **Valid Expression**[1](https://confluence.ihtsdotools.org/display/DOCECL/A.4+Conjunction+and+Disjunction+-+Valid+Expressions#Footnote1) |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| **Precoordinated**        | **Postcoordinated**                                                                                                                      |
| < \[ 19829001             | Disorder of lung                                                                                                                         |
| < \[ 301867009            | Edema of trunk                                                                                                                           |
| \[ 116676008              | Associated morphology                                                                                                                    |
| \[ 40829002               | Acute edema                                                                                                                              |
| \[ 363698007              | Finding site                                                                                                                             |
| \[ 278985004              | Fissure of right lung                                                                                                                    |
| \[ 61233003               | Silo-fillers' disease                                                                                                                    |
| < \[ 19829001             | Disorder of lung                                                                                                                         |
| < \[ 301867009            | Edema of trunk                                                                                                                           |
| \[ 116676008              | Associated morphology                                                                                                                    |
| \[ 40829002               | Acute edema                                                                                                                              |
| \[ 19242006               | Pulmonary edema                                                                                                                          |
| < \[ 19829001             | Disorder of lung                                                                                                                         |
| ^ \[ 700043003            | Example problem list concepts reference set                                                                                              |

< [404684003 | Clinical finding|](http://snomed.info/id/404684003) :\
[363698007 | Finding site|](http://snomed.info/id/363698007) =\
<< [39057004 | Pulmonary valve structure|](http://snomed.info/id/39057004) AND\
[116676008 | Associated morphology|](http://snomed.info/id/116676008) =\
<< [415582006 | Stenosis|](http://snomed.info/id/415582006) | [91442002 | Rheumatic pulmonary valve stenosis|](http://snomed.info/id/91442002) | [56786000 | Pulmonic valve stenosis|](http://snomed.info/id/56786000) :\
[363698007 | Finding site|](http://snomed.info/id/363698007) =\
[90318009 | Structure of anulus fibrosus of pulmonary artery|](http://snomed.info/id/90318009) ,\
[116676008 | Associated morphology|](http://snomed.info/id/116676008) =\
[88015002 | Partial stenosis|](http://snomed.info/id/88015002)\
[86299006 | Tetralogy of Fallot|](http://snomed.info/id/86299006)\
< [404684003 | Clinical finding|](http://snomed.info/id/404684003) :\
[116676008 | Associated morphology|](http://snomed.info/id/116676008) =\
<< [55641003 | Infarct|](http://snomed.info/id/55641003) OR\
[42752001 | Due to|](http://snomed.info/id/42752001) =\
<< [22298006 | Myocardial infarction|](http://snomed.info/id/22298006) | [45456005 | Renal infarct|](http://snomed.info/id/45456005) | [95281009 | Sudden cardiac death|](http://snomed.info/id/95281009) :\
[42752001 | Due to|](http://snomed.info/id/42752001) =\
[22298006 | Myocardial infarction|](http://snomed.info/id/22298006)\
[703326006 | Mitral regurgitation due to acute myocardial infarction|](http://snomed.info/id/703326006)

< [404684003 |Clinical finding|](http://snomed.info/id/404684003) :\
{ [363698007 |Finding site|](http://snomed.info/id/363698007) = << [39057004 |Pulmonary valve structure|](http://snomed.info/id/39057004) ,\
[116676008 |Associated morphology|](http://snomed.info/id/116676008) = << [415582006 |Stenosis|](http://snomed.info/id/415582006) } OR\
{ [363698007 |Finding site|](http://snomed.info/id/363698007) = << [53085002 |Right ventricular structure|](http://snomed.info/id/53085002) ,\
[116676008 |Associated morphology|](http://snomed.info/id/116676008) = << [56246009 |Hypertrophy|](http://snomed.info/id/56246009) } | [85971001 | Rheumatic pulmonary valve stenosis with insufficiency|](http://snomed.info/id/85971001) | [56786000 | Pulmonic valve stenosis|](http://snomed.info/id/56786000) :\
[363698007 | Finding site|](http://snomed.info/id/363698007) =\
[90318009 | Structure of anulus fibrosus of pulmonary artery|](http://snomed.info/id/90318009) ,\
[116676008 | Associated morphology|](http://snomed.info/id/116676008) =\
[88015002 | Partial stenosis|](http://snomed.info/id/88015002)\
[86299006 | Tetralogy of Fallot|](http://snomed.info/id/86299006)\
^ [450990004 | Adverse drug reactions reference set for GP/FP health issue|](http://snomed.info/id/450990004) :\
[246075003 | Causative agent|](http://snomed.info/id/246075003) =\
(< [373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005)\
OR < [105590001 | Substance|](http://snomed.info/id/105590001) ) | [294811002 | Corticotrophic hormone allergy|](http://snomed.info/id/294811002) | -\
[293584003 | Paracetamol allergy|](http://snomed.info/id/293584003)\
[293585002 | Salicylate allergy|](http://snomed.info/id/293585002)\
< [404684003 | Clinical finding|](http://snomed.info/id/404684003) :\
[116676008 | Associated morphology|](http://snomed.info/id/116676008) =\
(<< [56208002 | Ulcer|](http://snomed.info/id/56208002)\
AND << [50960005 | Hemorrhage|](http://snomed.info/id/50960005) ) | [12847006 | Acute duodenal ulcer with hemorrhage|](http://snomed.info/id/12847006) | [64572001 |Disease|](http://snomed.info/id/64572001) :\
{ [116676008 |Associated morphology|](http://snomed.info/id/116676008) = [55075001 |Bleeding ulcer|](http://snomed.info/id/55075001) ,\
[363698007 |Finding site|](http://snomed.info/id/363698007) = [14374004 |Structure of lymphatic vessel of oesophagus|](http://snomed.info/id/14374004) }

***

| Footnotes Ref                                                                                                                | Notes                                                                                                     |
| ---------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- |
| [1](https://confluence.ihtsdotools.org/display/DOCECL/A.4+Conjunction+and+Disjunction+-+Valid+Expressions#FootnoteMarker1-0) | Where necessary, these examples make some assumptions about the membership of the example reference sets. |
