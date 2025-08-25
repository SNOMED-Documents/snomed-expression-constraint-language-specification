# B.1 Simple Expression Constraints - Invalid Expressions

| **Expression Constraint** | **INVALID Expression**[1](https://confluence.ihtsdotools.org/display/DOCECL/B.1+Simple+Expression+Constraints+-+Invalid+Expressions#Footnote1) |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| **Precoordinated**        | **Postcoordinated**                                                                                                                            |
| \[ 404684003              | Clinical finding                                                                                                                               |
| \[ 363698007              | Finding site                                                                                                                                   |
| \[ 80891009               | Heart structure                                                                                                                                |
| \[ 71388002               | Procedure                                                                                                                                      |
| < \[ 404684003            | Clinical finding                                                                                                                               |
| \[ 405813007              | Procedure site - Direct                                                                                                                        |
| \[ 80891009               | Heart structure                                                                                                                                |
| \[ 71388002               | Procedure                                                                                                                                      |
| << \[ 73211009            | Diabetes mellitus                                                                                                                              |
| \[ 363698007              | Finding site                                                                                                                                   |
| \[ 113331007              | Structure of endocrine system                                                                                                                  |
| \[ 362969004              | Disorder of endocrine system                                                                                                                   |
| \<! \[ 404684003          | Clinical finding                                                                                                                               |
| \[ 116676008              | Associated morphology                                                                                                                          |
| \[ 79654002               | Edema                                                                                                                                          |
| \[ 363698007              | Finding site                                                                                                                                   |
| \[ 80891009               | Heart structure                                                                                                                                |
| \[ 233709006              | Toxic pulmonary edema                                                                                                                          |

> [40541001 | Acute pulmonary edema|](http://snomed.info/id/40541001) | [40541001 | Acute pulmonary edema|](http://snomed.info/id/40541001) | [40541001 | Acute pulmonary edema|](http://snomed.info/id/40541001) :\
> [246112005 | Severity|](http://snomed.info/id/246112005) =\
> [24484000 | Severe|](http://snomed.info/id/24484000)\
> [233709006 | Toxic pulmonary edema|](http://snomed.info/id/233709006)\
> [304527002 | Acute asthma|](http://snomed.info/id/304527002)
>
> > [40541001 | Acute pulmonary edema|](http://snomed.info/id/40541001) | [233709006 | Toxic pulmonary edema|](http://snomed.info/id/233709006) | [40541001 | Acute pulmonary edema|](http://snomed.info/id/40541001) :\
> > [246112005 | Severity|](http://snomed.info/id/246112005) =\
> > [24484000 | Severe|](http://snomed.info/id/24484000)\
> > [304527002 | Acute asthma|](http://snomed.info/id/304527002)\
> > ! [40541001 | Acute pulmonary edema|](http://snomed.info/id/40541001) | [404684003 | Clinical finding|](http://snomed.info/id/404684003) | [64572001 | Disease|](http://snomed.info/id/64572001) :\
> > [263502005 | Clinical course|](http://snomed.info/id/263502005) =\
> > [424124008 | Sudden onset AND/OR short duration|](http://snomed.info/id/424124008) [3](https://confluence.ihtsdotools.org/display/DOCECL/B.1+Simple+Expression+Constraints+-+Invalid+Expressions#Footnote3)\
> > [267038008 | Edema|](http://snomed.info/id/267038008)\
> > ^ [700043003 | Example problem list concepts reference set|](http://snomed.info/id/700043003) | [6143009 | Diabetic education|](http://snomed.info/id/6143009) | [71388002 | Procedure|](http://snomed.info/id/71388002) :\
> > [405813007 | Procedure site - Direct|](http://snomed.info/id/405813007) =\
> > [80891009 | Heart structure|](http://snomed.info/id/80891009)\
> > [75367002 | Blood pressure|](http://snomed.info/id/75367002)

* \| -| -\
  \-| -\
  \-| -

***

| Footnotes Ref                                                                                                                    | Notes                                                                                                                                                                                                                                                                                                                |
| -------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [1](https://confluence.ihtsdotools.org/display/DOCECL/B.1+Simple+Expression+Constraints+-+Invalid+Expressions#FootnoteMarker1-0) | Where necessary, these examples make some assumptions about the membership of the example reference sets.                                                                                                                                                                                                            |
| [2](https://confluence.ihtsdotools.org/display/DOCECL/B.1+Simple+Expression+Constraints+-+Invalid+Expressions#FootnoteMarker2-0) | Please note that this makes the assumption that the given expression constraint is executed against a finite set of expressions that has been pre-classified (e.g. in an expression repository), and that after classification there is at least one intermediate expression between this expression and \[404684003 |
| [3](https://confluence.ihtsdotools.org/display/DOCECL/B.1+Simple+Expression+Constraints+-+Invalid+Expressions#FootnoteMarker3-0) | Please note that this makes the assumption that the given expression constraint is executed against a finite set of expressions that has been pre-classified (e.g. in an expression repository), and that after classification there is at least one intermediate expression between \[40541001                      |
