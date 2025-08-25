# A.6 Nested Expression Constraints - Valid Expressions

| **Expression Constraint** | **Valid Expression**[1](https://confluence.ihtsdotools.org/display/DOCECL/A.6+Nested+Expression+Constraints+-+Valid+Expressions#Footnote1) |
| ------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------ |
| **Precoordinated**        | **Postcoordinated**                                                                                                                        |
| << (^ \[ 700043003        | Example problem list concepts reference set                                                                                                |
| \[ 255234002              | After                                                                                                                                      |
| \[ 194828000              | Angina                                                                                                                                     |
| \[ 371807002              | Atypical angina                                                                                                                            |
| ^ (< \[ 450973005         | GP/FP health issue reference set                                                                                                           |
| \[ 297009                 | Acute myringitis                                                                                                                           |
| (< \[ 404684003           | Clinical finding                                                                                                                           |
| \[ 363698007              | Finding site                                                                                                                               |
| AND ^ \[ 700043003        | Example problem list concepts reference set                                                                                                |
| \[ 457652006              | Calcification of pulmonary valve                                                                                                           |
| (< \[ 404684003           | Clinical finding                                                                                                                           |
| AND (< \[ 64572001        | Disease                                                                                                                                    |
| { \[ 363698007            | Finding site                                                                                                                               |
| \[ 116676008              | Associated morphology                                                                                                                      |
| \[ 56786000               | Pulmonic valve stenosis                                                                                                                    |
| (<< \[ 17636008           | Specimen collection                                                                                                                        |
| \[ 424226004              | Using device                                                                                                                               |
| . \[ 363701004            | Direct substance                                                                                                                           |
| \[ 87612001               | Blood                                                                                                                                      |
| (<< \[ 404684003          | Clinical finding (finding)                                                                                                                 |
| \[ 255234002              | After                                                                                                                                      |
| { \[ 370135005            | Pathological process                                                                                                                       |
| \[ 255234002              | After                                                                                                                                      |
| \[ 116676008              | Associated morphology                                                                                                                      |
| \[ 441795000              | Infected seroma after surgical procedure                                                                                                   |
| << \[ 125605004           | Fracture of bone                                                                                                                           |
| \[0..0] ((<< \[ 410662002 | Concept model attribute                                                                                                                    |
| { \[ 363698007            | Finding site                                                                                                                               |
| \[ 71341001               | Bone structure of femur                                                                                                                    |
| \[ 116676008              | Associated morphology                                                                                                                      |
| \[ 20946005               | Fracture, closed                                                                                                                           |
| \[ 439987009              | Open fracture of bone                                                                                                                      |
| < \[ 404684003            | Clinical finding                                                                                                                           |
| \[ 47429007               | Associated with                                                                                                                            |
| \[ 116676008              | Associated morphology                                                                                                                      |
| \[ 47429007               | Associated with                                                                                                                            |
| \[ 57054005               | Acute myocardial infarction                                                                                                                |

***

| Footnotes Ref                                                                                                                  | Notes                                                                                                     |
| ------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------- |
| [1](https://confluence.ihtsdotools.org/display/DOCECL/A.6+Nested+Expression+Constraints+-+Valid+Expressions#FootnoteMarker1-0) | Where necessary, these examples make some assumptions about the membership of the example reference sets. |
