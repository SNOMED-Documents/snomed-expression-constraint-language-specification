# B.4 Conjunction and Disjunction - Invalid Expressions

**Expression Constraint**| **INVALID Expression**[1](https://confluence.ihtsdotools.org/display/DOCECL/B.4+Conjunction+and+Disjunction+-+Invalid+Expressions#Footnote1 "Footnote: Click here to display the footnote")  
---|---  
**Precoordinated**| **Postcoordinated**  
< [ 19829001 | Disorder of lung|](http://snomed.info/id/19829001 "19829001 | Disorder of lung |") AND   
< [ 301867009 | Edema of trunk|](http://snomed.info/id/301867009 "301867009 | Edema of trunk |") |  [ 73452002 | Abscess of lung|](http://snomed.info/id/73452002 "73452002 | Abscess of lung |") |  [ 248508001 | Abdominal wall edema|](http://snomed.info/id/248508001 "248508001 | Abdominal wall edema |") :   
[ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 40829002 | Acute edema|](http://snomed.info/id/40829002 "40829002 | Acute edema |")  
[ 248508001 | Abdominal wall edema|](http://snomed.info/id/248508001 "248508001 | Abdominal wall edema |")  
< [ 19829001 | Disorder of lung|](http://snomed.info/id/19829001 "19829001 | Disorder of lung |") OR   
< [ 301867009 | Edema of trunk|](http://snomed.info/id/301867009 "301867009 | Edema of trunk |") |  [ 19829001 | Disorder of lung|](http://snomed.info/id/19829001 "19829001 | Disorder of lung |") |  [ 128121009 | Disorder of trunk|](http://snomed.info/id/128121009 "128121009 | Disorder of trunk |") :   
[ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 44132006 | Abscess|](http://snomed.info/id/44132006 "44132006 | Abscess |")  
[ 301867009 | Edema of trunk|](http://snomed.info/id/301867009 "301867009 | Edema of trunk |")  
[ 128121009 | Disorder of trunk|](http://snomed.info/id/128121009 "128121009 | Disorder of trunk |")  
< [ 19829001 | Disorder of lung|](http://snomed.info/id/19829001 "19829001 | Disorder of lung |") AND   
^  [ 700043003 | Example problem list concepts reference set|](http://snomed.info/id/700043003 "700043003 | Example problem list concepts reference set |") |  [ 73452002 | Abscess of lung|](http://snomed.info/id/73452002 "73452002 | Abscess of lung |") |  [ 19829001 | Disorder of lung|](http://snomed.info/id/19829001 "19829001 | Disorder of lung |") :   
[ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 44132006 | Abscess|](http://snomed.info/id/44132006 "44132006 | Abscess |")  
< [ 404684003 |Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :  
[ 363698007 |Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") = << [ 39057004 |Pulmonary valve structure|](http://snomed.info/id/39057004 "39057004 | Pulmonary valve structure |") AND  
[ 116676008 |Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") = << [ 415582006 |Stenosis|](http://snomed.info/id/415582006 "415582006 | Stenosis |") |  [ 301104003 | Pulmonary valve finding|](http://snomed.info/id/301104003 "301104003 | Pulmonary valve finding |") |  [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
[ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 88015002 | Partial stenosis|](http://snomed.info/id/88015002 "88015002 | Partial stenosis |")  
[ 60573004 | Aortic valve stenosis|](http://snomed.info/id/60573004 "60573004 | Aortic valve stenosis |")  
< [ 404684003 |Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :  
[ 116676008 |Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") = << [ 55641003 |Infarct|](http://snomed.info/id/55641003 "55641003 | Infarct |") OR  
[ 42752001 |Due to|](http://snomed.info/id/42752001 "42752001 | Due to |") = << [ 22298006 |Myocardial infarction|](http://snomed.info/id/22298006 "22298006 | Myocardial infarction |") |  [ 368009 | Heart valve disorder|](http://snomed.info/id/368009 "368009 | Heart valve disorder |") |  [ 95281009 | Sudden cardiac death|](http://snomed.info/id/95281009 "95281009 | Sudden cardiac death |") :   
[ 42752001 | Due to|](http://snomed.info/id/42752001 "42752001 | Due to |") =   
[ 10633002 | Acute congestive heart failure|](http://snomed.info/id/10633002 "10633002 | Acute congestive heart failure |")  
[ 461089003 | Cardiac abnormality due to heart abscess|](http://snomed.info/id/461089003 "461089003 | Cardiac abnormality due to heart abscess |")  
< [ 404684003 |Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :  
{ [ 363698007 |Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") = << [ 39057004 |Pulmonary valve structure|](http://snomed.info/id/39057004 "39057004 | Pulmonary valve structure |") ,  
[ 116676008 |Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") = << [ 415582006 |Stenosis|](http://snomed.info/id/415582006 "415582006 | Stenosis |") } OR  
{ [ 363698007 |Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") = << [ 53085002 |Right ventricular structure|](http://snomed.info/id/53085002 "53085002 | Right ventricular structure |") ,  
[ 116676008 |Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") = << [ 56246009 |Hypertrophy|](http://snomed.info/id/56246009 "56246009 | Hypertrophy |") } |  [ 93075009 | Congenital hypertrophy of pulmonary valve|](http://snomed.info/id/93075009 "93075009 | Congenital hypertrophy of pulmonary valve |") |  [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 39057004 | Pulmonary valve structure|](http://snomed.info/id/39057004 "39057004 | Pulmonary valve structure |") ,   
[ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 56246009 | Hypertrophy|](http://snomed.info/id/56246009 "56246009 | Hypertrophy |")  
[ 204370002 | Stenosis of infundibulum of right ventricle|](http://snomed.info/id/204370002 "204370002 | Stenosis of infundibulum of right ventricle |")  
^  [ 450990004 | Adverse drug reactions reference set for GP/FP health issue|](http://snomed.info/id/450990004 "450990004 | Adverse drug reactions reference set for GP/FP health issue |") :   
[ 246075003 | Causative agent|](http://snomed.info/id/246075003 "246075003 | Causative agent |") =   
(< [ 373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |")   
OR < [ 105590001 | Substance|](http://snomed.info/id/105590001 "105590001 | Substance |") ) |  [ 87628006 | Bacterial infectious disease|](http://snomed.info/id/87628006 "87628006 | Bacterial infectious disease |") |  [ 609328004 | Allergic disposition|](http://snomed.info/id/609328004 "609328004 | Allergic disposition |") :   
[ 246075003 | Causative agent|](http://snomed.info/id/246075003 "246075003 | Causative agent |") =   
[ 84489001 | Mold|](http://snomed.info/id/84489001 "84489001 | Mold |")  
[ 609328004 | Allergic disposition|](http://snomed.info/id/609328004 "609328004 | Allergic disposition |")  
[ 10629471000119106 | Allergic rhinitis caused by mould|](http://snomed.info/id/10629471000119106 "10629471000119106 | Allergic rhinitis caused by mould |")  
< [ 404684003 |Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :  
[ 116676008 |Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
(<< [ 56208002 |Ulcer|](http://snomed.info/id/56208002 "56208002 | Ulcer |") AND << [ 50960005 |Hemorrhage|](http://snomed.info/id/50960005 "50960005 | Hemorrhage |") ) |  [ 196652006 | Acute duodenal ulcer|](http://snomed.info/id/196652006 "196652006 | Acute duodenal ulcer |") |  [ 64572001 | Disease|](http://snomed.info/id/64572001 "64572001 | Disease |") :   
[ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 405719001 | Chronic ulcer|](http://snomed.info/id/405719001 "405719001 | Chronic ulcer |")  
[ 74474003 | Gastrointestinal haemorrhage|](http://snomed.info/id/74474003 "74474003 | Gastrointestinal haemorrhage |")  
  
* * *

Footnotes Ref | Notes  
---|---  
[1](https://confluence.ihtsdotools.org/display/DOCECL/B.4+Conjunction+and+Disjunction+-+Invalid+Expressions#FootnoteMarker1-0 "Footnote: Click to return to reference in text") |  Where necessary, these examples make some assumptions about the membership of the example reference sets. 
