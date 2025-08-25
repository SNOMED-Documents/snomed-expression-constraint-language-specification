# B.5 Exclusion and Not Equals - Invalid Expressions

**Expression Constraint**| **INVALID Expression**  
---|---  
**Precoordinated**| **Postcoordinated**  
<< [ 19829001 | Disorder of lung|](http://snomed.info/id/19829001 "19829001 | Disorder of lung |") MINUS   
<< [ 301867009 | Edema of trunk|](http://snomed.info/id/301867009 "301867009 | Edema of trunk |") |  [ 27719009 | Acute gastrointestinal hemorrhage|](http://snomed.info/id/27719009 "27719009 | Acute gastrointestinal hemorrhage |") |  [ 19829001 | Disorder of lung|](http://snomed.info/id/19829001 "19829001 | Disorder of lung |") :   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 40829002 | Acute edema|](http://snomed.info/id/40829002 "40829002 | Acute edema |") ,  [ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =  [ 22943007 | Trunk structure|](http://snomed.info/id/22943007 "22943007 | Trunk structure |") }  
[ 19242006 | Pulmonary edema|](http://snomed.info/id/19242006 "19242006 | Pulmonary edema |")  
<< [ 19829001 | Disorder of lung|](http://snomed.info/id/19829001 "19829001 | Disorder of lung |") MINUS   
^  [ 700043003 | Example problem list concepts reference set|](http://snomed.info/id/700043003 "700043003 | Example problem list concepts reference set |") |  [ 67599009 | Pulmonary congestion|](http://snomed.info/id/67599009 "67599009 | Pulmonary congestion |") |  [ 67599009 | Pulmonary congestion|](http://snomed.info/id/67599009 "67599009 | Pulmonary congestion |") :   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 3341006 | Right lung structure|](http://snomed.info/id/3341006 "3341006 | Right lung structure |")  
< [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
[ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
((<< [ 56208002 | Ulcer|](http://snomed.info/id/56208002 "56208002 | Ulcer |") AND   
<< [ 50960005 | Hemorrhage|](http://snomed.info/id/50960005 "50960005 | Hemorrhage |") ) MINUS   
<< [ 26036001 | Obstruction|](http://snomed.info/id/26036001 "26036001 | Obstruction |") ) |  [ 397825006 | Gastric ulcer|](http://snomed.info/id/397825006 "397825006 | Gastric ulcer |") |  [ 64572001 | Disease|](http://snomed.info/id/64572001 "64572001 | Disease |") :   
[ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =  [ 26036001 | Obstruction|](http://snomed.info/id/26036001 "26036001 | Obstruction |")  
[ 235670001 | Gastric stomal obstruction|](http://snomed.info/id/235670001 "235670001 | Gastric stomal obstruction |")  
< [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
[ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |")   
!= << [ 26036001 | Obstruction|](http://snomed.info/id/26036001 "26036001 | Obstruction |") |  [ 81060008 | Intestinal obstruction|](http://snomed.info/id/81060008 "81060008 | Intestinal obstruction |") |  [ 64572001 | Disease|](http://snomed.info/id/64572001 "64572001 | Disease |") :   
[ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 26036001 | Obstruction|](http://snomed.info/id/26036001 "26036001 | Obstruction |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 422897007 | Vascular structure of stomach|](http://snomed.info/id/422897007 "422897007 | Vascular structure of stomach |")  
[ 56265001 | Heart disease|](http://snomed.info/id/56265001 "56265001 | Heart disease |")  
< [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
[0..0]  [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
<< [ 26036001 | Obstruction|](http://snomed.info/id/26036001 "26036001 | Obstruction |") |  [ 81060008 | Intestinal obstruction|](http://snomed.info/id/81060008 "81060008 | Intestinal obstruction |") |  [ 64572001 | Disease|](http://snomed.info/id/64572001 "64572001 | Disease |") :   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 26036001 | Obstruction|](http://snomed.info/id/26036001 "26036001 | Obstruction |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 422897007 | Vascular structure of stomach|](http://snomed.info/id/422897007 "422897007 | Vascular structure of stomach |") }   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 45771005 | Acute bleeding ulcer|](http://snomed.info/id/45771005 "45771005 | Acute bleeding ulcer |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 422897007 | Vascular structure of stomach|](http://snomed.info/id/422897007 "422897007 | Vascular structure of stomach |") }  
[ 234059001 | Venous stenosis|](http://snomed.info/id/234059001 "234059001 | Venous stenosis |")  
< [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
[0..0]  [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |")   
!= << [ 26036001 | Obstruction|](http://snomed.info/id/26036001 "26036001 | Obstruction |") |  [ 196652006 | Acute duodenal ulcer|](http://snomed.info/id/196652006 "196652006 | Acute duodenal ulcer |") |  [ 64572001 | Disease|](http://snomed.info/id/64572001 "64572001 | Disease |") :   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 26036001 | Obstruction|](http://snomed.info/id/26036001 "26036001 | Obstruction |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 422897007 | Vascular structure of stomach|](http://snomed.info/id/422897007 "422897007 | Vascular structure of stomach |") }   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 45771005 | Acute bleeding ulcer|](http://snomed.info/id/45771005 "45771005 | Acute bleeding ulcer |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 422897007 | Vascular structure of stomach|](http://snomed.info/id/422897007 "422897007 | Vascular structure of stomach |") }  
[ 8377001 | Hernia, with obstruction|](http://snomed.info/id/8377001 "8377001 | Hernia, with obstruction |")  
< [ 404684003 | Clinical finding|](http://snomed.info/id/404684003 "404684003 | Clinical finding |") :   
[0..0]  [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") !=   
<< [ 26036001 | Obstruction|](http://snomed.info/id/26036001 "26036001 | Obstruction |") AND   
[1..*]  [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
<< [ 26036001 | Obstruction|](http://snomed.info/id/26036001 "26036001 | Obstruction |") |  [ 196652006 | Acute duodenal ulcer|](http://snomed.info/id/196652006 "196652006 | Acute duodenal ulcer |") |  [ 64572001 | Disease|](http://snomed.info/id/64572001 "64572001 | Disease |") :   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 26036001 | Obstruction|](http://snomed.info/id/26036001 "26036001 | Obstruction |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 422897007 | Vascular structure of stomach|](http://snomed.info/id/422897007 "422897007 | Vascular structure of stomach |") }   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 45771005 | Acute bleeding ulcer|](http://snomed.info/id/45771005 "45771005 | Acute bleeding ulcer |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 422897007 | vascular structure of stomach|](http://snomed.info/id/422897007 "422897007 | vascular structure of stomach |") }  
[ 8377001 | Hernia, with obstruction|](http://snomed.info/id/8377001 "8377001 | Hernia, with obstruction |")  
[ 64572001 | Disease|](http://snomed.info/id/64572001 "64572001 | Disease |") :   
{ [ 116676008 | Associated morphology|](http://snomed.info/id/116676008 "116676008 | Associated morphology |") =   
[ 45771005 | Acute bleeding ulcer|](http://snomed.info/id/45771005 "45771005 | Acute bleeding ulcer |") ,   
[ 363698007 | Finding site|](http://snomed.info/id/363698007 "363698007 | Finding site |") =   
[ 422897007 | Vascular structure of stomach|](http://snomed.info/id/422897007 "422897007 | Vascular structure of stomach |") }  
[ 56265001 | Heart disease|](http://snomed.info/id/56265001 "56265001 | Heart disease |")  
  
* * *
