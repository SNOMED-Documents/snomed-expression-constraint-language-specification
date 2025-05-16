# B.3 Cardinality - Invalid Expressions

**Expression Constraint**| **INVALID Expression**[1](https://confluence.ihtsdotools.org/display/DOCECL/B.3+Cardinality+-+Invalid+Expressions#Footnote1 "Footnote: Click here to display the footnote")  
---|---  
**Precoordinated**| **Postcoordinated**  
< [ 373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") :   
[1..3]  [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active
                              ingredient |") =   
< [ 105590001 | Substance|](http://snomed.info/id/105590001 "105590001 | Substance |") |  [ 279999999108 | Inert tablet|](http://snomed.org/fictid#279999999108 "\(eg:279999999108\)  | Inert tablet |") |  [ 373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") :   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009 "412031009 | Paracetamol or derivative |") },   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 387494007 | Codeine|](http://snomed.info/id/387494007 "387494007 | Codeine |") },   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 255641001 | Caffeine|](http://snomed.info/id/255641001 "255641001 | Caffeine |") },   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 44068004 | Doxylamine|](http://snomed.info/id/44068004 "44068004 | Doxylamine |") }  
[ 437867004 | Chlorphenamine + dextromethorphan + paracetamol + pseudoephedrine|](http://snomed.info/id/437867004 "437867004 | Chlorphenamine + dextromethorphan + paracetamol + pseudoephedrine |")  
< [ 373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") :   
[1..1]  [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
< [ 105590001 | Substance|](http://snomed.info/id/105590001 "105590001 | Substance |") |  [ 279999999108 | Inert tablet|](http://snomed.org/fictid#279999999108 "\(eg:279999999108\)  | Inert tablet |") |  [ 373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") :   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009 "412031009 | Paracetamol or derivative |") },   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 387494007 | Codeine|](http://snomed.info/id/387494007 "387494007 | Codeine |") }  
[ 412556009 | Paracetamol + codeine|](http://snomed.info/id/412556009 "412556009 | Paracetamol + codeine |")  
< [ 373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") :   
[0..1]  [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
< [ 105590001 | Substance|](http://snomed.info/id/105590001 "105590001 | Substance |") |  [ 412556009 | Paracetamol + codeine|](http://snomed.info/id/412556009 "412556009 | Paracetamol + codeine |") |  [ 373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") :   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009 "412031009 | Paracetamol or derivative |") },   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 387494007 | Codeine|](http://snomed.info/id/387494007 "387494007 | Codeine |") }  
< [ 373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") :   
[1..*]  [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
< [ 105590001 | Substance|](http://snomed.info/id/105590001 "105590001 | Substance |") |  [ 279999999108 | Inert tablet|](http://snomed.org/fictid#279999999108 "\(eg:279999999108\)  | Inert tablet |") |  [ 373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") :   
[ 411116001 | Has dose form|](http://snomed.info/id/411116001 "411116001 | Has dose form |") =   
[ 385055001 | Tablet|](http://snomed.info/id/385055001 "385055001 | Tablet |")  
< [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
[1..1]  [ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
< [ 91723000 | Anatomical structure|](http://snomed.info/id/91723000 "91723000 | Anatomical structure |") |  [ 75857000 | Fracture of radius and ulna|](http://snomed.info/id/75857000 "75857000 | Fracture of radius and ulna |") |  [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 72704001 | Fracture|](http://snomed.info/id/72704001 "72704001 | Fracture |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 62413002 | Bone structure of radius|](http://snomed.info/id/62413002 "62413002 | Bone structure of radius |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 23416004 | Bone structure of ulna|](http://snomed.info/id/23416004 "23416004 | Bone structure of ulna |") }  
[ 40733004 | Infectious disease|](http://snomed.info/id/40733004 "40733004 | Infectious disease |")  
< [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
[2..*]  [ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
< [ 91723000 | Anatomical structure|](http://snomed.info/id/91723000 "91723000 | Anatomical structure |") |  [ 23406007 | Arm fracture|](http://snomed.info/id/23406007 "23406007 | Arm fracture |") |  [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 72704001 | Fracture|](http://snomed.info/id/72704001 "72704001 | Fracture |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 702468001 | Bone structure of lower leg|](http://snomed.info/id/702468001 "702468001 | Bone structure of lower leg |") }  
[ 40733004 | Infectious disease|](http://snomed.info/id/40733004 "40733004 | Infectious disease |")  
< [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
{ [2..*]  [ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
< [ 91723000 | Anatomical structure|](http://snomed.info/id/91723000 "91723000 | Anatomical structure |") } |  [ 75857000 | Fracture of radius and ulna|](http://snomed.info/id/75857000 "75857000 | Fracture of radius and ulna |") |  [ 64572001 | Disease|](http://snomed.info/id/64572001 "64572001 | Disease |") :   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 396351009 | Congenital septal defect|](http://snomed.info/id/396351009 "396351009 | Congenital septal defect |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 113262008 | Thoracic aorta structure|](http://snomed.info/id/113262008 "113262008 | Thoracic aorta structure |") }   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 90141005 | Congenital hypertrophy|](http://snomed.info/id/90141005 "90141005 | Congenital hypertrophy |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 244384009 | Entire right ventricle|](http://snomed.info/id/244384009 "244384009 | Entire right ventricle |") }  
< [ 373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") :   
[1..3] { [1..*]  [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
< [ 105590001 | Substance|](http://snomed.info/id/105590001 "105590001 | Substance |") } |  [ 279999999108 | Inert tablet|](http://snomed.org/fictid#279999999108 "\(eg:279999999108\)  | Inert tablet |") |  [ 373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") :   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009 "412031009 | Paracetamol or derivative |") },   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 387494007 | Codeine|](http://snomed.info/id/387494007 "387494007 | Codeine |") },   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 255641001 | Caffeine|](http://snomed.info/id/255641001 "255641001 | Caffeine |") },   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 44068004 | Doxylamine|](http://snomed.info/id/44068004 "44068004 | Doxylamine |") }  
[ 437867004 | Chlorphenamine + dextromethorphan + paracetamol + pseudoephedrine|](http://snomed.info/id/437867004 "437867004 | Chlorphenamine + dextromethorphan + paracetamol + pseudoephedrine |")  
< [ 373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") :   
[0..1] { [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
< [ 105590001 | Substance|](http://snomed.info/id/105590001 "105590001 | Substance |") } |  [ 412556009 | Paracetamol + codeine|](http://snomed.info/id/412556009 "412556009 | Paracetamol + codeine |") |  [ 373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") :   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009 "412031009 | Paracetamol or derivative |") },   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 387494007 | Codeine|](http://snomed.info/id/387494007 "387494007 | Codeine |") }  
< [ 373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") :   
[1..*] { [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
< [ 105590001 | Substance|](http://snomed.info/id/105590001 "105590001 | Substance |") } |  [ 279999999108 | Inert tablet|](http://snomed.org/fictid#279999999108 "\(eg:279999999108\)  | Inert tablet |") |  [ 373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") :   
[ 411116001 | Has dose form|](http://snomed.info/id/411116001 "411116001 | Has dose form |") =   
[ 385055001 | Tablet|](http://snomed.info/id/385055001 "385055001 | Tablet |")  
< [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
[1..1] { [ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
< [ 91723000 | Anatomical structure|](http://snomed.info/id/91723000 "91723000 | Anatomical structure |") } |  [ 75857000 | Fracture of radius and ulna|](http://snomed.info/id/75857000 "75857000 | Fracture of radius and ulna |") |  [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 72704001 | Fracture|](http://snomed.info/id/72704001 "72704001 | Fracture |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 62413002 | Bone structure of radius|](http://snomed.info/id/62413002 "62413002 | Bone structure of radius |") },   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 72704001 | Fracture|](http://snomed.info/id/72704001 "72704001 | Fracture |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 23416004 | Bone structure of ulna|](http://snomed.info/id/23416004 "23416004 | Bone structure of ulna |") }  
[ 40733004 | Infectious disease|](http://snomed.info/id/40733004 "40733004 | Infectious disease |")  
< [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
[0..0] { [2..*]  [ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
< [ 91723000 | Anatomical structure|](http://snomed.info/id/91723000 "91723000 | Anatomical structure |") } | -|  [ 64572001 | Disease|](http://snomed.info/id/64572001 "64572001 | Disease |") :   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 396351009 | Congenital septal defect|](http://snomed.info/id/396351009 "396351009 | Congenital septal defect |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 25943004 | Structure of atrioventricular node|](http://snomed.info/id/25943004 "25943004 | Structure of atrioventricular node |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 113262008 | Thoracic aorta structure|](http://snomed.info/id/113262008 "113262008 | Thoracic aorta structure |") }   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 90141005 | Congenital hypertrophy|](http://snomed.info/id/90141005 "90141005 | Congenital hypertrophy |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 244384009 | entire right ventricle|](http://snomed.info/id/244384009 "244384009 | entire right ventricle |") }  
  
Footnotes Ref | Notes  
---|---  
[1](https://confluence.ihtsdotools.org/display/DOCECL/B.3+Cardinality+-+Invalid+Expressions#FootnoteMarker1-0 "Footnote: Click to return to reference in text") |  The SNOMED CT identifiers created with the '9999999' namespace are for example only, and should not be used in a production environment.
