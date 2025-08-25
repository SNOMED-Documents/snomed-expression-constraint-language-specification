# Requirements

In this chapter, we state the requirements of the SNOMED CT Expression Constraint Language. These requirements are grouped into General SNOMED CT Language Requirements (which are shared by all SNOMED CT computable languages), Expression Constraint and Query Requirements, and Concept Model Requirements.

## General SNOMED CT Language Requirements

The general SNOMED CT language requirements include:

**Requirement G.1** : Backward compatibility

The language must be backwardly compatible with any version of the language that has previously been adopted as an SNOMED International standard.

**Requirement G.2** : Consistency

Each logical feature of the language should have a single, consistent meaning across all the languages in the SNOMED CT family of languages. Each logical feature should also have a consistent set of syntax representations.

**Requirement G.3** : Sufficient and necessary

Each language must be sufficiently expressive to meet the requirements of the use cases for which it was designed. However, functionality without a corresponding use case will not be included, as this increases the complexity of implementation unnecessarily.

**Requirement G.4** : Machine processability

In order to facilitate the easy adoption by technical audiences, instances of each language must be able to be parsed into a logical representation using a machine processable syntax specification. This requirement will be met by defining the language syntax in ABNF.

**Requirement G.5** : Human readability

Non-technical stakeholders require that the language is as human readable as possible, while still meeting the other requirements. This is essential for both the clinical validation of expressions, as well as for the education and training required to author expressions.

## Expression Constraint and Query Requirements

The general expression constraint language requirements include:

**Requirement E.1** : Able to be evaluated against SNOMED CT content

Expression constraints must be able to be evaluated against a specific set of SNOMED CT content (referred to as the substrate). When evaluated against a finite set of precoordinated concepts or postcoordinated SNOMED CT expressions, a finite subset of the substrate can be found which satisfies the expression constraint.

Please note that the substrate over which the expression constraint is evaluated is not explicitly defined within the expression constraint, and must therefore be established by some other means. By default, the assumed substrate is the set of active components from the snapshot release (in distribution normal form) of the SNOMED CT versioned edition currently loaded into the given tool.

**Requirement E.2** : Expression constraint functional requirements

The expression constraint language must support the following capabilities:

<table><thead><tr><th width="270.171875">Function</th><th>Details</th></tr></thead><tbody><tr><td>Concept reference</td><td>The ability to reference a precoordinated SNOMED CT concept using its identifier and optional human-readable term.</td></tr><tr><td>Concept hierarchy</td><td>The ability to refer to a set of concepts which is exactly equal to the descendants, descendants and self, ancestors, or ancestors and self of a given concept.</td></tr><tr><td>Immediate children and parents</td><td>The ability to refer to a set of concepts which are either immediate children or immediate parents of a given concept (based on non-redundant [ 116680003</td></tr><tr><td>Conjunction</td><td>The ability to connect two expression constraints, attribute groups or attribute sets via a logical AND operator.</td></tr><tr><td>Disjunction</td><td>The ability to connect two expression constraints, attribute groups or attribute sets via a logical OR operator.</td></tr><tr><td>Refinement</td><td>The ability to refine (or specialize) the meaning of an expression constraint using one or more attributes values.</td></tr><tr><td>Reverse</td><td>The ability to constrain the source concepts of a set of relationships, and refer to the destination concepts of these relationships.</td></tr><tr><td>Dotted attribute</td><td>The ability to refer to the value (or set of values) of an attribute that is included in the definition of a set of concepts.</td></tr><tr><td>Attribute group</td><td>The ability to group a collection of attributes which operate together as part of a refinement.</td></tr><tr><td>Attribute</td><td>The ability to specify an attribute name-value pair which further refines the meaning of the matching expressions.</td></tr><tr><td>Attribute descendants</td><td>The ability to define an attribute which may apply to either the descendants of the given attribute name, or the descendants and self of the given attribute name.</td></tr><tr><td>Nesting</td><td>The ability to use an expression constraint to represent the valid set of attribute names and/or attribute values.</td></tr><tr><td>Concrete values</td><td>The ability to use integers, decimals, strings and booleans as attribute values.</td></tr><tr><td>Concrete value comparison</td><td>The ability to compare the attribute value of the matching expressions with the attribute value in the expression constraint using mathematical comparison operators (e.g. =, &#x3C;, >, &#x3C;=, >=, !=).</td></tr><tr><td>Member of</td><td>The ability to refer to a set of concepts that are referenced by members of a reference set (or set of reference sets).</td></tr><tr><td>Reference set field value selection</td><td>The ability to return the value of any non-metadata field of a reference set.</td></tr><tr><td>Exclusion</td><td>The ability to filter out a set of expressions from the result, by either removing expressions whose focus concept is in a specific set, or removing expressions whose attribute value matches a given value.</td></tr><tr><td>Any</td><td>The ability to refer to any concept in the substrate, without relying on the availability of a single root concept.</td></tr><tr><td>Description filter</td><td>The ability to filter the result set, based on the properties of each concept's descriptions. Expression constraints should be able to filter the concepts based on whether or not it has a description with a matching term, type, language, membership of a language reference set, and acceptability within that language reference set. Term matching approaches should include wildcard and word-prefix-any-order. Expression constraints should also be able to filter concepts based on the module, effectiveTime, active status and identifier of their descriptions.</td></tr><tr><td>Concept filter</td><td>The ability to filter the result set, based on the properties of each concept. Expression constraints should be able to restrict the definition status, module, effectiveTime and active status of matching concepts.</td></tr><tr><td>Member filter</td><td>The ability to filter rows of a reference set member, based on the value of specified fields.</td></tr><tr><td>History supplements</td><td>The ability to include inactive concepts that are associated with any active concept in a given result set, via an historical association reference set.</td></tr></tbody></table>

## Concept Model Requirements

The SNOMED CT concept model requirements include:

**Requirement C.1** : The ability to express SNOMED CT concept model constraints

The language must support the ability to express SNOMED CT concept model constraints, such that the resulting expression constraint can be used to validate SNOMED CT concept definitions and postcoordinated expressions.

In particular, the language must support the ability to define the domain and cardinality of each attribute in the SNOMED CT concept model, and the range of all concept model **object** attributes (whose range is a set of SNOMED CT concepts). The domain of an attribute is the set of valid source concepts of relationships of that type. In most cases, this will be defined as the descendants and self of a given concept. The range of a concept model object attribute is the set of valid destination concepts of relationships of that type. This will be defined as the set of concepts that match a given expression constraint. The cardinality of an attribute constrains the number of times an active relationship of this type can be added to a concept in the SNOMED CT snapshot release (in necessary normal form). For more information about the SNOMED CT necessary normal form, please refer to [Generating Necessary Normal Form Relationships from the OWL Refsets](https://app.gitbook.com/s/UVgNFMSypqSsi48DpFEe/design-considerations/2.5-generating-necessary-normal-form-relationships-from-the-owl-refsets "mention").

Please note that the range of a concept model **data** attribute (whose value is concrete) will be specified using a value list constraint from the [SNOMED CT Template Syntax](https://app.gitbook.com/o/h8Z6qGxuQrzM9vbx5bPT/s/zMLFwMoInWP79jP2Up2p/).
