<h3 id="conformance-verbs"> Conformance Verbs</h3>
The conformance verbs - SHALL, SHOULD, MAY - used in this guide are defined in <a href="http://hl7.org/fhir/R4/conformance-rules.html">FHIR Conformance Rules.</a>.

<h3 id="must-support">Must Support</h3>
For profiles defined in other IGs, the meaning of Must Support is established in the defining IG. 
<br>
Note that the Must Support requirements for this IG are modeled after the US Core implementation guide, with the requirements for CARIN Server APIs modeled on those for US Core Responders, and the requirements for CARIN Consumer Apps modeled on those for US Core Requestors.
<br>
For profiles defined in this IG, Must Support means the following:
<br>
The CARIN BB’s interpretation of Must Support and Missing Data is aligned with US Core IG must support.  When querying and reading CARIN BB Profiles, *Must Support* on any profile data element **SHALL** be interpreted as follows:
<br>
<ul>
<li>Health Plan API actors **SHALL** be capable of populating all data elements as part of the query results as specified by the CARINBlueButtonHealthPlanAPICapabilityStatement.</li>
<li>Consumer App actors **SHALL** be capable of processing resource instances containing the data elements without generating an error or causing the application to fail. </li>
<li>Consumer App actors **SHALL** be capable of displaying the data elements for human use.</li>
<li>Consumer App actors **SHOULD** be capable of storing the information for other purposes.</li>
<li>In situations where information on a particular data element is not present and the reason for absence is unknown, Health Plan API actors **SHALL NOT** include the data elements in the resource instance returned as part of the query results.</li>
<li>When querying Health Plan API actors, Consumer App actors **SHALL** interpret missing data elements within resource instances as data not present in the Health Plan API actors system.</li>
<li>In situations where information on a particular data element is missing and the Health Plan API actor knows the precise reason for the absence of data, Health Plan API actors **SHALL** send the reason for the missing information using values (such as nullFlavors) from the value set where they exist or use the dataAbsentReason extension.</li>
<li>Consumer App actors **SHALL** be able to process resource instances containing data elements asserting missing information.</li>
<li>NOTE: The above definition of *Must Support* is derived from HL7v2 concept Required but may be empty - RE described in HL7v2 V28_CH02B_Conformance.doc.</li>
<li>NOTE: Readers are advised to understand 
<a href="http://hl7.org/fhir/R4/terminologies.html">FHIR Terminology</a> requirements, 
<a href="http://hl7.org/fhir/R4/http.html">FHIR RESTful API</a>  based on the HTTP protocol, along with 
<a href="http://hl7.org/fhir/R4/datatypes.html">FHIR Data Types</a>, 
<a href="http://hl7.org/fhir/R4/search.html">FHIR Search</a> and 
<a href="http://hl7.org/fhir/R4/resource.html">FHIR Resource</a> formats before implementing CARIN BB IG requirements.</li>
</ul>

<h3 id="missing-data">Missing Data</h3>
If the source system does not have data for a *Must Support* data element with minimum cardinality = 0, the data element is omitted from the resource. If the source system does not have data for a required data element (in other words, where the minimum cardinality is > 0), follow guidance defined in the core FHIR specification and summarized in the <a href="http://hl7.org/fhir/us/core/general-guidance.html#missing-data">US Core</a>.

<h3 id="conformance-to-us-core-profiles">Conformance to US Core Profiles</h3>
Any actor acting as a Health Plan API actor in this IG **SHALL**:
<ul>
<li>Be able to populate all profile data elements that have a minimum cardinality >= 1 and/or flagged as *Must Support* as defined by that profiles StructureDefinition.</li>
<li>Conform to the US Core Server Capability Statement expectations for that profile's type.</li>
</ul>
Any actor acting a FHIR Client in this IG **SHALL**:
<ul>
<li>Be able to process and retain all profile data elements that have a minimum cardinality >= 1 and/or flagged as Must Support as defined by that profiles StructureDefinition.</li>
<li>Conform to the US Core Client Capability Statement expectations for that profiles type.</li>
</ul>
<h3 id="common-clinical-data-set">U.S. Core Data for Interoperability and 2015 Edition Common Clinical Data Set</h3>
The US Core Profiles were originally designed to meet the 2015 Edition certification criterion for Patient Selection 170.315(g)(7), and Application Access - Data Category Request 170.315(g)(8). They were created for each item in the <a href="https://www.healthit.gov/sites/default/files/ccds_reference_document_v1_1.pdf">2015 Edition Common Clinical Data Set (CCDS)</a>]. The 3.1.0 version of the US Core Profiles IG includes new requirements from the latest proposed ONC  <a href="https://www.healthit.gov/topic/laws-regulation-and-policy/notice-proposed-rulemaking-improve-interoperability-health">U.S. Core Data for Interoperability(USCDI)</a>) and includes all the <a href="https://www.healthit.gov/isa/api-resource-collection-health-arch">API Resource Collection in Health (ARCH)</a> resources.

