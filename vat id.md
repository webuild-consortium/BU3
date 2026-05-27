# WE BUILD Attestation Rulebook of type VAT ID


* Author(s):
    * [Sierd Westerfield](mailto:s.westerfield@belastingdienst.nl), Tax Administration Netherlands



| Version | Date | Description |
|---------|------------|------------|
| 0.7 | 30-04-2026 | Copy from Open Social Rulebook specification |
| [VERSION NUMBER] | [PUBLICATION DATE] | [DESCRIPTION OR LINK TO THE CHANGELOG] |

*Provide a contact email address and/or a link to an issue tracking system that can be used for
providing feedback, e.g.:*

**Feedback:**

* <https://example.com/tracker>

## 1 Introduction

### 1.1 Document scope and purpose

The VAT-ID attestation is an official document issued by a recognized authority, such as the Tax Administration, that verifies the validity of a VAT-ID. This attestation serves as proof of the company’s or administrative unit’s VAT-ID and its corresponding validity period. It contains only information directly related to the VAT-ID.

The VAT-ID attestation can be utilized by a company to substantiate its identity and ownership of the provided VAT-ID. The recipient of the attestation can trust its authenticity, eliminating the need for external verification through the VAT Information Exchange System (VIES) or the request for a physical VAT-ID Certificate.

The most practical applications of the VAT-ID attestation are within procurement processes. Both the buyer and seller provide proof of their VAT ID. This eliminates the necessity of relying on external databases to verify the validity of the VAT ID.

In tender procedures, proof of the VAT ID is required. For instance, companies seeking to participate in the WeBuild project were required to submit a VAT ID Certificate to the commission. For companies based in the Netherlands, the Tax Agency was contacted to request the proof. The Tax Agency provided the proof on paper, affixed with a stamp. The company then scanned the document and uploaded it to the commission as part of its application submission.

The VAT-ID attestation also provides information on:
* The address of the economic operator.
* The economic activities in which the economic operator engages. These activities are referenced in both NACE codes, local equivalents, and a concise description of the activity.
* The period in which the VAT-ID is valid.

The VAT-ID attestation seeks to replace the traditional paper-based proof with an attestation. The VAT-ID Attestation is expected to enhance both the efficiency and security of the process. 


### 1.2 Document structure

*Provide a brief overview of the Rulebook's sections and their purpose. The main
sections of the Rulebook SHOULD be*

* Chapter 2, which describes the attestation attributes and metadata in an
encoding-independent manner.
* Chapter 3, which specifies how the attestation
attributes and metadata are encoded in case the attestation complies with [ISO/IEC
18013-5] and/or [SD-JWT VC] and/or [W3C VCDM v2.0]. Each encoding SHALL be specified in a separate section, or even in a separate chapter.
* Chapter 4, which specifies attestation usage.
* Chapter 5, which defines how trust anchors for attestation verification can be obtained.
* Chapter 6, which defines attestation revocation mechanisms.
* Chapter 7, which provides compliance information.

### 1.3 Key words

*The following are the recommended keywords. Modify if necessary*

This document uses the capitalised key words 'SHALL', 'SHOULD' and 'MAY' as
specified in [RFC 2119], i.e., to indicate requirements, recommendations and
options specified in this document.

In addition, 'must' (non-capitalised) is used to indicate an external
constraint, i.e., a requirement that is not mandated by this document, but, for
instance, by an external document. The word 'can' indicates a capability,
whereas other words, such as 'will', and 'is' or 'are' are intended as
statements of fact.

### 1.4 Terminology

*It is recommended to use the terminology defined in Annex 1 of ARF. For example
the following text can be used.*

This document uses the terminology specified in Annex 1 of the ARF.

## 2 Attestation attributes and metadata

### Chapter overview and requirements

*This chapter is used for defining all attributes that an
attestation of the defined type may contain. In this section
the attributes SHALL be defined in an encoding-independent manner (see ARB_06 in [Topic 12]).
Each attribute can be mandatory, optional, or conditional
and this SHALL be specified in the corresponding section (see ARB_09 in [Topic 12]).*

*When attributes are defined, referring to attributes that
already exist in a catalogue of attestation attributes
SHOULD be considered (see ARB_07 in [Topic 12]).*

*Where use-case documentation or an attestation description already defines attribute meanings,
logical models, code lists, or integrity constraints, authors SHOULD align terminology with those
sources and may copy and refine that material for this Rulebook.*

*[Topic 12] of Annex 2 of the ARF defines the following High-Level Requirements with
respect to the Attestation Rulebooks:*

**Requirements for QEAA**

* An attribute as meant in Annex V point a)  of the [European Digital Identity Regulation]
SHALL be included (see ARB_11 in [Topic 12]). See also section 2.1.
* One or more attributes or metadata representing the set of data meant in Annex
V point b) of the [European Digital Identity Regulation] SHALL be included (see ARB_13 in [Topic 12])
* One or more attributes representing the set of data meant in Annex V point c)  
of the [European Digital Identity Regulation] SHALL be included (see ARB_16 in [Topic 12]).
* One or more attributes or metadata representing the set of data meant in Annex V point e)
of the [European Digital Identity Regulation] SHALL be included (see ARB_18 in [Topic 12]).
* One or more attributes or metadata representing the location meant in Annex V point h)
of the [European Digital Identity Regulation] SHALL be included. This location SHALL
indicate at least the URL at which a machine-readable version of the trust anchor to be
used for verifying the QEAA can be found or looked up (see ARB_20 in [Topic 12]).

