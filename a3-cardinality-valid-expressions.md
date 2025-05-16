# A.3 Cardinality - Valid Expressions

**Expression Constraint**| **Valid Expression**[1](https://confluence.ihtsdotools.org/display/DOCECL/A.3+Cardinality+-+Valid+Expressions#Footnote1 "Footnote: Click here to display the footnote")  
---|---  
**Precoordinated**| **Postcoordinated**  
  
< [ 373873005 |Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") : [1..3]  [ 127489000 |Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") = < [ 105590001 |Substance|](http://snomed.info/id/105590001 "105590001 | Substance |") |  [ 322236009 | Paracetamol 500mg tablet|](http://snomed.info/id/322236009 "322236009 | Paracetamol 500mg tablet |") |  [ 373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") :   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009 "412031009 | Paracetamol or derivative |") }  
[ 404826002 | Benzocaine + butamben + tetracaine hydrochloride|](http://snomed.info/id/404826002 "404826002 | Benzocaine + butamben + tetracaine hydrochloride |") |  [ 373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") :   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009 "412031009 | Paracetamol or derivative |") },   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 387494007 | Codeine|](http://snomed.info/id/387494007 "387494007 | Codeine |") }  
  
< [ 373873005 |Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") : [1..1]  [ 127489000 |Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") = < [ 105590001 |Substance|](http://snomed.info/id/105590001 "105590001 | Substance |") |  [ 370166004 | Aspirin 325mg tablet|](http://snomed.info/id/370166004 "370166004 | Aspirin 325mg tablet |") |  [ 373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") :   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009 "412031009 | Paracetamol or derivative |") }  
  
< [ 373873005 |Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") : [0..1]  [ 127489000 |Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") = < [ 105590001 |Substance|](http://snomed.info/id/105590001 "105590001 | Substance |") |  [ 279999999108 | Inert tablet|](http://snomed.org/fictid#279999999108 "\(eg:279999999108\)  | Inert tablet |") |  [ 373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") :   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009 "412031009 | Paracetamol or derivative |") }  
[ 370166004 | Aspirin 325mg tablet|](http://snomed.info/id/370166004 "370166004 | Aspirin 325mg tablet |")  
  
< [ 373873005 |Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") : [1..*]  [ 127489000 |Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") = < [ 105590001 |Substance|](http://snomed.info/id/105590001 "105590001 | Substance |") |  [ 7947003 | Aspirin|](http://snomed.info/id/7947003 "7947003 | Aspirin |") |  [ 373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") :   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009 "412031009 | Paracetamol or derivative |") },   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 255641001 | Caffeine|](http://snomed.info/id/255641001 "255641001 | Caffeine |") },   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 387458008 | Aspirin|](http://snomed.info/id/387458008 "387458008 | Aspirin |") }  
[ 437867004 | Chlorphenamine + dextromethorphan + paracetamol + pseudoephedrine|](http://snomed.info/id/437867004 "437867004 | Chlorphenamine + dextromethorphan + paracetamol + pseudoephedrine |")  
< [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
[1..1]  [ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
< [ 91723000 | Anatomical structure|](http://snomed.info/id/91723000 "91723000 | Anatomical structure |") |  [ 125596004 | Injury of elbow|](http://snomed.info/id/125596004 "125596004 | Injury of elbow |") |  [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 72704001 | Fracture|](http://snomed.info/id/72704001 "72704001 | Fracture |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 299701004 | Bone of forearm|](http://snomed.info/id/299701004 "299701004 | Bone of forearm |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 62413002 | Bone structure of radius|](http://snomed.info/id/62413002 "62413002 | Bone structure of radius |") } [2](https://confluence.ihtsdotools.org/display/DOCECL/A.3+Cardinality+-+Valid+Expressions#Footnote2 "Footnote: Click here to display the footnote")  
< [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
[2..*]  [ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
< [ 91723000 | Anatomical structure|](http://snomed.info/id/91723000 "91723000 | Anatomical structure |") |  [ 86299006 | Tetralogy of Fallot|](http://snomed.info/id/86299006 "86299006 | Tetralogy of Fallot |") |  [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 72704001 | Fracture|](http://snomed.info/id/72704001 "72704001 | Fracture |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 299701004 | Bone of forearm|](http://snomed.info/id/299701004 "299701004 | Bone of forearm |") },   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 72704001 | Fracture|](http://snomed.info/id/72704001 "72704001 | Fracture |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 702468001 | Bone structure of lower leg|](http://snomed.info/id/702468001 "702468001 | Bone structure of lower leg |") }  
< [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
{ [2..*]  [ 363698007 | finding site|](http://snomed.info/id/363698007 "363698007 | finding site |") =   
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
[ 244384009 | Entire right ventricle|](http://snomed.info/id/244384009 "244384009 | Entire right ventricle |") }  
  
< [ 373873005 |Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") : [1..3] { [1..*]  [ 127489000 |Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") = < [ 105590001 |Substance|](http://snomed.info/id/105590001 "105590001 | Substance |") } |  [ 322236009 | Paracetamol 500mg tablet|](http://snomed.info/id/322236009 "322236009 | Paracetamol 500mg tablet |") |  [ 373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") :   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009 "412031009 | Paracetamol or derivative |") }  
[ 404826002 | Benzocaine + butamben + tetracaine hydrochloride|](http://snomed.info/id/404826002 "404826002 | Benzocaine + butamben + tetracaine hydrochloride |") |  [ 373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") :   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009 "412031009 | Paracetamol or derivative |") },   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 387494007 | Codeine|](http://snomed.info/id/387494007 "387494007 | Codeine |") }  
  
< [ 373873005 |Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") : [0..1] { [ 127489000 |Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") = < [ 105590001 |Substance|](http://snomed.info/id/105590001 "105590001 | Substance |") } |  [ 111115279999999108 | Inert tablet|](http://snomed.org/fictid#111115279999999108 "\(eg:111115279999999108\)  | Inert tablet |") |  [ 373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") :   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009 "412031009 | Paracetamol or derivative |") }  
[ 370166004 | Aspirin 325mg tablet|](http://snomed.info/id/370166004 "370166004 | Aspirin 325mg tablet |")  
  
< [ 373873005 |Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") : [1..*] { [ 127489000 |Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") = < [ 105590001 |Substance|](http://snomed.info/id/105590001 "105590001 | Substance |") } |  [ 370166004 | Aspirin 325mg tablet|](http://snomed.info/id/370166004 "370166004 | Aspirin 325mg tablet |") |  [ 373873005 | Pharmaceutical / biologic product|](http://snomed.info/id/373873005 "373873005 | Pharmaceutical / biologic product |") :   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 412031009 | Paracetamol or derivative|](http://snomed.info/id/412031009 "412031009 | Paracetamol or derivative |") },   
{ [ 127489000 | Has active ingredient|](http://snomed.info/id/127489000 "127489000 | Has active ingredient |") =   
[ 387494007 | Codeine|](http://snomed.info/id/387494007 "387494007 | Codeine |") }  
< [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
[1..1] { [ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
< [ 91723000 | Anatomical structure|](http://snomed.info/id/91723000 "91723000 | Anatomical structure |") } |  [ 125596004 | Injury of elbow|](http://snomed.info/id/125596004 "125596004 | Injury of elbow |") |  [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
{ [ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 299701004 | Bone of forearm|](http://snomed.info/id/299701004 "299701004 | Bone of forearm |") },   
{ [ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 62413002 | Bone structure of radius|](http://snomed.info/id/62413002 "62413002 | Bone structure of radius |") }  
  
< [ 404684003 |Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :  
[0..0] { [2..*]  [ 363698007 |Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") = < [ 91723000 |Anatomical structure|](http://snomed.info/id/91723000 "91723000 | Anatomical structure |") } |  [ 86299006 | Tetralogy of Fallot|](http://snomed.info/id/86299006 "86299006 | Tetralogy of Fallot |") |  [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 39057004 | Pulmonary valve structure|](http://snomed.info/id/39057004 "39057004 | Pulmonary valve structure |") ,   
[ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 415582006 | Stenosis|](http://snomed.info/id/415582006 "415582006 | Stenosis |")  
  
* * *

Footnotes Ref | Notes  
---|---  
[1](https://confluence.ihtsdotools.org/display/DOCECL/A.3+Cardinality+-+Valid+Expressions#FootnoteMarker1-0 "Footnote: Click to return to reference in text") |  The SNOMED CT identifiers created with the '9999999' namespace are for example only, and should not be used in a production environment.  
[2](https://confluence.ihtsdotools.org/display/DOCECL/A.3+Cardinality+-+Valid+Expressions#FootnoteMarker2-0 "Footnote: Click to return to reference in text") |  As mentioned earlier, only non-redundant defining attributes are included in the cardinality count. Because <a href="http://snomed.info/id/62413002" title="62413002 | Bone structure of radius |" class="external-link" rel="nofollow"> <span style="color: #606060;" class="sctid">62413002</span> <span style="color: #00ccff;" class="sctpipe">|</span> <span style="color: #000000;" class="sctid">Bone structure of radius</span><span style="color: #00ccff;" class="sctpipe">|</span></a> is a subtype of <a href="http://snomed.info/id/299701004" title="299701004 | Bone of forearm |" class="external-link" rel="nofollow"> <span style="color: #606060;" class="sctid">299701004</span> <span style="color: #00ccff;" class="sctpipe">|</span> <span style="color: #000000;" class="sctid">Bone of forearm</span><span style="color: #00ccff;" class="sctpipe">|</span></a> , the refinement &quot; <a href="http://snomed.info/id/363698007" title="363698007 | Finding site |" class="external-link" rel="nofollow"> <span style="color: #606060;" class="sctid">363698007</span> <span style="color: #00ccff;" class="sctpipe">|</span> <span style="color: #000000;" class="sctid">Finding site</span><span style="color: #00ccff;" class="sctpipe">|</span></a> <span style="color: #a00000;" class="sctid"> = </span> <a href="http://snomed.info/id/299701004" title="299701004 | Bone of forearm |" class="external-link" rel="nofollow"> <span style="color: #606060;" class="sctid">299701004</span> <span style="color: #00ccff;" class="sctpipe">|</span> <span style="color: #000000;" class="sctid">Bone of forearm</span><span style="color: #00ccff;" class="sctpipe">|</span></a> &quot; is redundant.
