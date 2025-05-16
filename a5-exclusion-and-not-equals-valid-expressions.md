# A.5 Exclusion and Not Equals - Valid Expressions

**Expression Constraint**| **Valid Expression**[1](https://confluence.ihtsdotools.org/display/DOCECL/A.5+Exclusion+and+Not+Equals+-+Valid+Expressions#Footnote1 "Footnote: Click here to display the footnote")  
---|---  
**Precoordinated**| **Postcoordinated**  
<< [ 19829001 | Disorder of lung|](http://snomed.info/id/19829001 "19829001 | Disorder of lung |") MINUS   
<< [ 301867009 | Edema of trunk|](http://snomed.info/id/301867009 "301867009 | Edema of trunk |") |  [ 372146004 | Acute chest syndrome|](http://snomed.info/id/372146004 "372146004 | Acute chest syndrome |") |  [ 27819004 | Pulmonary ossification|](http://snomed.info/id/27819004 "27819004 | Pulmonary ossification |") :   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 18115005 | Pathologic calcification|](http://snomed.info/id/18115005 "18115005 | Pathologic calcification |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 31094006 | Structure of lobe of lung|](http://snomed.info/id/31094006 "31094006 | Structure of lobe of lung |") }  
[ 413839001 | Chronic lung disease|](http://snomed.info/id/413839001 "413839001 | Chronic lung disease |")  
<< [ 19829001 | Disorder of lung|](http://snomed.info/id/19829001 "19829001 | Disorder of lung |") MINUS   
^  [ 700043003 | Example problem list concepts reference set|](http://snomed.info/id/700043003 "700043003 | Example problem list concepts reference set |") |  [ 233613009 | Fungal pneumonia|](http://snomed.info/id/233613009 "233613009 | Fungal pneumonia |") |  [ 27819004 | Pulmonary ossification|](http://snomed.info/id/27819004 "27819004 | Pulmonary ossification |") :   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 18115005 | Pathologic calcification|](http://snomed.info/id/18115005 "18115005 | Pathologic calcification |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 31094006 | Structure of lobe of lung|](http://snomed.info/id/31094006 "31094006 | Structure of lobe of lung |") }  
< [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
[ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
((<< [ 56208002 | Ulcer|](http://snomed.info/id/56208002 "56208002 | Ulcer |") AND   
<< [ 50960005 | Hemorrhage|](http://snomed.info/id/50960005 "50960005 | Hemorrhage |") ) MINUS   
<< [ 26036001 | Obstruction|](http://snomed.info/id/26036001 "26036001 | Obstruction |") ) |  [ 15902003 | Gastric ulcer with hemorrhage|](http://snomed.info/id/15902003 "15902003 | Gastric ulcer with hemorrhage |") |  [ 64572001 | Disease|](http://snomed.info/id/64572001 "64572001 | Disease |") :   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 55075001 | Bleeding ulcer|](http://snomed.info/id/55075001 "55075001 | Bleeding ulcer |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 14374004 | Structure of lymphatic vessel of esophagus|](http://snomed.info/id/14374004 "14374004 | Structure of lymphatic vessel of esophagus |") }  
< [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
[ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") !=   
<< [ 26036001 | Obstruction|](http://snomed.info/id/26036001 "26036001 | Obstruction |") |  [ 233613009 | Fungal pneumonia|](http://snomed.info/id/233613009 "233613009 | Fungal pneumonia |") |  [ 64572001 | Disease|](http://snomed.info/id/64572001 "64572001 | Disease |") :   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 26036001 | Obstruction|](http://snomed.info/id/26036001 "26036001 | Obstruction |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 422897007 | Vascular structure of stomach|](http://snomed.info/id/422897007 "422897007 | Vascular structure of stomach |") }   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 45771005 | Acute bleeding ulcer|](http://snomed.info/id/45771005 "45771005 | Acute bleeding ulcer |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 422897007 | Vascular structure of stomach|](http://snomed.info/id/422897007 "422897007 | Vascular structure of stomach |") }  
[ 46708007 | Acute gastric ulcer with hemorrhage AND obstruction|](http://snomed.info/id/46708007 "46708007 | Acute gastric ulcer with hemorrhage AND obstruction |")  
< [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") : [0..0]   
[ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
<< [ 26036001 | Obstruction|](http://snomed.info/id/26036001 "26036001 | Obstruction |") |  [ 233613009 | Fungal pneumonia|](http://snomed.info/id/233613009 "233613009 | Fungal pneumonia |") |  [ 64572001 | Disease|](http://snomed.info/id/64572001 "64572001 | Disease |") :   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 55075001 | Bleeding ulcer|](http://snomed.info/id/55075001 "55075001 | Bleeding ulcer |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 14374004 | Structure of lymphatic vessel of oesophagus|](http://snomed.info/id/14374004 "14374004 | Structure of lymphatic vessel of oesophagus |") }  
[ 15902003 | Gastric ulcer with hemorrhage|](http://snomed.info/id/15902003 "15902003 | Gastric ulcer with hemorrhage |")  
< [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") : [0..0]   
[ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") !=   
<< [ 26036001 | Obstruction|](http://snomed.info/id/26036001 "26036001 | Obstruction |") |  [ 244815007 | Pyloric obstruction|](http://snomed.info/id/244815007 "244815007 | Pyloric obstruction |") |  [ 64572001 | Disease|](http://snomed.info/id/64572001 "64572001 | Disease |") :   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 26036001 | Obstruction|](http://snomed.info/id/26036001 "26036001 | Obstruction |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 314600001 | Choledochoenterostomy stoma|](http://snomed.info/id/314600001 "314600001 | Choledochoenterostomy stoma |") }  
[ 84906002 | Local cyanosis|](http://snomed.info/id/84906002 "84906002 | Local cyanosis |")  
< [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
[0..0]  [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |")   
!= << [ 26036001 | Obstruction|](http://snomed.info/id/26036001 "26036001 | Obstruction |") AND   
[1..*]  [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |")   
= << [ 26036001 | Obstruction|](http://snomed.info/id/26036001 "26036001 | Obstruction |") |  [ 244815007 | Pyloric obstruction|](http://snomed.info/id/244815007 "244815007 | Pyloric obstruction |") |  [ 64572001 | Disease|](http://snomed.info/id/64572001 "64572001 | Disease |") :   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 26036001 | Obstruction|](http://snomed.info/id/26036001 "26036001 | Obstruction |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 314600001 | Choledochoenterostomy stoma|](http://snomed.info/id/314600001 "314600001 | Choledochoenterostomy stoma |") }  
  
* * *

Footnotes Ref | Notes  
---|---  
[1](https://confluence.ihtsdotools.org/display/DOCECL/A.5+Exclusion+and+Not+Equals+-+Valid+Expressions#FootnoteMarker1-0 "Footnote: Click to return to reference in text") |  Where necessary, these examples make some assumptions about the membership of the example reference sets. 
