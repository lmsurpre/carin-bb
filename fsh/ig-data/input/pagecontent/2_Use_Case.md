
<h3 id="terms-and-concepts">Terms and Concepts</h3>

<table border="1" class="codes">
  <thead>
    <tr>
      <td>
        <b>Term</b>
      </td>
      <td>
        <b>Definition</b>
      </td>
    </tr>
  </thead>
  <tbody>
    <tr>
              <td>Subscriber</td>
              <td>TBD</td>
    </tr>
    <tr>
              <td>Dependent</td>
              <td>TBD</td>
    </tr>
    <tr>
              <td>Member</td>
              <td>TBD</td>
    </tr>
        <tr>
              <td>Beneficiary</td>
              <td>TBD</td>
    </tr>
        <tr>
              <td>Patient</td>
              <td>TBD</td>
    </tr>
        <tr>
              <td>Personal Representative</td>
              <td>Per the HIPAA privacy regulations at 45 CFR 164.502(g), a <a href="https://urldefense.proofpoint.com/v2/url?u=https-3A__www.hhs.gov_hipaa_for-2Dprofessionals_privacy_guidance_personal-2Drepresentatives_index.html&d=DwMD-g&c=aIUDzRSH0GV4AQi9KEcOBQ&r=yWXMVZr0SziUyEVZ56vTdlmXBCJDn2JEHB1y1-Ra3ig&m=kW-2JMnVMmexZk4eJoDWtnQeGJ4pZp68igBn9CMjP7M&s=YqcWL-o6QklLgDfOA91f5ysHOEn9YZjX7k7m7ROTuU0&e=">personal-representative</a> is someone authorized under state or other applicable law to act on behalf of the individual in making health care related decisions (such as a parent, guardian, or person with a medical power of attorney)</td>
    </tr>
    <tr>
              <td>Coordination of Benefits</td>
              <td>TBD</td>
    </tr>
    <tr>
              <td>Payer</td>
              <td>TBD</td>
    </tr>
    <tr>
              <td>Encounter data vs Claims</td>
              <td>Encounter data means the information or data relating to the receipt of any item(s) or service(s) by an enrollee under a contract between a State and a managed care plan. Encounter data are conceptually equivalent to the paid claims records that state Medicaid agencies create when they pay providers on a FFS basis</td>
    </tr>
    <tr>
              <td>EOB.careteam</td>
              <td>The members of the team or organization who provided the products and services as submitted on the claim by the provider to the payer</td>
    </tr>
    <tr>
              <td>CareTeam Resource</td>
              <td>The Care Team includes all the people and organizations who plan to participate in the coordination and delivery of care for a patient</td>
    </tr>
    </tbody>
</table>


<h3 id="use-cases">Use Cases </h3>
<h4>Background</h4>
<b>TO BE REVISED</b>
Consumer-directed exchange occurs when a consumer or an authorized caregiver invokes their HIPAA Individual Right of Access (45 CFR  164.524) and requests their digital health information from a HIPAA covered entity (CE) via an application or other third-party data steward.
**Use Case**: Consumer Access to their Claims Data
<h4>Technical Workflow</h4>
<img style="width:100%;float:none;align:middle;" src="CARINSequence.png" />

Actors:
<ul>
<li>Consumer (aka Subscriber, Beneficiary, Patient, or Personal Representative)</li>
<li>Consumer App- A digital third-party application selected by and primarily for the Consumer with a consumer-facing user interface</li>
<li>Health Plan API (aka Payer, Covered Entity)</li>
<li>Health Plan’s Identity and Access Authorization server </li>
</ul>

Flow:
<ol>
<li>Consumer App presents a list of potential Payers / Health Plans to access to the Consumer.</li>
<li>Consumer selects the Payer / Health Plan.</li>
<li>Consumer App opens the link to the Health Plan's Identity and Access Authorization server.</li>
<li>Consumer enters the credentials.</li>
<li>Health Plan's Identity and Access Authorization server validates the credentials, generates and returns to the Consumer App an OIDC token with Consumer and authorized patient/beneficiary identities encoded.</li>
<li>Consumer App successfully links the user to the Payer / Health Plan and notifies the Consumer.</li>
<li>Consumer requests the Consumer App to fetch Explanation Of Benefit records.</li>
<li>Consumer App generates and sends to the Health Plan's CARIN BB enabled FHIR API a request (which includes Patient ID, and token from the step #5) to fetch the Explanation Of Benefit (EOB) and supporting reference FHIR resources.</li>
<li>Health Plan's CARIN BB enabled FHIR API responds with a bundle of the requested EOB and supporting reference FHIR resources.</li>
<li>Consumer App presents the EOB and supporting reference FHIR resources to the Consumer.</li>
</ol>

<h3>Personas and Patient Stories</h3>
<b>TBD</b>