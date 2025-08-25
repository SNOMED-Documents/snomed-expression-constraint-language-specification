# A.1 Simple Expression Constraints - Valid Expressions

| **Expression Constraint** | **Valid Expression**[1](https://confluence.ihtsdotools.org/display/DOCECL/A.1+Simple+Expression+Constraints+-+Valid+Expressions#Footnote1) |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| **Precoordinated**        | **Postcoordinated**                                                                                                                        |
| \[ 404684003              | Clinical finding                                                                                                                           |
| < \[ 404684003            | Clinical finding                                                                                                                           |
| \[ 363698007              | Finding site                                                                                                                               |
| \[ 80891009               | Heart structure                                                                                                                            |
| \[ 56265001               | Heart disease                                                                                                                              |
| << \[ 73211009            | Diabetes mellitus                                                                                                                          |
| \[ 42752001               | Due to                                                                                                                                     |
| \[ 61823004               | Injury of pancreas                                                                                                                         |
| \[ 46635009               | Diabetes mellitus type 1                                                                                                                   |
| \[ 105401000119101        | Diabetes mellitus due to pancreatic injury                                                                                                 |
| \<! \[ 404684003          | Clinical finding                                                                                                                           |
| \[ 116676008              | Associated morphology                                                                                                                      |
| \[ 79654002               | Edema                                                                                                                                      |
| \[ 267038008              | Edema                                                                                                                                      |

> [40541001 | Acute pulmonary edema|](http://snomed.info/id/40541001) | [111273006 | Acute respiratory disease|](http://snomed.info/id/111273006) | [64572001 | Disease|](http://snomed.info/id/64572001) :\
> [116676008 | Associated morphology|](http://snomed.info/id/116676008) =\
> [79654002 | Edema|](http://snomed.info/id/79654002) ,\
> [363698007 | Finding site|](http://snomed.info/id/363698007) =\
> [39607008 | Lung structure|](http://snomed.info/id/39607008)\
> [404684003 | Clinical finding|](http://snomed.info/id/404684003)\
> [138875005 | SNOMED CT concept|](http://snomed.info/id/138875005)
>
> > [40541001 | Acute pulmonary edema|](http://snomed.info/id/40541001) | [40541001 | Acute pulmonary edema|](http://snomed.info/id/40541001) | [64572001 | Disease|](http://snomed.info/id/64572001) :\
> > [263502005 | Clinical course|](http://snomed.info/id/263502005) =\
> > [424124008 | Sudden onset AND/OR short duration|](http://snomed.info/id/424124008) ,\
> > { [116676008 | Associated morphology|](http://snomed.info/id/116676008) =\
> > [40829002 | Acute edema|](http://snomed.info/id/40829002) ,\
> > [363698007 | Finding site|](http://snomed.info/id/363698007) =\
> > [39607008 | Lung structure|](http://snomed.info/id/39607008) }\
> > [111273006 | Acute respiratory disease|](http://snomed.info/id/111273006)\
> > [404684003 | Clinical finding|](http://snomed.info/id/404684003)\
> > [138875005 | SNOMED CT concept|](http://snomed.info/id/138875005)\
> > ! [40541001 | Acute pulmonary edema|](http://snomed.info/id/40541001) | [111273006 | Acute respiratory disease|](http://snomed.info/id/111273006) | [19829001 | Disorder of lung|](http://snomed.info/id/19829001) :\
> > { [116676008 | Associated morphology|](http://snomed.info/id/116676008) =\
> > [79654002 | Edema|](http://snomed.info/id/79654002) ,\
> > [363698007 | Finding site|](http://snomed.info/id/363698007) =\
> > [39607008 | Lung structure|](http://snomed.info/id/39607008) } [3](https://confluence.ihtsdotools.org/display/DOCECL/A.1+Simple+Expression+Constraints+-+Valid+Expressions#Footnote3)\
> > [19242006 | Pulmonary edema|](http://snomed.info/id/19242006)\
> > ^ [700043003 | Example problem list concepts reference set|](http://snomed.info/id/700043003) | [394659003 | Acute coronary syndrome|](http://snomed.info/id/394659003) | -\
> > [194828000 | Angina|](http://snomed.info/id/194828000)\
> > [29857009 | Chest pain|](http://snomed.info/id/29857009)

* \| [138875005 | SNOMED CT concept|](http://snomed.info/id/138875005) | [404684003 | Clinical finding|](http://snomed.info/id/404684003) :\
  [363698007 | Finding site|](http://snomed.info/id/363698007) =\
  [80891009 | Heart structure|](http://snomed.info/id/80891009)\
  [404684003 | Clinical finding|](http://snomed.info/id/404684003) | [71388002 | Procedure|](http://snomed.info/id/71388002) :\
  [405813007 | Procedure site - Direct|](http://snomed.info/id/405813007) =\
  [66754008 | Appendix structure|](http://snomed.info/id/66754008)\
  [322236009 | Paracetamol 500mg tablet|](http://snomed.info/id/322236009) | [373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005) :\
  { [127489000 | Has active ingredient|](http://snomed.info/id/127489000) =\
  [412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009) }

| Footnotes Ref                                                                                                                  | Notes                                                                                                                                                                                                                                                                                                        |
| ------------------------------------------------------------------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| [1](https://confluence.ihtsdotools.org/display/DOCECL/A.1+Simple+Expression+Constraints+-+Valid+Expressions#FootnoteMarker1-0) | Where necessary, these examples make some assumptions about the membership of the example reference sets.                                                                                                                                                                                                    |
| [2](https://confluence.ihtsdotools.org/display/DOCECL/A.1+Simple+Expression+Constraints+-+Valid+Expressions#FootnoteMarker2-0) | Please note that this makes the assumption that the given expression constraint is executed against a finite set of expressions that has been pre-classified (e.g. in an expression repository), and that after classification there are no intermediate expressions between this expression and \[404684003 |
| [3](https://confluence.ihtsdotools.org/display/DOCECL/A.1+Simple+Expression+Constraints+-+Valid+Expressions#FootnoteMarker3-0) | Please note that this makes the assumption that the given expression constraint is executed against a finite set of expressions that has been pre-classified (e.g. in an expression repository), and that after classification there are no intermediate expressions between \[40541001                      |