**Requirements for PuB-EAA**

* An attribute as meant in  Annex VII point a) of the [European Digital Identity Regulation]
SHALL be included (see ARB_11 in [Topic 12]). See also section 2.1.
* One or more attributes or metadata representing the set of data meant in Annex
 VII point b) of the [European Digital Identity Regulation] SHALL be included (see ARB_14 in [Topic 12]).
* One or more attributes representing the set of data meant in Annex VII point c)
of the [European Digital Identity Regulation] SHALL be included (see ARB_16 in [Topic 12]).
* One or more attributes or metadata representing the set of data meant in Annex VII point e)
of the [European Digital Identity Regulation] SHALL be included (see ARB_18 in [Topic 12]).
* one or more attributes or metadata representing the location meant in Annex VII point h)
of the [European Digital Identity Regulation] SHALL be included. This location SHALL
indicate at least the URL at which a machine-readable version of the qualified
certificate that signed the PuB-EAA can be found or looked up. (see ARB_20 in [Topic 12])


### 2.1 Introduction

The VAT-ID attestation is an attestation provided by an authentic source such as a TAX-Administration. The attestation proves the VAT-ID of the company or administrative unit within the company and the validity period of that VAT-ID. The VAT-ID attestation only contains information directly related to the VAT-ID. 
The VAT-ID attestation can be used by a company to prove that the company really is the company with that number. The receiver of the attestation can trust the content and there is no need for checking the VAT-ID at VIES (VAT Information Exchange System)1 or request a (paper) VAT-ID Certificate. 

*According to Annex V point a) and  Annex VII point a) of the [European Digital Identity Regulation]
an indication, at least in a form suitable for automated processing, that the attestation
has been issued as a QEAA or Pub-EAA SHALL be defined. Similarly, according to ARB_12
of [Topic 12] of Annex 2 of the ARF a similar indication SHOULD be defined for non-qualified EAA.

This document defines the attribute "VAT-ID" which SHALL have
the value "QEAA" or "PuB-EAA".*
````
Administrative unit
├─ Administrative_Unit_Name                [1]       (Name of the Administrative Unit)
├─ Validity_Period                         [1..n]    (Period(s) for which the VAT-ID is valid)
│   ├─ start_Date                          [1]       (start date of the validity period of the VAT-ID)
│   └─ end_Date                            [0]       (end date of the validity period of the VAT-ID)
├─ Validity_Area_Limitation                [0..n]    (array of countries in which the VAT-ID may be used)
├─ Adminitrative_Unit_Type                 [0]       (Type of Organisation in free text)
├─ Administrative_Unit_Address             [0]       (The postal address registered for the Administrative unit)
│   ├─ po_box                              [0]  
│   ├─ thoroughfare                        [0]  
│   ├─ location_designator                 [0]  
│   ├─ post_code                           [0]  
│   ├─ post_name                           [0]  
│   ├─ admin_unit_L1                       [0]  
│   └─ admin_unit_L2                       [0]  
├─Economic_Activity_Type                   [0..n]    (reference to the economic operator)
│   ├─ Economic_Activity_Type_Nomenclature [1]       (nomenclature used to describe the economic activity)
│   ├─ Economic_Activity_Type_ID           [1]       (id used in the nomenclature)
│   └─  Economic_Activity_Type_Description [0..n]
│      ├─ Language                         [1]  
│      └─ Description                      [1]
└─ Issuer                                  [1]   
    ├─ Issuing_country                     [1]
    ├─ Issuing_organisation                [1]        (the organisation that issues the VAT-ID, this may differ from the Attestation issuing organisation)
    ├─ Issuing_date                        [1]        (date on which the attestation is issued)
    └─ Attestation_issuing_Organisation    [1]

````


### 2.2 Administrative Unit 
#### 2.2.1 Mandatory attributes
| Data Identifier                | Semantic Reference                          | Definition                              | Data Type       | Example Value      |
|--------|----------|--------------------------------------------------------------------------|------------|--------------|
| VAT_ID                         | VAT Identification Number                   | Unique identifier for VAT purposes     | String           | DE123456789        |
| Administrative_Unit_Name       | Name of the Administrative Unit             | Name of the unit responsible for VAT    | String           | Siemens        |
| Validity_Period                | Period of Validity                          | Duration during which the data is valid| Date Range       | 2026-01-01 to 2026-12-31 |
| Economic_Operator              | Operator conducting economic activity       | Entity responsible for economic operations | Economic Operator object        | ..|
| Issuer                         | Issuing Authority                           | Authority that issues the VAT ID       | Issuer Object           | ..   |



