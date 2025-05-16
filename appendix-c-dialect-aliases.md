# Appendix C - Dialect Aliases

This appendix provides a list of example aliases that may be used to specify a particular dialect in an ECL filter constraint. Please refer to the 'Dialect Filter' section on [6.8 Description Filters](6.8-Description-Filters_115872392.html) for more information on how these dialect aliases are used in ECL.

All dialect aliases should follow the ABNF syntax shown below. This format is designed to be compatible with [BCP-47 (Internet Best Current Practice Specification)](https://www.rfc-editor.org/rfc/rfc5646.html), which ensures alignment with a range of other specifications - e.g. HTTP "accept-language" headers, and the HL7 FHIR "designation.language" data element.

**dialectAlias** = ( language [ "-" script ] [ "-" region ] [ "-" privateuse ] ) / privateuse

**language** = alpha alpha ; ISO 639-1 code ([List of codes](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes))

**script** = alpha alpha alpha alpha ; ISO 15924 code ([List of codes](https://en.wikipedia.org/wiki/ISO_15924#List_of_codes))

**region** = alpha alpha ; ISO 3166-1 code ([List of codes](https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes))

**privateuse** = "x" 1*("-" 1*8(alpha / digit) ) ; the clinical scope or context of use

The table below lists the valid 'dialect' filter values and their equivalent 'dialectId' filter values, for a selection of known language reference sets. To request the addition of a new dialect alias, please use the 'Feedback' button on the bottom of this page. 

dialect| dialectId  
---|---  
da-dk| 554461000005103 |Danish language reference set|  
en-au| 32570271000036106 |Australian English language reference set|  
en-ca| 19491000087109 |Canada English language reference set|  
en-gb| 900000000000508004 |Great Britain English language reference set|  
en-ie| 21000220103 |Irish language reference set|  
en-nz| 271000210107 |New Zealand English language reference set|  
en-nz-x-pat| 281000210109 |New Zealand English patient friendly terms language reference set|  
en-us| 900000000000509007 |United States of America English language reference set|  
en-x-gmdn| 608771002 |GMDN language reference set|  
en-x-nhs-clinical| 999001261000000100 |National Health Service realm language reference set (clinical part)|  
en-x-nhs-dmd| 999000671000001103 |National Health Service dictionary of medicines and devices realm language reference set|  
en-x-nhs-pharmacy| 999000691000001104 |National Health Service realm language reference set (pharmacy part)|  
en-gb-x-drug| 999000681000001101 |United Kingdom Drug Extension Great Britain English language reference set|  
en-gb-x-ext| 999001251000000103 |United Kingdom Extension Great Britain English language reference set|  
es| 450828004 |Conjunto de referencias de lenguaje castellano para América Latina|  
es-uy| 5641000179103 |Conjunto de referencias de lenguaje castellano para Uruguay|  
et-ee| 71000181105 |Estonian language reference set|  
de| 722130004 |German language reference set|  
fr| 722131000 |French language reference set|  
fr-be| 21000172104 |Belgian French language reference set|  
fr-ca| 20581000087109 |Canada French language reference set|  
ja| 722129009 | Japanese language reference set|  
mi| 291000210106 |Maori language reference set|  
nl-be| 31000172101 |Belgian Dutch language reference set|  
nl-nl| 31000146106 |Netherlands Dutch language reference set|  
nb-no| 61000202103 |Norwegian Bokmål language reference set|  
nn-no| 91000202106 |Norwegian Nynorsk language reference set|  
sv-se| 46011000052107 |Swedish language reference set|  
zh| 722128001 |Chinese language reference set|  
  
  
  

