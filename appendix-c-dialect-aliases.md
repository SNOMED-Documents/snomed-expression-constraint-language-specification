# Appendix C - Dialect Aliases

This appendix provides a list of example aliases that may be used to specify a particular dialect in an ECL filter constraint. Please refer to the 'Dialect Filter' section on [6.8 Description Filters](6.8-Description-Filters_115872392.html) for more information on how these dialect aliases are used in ECL.

All dialect aliases should follow the ABNF syntax shown below. This format is designed to be compatible with [BCP-47 (Internet Best Current Practice Specification)](https://www.rfc-editor.org/rfc/rfc5646.html), which ensures alignment with a range of other specifications - e.g. HTTP "accept-language" headers, and the HL7 FHIR "designation.language" data element.

**dialectAlias** = ( language \[ "-" script ] \[ "-" region ] \[ "-" privateuse ] ) / privateuse

**language** = alpha alpha ; ISO 639-1 code ([List of codes](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes))

**script** = alpha alpha alpha alpha ; ISO 15924 code ([List of codes](https://en.wikipedia.org/wiki/ISO_15924#List_of_codes))

**region** = alpha alpha ; ISO 3166-1 code ([List of codes](https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes))

**privateuse** = "x" 1\*("-" 1\*8(alpha / digit) ) ; the clinical scope or context of use

The table below lists the valid 'dialect' filter values and their equivalent 'dialectId' filter values, for a selection of known language reference sets. To request the addition of a new dialect alias, please use the 'Feedback' button on the bottom of this page.

| dialect           | dialectId          |
| ----------------- | ------------------ |
| da-dk             | 554461000005103    |
| en-au             | 32570271000036106  |
| en-ca             | 19491000087109     |
| en-gb             | 900000000000508004 |
| en-ie             | 21000220103        |
| en-nz             | 271000210107       |
| en-nz-x-pat       | 281000210109       |
| en-us             | 900000000000509007 |
| en-x-gmdn         | 608771002          |
| en-x-nhs-clinical | 999001261000000100 |
| en-x-nhs-dmd      | 999000671000001103 |
| en-x-nhs-pharmacy | 999000691000001104 |
| en-gb-x-drug      | 999000681000001101 |
| en-gb-x-ext       | 999001251000000103 |
| es                | 450828004          |
| es-uy             | 5641000179103      |
| et-ee             | 71000181105        |
| de                | 722130004          |
| fr                | 722131000          |
| fr-be             | 21000172104        |
| fr-ca             | 20581000087109     |
| ja                | 722129009          |
| mi                | 291000210106       |
| nl-be             | 31000172101        |
| nl-nl             | 31000146106        |
| nb-no             | 61000202103        |
| nn-no             | 91000202106        |
| sv-se             | 46011000052107     |
| zh                | 722128001          |






<a href="https://docs.google.com/forms/d/e/1FAIpQLScTmbZIf0UEQwYDkY27EEWBkaiYkHSbR0_9DmFrMLXoQLyL7Q/viewform?usp=pp_url&entry.1767247133=ECL+Specification&entry.670899847=Appendix%20C%20-%20Dialect%20Aliases" class="button primary">Provide Feedback</a>
