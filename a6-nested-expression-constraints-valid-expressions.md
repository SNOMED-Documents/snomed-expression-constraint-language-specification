# A.6 Nested Expression Constraints - Valid Expressions

**Expression Constraint**| **Valid Expression**[1](https://confluence.ihtsdotools.org/display/DOCECL/A.6+Nested+Expression+Constraints+-+Valid+Expressions#Footnote1 "Footnote: Click here to display the footnote")  
---|---  
**Precoordinated**| **Postcoordinated**  
<< (^  [ 700043003 | Example problem list concepts reference set|](http://snomed.info/id/700043003 "700043003 | Example problem list concepts reference set |") ) |  [ 394659003 | Acute coronary syndrome|](http://snomed.info/id/394659003 "394659003 | Acute coronary syndrome |") |  [ 194828000 |Angina|](http://snomed.info/id/194828000 "194828000 | Angina |") :  
[ 255234002 |After|](http://snomed.info/id/255234002 "255234002 | After |") =  [ 22298006 |Myocardial infarction|](http://snomed.info/id/22298006 "22298006 | Myocardial infarction |")  
[ 194828000 | Angina|](http://snomed.info/id/194828000 "194828000 | Angina |")  
[ 371807002 | Atypical angina|](http://snomed.info/id/371807002 "371807002 | Atypical angina |")  
^ (< [ 450973005 | GP/FP health issue reference set|](http://snomed.info/id/450973005 "450973005 | GP/FP health issue reference set |") ) |  [ 140004 | Chronic pharyngitis|](http://snomed.info/id/140004 "140004 | Chronic pharyngitis |") | -  
[ 297009 | Acute myringitis|](http://snomed.info/id/297009 "297009 | Acute myringitis |")  
(< [ 404684003 |Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :  
[ 363698007 |Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") = << [ 39057004 |Pulmonary valve structure|](http://snomed.info/id/39057004 "39057004 | Pulmonary valve structure |") )   
AND ^  [ 700043003 |Example problem list concepts reference set|](http://snomed.info/id/700043003 "700043003 | Example problem list concepts reference set |") |  [ 204351007 | Fallot&#39;s trilogy|](http://snomed.info/id/204351007 "204351007 | Fallot's trilogy |") | -  
[ 457652006 | Calcification of pulmonary valve|](http://snomed.info/id/457652006 "457652006 | Calcification of pulmonary valve |")  
(< [ 404684003 |Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :  [ 363698007 |Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") = << [ 39057004 |Pulmonary valve structure|](http://snomed.info/id/39057004 "39057004 | Pulmonary valve structure |") )   
AND (< [ 64572001 |Disease|](http://snomed.info/id/64572001 "64572001 | Disease |") :  [ 116676008 |Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") = << [ 415582006 |Stenosis|](http://snomed.info/id/415582006 "415582006 | Stenosis |") ) |  [ 204351007 | Fallot&#39;s trilogy|](http://snomed.info/id/204351007 "204351007 | Fallot's trilogy |") |  [ 19036004 |Rheumatic heart valve stenosis|](http://snomed.info/id/19036004 "19036004 | Rheumatic heart valve stenosis |") :  
{ [ 363698007 |Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =  [ 39057004 |Pulmonary valve structure|](http://snomed.info/id/39057004 "39057004 | Pulmonary valve structure |") ,   
[ 116676008 |Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =  [ 415582006 |Stenosis|](http://snomed.info/id/415582006 "415582006 | Stenosis |") }  
[ 56786000 | Pulmonic valve stenosis|](http://snomed.info/id/56786000 "56786000 | Pulmonic valve stenosis |")  
(<< [ 17636008 |Specimen collection|](http://snomed.info/id/17636008 "17636008 | Specimen collection |") :   
[ 424226004 |Using device|](http://snomed.info/id/424226004 "424226004 | Using device |") = << [ 19923001 |Catheter|](http://snomed.info/id/19923001 "19923001 | Catheter |") )   
.  [ 363701004 |Direct substance|](http://snomed.info/id/363701004 "363701004 | Direct substance |") |  [ 78014005 | Urine|](http://snomed.info/id/78014005 "78014005 | Urine |") | -  
[ 87612001 | Blood|](http://snomed.info/id/87612001 "87612001 | Blood |")  
(<< [ 404684003 |Clinical finding (finding)|](http://snomed.info/id/404684003 "404684003 | Clinical finding \(finding\) |") OR << [ 272379006 |Event (event)|](http://snomed.info/id/272379006 "272379006 | Event \(event\) |") ):   
[ 255234002 |After|](http://snomed.info/id/255234002 "255234002 | After |") = << [ 71388002 |Procedure (procedure)|](http://snomed.info/id/71388002 "71388002 | Procedure \(procedure\) |") |  [ 235948002 | Postoperative acute pancreatitis|](http://snomed.info/id/235948002 "235948002 | Postoperative acute pancreatitis |") |  [ 64572001 |Disease|](http://snomed.info/id/64572001 "64572001 | Disease |") :  
{ [ 370135005 |Pathological process|](http://snomed.info/id/370135005 "370135005 | Pathological process |") =  [ 441862004 |Infectious process|](http://snomed.info/id/441862004 "441862004 | Infectious process |") ,  
[ 255234002 |After|](http://snomed.info/id/255234002 "255234002 | After |") =  [ 387713003 |Surgical procedure|](http://snomed.info/id/387713003 "387713003 | Surgical procedure |") ,  
[ 116676008 |Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =  [ 112633009 |Surgical would|](http://snomed.info/id/112633009 "112633009 | Surgical would |") }  
[ 441795000 | Infected seroma after surgical procedure|](http://snomed.info/id/441795000 "441795000 | Infected seroma after surgical procedure |")  
<< [ 125605004 |Fracture of bone|](http://snomed.info/id/125605004 "125605004 | Fracture of bone |") :  
[0..0] ((<< [ 410662002 |Concept model attribute|](http://snomed.info/id/410662002 "410662002 | Concept model attribute |") MINUS  [ 363698007 |Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") ) MINUS  [ 116676008 |Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") ) = * |  [ 125605004 | Fracture of bone|](http://snomed.info/id/125605004 "125605004 | Fracture of bone |") |  [ 64572001 | Disease|](http://snomed.info/id/64572001 "64572001 | Disease |") :   
{ [ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 71341001 | Bone structure of femur|](http://snomed.info/id/71341001 "71341001 | Bone structure of femur |") ,   
[ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 20946005 | Fracture, closed|](http://snomed.info/id/20946005 "20946005 | Fracture, closed |") }  
[ 439987009 | Open fracture of bone|](http://snomed.info/id/439987009 "439987009 | Open fracture of bone |")  
< [ 404684003 |Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :  
[ 47429007 |Associated with|](http://snomed.info/id/47429007 "47429007 | Associated with |") = (< [ 404684003 |Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
[ 116676008 |Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") = << [ 55641003 |Infarct|](http://snomed.info/id/55641003 "55641003 | Infarct |") ) |  [ 71023004 | Pericarditis secondary to acute myocardial infarction|](http://snomed.info/id/71023004 "71023004 | Pericarditis secondary to acute myocardial infarction |") |  [ 3238004 | Pericarditis (disorder)|](http://snomed.info/id/3238004 "3238004 | Pericarditis \(disorder\) |") :   
[ 47429007 | Associated with|](http://snomed.info/id/47429007 "47429007 | Associated with |") =   
[ 57054005 | Acute myocardial infarction|](http://snomed.info/id/57054005 "57054005 | Acute myocardial infarction |")  
  
* * *

Footnotes Ref | Notes  
---|---  
[1](https://confluence.ihtsdotools.org/display/DOCECL/A.6+Nested+Expression+Constraints+-+Valid+Expressions#FootnoteMarker1-0 "Footnote: Click to return to reference in text") |  Where necessary, these examples make some assumptions about the membership of the example reference sets. 