#### 2.2.2 Optional attributes
| **Data Identifier**  | **Semantic Reference** | **Definition** | **Data type** | **Example value** |
|--------|----------|--------------------------------------------------------------------------|------------|--------------|
| Administrative_Unit_Type       | ...                 | Type (e.g., Government, Local Authority)| Economic Activity Type Object | ...          |
| Administrative_Unit_Address    | ...          |  The address where the company is located based on the information from the authentic source of the VAT-ID. This address may differ from the address in the business register.           | Address Object           | ...  |
| Validity_Area_Limitation      | ...               | Country in which the VAT_ID may be used. Alpha‑2 country code, as specified in ISO 3166‑2. Omit if there are no restrictions    | array of tstr            | DE |

### 2.3 Economic Operator 
#### 2.3.1 Mandatory attributes
There SHALL be a reference from the Administrative Unit to the Economic Operator. However the the Economic Operator can either be a [Legal Person](https://iri.suomi.fi/terminology/webuild/concept-109) or a [Natural Person](https://iri.suomi.fi/terminology/webuild/concept-6005). The economic operator object SHALL be filled to one of the two, not to both. 

#### 2.3.2 Optional attributes

| **Data Identifier** | **Semantic Reference** | **Definition** | **Data type** | **Example value** |
|--------|----------|---------------------------------------------------------------|------------|--------------|
| economic_Operator.legal_identifier| [legalIdentifier](https://iri.suomi.fi/terminology/webuild/legalidentifier) |The relevant unique identifier attributed in accordance with Article 9 of EWB (WEBUILD specific EUID where available, otherwise a similar constructed, unique per issuer identifier. <Countrycode ISO 3166-1 alpha-2>. eks. SE +  BOLREG + 123456789 -> SEBOLREG.123456789 | tstr | SEBOLREG.123456789 |
|economic_Operator.legal_name|[legalName](https://iri.suomi.fi/terminology/webuild/legalname) | the name under which the legal entity is legally registered|tstr| ACME |
| economic_Operator.family_name| [familyName](https://ebw-vocabulary.spherity.dev/ebw/v0.1/vocabulary#familyName) | Current last name(s) or surname(s) of the user to whom the person identification data relates. |tstr| Doe|
| economic_Operator.given_name| [givenName](https://ebw-vocabulary.spherity.dev/ebw/v0.1/vocabulary#givenName) | Current first name(s), including middle name(s) where applicable, of the user to whom the person identification data relates.|tstr|John|
| economic_Operator.birth_date| [dateOfBirth](https://ebw-vocabulary.spherity.dev/ebw/v0.1/vocabulary#dateOfBirth) | Day, month, and year on which the user to whom the person identification data relates was born. |Date|27-04-1968|
| economic_Operator.birth_place| [placeOfBirth](https://ebw-vocabulary.spherity.dev/ebw/v0.1/vocabulary#placeOfBirth) | The country as an alpha-2 country code as specified in ISO 3166-1, or the state, province, district, or local area or the municipality, city, town, or village where the user to whom the person identification data relates was born. |tstr|Amsterdam|
|economic_Operator.Tin| tin |tax reference number |tstr||
|economic_Operator. personal_Administrative_Number|[personalAdministrative Number](https://webuild-consortium.github.io/wp4-semantics-group/ebwv/vocabulary.html#personalAdministrativeNumber)|A value assigned to the natural person that is unique among all personal administrative numbers issued by the provider of person identification data. The personal Administrative Number may only be used if the local law allows for unrestricted use|tstr|123456782|


### 2.4 Validity Period
#### 2.4.1 Mandatory attributes
| **Data Identifier** | **Semantic Reference** | **Definition** | **Data type** | **Example value** |
|--------|----------|--------------------------------------------------------------------------|------------|--------------|
| validity_Period.start_Date| [PeriodOfTime.startDate](https://webuild-consortium.github.io/wp4-semantics-group/ebwv/vocabulary.html#startDate) | Date of registration of the VAT-ID. | date |2011-12-24 | 

### 2.4.2 Optional attributes

| **Data Identifier** | **Semantic Reference** | **Definition** | **Data type** | **Example value** |
|--------|----------|--------------------------------------------------------------------------|------------|--------------|
| validity_Period.end_Date | [PeriodOfTime.endDate](https://webuild-consortium.github.io/wp4-semantics-group/ebwv/vocabulary.html#endDate) | The end date after which VAT-ID registration ended. | date | 2021-1-24|

### 2.5 Address
#### 2.5.1 Mandatory attributes
No mandatory attributes
#### 2.5.2 Optional attributes
| **Data Identifier** | **Semantic Reference** | **Definition** | **Data type** | **Example value** |
|--------|----------|--------------------------------------------------------------------------|------------|--------------|
| address.po_box | [registeredAddress.poBox](https://webuild-consortium.github.io/wp4-semantics-group/ebwv/vocabulary.html#poBox) | P.O. box number or identifier within the address; optional | tstr | PO Box 123 |
| address.thoroughfare | [registeredAddress.thoroughfare](https://sanastot.suomi.fi/en/terminology/webuild/concept/thoroughfare) | Street name and house number or other thoroughfare designation; optional | tstr | Main Street 10 |
| address.location_designator | [registeredAddress.locationDesignator](https://iri.suomi.fi/terminology/webuild/locatordesignator) | Internal location designation within a building (e.g., floor, unit); optional | tstr | Floor 3, Unit B |
| address.post_code | [registeredAddress.postCode](https://iri.suomi.fi/terminology/webuild/postcode) | Postal or ZIP code; optional | tstr | 12345 |
| address.post_name | [registeredAddress.postName](https://iri.suomi.fi/terminology/webuild/postname) | Town or locality name; optional | tstr | Amsterdam |
| address.admin_unit_L1 | [registeredAddress.adminUnitL1](https://iri.suomi.fi/terminology/webuild/adminUnitL1) | First-level administrative division (e.g., province, state); optional | tstr | North Holland |
| address.admin_unit_L2 | [registeredAddress.adminUnitL2](https://iri.suomi.fi/terminology/webuild/adminUnitL2) | Second-level administrative division (e.g., district, municipality); optional | tstr | Amsterdam Municipality

### 2.6 Economic Activity Type attributes
#### 2.6.1 Mandatory attributes

| **Data Identifier** | **Semantic Reference** | **Definition** | **Data type** | **Example value** |
|--------|----------|--------------------------------------------------------------------------|------------|--------------|
| Economic_Activity_Type.Nomenclature| tbd | The nomenclature that is used to describe the administrative unit. NACE should be used as default. However some countries have more elaborate nomenclature.| tstr | nace |
| Economic_Activity_Type.ID | tbd | The ID that under which the Administrative unit is registered.|tstr | C26.5.2 |
| Economic_Activity_Type.Description |Economic Activity Description| The human readable text that describes the economic ativity in a specific language|array|
### 2.8 Description attributes
#### 2.8.1 Mandatory attributes
| **Data Identifier** | **Semantic Reference** | **Definition** | **Data type** | **Example value** |
|--------|----------|--------------------------------------------------------------------------|------------|--------------|
|Description.Language|Languae| The language used for the description using ISO 639-1| tstr | nl|
|Description.Text|	The Description in plain text readable for the end user | tstr | Manufacture of bearings, gears, gearing and driving elements|

### 2.9 Metadata
#### 2.9.1 Mandatory metadata 

| **Data Identifier** |**Semantic Reference** | **Definition** | **Data type** | **Example value** | 
|--------|----------|--------------------------------------------------------------------------|------------|--------------|
| issuer.authentic_source_country   | issuing_country  | Alpha‑2 country code, as specified in ISO 3166‑2, of the country or territory of the provider of the VAT ID. |date | 05 | 
| issuer.VAT_ID_AuthenticSource   | authenticSource | Name of the administrative authority that issued the VAT ID. | tstr| |
| issuer.country   |issuing_country  | Alpha‑2 country code, as specified in ISO 3166‑2, of the country or territory of the provider of the VAT ID. |tstr |     | 
| issuer.issuing_authority   | issuerAuthority| Name of the administrative authority or qualified trust service provider that issued the VAT ID attestation. |tstr|  |
| issuer.attestation_legal_category  | issuerLegalCategory| The type of attestation category. (Pub-EAA/QEAA)      |tstr| PUB-EAA  |
| issuer.attestation_issuing_date| issuingDate| The date the attestation was issued|date| 2025-12-5|


#### 2.7.2 Optional metadata

| **Data Identifier** |**Semantic Reference** | **Definition** | **Data type** | **Example value** | 
|--------|----------|--------------------------------------------------------------------------|------------|--------------|
| issuer.location_status      | locationStatus| The location of validity status information on the VAT ID used for revocation/suspension checks.|tstr||
| trust_anchor         | trustAnchor| This meta-data attribute indicates at least the URL at which a machine‑readable version of the trust anchor to be used for verifying the VAT ID can be found or looked up. This corresponds to Annex V/VII point h) of the [European Digital Identity Regulation] and EBW Article 8 issuance as EAA/QEAA.  |tstr||



### 2.8 Code lists

*Use this section for controlled vocabularies, enumerations, value sets, or external catalogues
that are necessary to interpret one or more attributes or metadata items. Definitions may be reused
from the attestation description or other use-case documentation and refined here where needed.*

*For each code list, authors SHOULD state the field to which it applies, the allowed values, their
meaning, the source vocabulary or reference, and any extensibility rule or governance note.*

| **Field name** | **Allowed values** | **Meaning** | **Source / vocabulary** | **Notes / extensibility** |
|--------|----------|--------------------------------------------------------------------------|------------|--------------|
| Economic_Activity_Type.Nomenclature | NACE-BEL, CZ‑NACE, DB07, WZ, KAD, CNAE, NAF, NKD, ATECO, TEAOR, SBI, ONACE, PKD, CAE, CAEN, SKD, OKEC, TOL, SNI, UK SIC, NOGA| Each name refers to the local adaptation of the NACE list. | [Overview of alternative nomenclatures](#81-list-of-alternative-nace-codes)| List SHOULD be used or refer to NACE closest alternative |


### 2.9 Integrity rules

*Use this section to define integrity or consistency rules that are not fully captured by the
encoding format or schema alone, such as cross-field dependencies, temporal consistency checks,
mutual exclusivity, or conditional combinations of values.*

*Integrity rules may be copied and refined from an attestation description, logical model, or
business-rule specification where available.*

| **Rule ID** | **Rule statement** | **Why it exists** | **Where enforced** | **Verifier / issuer behavior on failure** |
|-------------|--------------------|-------------------|--------------------|-------------------------------------------|
| EO 1 | If 'economic_Operator.legal_identifier' is present, only 'economic_Operator.legal_name', all other variables SHALL be NULL. If 'economic_Operator.legal_identifier' is NULL, 'Tin' OR 'personal_Administrative_Number' OR "Personal Identifiers that can be linked to the PID" SHALL be filled. | There may only be one reference to the holder of the Wallet. If there is more than one, there could be an inconsistancy  | *Issuer, verifier, schema validation, or business process* | *Describe rejection, warning, or remediation behavior* |
| VP 1 | If 'validity_Period.end_Date' is not NULL, 'validity_Period.end_Date' SHALL be higher than 'validity_Period.start_Date'| Validity periods may not be negative | The VAT-ID attestation may not be issued, because there shouldn't be a negative period in the register|
| VP 2 | If any 'validity_Period' overlaps with another validity period the attestation SHALL NOT be issued| Validity periods may not overlap because this should not happen and might create problems for relying parties. This rule also takes care of the issue of multiple validity periods without an enddate||
| VP 3 | If 'validity_Period.end_Date' is more than 5 years in the past, the validity period SHOULD be omited. | Old validity periods are not relevant to relying parties, the limit of 5 years should be used as a rule of thumb ||
| VP 4 | If there is more than one 'validity_Period' the issuer MAY omit older validity_Periods| Issuers have the freedom to omit older validity periods, when they find they are not relevant ||
| EA 1 | If ('Economic_Activity_Type.ID' AND 'Economic_Activity_Type.Nomenclature <>"NACE")  is equal ('Economic_Activity_Type.ID' AND 'Economic_Activity_Type.Nomenclature == "NACE") Then 'Economic_Activity_Type.Nomenclature SHOULD be "NACE"| The default Nomenclature is NACE, if the ID in the local Nomenclature directly relates to the NACE ID, the NACE ID and TYPE SHOULD be used. | Issuers SHOULD implement a tranlation table to create mostly NACE codes|


# 3 Attestation encoding

## 3.1 ISO/IEC 18013-5-compliant encoding

*If the attestation type supports the the format specified in ISO/IEC 18013-5,
then in this section the  ISO/IEC 18013-5-compliant encoding of attributes and metadata
should be defined.*

*It is noted that (see ARB_02 in [Topic 12]) the Schema Provider SHALL analyse whether it must
be possible for a User to present that type of attestation when the Wallet Unit
and the Relying Party are in proximity and attestations are presented without
using the internet. If so,the attestations must be issued in the ISO/IEC 18013-5-compliant
mdoc format.*

*Furthermore, in this section a document type SHALL be defined, which SHALL be
unique within the scope of the EUDI Wallet ecosystem (see ARB_05 in [Topic 12]).*

[RULEBOOK AUTHOR TO DEFINE THE ATTESTATION TYPE]

*Provide a list of available encoding formats and their specifications (e.g., encoding, maximum lengths,
date formats, etc). For example:*

* tstr, uint, bstr, bool and tdate are CDDL representation types defined in
  [RFC 8610].
    * Regarding type tstr: this document confirms that, as specified in [RFC
    8949], a tstr SHALL be encoded in UTF-8 and SHALL support the full Unicode
    range.
    * All attributes having encoding type tstr SHALL have a maximum length of
    150 characters.
    * This document specifies full-date as full-date = #6.1004(tstr), where tag
    1004 is specified in [RFC 8943].
    * In accordance with [RFC 8949], section 3.4.1, a tdate attribute SHALL
    contain a date-time string as specified in [RFC 3339]. In accordance with
    [RFC 8943], a full-date attribute SHALL contain a full-date string as
    specified in [RFC 3339].
    * The following requirements apply to the representation of dates in
    attributes, unless otherwise indicated:
        * Fractions of seconds SHALL NOT be used;
        * A local offset from UTC SHALL NOT be used; the time-offset defined in
        [RFC 3339] SHALL be to "Z".
    * [RFC 8949], section 4.2, describes four rules for canonical CBOR. Three of
    those rules SHALL be implemented for all CBOR structures, as
    follows:
        * integers (major types 0 and 1) SHALL be as small as possible;
        * the expression of the length in a bstr, tstr, array or map SHALL be as
        short as possible;
        * indefinite-length items SHALL be made into definite-length items.

*This section should include a table the data identifier specified in
Chapter 2,  the corresponding attribute identifier to be used in
presentation requests and responses according to [ISO/IEC 18013-5] and the encoding
of each attribute.*

*Additionally, the following rules should be followed:*

* When specifying new attributes, existing conventions
for attribute identifier values and attribute syntaxes SHOULD
be considered (see ARB_07 in [Topic 12]).
* Each attribute SHALL be defined within an attribute namespace.
    * An attribute namespace
SHALL fully define the identifier, the syntax, and the semantics of each attribute
within that namespace.
    * An attribute namespace SHALL have an identifier that is
unique within the scope of the EUDI Wallet ecosystem, and each attribute
identifier SHALL be unique within that namespace (see ARB_06a in [Topic 12])
    * A domestic namespace MAY defined
to specify attributes that are specific to this Rulebook and are not included in
the applicable EU-wide or sectoral namespace (see ARB_10 in [Topic 12]).

| **Data Identifier** | **Attribute identifier** | **Encoding format** | **Namespace**|
|------------------------|--------------|------------------|------------------|
| family_name | family_name | tstr | com.example.att.1|

*The corresponding entry for the "attestation_legal_category" attribute defined
in Section 2.1 SHALL be:*

| **Data Identifier** | **Attribute identifier** | **Encoding format** |**Namespace**|
|------------------------|--------------|------------------|------------------|
| attestation_legal_category | attestation_legal_category | tstr |com.example.att.1|

Finally, illustrative examples SHALL be included.

[RULEBOOK AUTHOR TO PROVIDE AN EXAMPLE OF FULL OR PARTIAL mDOC OF THE ATTESTATION]

[RULEBOOK AUTHOR TO PROVIDE THE ATTRIBUTES AND THEIR VALUES INCLUDED IN THE EXAMPLE]

### 3.2 SD-JWT VC-based encoding

*If the attestation type supports the format specified in "SD-JWT-based Verifiable
Credentials (SD-JWT VC)", then in this section the SD-JWT VC-compliant encoding
of attributes and metadata SHALL be defined. It SHALL be ensured that the attestations
comply with the 'SD-JWT VCs' profile specified in [HAIP] (see ARB_01b in [Topic 12]).*

*It is noted that a Schema Provider MAY specify in the Attestation
Rulebook that that type of attestation must be issued in the [SD-JWT VC]-compliant
format, provided the [SD-JWT VC] specification has been approved by an EU standardisation
body or by the European Digital Identity Cooperation Group established pursuant to
Article 46e(1) of the [European Digital Identity Regulation] (see ARB_03 in [Topic 12]).*

*In this section, a Verifiable Credential Type (`vct`) SHALL be defined,
which SHALL be unique within the scope of the EUDI Wallet ecosystem (see ARB_05 in [Topic 12]).*

[RULEBOOK AUTHOR TO DEFINE THE ATTESTATION TYPE]

*Additionally, when specifying new attributes, existing conventions
for attribute identifier values and attribute syntaxes SHOULD
be considered (see ARB_07 in [Topic 12]).*

*Rulebook authors SHALL ensure that each claim name is either

* included in the IANA registry for JWT claims,
* is a Public Name as defined in [RFC 7519], or
* or is a Private Name specific to the attestation type. (see ARB_06b in [Topic 12]).*

*For all claims (i.e., all top-level properties, all nested properties, and all array entries),
the Rulebook SHALL specify whether an Attestation Provider MUST, MAY, or MUST NOT make that
claim selectively disclosable (see ARB_30 in [Topic 12]).*

*Rulebook authors SHOULD consider defining a Type Metadata Document for the attestation type
specified in the Rulebook, as defined in Chapter 6 of [SD-JWT VC]. If such a document is defined,
it SHOULD contain the Claim Selective Disclosure Metadata (defined in Section 9.3 of [SD-JWT VC])
for each of the claims, in order to specify if that claim is selectively disclosable (see ARB_31
in [Topic 12]).*

*IANA-registered claims should be presented in table that
includes their data identifier, attribute identifier,
encoding format, and reference or note. For example,*

| **Data Identifier** | **Attribute identifier** | **Encoding format** |**Reference/Notes** |**Disclosable**|
|-------------------- |--------------------------|---------------------|--------------------|---------------|
| family_name | family_name | string | Section 5.1 of [OIDC] | MUST |

*A similar table should be used for Public Names and for Private Names specific
to the attestation type defined in this document. For
example:*

| **Data Identifier** | **Attribute identifier** | **Encoding format** | **Notes** |**Disclosable**|
|---------------------|--------------------------|---------------------|-----------|---------------|
| trust_anchor | trust_anchor | string | The trust anchor defined in Section 5 | MUST NOT |

*The corresponding entry for the "attestation_legal_category" attribute defined
in Section 2.1 SHALL be:*

| **Data Identifier** | **Attribute identifier** | **Encoding format** | **Notes** |**Disclosable**|
|---------------------|--------------------------|---------------------|-----------|---------------|
| attestation_legal_category | attestation_legal_category | string | Defined in Attestation Rulebook template |MUST NOT|

Finally, illustrative examples SHALL be included.

[RULEBOOK AUTHOR TO PROVIDE AN EXAMPLE OF THE JWT CLAIM SET USED BY THE PROVIDER]

[RULEBOOK AUTHOR TO PROVIDE AN EXAMPLE OF THE ISSUED SD-JWT (IN base64 ENCODING)]

[RULEBOOK AUTHOR TO PROVIDE AN EXAMPLE OF A HUMAN READABLE VERSION OF THE SD-JWT PAYLOAD
AND A DESCRIPTION OF THE DISCLOSURES INCLUDED IN THE EXAMPLE]

### 3.3 W3C Verifiable Credentials Data Model-based encoding

*If the attestation type supports the the format specified in W3C Verifiable Credentials
Data Model, then in this section the  corresponding encoding  of attributes and
metadata should be defined.*

*It is noted that only a a non-qualified EAA can use this format (see ARB_01a in [Topic 12])*

*Tables similar to the ones specified in section 4 SHALL be defined.*

*This section SHALL reference one or more documents specifying in detail how a
Relying Party can request attributes from a such an attestation, and how a User
can selectively disclose attributes from such an attestation. Moreover, these
referenced documents SHALL be approved by an EU standardisation body or by the European
Digital Identity Cooperation Group established pursuant to Article 46e(1) of the
[European Digital Identity Regulation] (see ARB_04 in [Topic 12]).*

*Finally, illustrative examples SHALL be included.*

[RULEBOOK AUTHOR TO PROVIDE HUMAN READABLE EXAMPLE OF THE ISSUED ATTESTATION]

[RULEBOOK AUTHOR TO PROVIDE AN EXAMPLE OF THE PROOF TYPE]

## 4 Attestation usage

*Briefly describe the primary use cases or scenarios for which this attestation
type is intended*

*Additionally, in this section it SHOULD  be specified whether a Relying Party receiving the attestation
must request and verify a PID (see ARB_27 in [Topic 12]). Also beyond PID verification,
it SHOULD be defined what other key obligations does a Relying Party have when processing
this attestation type (e.g., signature verification, freshness checks)*

*Furthermore, provide potential presentation requirements, e.g., are there specific
requirements for how this attestation must be presented (e.g., online, offline, specific protocols)?"*

*Specify whether an attestation of this type SHALL or SHOULD be device-bound or non-device-bound, see ARB_34 in [Topic 12]*

*If an attestation of this type is device-bound, specify if it SHALL, SHOULD or MAY be cryptographically bound to another type of attestation on the same Wallet Unit. If needed (based on this decision), include the attribute `cryptographically_bound_to` defined in ARB_28 as an optional, recommended, or mandatory attribure in [Section 2.5](#26-optional-metadata). If present in an Attestation Rulebook, the identifier for this attribute SHALL be "cryptographically_bound_to" for both ISO/IEC 18013-5 and SD-JWT VC-compliant attestations, and its contents SHALL be a `tstr` or `string` (as applicable) containing an attestation type or vct (see ARB_05). Finally, specify the value of the `tstr` or `string`.* 

*EXAMPLE   In case an attestation type of this type must be bound to a PID, the value of the `tstr` or `string` must be set to "eu.europa.ec.eudi.pid.1" or "urn:eudi:pid:1". Note that it does not matter whether the attestation type or the vct value is used.*

*Finally, in this section information about potential transactional data
SHALL be defined; see [Topic 20] of Annex 2 of the ARF.*

## 5 Trust anchors

*Mechanisms for the provision of a trust anchor that SHALL
be used for the verification of an attestation SHALL be defined in this section.*

*It is noted that the ARF specifies the following for QEAAs and Pub-EAAs:*

> To do this for [...] QEAAs the Relying Party Instance uses a trust anchor of
the Provider obtained from a Trusted List. Note that the PID Provider or QEAA
Provider may use an intermediate signing certificate to sign the PID or
attestation, and use the trust anchor to sign the signing certificate, instead
of signing the PID or attestation directly with the trust anchor.
>
> For PuB-EAAs, the Relying Party Instance verifies a PuB-EAA by first
verifying the signature of the PuB-EAA Provider over the PuB-EAA, using the
PuB-EAA Provider certificate issued by a QTSP. Subsequently, the Relying Party
Instance verifies the signature over this certificate, using the corresponding
trust anchor from the QTSP Trusted List. Note that both the PuB-EAA Provider
and the QTSP may use an intermediate signing certificate. All other things
being equal, the verification of a PuB-EAA will therefore involve one or more
extra certificates, compared to the verification of a PID or QEAA.

*For non-qualified EAA in this section it SHOULD  be defined (see ARB_26 in [Topic 12])
how the attributes or metadata representing the location at which a machine-readable
version of the trust anchor to be used for verifying the attestation can be found,
specified in section 2, are used. This includes a detailed description about how
a Relying Party can obtain the trust anchors, as well as a detailed description about
how this trust anchor can be used for verifying that the provider is authorized
to issue the attestation. Additionally, for non-qualified EAA Providers this section
MAY include a description of mechanisms that can be used by a Wallet Unit for
verifying that the provider is authorized to issue this type of attestation (see
ISSU_34 in [Topic 10])*

## 6 Revocation

(Refer to [Topic 7] of the ARF for a list of High-Level Requirements related to Revocation)

*In this section information about the revocation mechanism used SHALL be defined.*

*For PID, QEAA, or PuB-EAA it SHALL  be defined whether  only short-lived attestations
will be used, having a validity period of 24 hours or less, such that revocation
will never be necessary, or that the attestations are revocable.*

*For revocable attestations it SHALL be defined which of the following methods must be implemented:*

* Use an Attestation Status List mechanism included in a Technical Specification
that will be specified by the Commission.
* Use an Attestation Revocation List mechanism included in a Technical Specification
that will be specified by the Commission.

## 7 Compliance

*In this section explicitly state how this specific rulebook complies with the
general EUDI framework, ARF, and relevant regulations*

[RULEBOOK AUTHOR TO DEFINE]

## 8 References

| **Item Reference** | **Standard name/details**|
|--------------------|---------------------------|
| [European Digital Identity Regulation] | [Regulation (EU) 2024/1183](https://eur-lex.europa.eu/legal-content/EN/TXT/HTML/?uri=OJ:L_202401183) of the European Parliament and of the Council of 11 April 2024 amending Regulation (EU) No 910/2014 as regards establishing the European Digital Identity Framework |
| [HAIP] | Yasuda, K. *et al,* OpenID4VC High Assurance Interoperability Profile, OpenId Foundation, Version draft-03 |
| [IANA-JWT-Claims] | IANA JSON Web Token Claims Registry. Available: <https://www.iana.org/assignments/jwt/jwt.xhtml> |
| [ISO/IEC 18013-5] |  ISO/IEC 18013-5, Personal identification --- ISO-compliant driving licence - Part 5: Mobile driving licence (mDL) application, First edition, 2021-09 |
| [OIDC] | Sakimura, N. et al., "OpenID Connect Core 1.0", OpenID Foundation. Available: <https://openid.net/specs/openid-connect-core-1_0.html> |
| [RFC 3339] | RFC 3339  - Date and Time on the Internet: Timestamps, G. Klyne et al., July 2002 |
| [RFC 8610] | RFC 8610  - Concise Data Definition Language (CDDL): A Notational Convention to Express Concise Binary Object Representation (CBOR) and JSON Data Structures, H. Birkholz et al., June 2019 |
| [RFC 8943] | RFC 8943  - Concise Binary Object Representation (CBOR) Tags for Date, M. Jones et al., November 2020 |
| [RFC 8949] | RFC 8949 - Concise Binary Object Representation (CBOR), C. Bormann et al., December 2020 |
| [SD-JWT VC] |  SD-JWT-based Verifiable Credentials (SD-JWT VC). Available: <https://datatracker.ietf.org/doc/draft-ietf-oauth-sd-jwt-vc/>, version draft-ietf-oauth-sd-jwt-vc-09  |
| [Topic 7] | ARF Annex 2 - Topic 7 - Attestation revocation and revocation checking Available: <https://eu-digital-identity-wallet.github.io/eudi-doc-architecture-and-reference-framework/latest/annexes/annex-2/annex-2-high-level-requirements/#a237-topic-7-attestation-revocation-and-revocation-checking>|
| [Topic 10] | ARF Annex 2 - Topic 10 - Issuing a PID or attestation to a Wallet Unit: <https://eu-digital-identity-wallet.github.io/eudi-doc-architecture-and-reference-framework/latest/annexes/annex-2/annex-2-high-level-requirements/#a2310-topic-10-issuing-a-pid-or-attestation-to-a-wallet-unit>|
| [Topic 12] | ARF Annex 2 - Topic 12 - Attestation Rulebooks, Available: <https://eu-digital-identity-wallet.github.io/eudi-doc-architecture-and-reference-framework/latest/annexes/annex-2/annex-2-high-level-requirements/#a2312-topic-12-attestation-rulebooks>|
| [Topic 20] | ARF Annex 2 - Strong User authentication for electronic payments, Available: <https://eu-digital-identity-wallet.github.io/eudi-doc-architecture-and-reference-framework/latest/annexes/annex-2/annex-2-high-level-requirements/#a2320-topic-20-strong-user-authentication-for-electronic-payments>|
| [W3C VCDM v2.0] | Sporny, M. *et al,* Verifiable Credentials Data Model v2.0, W3C Recommendation.  |


### 8.1 List of Alternative Nomenclatures for Activity types

Generated by DUCK.AI using ChatGPT 5.1 mini

| Country | National implementation / name |
|---|---|
| Belgium | NACE-BEL |
| Bulgaria | NACE (Bulgarian implementation, Rev.2) |
| Czech Republic | CZ‑NACE |
| Denmark | DB07 / Danish adaptations (mapped to NACE) |
| Germany | WZ 2008 (Klassifikation der Wirtschaftszweige) |
| Estonia | NACE (Estonian implementation) |
| Ireland | NACE (CSO adapted list) |
| Greece | KAD (Classification of Economic Activities) |
| Spain | CNAE |
| France | NAF |
| Croatia | NKD |
| Italy | ATECO (ISTAT) |
| Cyprus | NACE (Cyprus Statistical Service) |
| Latvia | NACE (Latvian implementation) |
| Lithuania | NACE (Lithuanian implementation) |
| Luxembourg | NACE (STATEC) |
| Hungary | TEÁOR (TEÁOR 08) |
| Malta | NACE (NSO) |
| Netherlands | SBI (Standard Industrial Classification) |
| Austria | ÖNACE |
| Poland | PKD |
| Portugal | CAE |
| Romania | CAEN |
| Slovenia | SKD |
| Slovakia | SK NACE / OKEČ |
| Finland | TOL |
| Sweden | SNI |
| United Kingdom* | UK SIC (historical mappings to NACE) |
| Norway | NACE‑mapped national classification (Statistics Norway) |
| Iceland | NACE/ISIC mappings (Statistics Iceland) |
| Liechtenstein | NACE‑mapped classification |
| Switzerland | NOGA |

*The UK is no longer an EU member; included due to extensive historical mappings.
