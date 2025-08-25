# Syntax Specification

The following sections describe two syntaxes for use with the SNOMED CT Expression Constraint Language. These syntaxes are serialised representations of the logical model presented in the previous chapter, and are therefore logically equivalent.

The first of these syntaxes is referred to as the 'brief syntax' as it primarily uses a symbolic representation aimed to be as compact as possible. This syntax is considered to be the normative syntax, and is recommended for use in interoperable communications between systems.

The second syntax is referred to as the 'long syntax'. The long syntax introduces English-based textual alternatives to the symbols defined in the 'brief syntax', with the aim of increasing the human readability of the language. The textual alternatives provided in the 'long syntax' may (in theory) be translated into other languages to provide equivalent expression constraint representations that are human-readable by non-English speakers. Please note that the 'long syntax' (and any translations) is non-normative, and should only be used when a reliable mapping to the normative brief syntax is possible.

Please note that by default each expression constraint is evaluated against only the active components (and active members of each reference set) from the snapshot release (in distribution normal form) of a specified SNOMED CT versioned edition.

## Brief Syntax

The following ABNF definition specifies the Brief Syntax of the SNOMED CT Expression Constraint Language.\
This ABNF syntax and the ANTLR syntax is maintained in the [SNOMED Expression Constraint Language GitHub](https://github.com/IHTSDO/snomed-expression-constraint-language) repository.

{% code title="ECL 2.1 Brief Syntax" overflow="wrap" lineNumbers="true" %}
```abnf
expressionConstraint = ws ( refinedExpressionConstraint / compoundExpressionConstraint / dottedExpressionConstraint / subExpressionConstraint ) ws
refinedExpressionConstraint = subExpressionConstraint ws ":" ws eclRefinement
compoundExpressionConstraint = conjunctionExpressionConstraint / disjunctionExpressionConstraint / exclusionExpressionConstraint
conjunctionExpressionConstraint = subExpressionConstraint 1*(ws conjunction ws subExpressionConstraint)
disjunctionExpressionConstraint = subExpressionConstraint 1*(ws disjunction ws subExpressionConstraint)
exclusionExpressionConstraint = subExpressionConstraint ws exclusion ws subExpressionConstraint
dottedExpressionConstraint = subExpressionConstraint 1*(ws dottedExpressionAttribute)
dottedExpressionAttribute = dot ws eclAttributeName
subExpressionConstraint= [constraintOperator ws] ( ( [memberOf ws] (eclFocusConcept / "(" ws expressionConstraint ws ")") *(ws memberFilterConstraint)) / (eclFocusConcept / "(" ws expressionConstraint ws ")") ) *(ws (descriptionFilterConstraint / conceptFilterConstraint)) [ws historySupplement]
eclFocusConcept = eclConceptReference / wildCard / altIdentifier
dot = "."
memberOf = "^" [ ws "[" ws (refsetFieldNameSet / wildCard) ws "]" ]
refsetFieldNameSet = refsetFieldName *(ws "," ws refsetFieldName)
refsetFieldName = 1*alpha
eclConceptReference = conceptId [ws "|" ws term ws "|"]
eclConceptReferenceSet = "(" ws eclConceptReference 1*(mws eclConceptReference) ws ")"
conceptId = sctId
term = 1*nonwsNonPipe *( 1*SP 1*nonwsNonPipe )
altIdentifier = (QM altIdentifierSchemeAlias "#" altIdentifierCodeWithinQuotes QM / altIdentifierSchemeAlias "#" altIdentifierCodeWithoutQuotes) [ws "|" ws term ws "|"]
altIdentifierSchemeAlias = alpha *(dash / alpha / integerValue)
altIdentifierCodeWithinQuotes = 1*anyNonEscapedChar
altIdentifierCodeWithoutQuotes = 1*(alpha / digit / dash / "." / "_")
wildCard = "*"
constraintOperator = childOf / childOrSelfOf / descendantOrSelfOf / descendantOf / parentOf / parentOrSelfOf / ancestorOrSelfOf / ancestorOf / top / bottom
descendantOf = "<"
descendantOrSelfOf = "<<"
childOf = "<!"
childOrSelfOf = "<<!"
ancestorOf = ">"
ancestorOrSelfOf = ">>"
parentOf = ">!"
parentOrSelfOf = ">>!"
top = "!!>"
bottom = "!!<"
conjunction = (("a"/"A") ("n"/"N") ("d"/"D") mws) / ","
disjunction = ("o"/"O") ("r"/"R") mws
exclusion = ("m"/"M") ("i"/"I") ("n"/"N") ("u"/"U") ("s"/"S") mws
eclRefinement = subRefinement ws [conjunctionRefinementSet / disjunctionRefinementSet]
conjunctionRefinementSet = 1*(ws conjunction ws subRefinement)
disjunctionRefinementSet = 1*(ws disjunction ws subRefinement)
subRefinement = eclAttributeSet / eclAttributeGroup / "(" ws eclRefinement ws ")"
eclAttributeSet = subAttributeSet ws [conjunctionAttributeSet / disjunctionAttributeSet]
conjunctionAttributeSet = 1*(ws conjunction ws subAttributeSet)
disjunctionAttributeSet = 1*(ws disjunction ws subAttributeSet)
subAttributeSet = eclAttribute / "(" ws eclAttributeSet ws ")"
eclAttributeGroup = ["[" cardinality "]" ws] "{" ws eclAttributeSet ws "}"
eclAttribute = ["[" cardinality "]" ws] [reverseFlag ws] eclAttributeName ws (expressionComparisonOperator ws subExpressionConstraint / numericComparisonOperator ws "#" numericValue / stringComparisonOperator ws (typedSearchTerm / typedSearchTermSet) / booleanComparisonOperator ws booleanValue)
cardinality = minValue to maxValue
minValue = nonNegativeIntegerValue
to = ".."
maxValue = nonNegativeIntegerValue / many
many = "*"
reverseFlag = "R"
eclAttributeName = subExpressionConstraint
expressionComparisonOperator = "=" / "!="
numericComparisonOperator = "=" / "!=" / "<=" / "<" / ">=" / ">"
timeComparisonOperator = "=" / "!=" / "<=" / "<" / ">=" / ">"
stringComparisonOperator = "=" / "!="
booleanComparisonOperator = "=" / "!="
idComparisonOperator = "=" / "!="
descriptionFilterConstraint = "{{" ws [ "d" / "D" ] ws descriptionFilter *(ws "," ws descriptionFilter) ws "}}"
descriptionFilter = termFilter / languageFilter / typeFilter / dialectFilter / moduleFilter / effectiveTimeFilter / activeFilter / descriptionIdFilter
descriptionIdFilter = descriptionIdKeyword ws idComparisonOperator ws (descriptionId / descriptionIdSet)
descriptionIdKeyword = ("i"/"I") ("d"/"D")
descriptionId = sctId
descriptionIdSet = "(" ws descriptionId *(mws descriptionId) ws ")"
termFilter = termKeyword ws stringComparisonOperator ws (typedSearchTerm / typedSearchTermSet)
termKeyword = ("t"/"T") ("e"/"E") ("r"/"R") ("m"/"M")
typedSearchTerm = ( [ matchKeyword ws ":" ws ] matchSearchTermSet ) / ( wild ws ":" ws wildSearchTermSet )
typedSearchTermSet = "(" ws typedSearchTerm *(mws typedSearchTerm) ws ")"
wild = ("w"/"W") ("i"/"I") ("l"/"L") ("d"/"D")
matchKeyword = ("m"/"M") ("a"/"A") ("t"/"T") ("c"/"C") ("h"/"H")
matchSearchTerm = 1*(nonwsNonEscapedChar / escapedChar)
matchSearchTermSet = QM ws matchSearchTerm *(mws matchSearchTerm) ws QM
wildSearchTerm = 1*(anyNonEscapedChar / escapedWildChar)
wildSearchTermSet = QM wildSearchTerm QM
languageFilter = language ws booleanComparisonOperator ws (languageCode / languageCodeSet)
language = ("l"/"L") ("a"/"A") ("n"/"N") ("g"/"G") ("u"/"U") ("a"/"A") ("g"/"G") ("e"/"E")
languageCode = 2alpha
languageCodeSet = "(" ws languageCode *(mws languageCode) ws ")"
typeFilter = typeIdFilter / typeTokenFilter
typeIdFilter = typeId ws booleanComparisonOperator ws (subExpressionConstraint / eclConceptReferenceSet)
typeId = ("t"/"T") ("y"/"Y") ("p"/"P") ("e"/"E") ("i"/"I") ("d"/"D")
typeTokenFilter = type ws booleanComparisonOperator ws (typeToken / typeTokenSet)
type = ("t"/"T") ("y"/"Y") ("p"/"P") ("e"/"E")
typeToken = synonym / fullySpecifiedName / definition
typeTokenSet = "(" ws typeToken *(mws typeToken) ws ")"
synonym = ("s"/"S") ("y"/"Y") ("n"/"N")
fullySpecifiedName = ("f"/"F") ("s"/"S") ("n"/"N")
definition = ("d"/"D") ("e"/"E") ("f"/"F")
dialectFilter = (dialectIdFilter / dialectAliasFilter) [ ws acceptabilitySet ]
dialectIdFilter = dialectId ws booleanComparisonOperator ws (subExpressionConstraint / dialectIdSet)
dialectId = ("d"/"D") ("i"/"I") ("a"/"A") ("l"/"L") ("e"/"E") ("c"/"C") ("t"/"T") ("i"/"I") ("d"/"D")
dialectAliasFilter = dialect ws booleanComparisonOperator ws (dialectAlias / dialectAliasSet)
dialect = ("d"/"D") ("i"/"I") ("a"/"A") ("l"/"L") ("e"/"E") ("c"/"C") ("t"/"T")
dialectAlias = alpha *( dash / alpha / integerValue)
dialectAliasSet = "(" ws dialectAlias [ws acceptabilitySet] *(mws dialectAlias [ws acceptabilitySet] ) ws ")"
dialectIdSet = "(" ws eclConceptReference [ws acceptabilitySet] *(mws eclConceptReference [ws acceptabilitySet] ) ws ")"
acceptabilitySet = acceptabilityConceptReferenceSet / acceptabilityTokenSet
acceptabilityConceptReferenceSet = "(" ws eclConceptReference *(mws eclConceptReference) ws ")"
acceptabilityTokenSet = "(" ws acceptabilityToken *(mws acceptabilityToken) ws ")"
acceptabilityToken = acceptable / preferred
acceptable = ("a"/"A") ("c"/"C") ("c"/"C") ("e"/"E") ("p"/"P") ("t"/"T")
preferred = ("p"/"P") ("r"/"R") ("e"/"E") ("f"/"F") ("e"/"E") ("r"/"R")
conceptFilterConstraint = "{{" ws ("c" / "C") ws conceptFilter *(ws "," ws conceptFilter) ws "}}"
conceptFilter = definitionStatusFilter / moduleFilter / effectiveTimeFilter / activeFilter
definitionStatusFilter = definitionStatusIdFilter / definitionStatusTokenFilter
definitionStatusIdFilter = definitionStatusIdKeyword ws booleanComparisonOperator ws (subExpressionConstraint / eclConceptReferenceSet)
definitionStatusIdKeyword = ("d"/"D") ("e"/"E") ("f"/"F") ("i"/"I") ("n"/"N") ("i"/"I") ("t"/"T") ("i"/"I") ("o"/"O") ("n"/"N") ("s"/"S") ("t"/"T") ("a"/"A") ("t"/"T") ("u"/"U") ("s"/"S") ("i"/"I") ("d"/"D")
definitionStatusTokenFilter = definitionStatusKeyword ws booleanComparisonOperator ws (definitionStatusToken / definitionStatusTokenSet)
definitionStatusKeyword = ("d"/"D") ("e"/"E") ("f"/"F") ("i"/"I") ("n"/"N") ("i"/"I") ("t"/"T") ("i"/"I") ("o"/"O") ("n"/"N") ("s"/"S") ("t"/"T") ("a"/"A") ("t"/"T") ("u"/"U") ("s"/"S")
definitionStatusToken = primitiveToken / definedToken
definitionStatusTokenSet = "(" ws definitionStatusToken *(mws definitionStatusToken) ws ")"
primitiveToken = ("p"/"P") ("r"/"R") ("i"/"I") ("m"/"M") ("i"/"I") ("t"/"T") ("i"/"I") ("v"/"V") ("e"/"E")
definedToken = ("d"/"D") ("e"/"E") ("f"/"F") ("i"/"I") ("n"/"N") ("e"/"E") ("d"/"D")
moduleFilter = moduleIdKeyword ws booleanComparisonOperator ws (subExpressionConstraint / eclConceptReferenceSet)
moduleIdKeyword = ("m"/"M") ("o"/"O") ("d"/"D") ("u"/"U") ("l"/"L") ("e"/"E") ("i"/"I") ("d"/"D")
effectiveTimeFilter = effectiveTimeKeyword ws timeComparisonOperator ws ( timeValue / timeValueSet )
effectiveTimeKeyword = ("e"/"E") ("f"/"F") ("f"/"F") ("e"/"E") ("c"/"C") ("t"/"T") ("i"/"I") ("v"/"V") ("e"/"E") ("t"/"T") ("i"/"I") ("m"/"M") ("e"/"E")
timeValue = QM [ year month day ] QM
timeValueSet = "(" ws timeValue *(mws timeValue) ws ")"
year = digitNonZero digit digit digit
month = "01" / "02" / "03" / "04" / "05" / "06" / "07" / "08" / "09" / "10" / "11" / "12"
day = "01" / "02" / "03" / "04" / "05" / "06" / "07" / "08" / "09" / "10" / "11" / "12" / "13" / "14" / "15" / "16" / "17" / "18" / "19" / "20" / "21" / "22" / "23" / "24" / "25" / "26" / "27" / "28" / "29" / "30" / "31"
activeFilter = activeKeyword ws booleanComparisonOperator ws activeValue
activeKeyword = ("a"/"A") ("c"/"C") ("t"/"T") ("i"/"I") ("v"/"V") ("e"/"E")
activeValue = activeTrueValue / activeFalseValue
activeTrueValue = "1" / "true"
activeFalseValue = "0" / "false"
memberFilterConstraint = "{{" ws ("m" / "M") ws memberFilter *(ws "," ws memberFilter) ws "}}"
memberFilter = moduleFilter / effectiveTimeFilter / activeFilter / memberFieldFilter
memberFieldFilter = refsetFieldName ws (expressionComparisonOperator ws subExpressionConstraint / numericComparisonOperator ws "#" numericValue / stringComparisonOperator ws (typedSearchTerm / typedSearchTermSet) / booleanComparisonOperator ws booleanValue / ws timeComparisonOperator ws (timeValue / timeValueSet) )
historySupplement = "{{" ws "+" ws historyKeyword [ historyProfileSuffix / ws historySubset ] ws "}}"
historyKeyword = ("h"/"H") ("i"/"I") ("s"/"S") ("t"/"T") ("o"/"O") ("r"/"R") ("y"/"Y")
historyProfileSuffix = historyMinimumSuffix / historyModerateSuffix / historyMaximumSuffix
historyMinimumSuffix = ("-"/"_") ("m"/"M") ("i"/"I") ("n"/"N")
historyModerateSuffix = ("-"/"_") ("m"/"M") ("o"/"O") ("d"/"D")
historyMaximumSuffix = ("-"/"_") ("m"/"M") ("a"/"A") ("x"/"X")
historySubset = "(" ws expressionConstraint ws ")"
numericValue = ["-"/"+"] (decimalValue / integerValue)
stringValue = 1*(anyNonEscapedChar / escapedChar)
integerValue = digitNonZero *digit / zero
decimalValue = integerValue "." 1*digit
booleanValue = true / false
true = ("t"/"T") ("r"/"R") ("u"/"U") ("e"/"E")
false = ("f"/"F") ("a"/"A") ("l"/"L") ("s"/"S") ("e"/"E")
nonNegativeIntegerValue = (digitNonZero *digit ) / zero
sctId = digitNonZero 5*17( digit )
ws = *( SP / HTAB / CR / LF / comment ) ; optional white space
mws = 1*( SP / HTAB / CR / LF / comment ) ; mandatory white space
comment = "/*" *(nonStarChar / starWithNonFSlash) "*/"
nonStarChar = SP / HTAB / CR / LF / %x21-29 / %x2B-7E /UTF8-2 / UTF8-3 / UTF8-4
starWithNonFSlash = %x2A nonFSlash
nonFSlash = SP / HTAB / CR / LF / %x21-2E / %x30-7E /UTF8-2 / UTF8-3 / UTF8-4
SP = %x20 ; space
HTAB = %x09 ; tab
CR = %x0D ; carriage return
LF = %x0A ; line feed
QM = %x22 ; quotation mark
BS = %x5C ; back slash
star = %x2A ; asterisk
digit = %x30-39
zero = %x30
digitNonZero = %x31-39
nonwsNonPipe = %x21-7B / %x7D-7E / UTF8-2 / UTF8-3 / UTF8-4
anyNonEscapedChar = SP / HTAB / CR / LF / %x20-21 / %x23-5B / %x5D-7E / UTF8-2 / UTF8-3 / UTF8-4
escapedChar = BS QM / BS BS
escapedWildChar = BS QM / BS BS / BS star
nonwsNonEscapedChar = %x21 / %x23-5B / %x5D-7E / UTF8-2 / UTF8-3 / UTF8-4
alpha = %x41-5A / %x61-7A
dash = %x2D
UTF8-2 = %xC2-DF UTF8-tail
UTF8-3 = %xE0 %xA0-BF UTF8-tail / %xE1-EC 2( UTF8-tail ) / %xED %x80-9F UTF8-tail / %xEE-EF 2( UTF8-tail )
UTF8-4 = %xF0 %x90-BF 2( UTF8-tail ) / %xF1-F3 3( UTF8-tail ) / %xF4 %x80-8F 2( UTF8-tail )
UTF8-tail = %x80-BF
```
{% endcode %}

## Long Syntax

The following ABNF definition specifies the Long Syntax the [SNOMED CT Expression Constraint Language](http://snomed.org/ecl). Please note that all keywords are case insensitive.\
This ABNF syntax and the ANTLR syntax is maintained in the [SNOMED Expression Constraint Language GitHub](https://github.com/IHTSDO/snomed-expression-constraint-language) repository.

{% code title="ECL 2.1 - Long Syntax" overflow="wrap" lineNumbers="true" %}
```abnf
expressionConstraint = ws ( refinedExpressionConstraint / compoundExpressionConstraint / dottedExpressionConstraint / subExpressionConstraint ) ws
refinedExpressionConstraint = subExpressionConstraint ws ":" ws eclRefinement
compoundExpressionConstraint = conjunctionExpressionConstraint / disjunctionExpressionConstraint / exclusionExpressionConstraint
conjunctionExpressionConstraint = subExpressionConstraint 1*(ws conjunction ws subExpressionConstraint)
disjunctionExpressionConstraint = subExpressionConstraint 1*(ws disjunction ws subExpressionConstraint)
exclusionExpressionConstraint = subExpressionConstraint ws exclusion ws subExpressionConstraint
dottedExpressionConstraint = subExpressionConstraint 1*(ws dottedExpressionAttribute)
dottedExpressionAttribute = dot ws eclAttributeName
subExpressionConstraint= [constraintOperator ws] ( ( [memberOf ws] (eclFocusConcept / "(" ws expressionConstraint ws ")") *(ws memberFilterConstraint)) / (eclFocusConcept / "(" ws expressionConstraint ws ")") ) *(ws (descriptionFilterConstraint / conceptFilterConstraint)) [ws historySupplement]
eclFocusConcept = eclConceptReference / wildCard / altIdentifier
dot = "."
memberOf = ( "^" / ("m"/"M") ("e"/"E") ("m"/"M") ("b"/"B") ("e"/"E") ("r"/"R") ("o"/"O") ("f"/"F") ) [ ws "[" ws (refsetFieldNameSet / wildCard) ws "]" ]
refsetFieldNameSet = refsetFieldName *( ws "," ws refsetFieldName )
refsetFieldName = 1*alpha
eclConceptReference = conceptId [ws "|" ws term ws "|"]
eclConceptReferenceSet = "(" ws eclConceptReference 1*(mws eclConceptReference) ws ")"
conceptId = sctId
term = 1*nonwsNonPipe *( 1*SP 1*nonwsNonPipe )
altIdentifier = (QM altIdentifierSchemeAlias "#" altIdentifierCodeWithinQuotes QM / altIdentifierSchemeAlias "#" altIdentifierCodeWithoutQuotes) [ws "|" ws term ws "|"]
altIdentifierSchemeAlias = alpha *(dash / alpha / integerValue)
altIdentifierCodeWithinQuotes = 1*anyNonEscapedChar
altIdentifierCodeWithoutQuotes = 1*(alpha / digit / dash / "." / "_")
wildCard = "*" / ( ("a"/"A") ("n"/"N") ("y"/"Y") )
constraintOperator = childOf / childOrSelfOf / descendantOrSelfOf / descendantOf / parentOf / parentOrSelfOf / ancestorOrSelfOf / ancestorOf / top / bottom
descendantOf = "<" / ( ("d"/"D") ("e"/"E") ("s"/"S") ("c"/"C") ("e"/"E") ("n"/"N") ("d"/"D") ("a"/"A") ("n"/"N") ("t"/"T") ("o"/"O") ("f"/"F") mws )
descendantOrSelfOf = "<<" / ( ("d"/"D") ("e"/"E") ("s"/"S") ("c"/"C") ("e"/"E") ("n"/"N") ("d"/"D") ("a"/"A") ("n"/"N") ("t"/"T") ("o"/"O") ("r"/"R") ("s"/"S") ("e"/"E") ("l"/"L") ("f"/"F") ("o"/"O") ("f"/"F") mws )
childOf = "<!" / (("c"/"C") ("h"/"H") ("i"/"I") ("l"/"L") ("d"/"D") ("o"/"O") ("f"/"F") mws )
childOrSelfOf = "<<!" / (("c"/"C") ("h"/"H") ("i"/"I") ("l"/"L") ("d"/"D") ("o"/"O") ("r"/"R") ("s"/"S") ("e"/"E") ("l"/"L") ("f"/"F") ("o"/"O") ("f"/"F") mws )
ancestorOf = ">" / ( ("a"/"A") ("n"/"N") ("c"/"C") ("e"/"E") ("s"/"S") ("t"/"T") ("o"/"O") ("r"/"R") ("o"/"O") ("f"/"F") mws )
ancestorOrSelfOf = ">>" / ( ("a"/"A") ("n"/"N") ("c"/"C") ("e"/"E") ("s"/"S") ("t"/"T") ("o"/"O") ("r"/"R") ("o"/"O") ("r"/"R") ("s"/"S") ("e"/"E") ("l"/"L") ("f"/"F") ("o"/"O") ("f"/"F") mws )
parentOf = ">!" / (("p"/"P") ("a"/"A") ("r"/"R") ("e"/"E") ("n"/"N") ("t"/"T") ("o"/"O") ("f"/"F") mws )
parentOrSelfOf = ">>!" / (("p"/"P") ("a"/"A") ("r"/"R") ("e"/"E") ("n"/"N") ("t"/"T") ("o"/"O") ("r"/"R") ("s"/"S") ("e"/"E") ("l"/"L") ("f"/"F") ("o"/"O") ("f"/"F") mws )
top = "!!>" / (("t"/"T") ("o"/"O") ("p"/"P") mws )
bottom = "!!<" / (("b"/"B") ("o"/"O") ("t"/"T") ("t"/"T") ("o"/"O") ("m"/"M") mws )
conjunction = (("a"/"A") ("n"/"N") ("d"/"D") mws) / ","
disjunction = ("o"/"O") ("r"/"R") mws
exclusion = ("m"/"M") ("i"/"I") ("n"/"N") ("u"/"U") ("s"/"S") mws
eclRefinement = subRefinement ws [conjunctionRefinementSet / disjunctionRefinementSet]
conjunctionRefinementSet = 1*(ws conjunction ws subRefinement)
disjunctionRefinementSet = 1*(ws disjunction ws subRefinement)
subRefinement = eclAttributeSet / eclAttributeGroup / "(" ws eclRefinement ws ")"
eclAttributeSet = subAttributeSet ws [conjunctionAttributeSet / disjunctionAttributeSet]
conjunctionAttributeSet = 1*(ws conjunction ws subAttributeSet)
disjunctionAttributeSet = 1*(ws disjunction ws subAttributeSet)
subAttributeSet = eclAttribute / "(" ws eclAttributeSet ws ")"
eclAttributeGroup = ["[" cardinality "]" ws] "{" ws eclAttributeSet ws "}"
eclAttribute = ["[" cardinality "]" ws] [reverseFlag ws] eclAttributeName ws (expressionComparisonOperator ws subExpressionConstraint / numericComparisonOperator ws "#" numericValue / stringComparisonOperator ws (typedSearchTerm / typedSearchTermSet) / booleanComparisonOperator ws booleanValue)
cardinality = minValue to maxValue
minValue = nonNegativeIntegerValue
to = ".." / (mws ("t"/"T") ("o"/"O") mws)
maxValue = nonNegativeIntegerValue / many
many = "*" / ( ("m"/"M") ("a"/"A") ("n"/"N") ("y"/"Y"))
reverseFlag = ( ("r"/"R") ("e"/"E") ("v"/"V") ("e"/"E") ("r"/"R") ("s"/"S") ("e"/"E") ("o"/"O") ("f"/"F")) / "R"
eclAttributeName = subExpressionConstraint
expressionComparisonOperator = "=" / "!=" / ("n"/"N") ("o"/"O") ("t"/"T") ws "=" / "<>"
numericComparisonOperator = "=" / "!=" / ("n"/"N") ("o"/"O") ("t"/"T") ws "=" / "<>" / "<=" / "<" / ">=" / ">"
timeComparisonOperator = "=" / "!=" / ("n"/"N") ("o"/"O") ("t"/"T") ws "=" / "<>" / "<=" / "<" / ">=" / ">"
stringComparisonOperator = "=" / "!=" / ("n"/"N") ("o"/"O") ("t"/"T") ws "=" / "<>"
booleanComparisonOperator = "=" / "!=" / ("n"/"N") ("o"/"O") ("t"/"T") ws "=" / "<>"
idComparisonOperator = "=" / "!=" / ("n"/"N") ("o"/"O") ("t"/"T") ws "=" / "<>"
descriptionFilterConstraint = "{{" ws [ "d" / "D" ] ws descriptionFilter *(ws "," ws descriptionFilter) ws "}}"
descriptionFilter = termFilter / languageFilter / typeFilter / dialectFilter / moduleFilter / effectiveTimeFilter / activeFilter / descriptionIdFilter
descriptionIdFilter = descriptionIdKeyword ws idComparisonOperator ws (descriptionId / descriptionIdSet)
descriptionIdKeyword = ("i"/"I") ("d"/"D")
descriptionId = sctId
descriptionIdSet = "(" ws descriptionId *(mws descriptionId) ws ")"
termFilter = termKeyword ws stringComparisonOperator ws (typedSearchTerm / typedSearchTermSet)
termKeyword = ("t"/"T") ("e"/"E") ("r"/"R") ("m"/"M")
typedSearchTerm = ( [ matchKeyword ws ":" ws ] matchSearchTermSet ) / ( wild ws ":" ws wildSearchTermSet )
typedSearchTermSet = "(" ws typedSearchTerm *(mws typedSearchTerm) ws ")"
wild = ("w"/"W") ("i"/"I") ("l"/"L") ("d"/"D")
matchKeyword = ("m"/"M") ("a"/"A") ("t"/"T") ("c"/"C") ("h"/"H")
matchSearchTerm = 1*(nonwsNonEscapedChar / escapedChar)
matchSearchTermSet = QM ws matchSearchTerm *(mws matchSearchTerm) ws QM
wildSearchTerm = 1*(anyNonEscapedChar / escapedWildChar)
wildSearchTermSet = QM wildSearchTerm QM
languageFilter = language ws booleanComparisonOperator ws (languageCode / languageCodeSet)
language = ("l"/"L") ("a"/"A") ("n"/"N") ("g"/"G") ("u"/"U") ("a"/"A") ("g"/"G") ("e"/"E")
languageCode = 2alpha
languageCodeSet = "(" ws languageCode *(mws languageCode) ws ")"
typeFilter = typeIdFilter / typeTokenFilter
typeIdFilter = typeId ws booleanComparisonOperator ws (subExpressionConstraint / eclConceptReferenceSet)
typeId = ("t"/"T") ("y"/"Y") ("p"/"P") ("e"/"E") ("i"/"I") ("d"/"D")
typeTokenFilter = type ws booleanComparisonOperator ws (typeToken / typeTokenSet)
type = ("t"/"T") ("y"/"Y") ("p"/"P") ("e"/"E")
typeToken = synonym / fullySpecifiedName / definition
typeTokenSet = "(" ws typeToken *(mws typeToken) ws ")"
synonym = ("s"/"S") ("y"/"Y") ("n"/"N") [ ("o"/"O") ("n"/"N") ("y"/"Y") ("m"/"M") ]
fullySpecifiedName = ( ("f"/"F") ("s"/"S") ("n"/"N") ) / ( ("f"/"F") ("u"/"U") ("l"/"L") ("l"/"L") ("y"/"Y") ("s"/"S") ("p"/"P") ("e"/"E") ("c"/"C") ("i"/"I") ("f"/"F") ("i"/"I") ("e"/"E") ("d"/"D") ("n"/"N") ("a"/"A") ("m"/"M") ("e"/"E") )
definition = ("d"/"D") ("e"/"E") ("f"/"F") [ ("i"/"I") ("n"/"N") ("i"/"I") ("t"/"T") ("i"/"I") ("o"/"O") ("n"/"N") ]
dialectFilter = (dialectIdFilter / dialectAliasFilter) [ ws acceptabilitySet ]
dialectIdFilter = dialectId ws booleanComparisonOperator ws (subExpressionConstraint / dialectIdSet)
dialectId = ("d"/"D") ("i"/"I") ("a"/"A") ("l"/"L") ("e"/"E") ("c"/"C") ("t"/"T") ("i"/"I") ("d"/"D")
dialectAliasFilter = dialect ws booleanComparisonOperator ws (dialectAlias / dialectAliasSet)
dialect = ("d"/"D") ("i"/"I") ("a"/"A") ("l"/"L") ("e"/"E") ("c"/"C") ("t"/"T")
dialectAlias = alpha *( dash / alpha / integerValue)
dialectAliasSet = "(" ws dialectAlias [ws acceptabilitySet] *(mws dialectAlias [ws acceptabilitySet]) ws ")"
dialectIdSet = "(" ws eclConceptReference [ws acceptabilitySet] *(mws eclConceptReference [ws acceptabilitySet] ) ws ")"
acceptabilitySet = acceptabilityConceptReferenceSet / acceptabilityTokenSet
acceptabilityConceptReferenceSet = "(" ws eclConceptReference *(mws eclConceptReference) ws ")"
acceptabilityTokenSet = "(" ws acceptabilityToken *(mws acceptabilityToken) ws ")"
acceptabilityToken = acceptable / preferred
acceptable = ("a"/"A") ("c"/"C") ("c"/"C") ("e"/"E") ("p"/"P") ("t"/"T") [ ("a"/"A") ("b"/"B") ("l"/"L") ("e"/"E") ]
preferred = ("p"/"P") ("r"/"R") ("e"/"E") ("f"/"F") ("e"/"E") ("r"/"R") [ ("r"/"R") ("e"/"E") ("d"/"D") ]
conceptFilterConstraint = "{{" ws ("c" / "C") ws conceptFilter *(ws "," ws conceptFilter) ws "}}"
conceptFilter = definitionStatusFilter / moduleFilter / effectiveTimeFilter / activeFilter
definitionStatusFilter = definitionStatusIdFilter / definitionStatusTokenFilter
definitionStatusIdFilter = definitionStatusIdKeyword ws booleanComparisonOperator ws (subExpressionConstraint / eclConceptReferenceSet)
definitionStatusIdKeyword = ("d"/"D") ("e"/"E") ("f"/"F") ("i"/"I") ("n"/"N") ("i"/"I") ("t"/"T") ("i"/"I") ("o"/"O") ("n"/"N") ("s"/"S") ("t"/"T") ("a"/"A") ("t"/"T") ("u"/"U") ("s"/"S") ("i"/"I") ("d"/"D")
definitionStatusTokenFilter = definitionStatusKeyword ws booleanComparisonOperator ws (definitionStatusToken / definitionStatusTokenSet)
definitionStatusKeyword = ("d"/"D") ("e"/"E") ("f"/"F") ("i"/"I") ("n"/"N") ("i"/"I") ("t"/"T") ("i"/"I") ("o"/"O") ("n"/"N") ("s"/"S") ("t"/"T") ("a"/"A") ("t"/"T") ("u"/"U") ("s"/"S")
definitionStatusToken = primitiveToken / definedToken
definitionStatusTokenSet = "(" ws definitionStatusToken *(mws definitionStatusToken) ws ")"
primitiveToken = ("p"/"P") ("r"/"R") ("i"/"I") ("m"/"M") ("i"/"I") ("t"/"T") ("i"/"I") ("v"/"V") ("e"/"E")
definedToken = ("d"/"D") ("e"/"E") ("f"/"F") ("i"/"I") ("n"/"N") ("e"/"E") ("d"/"D")
moduleFilter = moduleIdKeyword ws booleanComparisonOperator ws (subExpressionConstraint / eclConceptReferenceSet)
moduleIdKeyword = ("m"/"M") ("o"/"O") ("d"/"D") ("u"/"U") ("l"/"L") ("e"/"E") ("i"/"I") ("d"/"D")
effectiveTimeFilter = effectiveTimeKeyword ws timeComparisonOperator ws ( timeValue / timeValueSet )
effectiveTimeKeyword = ("e"/"E") ("f"/"F") ("f"/"F") ("e"/"E") ("c"/"C") ("t"/"T") ("i"/"I") ("v"/"V") ("e"/"E") ("t"/"T") ("i"/"I") ("m"/"M") ("e"/"E")
timeValue = QM [ year month day ] QM
timeValueSet = "(" ws timeValue *(mws timeValue) ws ")"
year = digitNonZero digit digit digit
month = "01" / "02" / "03" / "04" / "05" / "06" / "07" / "08" / "09" / "10" / "11" / "12"
day = "01" / "02" / "03" / "04" / "05" / "06" / "07" / "08" / "09" / "10" / "11" / "12" / "13" / "14" / "15" / "16" / "17" / "18" / "19" / "20" / "21" / "22" / "23" / "24" / "25" / "26" / "27" / "28" / "29" / "30" / "31"
activeFilter = activeKeyword ws booleanComparisonOperator ws activeValue
activeKeyword = ("a"/"A") ("c"/"C") ("t"/"T") ("i"/"I") ("v"/"V") ("e"/"E")
activeValue = activeTrueValue / activeFalseValue
activeTrueValue = "1" / "true"
activeFalseValue = "0" / "false"
memberFilterConstraint = "{{" ws ("m" / "M") ws memberFilter *(ws "," ws memberFilter) ws "}}"
memberFilter = moduleFilter / effectiveTimeFilter / activeFilter / memberFieldFilter
memberFieldFilter = refsetFieldName ws (expressionComparisonOperator ws subExpressionConstraint / numericComparisonOperator ws "#" numericValue / stringComparisonOperator ws (typedSearchTerm / typedSearchTermSet) / booleanComparisonOperator ws booleanValue / ws timeComparisonOperator ws (timeValue / timeValueSet) )
historySupplement = "{{" ws "+" ws historyKeyword [ historyProfileSuffix / ws historySubset ] ws "}}"
historyKeyword = ("h"/"H") ("i"/"I") ("s"/"S") ("t"/"T") ("o"/"O") ("r"/"R") ("y"/"Y")
historyProfileSuffix = historyMinimumSuffix / historyModerateSuffix / historyMaximumSuffix
historyMinimumSuffix = ("-"/"_") ("m"/"M") ("i"/"I") ("n"/"N")
historyModerateSuffix = ("-"/"_") ("m"/"M") ("o"/"O") ("d"/"D")
historyMaximumSuffix = ("-"/"_") ("m"/"M") ("a"/"A") ("x"/"X")
historySubset = "(" ws expressionConstraint ws ")"
numericValue = ["-"/"+"] (decimalValue / integerValue)
stringValue = 1*(anyNonEscapedChar / escapedChar)
integerValue = digitNonZero *digit / zero
decimalValue = integerValue "." 1*digit
booleanValue = true / false
true = ("t"/"T") ("r"/"R") ("u"/"U") ("e"/"E")
false = ("f"/"F") ("a"/"A") ("l"/"L") ("s"/"S") ("e"/"E")
nonNegativeIntegerValue = (digitNonZero *digit ) / zero
sctId = digitNonZero 5*17( digit )
ws = *( SP / HTAB / CR / LF / comment ) ; optional white space
mws = 1*( SP / HTAB / CR / LF / comment ) ; mandatory white space
comment = "/*" *(nonStarChar / starWithNonFSlash) "*/"
nonStarChar = SP / HTAB / CR / LF / %x21-29 / %x2B-7E /UTF8-2 / UTF8-3 / UTF8-4
starWithNonFSlash = %x2A nonFSlash
nonFSlash = SP / HTAB / CR / LF / %x21-2E / %x30-7E /UTF8-2 / UTF8-3 / UTF8-4
SP = %x20 ; space
HTAB = %x09 ; tab
CR = %x0D ; carriage return
LF = %x0A ; line feed
QM = %x22 ; quotation mark
BS = %x5C ; back slash
star = %x2A ; asterisk
digit = %x30-39
zero = %x30
digitNonZero = %x31-39
nonwsNonPipe = %x21-7B / %x7D-7E / UTF8-2 / UTF8-3 / UTF8-4
anyNonEscapedChar = SP / HTAB / CR / LF / %x20-21 / %x23-5B / %x5D-7E / UTF8-2 / UTF8-3 / UTF8-4
escapedChar = BS QM / BS BS
escapedWildChar = BS QM / BS BS / BS star
nonwsNonEscapedChar = %x21 / %x23-5B / %x5D-7E / UTF8-2 / UTF8-3 / UTF8-4
alpha = %x41-5A / %x61-7A
dash = %x2D
UTF8-2 = %xC2-DF UTF8-tail
UTF8-3 = %xE0 %xA0-BF UTF8-tail / %xE1-EC 2( UTF8-tail ) / %xED %x80-9F UTF8-tail / %xEE-EF 2( UTF8-tail )
UTF8-4 = %xF0 %x90-BF 2( UTF8-tail ) / %xF1-F3 3( UTF8-tail ) / %xF4 %x80-8F 2( UTF8-tail )
UTF8-tail = %x80-BF
```
{% endcode %}

## Informative Comments

This section provides a short description of each ABNF rule listed above. The related brief and long syntax rules are grouped together with the same description.&#x20;

<pre class="language-abnf" data-title="Brief Syntax and Long Syntax with comments" data-overflow="wrap"><code class="lang-abnf">expressionConstraint = ws ( refinedExpressionConstraint / compoundExpressionConstraint / dottedExpressionConstraint / subExpressionConstraint ) ws
; An expression constraint is either a refined expression constraint, a compound expression constraint, a dotted expression constraint, or a sub expression constraint.

refinedExpressionConstraint = subExpressionConstraint ws ":" ws eclRefinement
; A refined expression constraint includes a subexpression constraint followed by a refinement.

compoundExpressionConstraint = conjunctionExpressionConstraint / disjunctionExpressionConstraint / exclusionExpressionConstraint
; A compound expression constraint contains two or more expression constraints joined by either a conjunction, disjunction or exclusion. When potential ambiguity in binary operator precedence may occur, round brackets must be used to clearly disambiguate the order in which these operator are applied. Brackets are not required in expression constraints in which all binary operators are conjunctions, or all binary operators are disjunctions. Please note that unary operators (i.e. constraint operators and member of functions) are always applied before binary operators (i.e. conjunction, disjunction and exclusion).

conjunctionExpressionConstraint = subExpressionConstraint 1(ws conjunction ws subExpressionConstraint)
; A conjunction expression constraint combines two or more expression constraints with a conjunction ("and") operator. More than one conjunction may be used without brackets. However any compound expression constraint (using a different binary operator) that appears within a conjunction expression constraint must be enclosed by brackets.

disjunctionExpressionConstraint = subExpressionConstraint 1(ws disjunction ws subExpressionConstraint)
; A disjunction expression constraint combines two or more expression constraints with a disjunction ("or") operator. More than one disjunction may be used without brackets. However any compound expression constraint (using a different binary operator) that appears within a disjunction expression constraint must be enclosed by brackets.

exclusionExpressionConstraint = subExpressionConstraint ws exclusion ws subExpressionConstraint
; An exclusion expression constraint combines two expression constrains with an exclusion ("minus") operator. A single exclusion operator may be used without brackets. However when the operands of the exclusion expression constraint are compound, these compound expression constraints must be enclosed by brackets.

dottedExpressionConstraint = subExpressionConstraint 1*(ws dottedExpressionAttribute)
; A dotted expression constraint contains a sub expression constraint, followed by one or more dotted attributes. When a single dotted attribute is used, the result is the set of attribute values (for the given attribute name) of each concept that results from evaluating the subExpressionConstraint. When more than one dotted attribute is used, each dottedExpressionAttribute is sequentially evaluated (from left to right) against the given result set.

dottedExpressionAttribute = dot ws eclAttributeName
; A dotted expression attribute consists of a 'dot', followed by an attribute name. Please note that the attribute name may be represented by any sub expression constraint.

subExpressionConstraint = [constraintOperator ws] ( ( [memberOf ws] (eclFocusConcept / "(" ws expressionConstraint ws ")") *(ws memberFilterConstraint)) / (eclFocusConcept / "(" ws expressionConstraint ws ")") ) *(ws (descriptionFilterConstraint / conceptFilterConstraint)) [ws historySupplement]
; A sub expression constraint optionally begins with a constraint operator and/or a memberOf function. It then includes either a single focus concept or an expression constraint (enclosed in brackets). If the memberOf function is applied, a member filter constraint may be used. A sub expression constraint may then optionally include one or more concept or description filter constraints, followed optionally by a history supplement.Notes: A memberOf function should be used only when the eclFocusConcept or expressionConstraint refers to a reference set concept, a set of reference set concepts, or a wild card. When both a constraintOperator and a memberOf function are used, they are applied from the inside to out (i.e. from right to left) - see section on the Order of Operation. Therefore, if a constraintOperator is followed by a memberOf function, then the memberOf function is processed prior to the constraintOperator.

eclFocusConcept = eclConceptReference / wildCard
; A focus concept is a concept reference or a wild card.

<strong>dot = "." ; Brief syntax only
</strong>; A dot connects an expression constraint with an attribute whose values are included in the result.

memberOf = "^" [ ws "[" ws (refsetFieldNameSet / wildCard) ws "]" ]**LS:**memberOf = ( "^" / ("m"/"M") ("e"/"E") ("m"/"M") ("b"/"B") ("e"/"E") ("r"/"R") ("o"/"O") ("f"/"F") ) [ ws "[" ws (refsetFieldNameSet / wildCard) ws "]" ]
; By default, the 'memberOf' function returns the set of referenced components in the set of reference sets which follows. In the brief syntax, the memberOf function is represented using the "^" symbol. In the long syntax, the text "memberOf " (case insensitive and followed by at least one white space) is also allowed. If a set of reference set fields is listed in square brackets after the memberOf function, then the values of these fields are returned.

refsetFieldNameSet = refsetFieldName *( ws "," ws refsetFieldName )
; A refsetFieldNameSet is a set of one or more reference set fields, separated by a comma and optional whitespace.

refsetFieldName = 1*alpha
; A refsetFieldName is the set of alphabetic characters used to name a reference set field.

eclConceptReference = conceptId [ws "|" ws term ws "|"]
; A conceptReference is represented by a ConceptId, optionally followed by a term enclosed by a pair of "|" characters. Whitespace before or after the ConceptId is ignored as is any whitespace between the initial "|" characters and the first non-whitespace character in the term or between the last non-whitespace character and before second "|" character.

eclConceptReferenceSet = "(" ws eclConceptReference 1*(mws eclConceptReference) ws ")"
; A concept reference set includes two or more concept references separated by mandatory white space and enclosed in brackets.

conceptId = sctId
; The ConceptId must be a valid SNOMED CT identifier for a concept. The initial digit may not be zero. The smallest number of digits is six, and the maximum is 18.

term = 1nonwsnonpipe ( 1SP 1nonwsnonpipe )
; The term must be the term from a SNOMED CT description that is associated with the concept identified by the preceding concept identifier. For example, the term could be the preferred description, or the preferred description associated with a particular translation. The term may include valid UTF-8 characters except for the pipe

wildCard = "" ; Brief syntax 
wildCard = "" / ( ("a"/"A") ("n"/"N") ("y"/"Y")) ; Long syntax
; A wild card represents any concept in the given substrate. In the brief syntax, a wildcard is represented using the "*" symbol. In the long syntax, the text "ANY" (case insensitive) is also allowed.

constraintOperator = childOf / childOrSelfOf / descendantOrSelfOf / descendantOf / parentOf / parentOrSelfOf / ancestorOrSelfOf / ancestorOf
; A constraint operator is either 'childOf', 'childOrSelfOf', 'descendantOrSelfOf', 'descendantOf', 'parentOf', 'parentOrSelfOf', 'ancestorOrSelfOf', or 'ancestorOf'.

descendantOf = "&#x3C;" ; Brief syntax
descendantOf = "&#x3C;" / ( ("d"/"D") ("e"/"E") ("s"/"S") ("c"/"C") ("e"/"E") ("n"/"N") ("d"/"D")("a"/"A") ("n"/"N") ("t"/"T") ("o"/"O")("f"/"F") mws ) ; Long syntax
; The descendantOf operator returns the set of all subtypes of the given concept (or set of concepts). In the brief syntax, the descendantOf operator is represented using the symbol "&#x3C;". In the long syntax, the text "descendantOf" (case insensitive and followed by at least one white space) is also allowed.

**BS:**descendantOrSelfOf = "&#x3C;&#x3C;" ; Brief syntax
**LS:**descendantOrSelfOf = "&#x3C;&#x3C;" / ( ("d"/"D") ("e"/"E") ("s"/"S") ("c"/"C") ("e"/"E") ("n"/"N") ("d"/"D") ("a"/"A") ("n"/"N") ("t"/"T") ("o"/"O")("r"/"R") ("s"/"S")("e"/"E") ("l"/"L") ("f"/"F") ("o"/"O")("f"/"F") mws ) ; Long syntax
; The descendantOrSelfOf operator returns the set of all subtypes of the given concept (or set of concepts), plus the concept (or set of concepts) itself. In the brief syntax, the descendantOrSelfOf operator is represented using the symbols "&#x3C;&#x3C;". In the long syntax, the text "descendantOrSelfOf" (case insensitive and followed by at least one white space) is also allowed.

childOf = "&#x3C;!" ; Brief syntax
childOf = "&#x3C;!" / (("c"/"C") ("h"/"H") ("i"/"I") ("l"/"L") ("d"/"D") ("o"/"O") ("f"/"F") mws ) ; Long syntax
; The childOf operator returns the set of all immediate children of the given concept (or set of concepts). In the brief syntax, the childOf operator is represented using the symbols "&#x3C;!". In the long syntax, the text "childOf" (case insensitive and followed by at least one white space) is also allowed.

childOrSelfOf = "&#x3C;&#x3C;!" ; Brief syntax
childOrSelfOf = "&#x3C;&#x3C;!" / (("c"/"C") ("h"/"H") ("i"/"I") ("l"/"L") ("d"/"D") ("o"/"O")("r"/"R") ("s"/"S")("e"/"E") ("l"/"L") ("f"/"F") ("o"/"O") ("f"/"F") mws ) ; Long syntax
; The childOrSelfOf operator returns the set of all immediate children of the given concept (or set of concepts), plus the concept (or set of concepts) itself. In the brief syntax, the childOrSelfOf operator is represented using the symbols "&#x3C;&#x3C;!". In the long syntax, the text "childOrSelfOf" (case insensitive and followed by at least one white space) is also allowed.

ancestorOf = ">" ; Brief syntax
ancestorOf = ">" / ( ("a"/"A") ("n"/"N") ("c"/"C") ("e"/"E") ("s"/"S") ("t"/"T") ("o"/"O") ("r"/"R") ("o"/"O")("f"/"F") mws ) ; Long syntax
; The ancestorOf operator returns the set of all supertypes of the given concept (or set of concepts). In the brief syntax, the ancestorOf operator is represented using the symbol ">". In the long syntax, the text "ancestorOf " (case insensitive and followed by at least one white space) is also allowed.

ancestorOrSelfOf = ">>" ; Brief syntax
ancestorOrSelfOf = ">>" / ( ("a"/"A") ("n"/"N") ("c"/"C") ("e"/"E") ("s"/"S") ("t"/"T") ("o"/"O") ("r"/"R") ("o"/"O") ("r"/"R") ("s"/"S") ("e"/"E") ("l"/"L" ("f"/"F") ("o"/"O")("f"/"F") mws ) ; Long syntax
; The ancestorOrSelfOf operator returns the set of all supertypes of the given concept (or set of concepts), plus the concept (or set of concepts) itself. In the brief syntax, the ancestorOrSelfOf operator is represented using the symbols ">>". In the long syntax, the text "ancestorOrSelfOf" (case insensitive and followed by at least one white space) is also allowed.

<strong>parentOf = ">!" ; Brief syntax
</strong><strong>parentOf = ">!" / (("p"/"P") ("a"/"A") ("r"/"R") ("e"/"E") ("n"/"N") ("t"/"T") ("o"/"O") ("f"/"F") mws ) ; Long syntax
</strong>; The parentOf operator returns the set of all immediate parents of the given concept (or set of concepts). In the brief syntax, the parentOf operator is represented using the symbols ">!". In the long syntax, the text "parentOf" (case insensitive and followed by at least one white space) is also allowed.

parentOrSelfOf = ">>!" ; Brief syntax
parentOrSelfOf = ">>!" / (("p"/"P") ("a"/"A") ("r"/"R") ("e"/"E") ("n"/"N") ("t"/"T") ("o"/"O") ("r"/"R") ("s"/"S") ("e"/"E") ("l"/"L" ("f"/"F") ("o"/"O") ("f"/"F") mws ) ; Long syntax
; The parentOrSelfOf operator returns the set of all immediate parents of the given concept (or set of concepts), plus the concept (or set of concepts) itself. In the brief syntax, the parentOrSelfOf operator is represented using the symbols ">>!". In the long syntax, the text "parentOrSelfOf" (case insensitive and followed by at least one white space) is also allowed.

conjunction = (("a"/"A") ("n"/"N") ("d"/"D") mws) / ","
; A conjunction is represented either by the word "and" (case insensitive and followed by at least one white space), or by a comma.

disjunction = ("o"/"O") ("r"/"R") mws
; A disjunction is represented by the word "or" (case insensitive and followed by at least one white space).

exclusion = ("m"/"M") ("i"/"I") ("n"/"N") ("u"/"U") ("s"/"S") mws
; The exclusion operator is represented by the word "minus" (case insensitive and followed by at least one white space).

eclRefinement = subRefinement ws [conjunctionRefinementSet / disjunctionRefinementSet]
; A refinement contains all the grouped and ungrouped attributes that refine the set of clinical meanings satisfied by the expression constraint. Refinements may represent the conjunction or disjunction of two smaller refinements, and may optionally be placed in brackets. Where both conjunction and disjunction are used, brackets are mandatory to disambiguate the intended meaning.

conjunctionRefinementSet = 1(ws conjunction ws subRefinement)
; A conjunction refinement set consists of one or more conjunction operators, each followed by a subRefinement.

disjunctionRefinementSet = 1(ws disjunction ws subRefinement)
; A disjunction refinement set consists of one or more disjunction operators, each followed by a subRefinement.

subRefinement = eclAttributeSet / eclAttributeGroup / "(" ws eclRefinement ws ")"
; A subRefinement is either an attribute set, an attribute group or a bracketed refinement.

eclAttributeSet = subAttributeSet ws [conjunctionAttributeSet / disjunctionAttributeSet]
; An attribute set contains one or more attribute name-value pairs separated by a conjunction or disjunction operator. An attribute set may optionally be placed in brackets.

conjunctionAttributeSet = 1(ws conjunction ws subAttributeSet)
; A conjunction attribute set consists of one or more conjunction operators, each followed by a subAttributeSet.

disjunctionAttributeSet = 1(ws disjunction ws subAttributeSet)
; A disjunction attribute set consists of one or more disjunction operators, each followed by a subAttributeSet.

subAttributeSet = eclAttribute / "(" ws eclAttributeSet ws ")"
; A subAttributeSet is either an attribute or a bracketed attribute set.

eclAttributeGroup = [ "[" cardinality "]" ws] "{" ws eclAttributeSet ws "}"
; An attribute group contains a collection of attributes that operate together as part of the refinement of the containing expression constraint. An attribute group may optionally be preceded by a cardinality. An attribute group cardinality indicates the minimum and maximum number of attribute groups that must satisfy the given attributeSet constraint for the expression constraint to be satisfied.

eclAttribute = [ "[" cardinality "]" ws] [reverseFlag ws] eclAttributeName ws (expressionComparisonOperator ws subExpressionConstraint / numericComparisonOperator ws "#" numericValue / stringComparisonOperator ws (typedSearchTerm / typedSearchTermSet) / booleanComparisonOperator ws booleanValue)
; An attribute is a name-value pair expressing a single refinement of the containing expression constraint. Either the attribute value must satisfy (or not) the given expression constraint, the attribute value is compared with a given numeric value (integer or decimal) using a numeric comparison operator, the attribute value must match (or not match) the given typedSearchTerm or typedSearchTermSet, or the attribute value must be equal to (or not equal to) the given boolean value. The attribute may optionally be preceded by a cardinality constraint and/or a reverse flag.

cardinality = minValue to maxValue
; The cardinality represents a constraint on the minimum and maximum number of times that the given attribute or attribute group may appear in a matching expression. The cardinality is enclosed in square brackets with the minimum cardinality appearing first, followed by a separator (two dots in the brief syntax), and then the maximum cardinality.

minValue = nonNegativeIntegerValue
; A value that represents the minimum number of times that an attribute or attribute group may appear. The minimum cardinality must always be less than or equal to the maximum cardinality.

to = ".." ; Brief syntax
to = ".." / (mws ("t"/"T") ("o"/"O") mws) ; Long syntax
; In the brief syntax, the minimum and maximum cardinality are separated by two dots (i.e. ".."). In the long syntax, the text "to" (case insensitive with at least one white space before and after) is also allowed between the two cardinalities.

maxValue = nonNegativeIntegerValue / many
; A value that represents the maximum number of times that an attribute or attribute group may appear. A maximum cardinality of 'many' indicates that there is no limit on the number of times the attribute may appear.

many = "" ; Brief syntax
many = "" / ( ("m"/"M") ("a"/"A") ("n"/"N") ("y"/"Y")) ; Long syntax
; In the brief syntax, a cardinality of 'many' is represented using the symbol "*". In the long syntax, the text "many" (case insensitive, with no trailing space) is also allowed.

reverseFlag = "R" ; Brief syntax
reverseFlag = (("r"/"R") ("e"/"E") ("v"/"V") ("e"/"E") ("r"/"R") ("s"/"S") ("e"/"E") ("o"/"O") ("f"/"F")) / "R" ; Long syntax
; When a reverse flag is used on an attribute, the matching relationships are traversed in the reverse of the normal direction. This means that the target concept of each relationship must match the focus concept to which the attribute is applied, while the source concept of the relationship must match the attribute value. In the brief syntax, the reverse flag is represented using the character "R" (in uppercase). In the long syntax, the text "reverseOf " (case insensitive) is also allowed.

eclAttributeName = subExpressionConstraint
; The attribute name is the name of an attribute (or relationship type) to which a value is applied to refine the meaning of a containing expression constraint. The attribute name is represented using a subExpressionConstraint, as defined above.

expressionComparisonOperator = "=" / "!=" ; Brief syntax
expressionComparisonOperator = "=" / "!=" / ("n"/"N") ("o"/"O") ("t"/"T") ws "=" / "&#x3C;>" ; Long syntax
; Attributes whose value is a concept may be compared to an expression constraint using either equals ("=") or not equals ("!="). In the long syntax "&#x3C;>" and "not =" (case insensitive) are also valid ways to represent not equals.

numericComparisonOperator = "=" / "!=" / "&#x3C;=" / "&#x3C;" / ">=" / ; Brief syntax
numericComparisonOperator = "=" / "!=" / ("n"/"N") ("o"/"O") ("t"/"T") ws "=" / "&#x3C;>" / "&#x3C;=" / "&#x3C;" / ">=" / ">" ; Long syntax
; Attributes whose value is numeric (i.e. integer or decimal) may be compared to a specific concrete value using a variety of comparison operators, including equals ("="), less than ("&#x3C;"), less than or equals ("&#x3C;="), greater than (">"), greater than or equals (">=") and not equals ("!="). In the long syntax "&#x3C;>" and "not =" (case insensitive) are also valid ways to represent not equals.

timeComparisonOperator = "=" / "!=" / "&#x3C;=" / "&#x3C;" / ">=" / ">" ; Brief syntax
timeComparisonOperator = "=" / "!=" / ("n"/"N") ("o"/"O") ("t"/"T") ws "=" / "&#x3C;>" / "&#x3C;=" / "&#x3C;" / ">=" / ">" ; Long syntax
; Date and time values may be compared using a variety of comparison operators, , including equals ("="), less than ("&#x3C;"), less than or equals ("&#x3C;="), greater than (">"), greater than or equals (">=") and not equals ("!="). In the long syntax "&#x3C;>" and "not =" (case insensitive) are also valid ways to represent not equals.

stringComparisonOperator = "=" / "!="
stringComparisonOperator = "=" / "!=" / ("n"/"N") ("o"/"O") ("t"/"T") ws "=" / "&#x3C;>"
; Attributes whose value is a string may be compared to an expression constraint using either equals ("=") or not equals ("!="). In the long syntax "&#x3C;>" and "not =" (case insensitive) are also valid ways to represent not equals.

booleanComparisonOperator = "=" / "!="
booleanComparisonOperator = "=" / "!=" / ("n"/"N") ("o"/"O") ("t"/"T") ws "=" / "&#x3C;>"
; Attributes whose value is a boolean may be compared to an expression constraint using either equals ("=") or not equals ("!="). In the long syntax "&#x3C;>" and "not =" (case insensitive) are also valid ways to represent not equals.

idComparisonOperator = "=" / "!=" ; Brief syntax
idComparisonOperator = "=" / "!=" / ("n"/"N") ("o"/"O") ("t"/"T") ws "=" / "&#x3C;>" ; Long syntax
; Filter criteria whose value is a SCTID may be compared to a SNOMED CT identifier using either equals ("=") or not equals ("!="). In the long syntax "&#x3C;>" and "not =" (case insensitive) are also valid ways to represent not equals.

descriptionFilterConstraint = "{{" ws ["d", / "D"] ws descriptionFilter *(ws "," ws descriptionFilter) ws "}}"
; A descriptionFilterConstraint is a constraint used to filter the concepts in the result set, according to whether or not the given conditions match at least one of the concept's descriptions. A description filter constraint is always enclosed in double curly braces. Within these braces, it should (preferably) start with the letter 'D' followed by one or more description filters.

descriptionFilter = termFilter / languageFilter / typeFilter / dialectFilter / moduleFilter / effectiveTimeFilter / activeFilter / descriptionIdFilter
; A description filter is either a term filter, a language filter, a type filter, a dialect filter, a module filter, an effective time filter, an active filter or a description id filter.

descriptionIdFilter = descriptionIdKeyword ws idComparisonOperator ws (descriptionId / descriptionIdSet)
; A descriptionIdFilter starts with the 'id' keyword, followed by an id comparison operator and either a single description id or a set of description ids.

descriptionIdKeyword = ("i"/"I") ("d"/"D")
; The description id keyword uses the text "id" (case insensitive)

descriptionId = sctId
; The descriptionId must be a valid SNOMED CT identifier for a description. The initial digit may not be zero. The smallest number of digits is six, and the maximum is 18.

descriptionIdSet = "(" ws descriptionId *(mws descriptionId) ws ")"
; A description id set consists of one or more description ids separated by mandatory white space and enclosed in brackets.

termFilter = termKeyword ws stringComparisonOperator ws (typedSearchTerm / typedSearchTermSet)
; A termFilter starts with the 'term' keyword, followed by a string comparison operator and either a typed search term or a typed search term set (with optional white space between). For example: term = "respiratory".

termKeyword = ("t"/"T") ("e"/"E") ("r"/"R") ("m"/"M")
; The term keyword uses the text "term" (case insensitive).

typedSearchTerm = ( [ matchKeyword ws ":" ws ] matchSearchTermSet ) / ( wild ws ":" ws wildSearchTermSet )
; A typed search term is either a match search term set or a wild search term set. A match search term set is optionally preceded by the text "match" and a colon. A wild search term set must be preceded by the text "wild" and a colon.

typedSearchTermSet = "(" ws typedSearchTerm *(mws typedSearchTerm) ws ")"
; A typed search term set consists of one or more typed search terms separated by mandatory white space and enclosed in brackets.

wild = ("w"/"W") ("i"/"I") ("l"/"L") ("d"/"D")
; A wildcard search type is indicated by the word "wild" (case insensitive).

matchKeyword = ("m"/"M") ("a"/"A") ("t"/"T") ("c"/"C") ("h"/"H")
; A word prefix any order search is indicated by the word "match" (case insensitive).

matchSearchTerm = 1(nonwsNonEscapedChar / escapedChar)
; A term used in a match search includes one or more of any non-whitespace printable character (other than double quotes or backslash) or an escaped character.

matchSearchTermSet = QM ws matchSearchTerm *(mws matchSearchTerm) ws QM
; A term set in a match search includes one or more terms separated by mandatory whitespace and enclosed in quotation marks.

wildSearchTerm = 1(anyNonEscapedChar / escapedWildChar)
<strong>; A term used in a wildcard search includes one or more printable characters (other than double quotes or backslash) or an escaped character.
</strong></code></pre>

\
\
\*\*BS/LS: \
\*\*BS/LS: \
\*\*BS/LS: **wildSearchTermSet** \*\*= QM wildSearchTerm QM

\| A term set in a wildcard search includes a wildcard search term (optionally including whitespace) enclosed in quotation marks.\
**BS/LS: languageFilter** = language ws booleanComparisonOperator ws (languageCode / languageCodeSet)

\| A language filter specifies the languages that a matching description may use. A language filter starts with the 'language' keyword, followed by a boolean comparison operator and either a single language code or a set of language codes.\
**BS/LS: language** = ("l"/"L") ("a"/"A") ("n"/"N") ("g"/"G") ("u"/"U") ("a"/"A") ("g"/"G") ("e"/"E")

\| The 'language' keyword uses the text "LANGUAGE" (case insensitive).\
\*\*BS/LS: **languageCode** \*\*= 2alpha

\| A language code is a 2 character alphanumeric string.\
\*\*BS/LS: **languageCodeSet** \*\*= "(" ws languageCode \*(mws languageCode) ws ")"

\| A language code set is one or more language codes, separated by mandatory whitespace, and enclosed in brackets.\
\*\*BS/LS: **typeFilter** \*\*= typeIdFilter / typeTokenFilter

\| A type filter specifies the description types that a matching description may have. A type filter is either a typeId filter or a typeToken filter.\
\*\*BS/LS: **typeIdFilter** \*\*= typeId ws booleanComparisonOperator ws (subExpressionConstraint / eclConceptReferenceSet)

\| A typeId filter starts with the 'typeId' keyword, followed by a boolean comparison operator, and either a subExpressionConstraint or a set of concept references.\
\*\*BS/LS: **typeId** \*\*= ("t"/"T") ("y"/"Y") ("p"/"P") ("e"/"E") ("i"/"I") ("d"/"D")

\| The 'typeId' keyword uses the text "TYPEID" (case insensitive).\
\*\*BS/LS: **typeTokenFilter** \*\*= type ws booleanComparisonOperator ws (typeToken / typeTokenSet)

\| A typeToken filter starts with the 'type' keyword, followed by a boolean comparison operator, and either a single type token or a set of type tokens.\
\*\*BS/LS: **type** \*\*= ("t"/"T") ("y"/"Y") ("p"/"P") ("e"/"E")

\| The 'type' keyword uses the text "TYPE" (case insensitive).\
\*\*BS/LS: **typeToken** \*\*= synonym / fullySpecifiedName / definition

\| A type token is either a 'synonym' token, a 'fully specified name' token or a 'definition' token.\
\*\*BS/LS: **typeTokenSet** \*\*= "(" ws typeToken \*(mws typeToken) ws ")"

\| A type token set is one or more type tokens, separated by mandatory whitespace and enclosed in brackets.\
\*\*BS: **synonym** \*\*= ("s"/"S") ("y"/"Y") ("n"/"N")\*\*LS: **synonym** \*\*= ("s"/"S") ("y"/"Y") ("n"/"N") \[ ("o"/"O") ("n"/"N") ("y"/"Y") ("m"/"M") ]

\| A 'synonym' token uses the text "SYN" (case insensitive). In the long syntax, the text "Synonym" (case insensitive) may be used instead.\
\*\*BS: **fullySpecifiedName** \*\*= ("f"/"F") ("s"/"S") ("n"/"N")\*\*LS: **fullySpecifiedName** \*\*= ( ("f"/"F") ("s"/"S") ("n"/"N") ) / ( ("f"/"F") ("u"/"U") ("l"/"L") ("l"/"L") ("y"/"Y") ("s"/"S") ("p"/"P") ("e"/"E") ("c"/"C") ("i"/"I") ("f"/"F") ("i"/"I") ("e"/"E") ("d"/"D") ("n"/"N") ("a"/"A") ("m"/"M") ("e"/"E") )

\| A 'fully specified name' token uses the text "FSN" (case insensitive). In the long syntax, the text "FullySpecifiedName" (case insensitive) may be used instead.\
\*\*BS: **definition** \*\*= ("d"/"D") ("e"/"E") ("f"/"F")\*\*LS: **definition** \*\*= ("d"/"D") ("e"/"E") ("f"/"F") \[ ("i"/"I") ("n"/"N") ("i"/"I") ("t"/"T") ("i"/"I") ("o"/"O") ("n"/"N") ]

\| A 'definition' token uses the text "DEF" (case insensitive). In the long syntax, the text "Definition" (case insensitive) may be used instead.\
**BS/LS: dialectFilter** = (dialectIdFilter / dialectAliasFilter) \[ ws acceptabilitySet ]

\| A dialect filter specifies the language reference sets to which a matching description must belong. A dialect filter consists of either a dialectId filter or a dialectAlias filter, optionally followed by a set of acceptability values.\
\*\*BS/LS: **dialectIdFilter** \*\*= dialectId ws booleanComparisonOperator ws (subExpressionConstraint / dialectIdSet)

\| A dialectId filter starts with the 'dialectId' keyword, followed by a boolean comparison operator, and either a subExpressionConstraint or a set of dialectIds.\
\*\*BS/LS: **dialectId** \*\*= ("d"/"D") ("i"/"I") ("a"/"A") ("l"/"L") ("e"/"E") ("c"/"C") ("t"/"T") ("i"/"I") ("d"/"D")

\| A 'dialectId' keyword uses the text "DIALECTID" (case insensitive).\
\*\*BS/LS: **dialectAliasFilter** \*\*= dialect ws booleanComparisonOperator ws (dialectAlias / dialectAliasSet)

\| A dialectAlias filter starts with the 'dialect' keyword, followed by a boolean comparison operator, and either a single dialect alias or a set of dialect aliases.\
\*\*BS/LS: **dialect** \*\*= ("d"/"D") ("i"/"I") ("a"/"A") ("l"/"L") ("e"/"E") ("c"/"C") ("t"/"T")

\| A 'dialect' keyword uses the text "DIALECT" (case insensitive).\
\*\*BS/LS: **dialectAlias** \*\*= alpha \*( dash / alpha / integerValue)

\| A dialect alias consists of a single alphanumeric character followed by zero or more alphanumeric characters, integer values or dashes.\
\*\*BS/LS: **dialectAliasSet** \*\*= "(" ws dialectAlias \[ws acceptabilitySet] \*(mws dialectAlias \[ws acceptabilitySet]) ws ")"

\| A dialect alias set is one or more dialect aliases followed by an optional acceptability set, separated by mandatory white space, and enclosed in brackets.\
**BS/LS: dialectIdSet**\*\*\*\* = "(" ws eclConceptReference \[ws acceptabilitySet] \*(mws eclConceptReference \[ws acceptabilitySet] ) ws ")"

\| A dialect id set is one or more concept references followed by an optional acceptability set, separated by mandatory white space, and enclosed in brackets.\
\*\*BS/LS: **acceptabilitySet** \*\*= acceptabilityConceptReferenceSet / acceptabilityTokenSet

\| An acceptability set specifies the acceptabilities that a matching description must have in the language reference set specified by the preceding dialect filter. An acceptability set is either a set of one or more concept references or an acceptabilityToken set.\
**BS/LS: acceptabilityConceptReferenceSet** = "(" ws eclConceptReference \*(mws eclConceptReference) ws ")"

\| An acceptability concept reference set is a set of one or more references to concepts that are a < 900000000000511003 |Acceptability|.\
\*\*BS/LS: **acceptabilityTokenSet** \*\*= "(" ws acceptabilityToken \*(mws acceptabilityToken) ws ")"

\| An acceptability token set is one or more acceptability tokens, separated by mandatory whitespace, and enclosed in brackets.\
\*\*BS/LS: **acceptabilityToken** \*\*= acceptable / preferred

\| An acceptability token is either an acceptable token and a preferred token.\
\*\*BS: **acceptable** \*\*= ("a"/"A") ("c"/"C") ("c"/"C") ("e"/"E") ("p"/"P") ("t"/"T")\*\*LS: **acceptable** \*\*= ("a"/"A") ("c"/"C") ("c"/"C") ("e"/"E") ("p"/"P") ("t"/"T") \[ ("a"/"A") ("b"/"B") ("l"/"L") ("e"/"E") ]

\| An acceptable token uses the text "ACCEPT" (case insensitive). In the long syntax, the text "Acceptable" (case insensitive) may be used instead.\
\*\*BS: **preferred** \*\*= ("p"/"P") ("r"/"R") ("e"/"E") ("f"/"F") ("e"/"E") ("r"/"R")\*\*LS: **preferred** \*\*= ("p"/"P") ("r"/"R") ("e"/"E") ("f"/"F") ("e"/"E") ("r"/"R") \[ ("r"/"R") ("e"/"E") ("d"/"D") ]

\| A preferred token uses the text "PREFER" (case insensitive). In the long syntax, the text "Preferred" (case insensitive) may be used instead.\
\*\*\*\*BS/LS:\*\*\*\***conceptFilterConstraint** = "\{{" ws ("c" / "C") ws conceptFilter \*(ws "," ws conceptFilter) ws "\}}"

\| A concept filter constraint is a constraint used to filter the concepts in the result set, according to whether or not the concept matches the given conditions. A concept filter constraint is always enclosed in double curly braces. Within these braces, it starts with the letter 'C' followed by one or more constraint filters.\
**BS/LS:conceptFilter** = definitionStatusFilter / moduleFilter / effectiveTimeFilter / activeFilter

\| A concept filter is either a definition status filter, a module filter, an effective time filter or an active filter.\
**BS/LS:definitionStatusFilter** = definitionStatusIdFilter / definitionStatusTokenFilter

\| A definition status filter is constraint that either filters the results of a query, based on each concept's definition status identifier or a token.\
**BS/LS:definitionStatusIdFilter** = definitionStatusIdKeyword ws booleanComparisonOperator ws (subExpressionConstraint / eclConceptReferenceset)

\| A definition status filter is a constraint that filters the results of a query, based on whether or not each concept's definition status matches a given identifier. The filter starts with the keyword "definitionStatusId", followed by a boolean comparison operator and either a subexpression constraint or a set of concept references that are a subtype of [900000000000444006 | Definition status|](http://snomed.info/id/900000000000444006) .\
**BS/LS:definitionStatusIdKeyword** = ("d"/"D") ("e"/"E") ("f"/"F") ("i"/"I") ("n"/"N") ("i"/"I") ("t"/"T") ("i"/"I") ("o"/"O") ("n"/"N") ("s"/"S") ("t"/"T") ("a"/"A") ("t"/"T") ("u"/"U") ("s"/"S") ("i"/"I") ("d"/"D")

\| The definition status id keyword is the text "definitionStatusId" (in any combination of upper or lower case).\
**BS/LS:definitionStatusTokenFilter** = definitionStatusKeyword ws booleanComparisonOperator ws (definitionStatusToken / definitionStatusTokenSet)

\| A definition status filter is a constraint that filters the results of a query, based on whether or not each concept's definition status matches a given token.\
**BS/LS:definitionStatusKeyword** = ("d"/"D") ("e"/"E") ("f"/"F") ("i"/"I") ("n"/"N") ("i"/"I") ("t"/"T") ("i"/"I") ("o"/"O") ("n"/"N") ("s"/"S") ("t"/"T") ("a"/"A") ("t"/"T") ("u"/"U") ("s"/"S")

\| The definition status keyword is the text "definitionStatus" (in any combination of upper or lower case).\
**BS/LS:definitionStatusToken** = primitiveToken / definedToken

\| A definition status token is either a primitive token or a defined token.\
**BS/LS:definitionStatusTokenSet** = "(" ws definitionStatusToken \*(mws definitionStatusToken) ws ")"

\| A definition status token set consists of one or more definition status tokens separated by mandatory white space and enclosed in brackets.\
**BS/LS:primitiveToken** = ("p"/"P") ("r"/"R") ("i"/"I") ("m"/"M") ("i"/"I") ("t"/"T") ("i"/"I") ("v"/"V") ("e"/"E")

\| A primitive token represents the definition status [900000000000074008 | Primitive|](http://snomed.info/id/900000000000074008) using the text "primitive" (in any combination of upper and lower case characters).\
**BS/LS:definedToken** = ("d"/"D") ("e"/"E") ("f"/"F") ("i"/"I") ("n"/"N") ("e"/"E") ("d"/"D")

\| A defined token represents the definition status [900000000000073002 | Defined|](http://snomed.info/id/900000000000073002) using the text "defined" (in any combination of upper and lower case characters).\
**BS/LS: moduleFilter** =moduleIdKeyword ws booleanComparisonOperator ws (subExpressionConstraint / eclConceptReferenceSet)

\| A module filter is a constraint that filters the results of a query based on the module to which each concept belongs. The filter starts with the keyword "moduleId", followed by a boolean comparison operator and either a subexpression constraint or a set of concept references that are a subtype of [900000000000443000 | Module|](http://snomed.info/id/900000000000443000) .\
**BS/LS:moduleIdKeyword** = ("m"/"M") ("o"/"O") ("d"/"D") ("u"/"U") ("l"/"L") ("e"/"E") ("i"/"I") ("d"/"D")

\| The module id keyword is the text "moduleId" (in any combination of upper or lower case).\
**BS/LS:effectiveTimeFilter** = effectiveTimeKeyword ws timeComparisonOperator ws ( timeValue / timeValeSet )

\| An effective time filter is a constraint that filters the results of a query based on the effective time assigned to each concept.\
**BS/LS:effectiveTimeKeyword** = ("e"/"E") ("f"/"F") ("f"/"F") ("e"/"E") ("c"/"C") ("t"/"T") ("i"/"I") ("v"/"V") ("e"/"E") ("t"/"T") ("i"/"I") ("m"/"M") ("e"/"E")

\| The effective time keyword is the text "effectiveTime" (in any combination of upper or lower case).\
**BS/LS:timeValue** = QM \[ year month day ] QM

\| A time value is a 8 digit string that represents the year, month and day of a specific date.\
\*\*BS/LS: timeValueSet \*\*= "(" ws timeValue \*(mws timeValue) ws ")"

\| A time value set consists of one or more time values separated by mandatory white space and enclosed in brackets.\
**BS/LS:year** = digitNonZero digit digit digit

\| A year is a 4 digit string starting with a non-zero digit.\
**BS/LS:month** = "01" / "02" / "03" / "04" / "05" / "06" / "07" / "08" / "09" / "10" / "11" / "12"

\| A month is a 2 digit string from "01" to "12" that represents a specific month of the year (e.g. "01" represents January)\
**BS/LS:day** = "01" / "02" / "03" / "04" / "05" / "06" / "07" / "08" / "09" / "10" / "11" / "12" / "13" / "14" / "15" / "16" / "17" / "18" / "19" / "20" / "21" / "22" / "23" / "24" / "25" / "26" / "27" / "28" / "29" / "30" / "31"

\| A day is a 2 digit string from "01" to "31" that represents a specific day within a month of a year.\
**BS/LS:activeFilter** = activeKeyword ws booleanComparisonOperator ws activeValue

\| An active filter is a constraint that filters the results of a query based on the active status of each concept\
**BS/LS:activeKeyword** = ("a"/"A") ("c"/"C") ("t"/"T") ("i"/"I") ("v"/"V") ("e"/"E")

\| The active keyword is the text "active" (in any combination of upper or lower case).\
**BS/LS:activeValue** = activeTrueValue / activeFalseValue

\| An active value represents the active status of a concept, and is either true (i.e. the concept is active) or false (i.e. the concept is inactive).\
**BS/LS:activeTrueValue** = "1" / "true"

\| An active true value is a value that represents an active concept. This value is either "1" or "true".\
**BS/LS:activeFalseValue** = "0" / "false"

\| An active false value is a value that represents an inactive concept. This value is either "0" or "false".\
\*\*BS/LS: memberFilterConstraint \*\*= "\{{" ws ("m" / "M") ws memberFilter \*(ws "," ws memberFilter) ws "\}}"

\| A member filter constraint is a constraint used to filter the rows in one or more result sets, according to values of particular fields. A member filter constraint is always surrounded by double curly braces. Within these braces, it starts with the letter 'M' followed by one or more member filters.\
\*\*BS/LS: memberFilter \*\*= moduleFilter / effectiveTimeFilter / activeFilter / memberFieldFilter

\| A member filter is either a module filter, an effective time filter, an active filter, or a member field filter.\
\*\*BS/LS: memberFieldFilter \*\*= refsetFieldName ws (expressionComparisonOperator ws subExpressionConstraint / numericComparisonOperator ws "#" numericValue / stringComparisonOperator ws (typedSearchTerm / typedSearchTermSet) / booleanComparisonOperator ws booleanValue / ws timeComparisonOperator ws (timeValue / timeValueSet) )

\| A member field filter always has three parts - (1) the reference set field name, (2) a comparison operator, and (3) the criteria on which to match the field's value. If the refset field is of type SNOMED CT concept, then an expression comparison operator is used, followed by a subexpression constraint. If the refset field is a numeric type, then a numeric comparison operator is used, followed by a hash symbol ("#") and a numeric value. If the refset field is of type string, then a string comparison operator is used, followed by a typed search term or a typed search term set. If the refset field is of type boolean, then a boolean comparison operator is used, followed by a boolean value. And if the refset field is of type dateTime, then a time comparison operator is used, followed by a time value or time value set.\
\*\*BS/LS: historySupplement \*\*= "\{{" ws "+" ws historyKeyword \[ historyProfileSuffix / ws historySubset ] ws "\}}"

\| A history supplement augments the results of the expression constraint with relevant inactive concepts. A history supplement is always surrounded by double curly braces. Within these braces, it starts with a plus symbol (i.e. "+"), followed by the history keyword. The history keyword is optionally followed by either a profile suffix, or a history subset.\
\*\*BS/LS: historyKeyword \*\*= ("h"/"H") ("i"/"I") ("s"/"S") ("t"/"T") ("o"/"O") ("r"/"R") ("y"/"Y")

\| The history keyword is the word "HISTORY" (case insensitive).\
\*\*BS/LS: historyProfileSuffix \*\*= historyMinimumSuffix / historyModerateSuffix / historyMaximumSuffix

\| A history profile suffix is either the suffix for history minimum, history moderate or history maximum.\
\*\*BS/LS: historyMinimumSuffix \*\*= ("-"/"\_")("m"/"M") ("i"/"I") ("n"/"N")

\| The history minimum suffix is "-MIN" (case insensitive). The suffix may start with either a hyphen (i.e. "-") or an underscore (i.e. "_")._\
&#xNAN;_\*\*BS/LS: historyModerateSuffix \*\*= ("-"/"_") ("m"/"M") ("o"/"O") ("d"/"D")

\| The history moderate suffix is "-MOD" (case insensitive). The suffix may start with either a hyphen (i.e. "-") or an underscore (i.e. "_")._\
&#xNAN;_\*\*BS/LS: historyMaximumSuffix \*\*= ("-"/"_") ("m"/"M") ("a"/"A") ("x"/"X")

\| The history maximum suffix is "-MAX" (case insensitive). The suffix may start with either a hyphen (i.e. "-") or an underscore (i.e. "\_").\
\*\*BS/LS: historySubset \*\*= "(" ws expressionConstraint ws ")"

\| A history subset is an expression constraint that defines a set of historical association reference sets, surrounded by round brackets. Only descendants of [900000000000522004 | Historical association reference set|](http://snomed.info/id/900000000000522004) may be included in a history subset.\
\*\*BS/LS:\*\***numericValue** = \["-"/"+"] (decimalValue / integerValue)

\| A numeric value is either an integer or a decimal. Positive numbers optionally start with a plus sign ("+"), while negative integers begin with a minus sign ("-").\
\*\*BS/LS:\*_**stringValue** = 1_(anyNonEscapedChar / escapedChar)

\| A string value includes one or more of any printable ASCII characters enclosed in quotation marks. Quotes and backslash characters within the string must be preceded by the escape character ("").\
\*\*BS/LS:\*\***integerValue** = digitNonZero \*digit / zero

\| An integer value is either starts with a non-zero digit followed by zero to many additional digits, or is the integer zero itself.\
\*\*BS/LS:\*\***decimalValue** = integerValue "." 1\*digit

\| A decimal value starts with an integer. This is followed by a decimal point and one to many digits.\
\*\*BS/LS:\*\***booleanValue** = true / false

\| A boolean value is either true or false.\
\*\*BS/LS:\*\***true** = ("t"/"T") ("r"/"R") ("u"/"U") ("e"/"E")

\| A boolean value of true is represented by the word "true" (case insensitive).\
\*\*BS/LS:\*\***false** = ("f"/"F") ("a"/"A") ("l"/"L") ("s"/"S") ("e"/"E")

\| A boolean value of false is represented by the word "false" (case insensitive).\
\*\*BS/LS:\*\***nonNegativeIntegerValue** = (digitNonZero \*digit ) / zero

\| A non-negative integer value (i.e. positive integers or zero), without a preceding plus sign ("+").\
\*\*BS/LS:\*\***sctId** = digitNonZero 5\*17( digit )

\| A SNOMED CT id is used to represent an attribute id or a [concept](https://confluence.ihtsdotools.org/display/DOCGLOSS/concept) id. The initial digit may not be zero. The smallest number of digits is six, and the maximum is 18.\
\*\*BS/LS:\*\***ws** = \*( SP / HTAB / CR / LF / comment )

\| Optional whitespace characters (space, tab, carriage return, linefeed or a comment) are ignored everywhere in the [expression](https://confluence.ihtsdotools.org/display/DOCGLOSS/expression) except:

1. Whitespace within a conceptId is an error.\
   **Note:** Whitespace before or after the last digit of a valid [Identifier](https://confluence.ihtsdotools.org/display/DOCGLOSS/Identifier) is ignored.
2. Non-consecutive spaces within a term are treated as a significant character of the term.\
   **Note:** Whitespace before the first or after the last non-whitespace character of a [term](https://confluence.ihtsdotools.org/display/DOCRELFMT/term+\(field\)) is ignored
3. Whitespace within the quotation marks of a concrete value is treated as a significant character.

\*\*BS/LS:\*_**mws** = 1_( SP / HTAB / CR / LF / comment )

\| Mandatory whitespace (i.e. space, tab, carriage return, linefeed or a comment) is required after certain keywords, including "And" and "Or".\
\*\*BS/LS:\*\***comment** = "/\*" _(nonStarChar / starWithNonLSlash) "_/"

\| A comment, which provides additional human-readable details about the expression constraint. Comments begin with a forward slash directly followed by a star (i.e. "/_") and end with a star directly followed by a forward slash (i.e. "_/").\
\*\*BS/LS:\*\***nonStarChar** = SP / HTAB / CR / LF / %x21-29 / %x2B-7E /UTF8-2 / UTF8-3 / UTF8-4

\| A character that is not a star (i.e. not %x2A).\
\*\*BS/LS:\*\***starWithNonLSlash** = %x2A nonLSlash

\| A star (i.e. "\*") followed by a character that is not a forward slash (i.e. not "/").\
\*\*BS/LS:\*\***nonLSlash** = SP / HTAB / CR / LF / %x21-2E / %x30-7E /UTF8-2 / UTF8-3 / UTF8-4

\| A character that is not a forward slash (i.e. not "/").\
\*\*BS/LS:\*\***SP** = %x20

\| Space character.\
\*\*BS/LS:\*\***HTAB** = %x09

\| Tab character.\
\*\*BS/LS:\*\***CR** = %x0D

\| Carriage return character.\
\*\*BS/LS:\*\***LF** = %x0A

\| Line feed character.\
\*\*BS/LS:\*\***QM** = %x22

\| Quotation mark character.\
\*\*BS/LS:\*\***BS** = %x5C ; back slash

\| BS represents the backslash character "".\
\*\*BS/LS: star \*\*= %x2A ; asterisk

\| Star represents an asterisk "\*".\
\*\*BS/LS:\*\***digit** = %x30-39

\| Any digit 0 through 9.\
\*\*BS/LS:\*\***zero** = %x30

\| The digit 0.\
\*\*BS/LS:\*\***digitNonZero** = %x31-39

\| Digits 1 through 9, but excluding 0.The first character of a [concept identifier](https://confluence.ihtsdotools.org/display/DOCGLOSS/concept+identifier) is constrained to a digit other than zero.\
\*\*BS/LS:\*\***nonwsnonpipe** = %x21-7B / %x7D-7E / UTF8-2 / UTF8-3 / UTF8-4

\| Non whitespace (and non pipe) includes printable ASCII characters (these are also valid UTF8 characters encoded as one octet) and also includes all UTF8 characters encoded as 2- 3- or 4-octet sequences. It excludes space (which is %x20) and the pipe character "\
\*\*BS/LS:\*\***anyNonEscapedChar** = SP / HTAB / CR / LF / %x20-21 / %x23-5B / %x5D-7E / UTF8-2 / UTF8-3 / UTF8-4

\| anyNonEscapedChar includes any printable ASCII characters which do not need to be preceded by an escape character (i.e. ""). This includes valid UTF8 characters encoded as one octet and all UTF8 characters encoded as 2, 3 or 4 octet sequences. It does, however, exclude the quotation mark (") and the backslash (). See RFC 3629 ( [UTF-8](https://confluence.ihtsdotools.org/display/DOCRELFMT/UTF-8), a [transformation](https://confluence.ihtsdotools.org/display/DOCGLOSS/transformation) format of [ISO](https://confluence.ihtsdotools.org/display/DOCGLOSS/ISO) 10646 authored by the Network Working Group).\
\*\*BS/LS:\*\***escapedChar** = BS QM / BS BS

\| The double quotation mark and the back slash character must both be escaped within a string-based concrete value by preceding them with a back slash.\
\*\*BS/LS: **escapedWildChar** \*\*= BS QM / BS BS / BS star

\| An escapedWildChar is one of the characters that must be escaped in a wildcard search term (i.e. " or \ or _), preceded by a backslash (i.e. \\). The character sequence is therefore either " or \\\ or \\_.\
\*\*BS/LS: **nonwsNonEscapedChar** \*\*= %x21 / %x23-5B / %x5D-7E / UTF8-2 / UTF8-3 / UTF8-4

\| A nonwsNonEscapedChar is any printable ASCII, UTF8-2, UTF8-3 or UTF8-4 character, excluding double quotes ("), backslash (\\), and space ( ).\
**BS/LS: alpha** = %x41-5A / %x61-7A

\| An alpha is any uppercase or lowercase character from "A" to "Z" (and "a" to "z") inclusive.\
\*\*BS/LS: **dash** \*\*= %x2D

\| A dash is a hyphen (i.e. "-").\
\*\*BS/LS:\*\***UTF8-2** = %xC2-DF UTF8-tail

\| UTF8 characters encoded as 2-octet sequences.\
\*\*BS/LS:\*\***UTF8-3** = %xE0 %xA0-BF UTF8-tail / %xE1-EC 2( UTF8-tail ) / %xED %x80-9F UTF8-tail / %xEE-EF 2( UTF8-tail )

\| UTF8 characters encoded as 3-octet sequences.\
\*\*BS/LS:\*\***UTF8-4** = %xF0 %x90-BF 2( UTF8-tail ) / %xF1-F3 3( UTF8-tail ) / %xF4 %x80-8F 2( UTF8-tail )

\| UTF8 characters encoded as 4-octet sequences.\
\*\*BS/LS:\*\***UTF8-tail** = %x80-BF

\| UTF8 characters encoded as 8-octet sequences.

## Order of Operation

This section explains the correct order of operation for unary operators, binary operators, filters and supplements.

### Unary Operators

Unary operators (e.g. descendantOf, descendantOrSelfOf, ancestorOf, ancestorOrSelfOf, memberOf) are applied from inside to out (i.e. from right to left). For example, when the following expression constraint is processed, the memberOf operator is applied first to the Example problem list concepts reference set, and then the descendants of the referenced components are determined.

```
< ^ 700043003 |Example problem list concepts reference set|

```

### Binary Operators

Whenever potential ambiguity in binary operator precedence may occur, round brackets must be used to clearly disambiguate the order in which these operators are applied. For example, the following expression constraint is not valid:

{% code overflow="wrap" %}
```
< 19829001 |Disorder of lung| OR ^ 700043003 |Example problem list concepts reference set|
MINUS ^ 450976002 |Disorders and diseases reference set for GP/FP reason for encounter|
```
{% endcode %}

And must be expressed using brackets, as either:

{% code overflow="wrap" %}
```
(< 19829001 |Disorder of lung| OR ^ 700043003 |Example problem list concepts reference set| )
MINUS ^ 450976002 |Disorders and diseases reference set for GP/FP reason for encounter|
```
{% endcode %}

or:

{% code overflow="wrap" %}
```
< 19829001 |Disorder of lung| OR (^ 700043003 |Example problem list concepts reference set|
MINUS ^ 450976002 |Disorders and diseases reference set for GP/FP reason for encounter| )
When multiple exclusion operators (i.e. 'minus') are applied, brackets are similarly required. For example, the following expression constraint is not valid:
< 19829001 |Disorder of lung| MINUS ^ 700043003 |Example problem list concepts reference set|
MINUS ^ 450976002 |Disorders and diseases reference set for GP/FP reason for encounter|
And must be expressed using brackets, as either:
(< 19829001 |Disorder of lung| MINUS ^ 700043003 |Example problem list concepts reference set| )
MINUS ^ 450976002 |Disorders and diseases reference set for GP/FP reason for encounter|
```
{% endcode %}

or:

{% code overflow="wrap" %}
```
< 19829001 |Disorder of lung| MINUS (^ 700043003 |Example problem list concepts reference set|
MINUS ^ 450976002 |Disorders and diseases reference set for GP/FP reason for encounter| )
```
{% endcode %}

However, when only a single binary operator is used, or when all binary operators are either conjunction (i.e. 'and') or disjunction (i.e. 'or'), brackets are not required. For example, all of the following expression constraints are valid without brackets:

{% code overflow="wrap" %}
```
< 19829001 |Disorder of lung| AND ^ 700043003 |Example problem list concepts reference set|
< 19829001 |Disorder of lung| OR ^ 700043003 |Example problem list concepts reference set|
< 19829001 |Disorder of lung| MINUS ^ 700043003 |Example problem list concepts reference set|
< 19829001 |Disorder of lung| OR ^ 700043003 |Example problem list concepts reference set|
OR ^ 450976002 |Disorders and diseases reference set for GP/FP reason for encounter|
< 19829001 |Disorder of lung| AND ^ 700043003 |Example problem list concepts reference set|
AND ^ 450976002 |Disorders and diseases reference set for GP/FP reason for encounter|
```
{% endcode %}

Please note that unary operators are always applied before binary operators.

### Filter Constraints

Filter constraints (e.g. concept, description, or member filters) apply only to the sub-expression constraint part that is directly to the left of the filter.

For example, the following expression constraint will apply the term filter to only the descendants or self of [415582006 | Stenosis|](http://snomed.info/id/415582006) . This expression constraint will match descendants of [404684003 | Clinical finding|](http://snomed.info/id/404684003) with a finding site that is a descendant or self of [39057004 | Pulmonary valve structure|](http://snomed.info/id/39057004) , and an associated morphology that is any descendant or self of [415582006 | Stenosis|](http://snomed.info/id/415582006) which has a description matching the term "insufficiency". Therefore, the concept [123801008 | Heart valve stenosis and regurgitation (disorder)|](http://snomed.info/id/123801008) will match this expression constraint because it has the associated morphology [708027006 | Valvular stenosis with valvular insufficiency|](http://snomed.info/id/708027006) .

{% code overflow="wrap" %}
```
< 404684003 |Clinical finding| :
363698007 |Finding site| = << 39057004 |Pulmonary valve structure| ,
116676008 |Associated morphology| = << 415582006 |Stenosis| {{ term = "insufficiency" }}
```
{% endcode %}

To apply a filter to a sub-expression constraint, which includes a refinement or binary operators, the subexpression must be enclosed in brackets. For example, the following expression constraint will find all the descendants of clinical finding, with a finding site that is a descendant or self of [39057004 | Pulmonary valve structure|](http://snomed.info/id/39057004) and an associated morphology that is a descendant or self of [415582006 | Stenosis|](http://snomed.info/id/415582006) , and will then match only those clinical finding concepts that have a description that matches the term "insufficiency". Therefore, the concept [123801008 | Heart valve stenosis and regurgitation (disorder)|](http://snomed.info/id/123801008) will **not** match this expression constraints, as it does not have a description that matches the term "insufficiency".

{% code overflow="wrap" %}
```
(< 404684003 |Clinical finding| :
363698007 |Finding site| = << 39057004 |Pulmonary valve structure| ,
116676008 |Associated morphology| = << 415582006 |Stenosis| ) {{ term = "insufficiency" }}
```
{% endcode %}

### History Supplements

History supplements are applied only to the sub-expression constraint part that is directly to its left, after any filter constraints on this sub-expression constraint part have been applied.

For example, the following expression constraint will match all concepts that are **both** an active member of the [734139008 | Anatomy structure and part association reference set|](http://snomed.info/id/734139008) **and** also either an active member of the [734138000 | Anatomy structure and entire association reference set|](http://snomed.info/id/734138000) or an inactive concept associated with an active member of the [734138000 | Anatomy structure and entire association reference set|](http://snomed.info/id/734138000) via the [900000000000527005 | SAME AS association reference set|](http://snomed.info/id/900000000000527005) . Because all active members of the [734139008 | Anatomy structure and part association reference set|](http://snomed.info/id/734139008) are active, there will be no inactive concepts in the result set.

<pre data-overflow="wrap"><code><strong>^ 734139008 |Anatomy structure and part association reference set|
</strong>AND ^ 734138000 |Anatomy structure and entire association reference set|
{{ + HISTORY ( 900000000000527005 |SAME AS association reference set| ) }}
</code></pre>

To apply the history supplement to the entire sub-expression constraint above, the sub-expression constraint must be enclosed in round brackets. For example, the following expression constraint will match concepts that are **both** members of the [734139008 | Anatomy structure and part association reference set|](http://snomed.info/id/734139008) **and** also members of the [734138000 | Anatomy structure and entire association reference set|](http://snomed.info/id/734138000) ; and it will also match on any inactive concept that is associated via a [900000000000527005 | SAME AS association reference set|](http://snomed.info/id/900000000000527005) to a member of both reference sets.

{% code overflow="wrap" %}
```
( ^ 734139008 |Anatomy structure and part association reference set|
AND ^ 734138000 |Anatomy structure and entire association reference set| )
{{ + HISTORY ( 900000000000527005 |SAME AS association reference set| ) }}
```
{% endcode %}

## Character Collation for Term Filters

To promote consistency between implementations of ECL, the following collation principles are recommended:

* **Search and match** - The default behaviour of a system implementing ECL queries with term filters, is to use locale-specific asymmetric searching at the secondary comparison strength level -as specified in the [Unicode Technical Standard #10 - Unicode Collation Algorithm](http://www.unicode.org/reports/tr10/#Asymmetric_Search_Secondary). This means that the search is, by default, case insensitive, with some language-specific character normalization behaviour.
  * _Asymmetric_ : Asymmetric searches require characters in the query that are unmarked (i.e. the 'base letters') to match characters in the target that are either _marked_ or _unmarked_ (with the same base letter). However, a character in the query that is _marked_ will only match a character in the target that is _marked_ in the same way.
  * _Secondary strength_ : Searches with a strength of secondary will only consider level 1 differences (e.g. "d" vs "e") and level 2 differences (e.g. "e" vs "é" in English). However, level 3 differences (e.g. "e" vs "E") are not considered. This provides the same effect as queries being case insensitive. For example, in English, "e" in the query will match both "e" and "E" in the target; and "E" in the query will similarly match both "e" and "E" in the target.
* **Language customizations** - Locale-based customizations of the standard are specified in the [Unicode Common Locale Data Repository (CLDR)](http://cldr.unicode.org/index/cldr-spec/collation-guidelines). The unicode CLDR specifies the characters that are considered to be 'marked' variants of the base letters, identical base letters, and/or contractions in each specified language. The description terms in the substrate should be indexed separately for each language supported.

For example, the following search behaviour is expected in the locales specified below.

* In **English** , **Swedish** and **Danish** , the following search behaviour is expected:\
  Note: No customizations are made in these 3 locales for the characters used in these searches. Therefore, the [CLDR root collation order](https://unicode.org/reports/tr35/tr35-collation.html#Root_Collation) is used.

<table><thead><tr><th width="190.7890625">Search Term</th><th>Target Matches</th><th>Target does NOT Match</th></tr></thead><tbody><tr><td>resume</td><td>resume, Resume, RESUME, résumé, rèsumè, Résumé, RÉSUMÉ, …</td><td>-</td></tr><tr><td>Resume</td><td>resume, Resume, RESUME, résumé, rèsumè, Résumé, RÉSUMÉ, …</td><td>-</td></tr><tr><td>résumé</td><td>résumé, Résumé, RÉSUMÉ, …</td><td>resume, Resume, RESUME, ...</td></tr><tr><td>Résumé</td><td>résumé, Résumé, RÉSUMÉ, …</td><td>resume, Resume, RESUME, ...</td></tr></tbody></table>

* In **English** , the following search behaviour is expected (based on the [CLDR 'en' locale](https://github.com/unicode-org/cldr/blob/master/common/collation/en.xml), which uses the [CLDR root collation order](https://unicode.org/reports/tr35/tr35-collation.html#Root_Collation)):

| Search Term | Target Matches                                                                                | Target does NOT Match                                                                                                       |
| ----------- | --------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| sjogren     | sjogren, Sjogren, SJOGREN, sjögren, Sjögren, SJÖGREN, sjøgren, Sjøgren, SJØGREN, ...          | -                                                                                                                           |
| sjögren     | sjögren, Sjögren, SJÖGREN, ...                                                                | sjogren, Sjogren, SJOGREN, sjøgren, Sjøgren, SJØGREN, ...                                                                   |
| Angstrom    | angstrom, Angstrom, ANGSTROM, ångström, Ångström, ÅNGSTRÖM, ångstrøm, Ångstrøm, ÅNGSTRØM, ... | ångstrœm, Ångstrœm, ÅNGSTRŒM, ...                                                                                           |
| Ångström    | ångström, Ångström, ÅNGSTRÖM, ...                                                             | angstrom, Angstrom, ANGSTROM, ångstrøm, Ångstrøm, ÅNGSTRØM, ...                                                             |
| Ångstrøm    | ångstrøm, Ångstrøm, ÅNGSTRØM, ...                                                             | angstrom, Angstrom, ANGSTROM, ångström, Ångström, ÅNGSTRÖM, ...                                                             |
| aangstrøm   | aangstrøm, Aangstrøm, AANGSTRØM, ...                                                          | angstrom, Angstrom, ANGSTROM, ångström, Ångström, ÅNGSTRÖM, ångstrøm, Ångstrøm, ÅNGSTRØM, ångstrœm, Ångstrœm, ÅNGSTRŒM, ... |

* In **Swedish** , the following search behaviour is expected (based on the customizations in the [CLDR 'sv' locale](https://github.com/unicode-org/cldr/blob/master/common/collation/sv.xml)):

| Search Term | Target Matches                                                                                | Target does NOT Match                                                                                                          |
| ----------- | --------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| sjogren     | sjogren, Sjogren, SJOGREN, ...                                                                | sjögren, Sjögren, SJÖGREN, sjøgren, Sjøgren, SJØGREN, ...                                                                      |
| sjögren     | sjögren, Sjögren, SJÖGREN, sjøgren, Sjøgren, SJØGREN, ...                                     | sjogren, Sjogren, SJOGREN , ...                                                                                                |
| Angstrom    | angstrom, Angstrom, ANGSTROM, ...                                                             | ångström, Ångström, ÅNGSTRÖM, ångstrøm, Ångstrøm, ÅNGSTRØM, ångstrœm, Ångstrœm, ÅNGSTRŒM, aangström, Aangström, AANGSTRÖM, ... |
| Ångström    | ångström, Ångström, ÅNGSTRÖM, ångstrøm, Ångstrøm, ÅNGSTRØM, ångstrœm, Ångstrœm, ÅNGSTRŒM, ... | angstrom, Angstrom, ANGSTROM, aangström, Aangström, AANGSTRÖM, ...                                                             |
| Ångstrøm    | ångstrøm, Ångstrøm, ÅNGSTRØM, ...                                                             | angstrom, Angstrom, ANGSTROM, ångström, Ångström, ÅNGSTRÖM, ångstrœm, Ångstrœm, ÅNGSTRŒM, ...                                  |
| aangstrøm   | aangstrøm, Aangstrøm, AANGSTRØM, ...                                                          | angstrom, Angstrom, ANGSTROM, ångström, Ångström, ÅNGSTRÖM, ångstrøm, Ångstrøm, ÅNGSTRØM, ångstrœm, Ångstrœm, ÅNGSTRŒM, ...    |

* And in **Danish** , the following search behaviour is expected (based on the customizations in the [CLDR 'da' locale](https://github.com/unicode-org/cldr/blob/master/common/collation/da.xml)):

| Search Term | Target Matches                                                                                                                    | Target does NOT Match                                                                                                         |
| ----------- | --------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| sjogren     | sjogren, Sjogren, SJOGREN, ...                                                                                                    | sjögren, Sjögren, SJÖGREN, sjøgren, Sjøgren, SJØGREN, ...                                                                     |
| sjögren     | sjögren, Sjögren, SJÖGREN, ...                                                                                                    | sjogren, Sjogren, SJOGREN, sjøgren, Sjøgren, SJØGREN, ...                                                                     |
| Angstrom    | angstrom, Angstrom, ANGSTROM, ...                                                                                                 | ångström, Ångström, ÅNGSTRÖM, ångstrøm, Ångstrøm, ÅNGSTRØM, ångstrœm, Ångstrœm, ÅNGSTRŒM, aangstrøm, Aangstrøm, AANGSTRØM ... |
| Ångström    | ångström, Ångström, ÅNGSTRÖM, aangström, Aangström, AANGSTRÖM, ...                                                                | angstrom, Angstrom, ANGSTROM, ångstrøm, Ångstrøm, ÅNGSTRØM, ångstrœm, Ångstrœm, ÅNGSTRŒM, ...                                 |
| Ångstrøm    | ångstrøm, Ångstrøm, ÅNGSTRØM, ångström, Ångström, ÅNGSTRÖM, aangstrøm, Aangstrøm, AANGSTRØM, aangström, Aangström, AANGSTRÖM, ... | angstrom, Angstrom, ANGSTROM, ångstrœm, Ångstrœm, ÅNGSTRŒM, ...                                                               |
| aangstrøm   | ångstrøm, Ångstrøm, ÅNGSTRØM, ångström, Ångström, ÅNGSTRÖM, aangstrøm, Aangstrøm, AANGSTRØM, aangström, Aangström, AANGSTRÖM, ... | angstrom, Angstrom, ANGSTROM, ångstrœm, Ångstrœm, ÅNGSTRŒM, ...                                                               |

dd