<h3 id="code-systems">Access to Licensed Code Systems</h3>
The Industry Standard Code Systems defined by this IG align with claims submission standards adopted by the Department of Health and Human  Services.  Some of the codes require licenses; others are available for use.  The CARIN team will be submitting proposed additions to the set of <a href="https://www.hl7.org/fhir/terminologies-systems.html">Externally Published code systems</a> ) for any Industry Standard Code Systems not included in this set.

<h4 id="licensed"> Licensed Industry Standard Code Systems</h4>
This IG includes value set bindings to industry standard codes that reference Code Systems which require implementers to purchase a license before the coded concepts can be used.   HL7 presently addresses similar license requirements for LOINC and SNOMED CT codes, which although are not used by this IG, are required for other IGs.  The following information summarizes the set of licensed Code Systems required by this IG and provides links to the information about where to go to purchase a license.
<ul>
<li>CPT (Current Procedural Terminology) Procedure Codes and Modifiers:  
The CPT procedure and modifier codes are owned by the 
<a href ="http://www.ama-assn.org/go/cpt">American Medical Association</a>. </li>
<li>CARC (Claim Adjustment Reason Codes) Codes:  CARC Codes are owned by X12.  
<a href="http://www.x12.org/codes/claim-adjustment-reason-codes/">http://www.x12.org/codes/claim-adjustment-reason-codes/</a>.</li>
<li>NUBC (National Uniform Billing Committee) Codes:  
The NUBC secretariat is the American Hospital Association.  <a href="https://www.nubc.org">https://www.nubc.org</a>. </li>
<li>NCPDP (National Council for Prescription Drug Program):  Retail Pharmacy data standards are defined by the NCPDP.  
<a href="https://www.ncpdp.org">https://www.ncpdp.org</a>.</li>
</ul>
<h4 id="available">Available Industry Standard Code Systems</h4>
This IG includes value set bindings to industry standard codes that are available for use without licenses.  An example is the <a href="http://www.icd10data.com/icd10pcs">ICD-10</a> procedure codes ICD-10-PCS codes which are defined in <a href="http://hl7.org/fhir/us/core/StructureDefinition/us-core-procedure">US Core Procedure Profile</a>.  (However, the US Core Procedure Profile cannot be used by this IG as it includes LOINC and SNOMED CT codes, which are not defined by HHS for claims submissions).  The following information summarizes the set of Code Systems required by this IG that are available for use and provides links to the location of the information.
<ul>
<li>ICD-CM Diagnosis Codes: International Statistical Classification of Diseases and Related Health Problems (ICD).  
This IG will use version 10.  The ICD-10-CM code set is maintained by the National Center for Health Statistics (NCHS) 
of the Centers for Disease Control and Prevention (CDC) for use in the United States. It is based on ICD-10, 
which was developed by the World Health Organization (WHO) and is used internationally a medical 
classification.  <a href="https://www.icd10data.com/ICD10CM/Codes">https://www.icd10data.com/ICD10CM/Codes</a></li>
<li>ICD-Procedure Codes (ICD-PCS):  The ICD-10-PCS code set is owned by CMS.   
<a href="http://www.ama-assn.org/go/cpt">http://www.ama-assn.org/go/cpt)</a>.</li>
<li>DRG (Diagnosis Related Group):  The DRGs are payment categories that are used to classify patients for the purpose of 
reimbursing hospitals for each case in a given category with a fixed fee regardless of the actual costs incurred.   
All versions of the DRG (MS-DRG, AP-DRG, etc.) are owned by CMS.  MS-DRGs are used for the Medicare population.  
<a href="https://www.cms.gov/Medicare/Medicare-Fee-for-Service-Payment/AcuteInpatientPPS/MS-DRG-Classifications-and-Software.html">
https://www.cms.gov/Medicare/Medicare-Fee-for-Service-Payment/AcuteInpatientPPS/MS-DRG-Classifications-and-Software.html</a>.
</li>
<li>HCPCS (Healthcare Common Procedure Coding System) Level II Procedure and Modifier Codes:  
HCPCS codes primarily include non-physician products, supplies, and procedures not included in CPT.  
They are owned by CMS and are available for use.  <a href="https://www.cms.gov/Medicare/Coding/HCPCSReleaseCodeSets/Alpha-Numeric-HCPCS-Items/2020-HCPCS-Record-Layout">https://www.cms.gov/Medicare/Coding/HCPCSReleaseCodeSets/Alpha-Numeric-HCPCS-Items/2020-HCPCS-Record-Layout</a>.
</li>
<li>NDC (National Drug Codes):  The US Federal Drug Administration (FDA) Data Standards Council 
assigns the first 5 digits of the 11 digit code.  <a href="http://hl7.org/fhir/sid/ndc.html">https://www.cms.gov/Medicare/Coding/HCPCSReleaseCodeSets/Alpha-Numeric-HCPCS-Items/2020-HCPCS-Record-Layout</a>.
</li>
<li>RARC (Remittance Advice Remark Codes) Codes:  The RARC codes are owned by CMS.  
<a href="http://www.wpc-edi.com/reference/codelists/healthcare/remittance-advice-remark-codes">
http://www.wpc-edi.com/reference/codelists/healthcare/remittance-advice-remark-codes</a>.</li>
</ul>
