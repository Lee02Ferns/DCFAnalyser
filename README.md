<h1>DCF (Discounted Cash Flow) & Impairment Analyser</h1>

<h2>Description</h2>
The DCF (Discounted Cash Flow) analyser is a financial model analyser designed to support impairment testing by enabling auditors and finance stakeholders to assess the sensitivity of cash generating units (CGUs) by adjusting varying assumptions.
<br />

<h2>Executive Summary</h2>

This solution highlights a scalable Power BI driven solution designed to support impairment testing through sensitivity analysis of cash generating units (CGUs). The analyser standardises complex client cash flow models into a template, enables interactive sensitivity scenario exploration, and provides clear visibility into headroom and impairment risk while remaining performant and maintainable with larger client datasets.

The solution was created using multiple tools. Alteryx was used to perform initial transformations and sensitivity scenario generation, while Power BI is leveraged as a analytical and visualisation layer using field parameters, calculation groups, and a star schema semantic model to allow users to interact with cash flow assumptions. This design balances analytical flexibility with engine and memory constraints commonly encountered in large financial models.

Beyond technical delivery, the solution was developed in close collaboration with senior audit stakeholders to align with real world audit testing workpapers and testing procedures. Key outcomes included reduced manual excel model rework, faster sensitivity assessment, and improved consistency across engagements. The case study demonstrates principal level strengths in analytical architecture, performance trade off evaluation, stakeholder alignment, and delivery of governed, production ready BI solutions.


<h2>Languages and Utilities Used</h2>

- <b>PowerBI</b> 
- <b>Alteryx</b>
- <b>Excel</b>

<h2>Project Overview</h2>

This project delivers a Discounted Cash Flow (DCF) and impairment analysis platform to support audit teams in assessing impairment risk across cash generating units. The solution standardises client cash flow inputs, enables controlled sensitivity analysis, and provides insights into headroom and impairment outcomes.

The analyser is designed for use across multiple industries (e.g. Technology, Retail, Energy) and focuses on scenario analysis, risk identification, and decision support.

<h3>What is the Business Problem?</h3>

Client provided DCF models are often:
<ul>
  <li>Highly customised and difficult to navigate</li>
  <li>Fragile when adjusting sensitivities</li>
  <li>Time consuming for audit teams to re-engineer for testing purposes</li>
</ul>

This results in excessive manual effort, inconsistent analysis, and reduced time available for professional judgement and insights.

<h3>Who are the stakeholders and users?</h3>

<ul>
  <li>Audit teams performing impairment testing</li>
  <li>Audit managers and partners reviewing outcomes</li>
  <li>Client finance and internal audit teams exploring sensitivity scenarios</li>
</ul>

<h3>What is the success criteria?</h3>

<ul>
  <li>Reduction in manual model build effort by audit teams</li>
  <li>Consistent and repeatable sensitivity analysis across engagements</li>
  <li>Immediate visibility of headroom / impairment impacts under alternative assumptions</li>
</ul>

<h2>Assumptions and constraints</h2>

To ensure appropriate use and governance, the solution operates under the following assumptions and constraints:

<ul>
  <li>Client cash flow models are assumed to be internally consistent and approved by management</li>
  <li>Sensitivity ranges are bounded to audit approved upper and lower thresholds</li>
  <li>The solution supports analytical assessment, not statutory valuation signs off</li>
  <li>Security and access controls are managed via standard Power BI role-based access</li>
</ul>

<h2>Data & Analytical Architecture</h2>

<h3>High Level Design Principles</h3>

<ul>
  <li>Separate data preparation from analytical calculations</li>
  <li>Precompute calculation logic where possible</li>
  <li>Retain flexibility of sensitivities within PowerBI for user interaction</li>
  <li>Optimise for performance, maintainability and audit transparency</li>
</ul>

<h3>Standardise Data Input</h3>

A structured excel template is used to collect client cash flow assumptions
<ul>
  <li>Contains standardised cash flow categories</li>
  <li>Built in data validation rules for data type and completeness</li>
  <li>Designed to minimise downstream transformation issues</li>
</ul>

<h2>Data Transformation Layer (Alteryx)</h2>

Alteryx is used as the primary transformation solution due to:
<ul>
  <li>Transparent and auditable workflows</li>
  <li>Strong error handling and validation capabilities</li>
  <li>Ability to create alteryx apps a seamless and professional method to ingest and transform the data for preparers</li>
</ul>

Responsiblities of this layer include:
<ul>
  <li>Normalising input data formats</li>
  <li>Generating upper and lower sentivitiy scenarios</li>
  <li>Producing a clean analytical dataset optimised for PowerBI</li>
</ul>

<h2>Key Architectural Decision: Sensitivity Modelling Strategy</h2>

A core design decision was how to support flexible sensitivity analysis without exceeding Power BI memory or performance constraints. Three approaches were evaluated:

<table>
  <tr>
    <th>Option</th>
    <th>Advantages</th>
    <th>Disadvantages</th>
  </tr>
  <tr>
    <td>A: Fully DAX based calculation in PowerBI</td>
    <td>
      <li>Simple ingestion model </li>
      <li>Single source of truth </li>
    </td>
    <td>
      <li>Memory intensive with multiple sensitivity dimensions</li>
      <li>Performance degradation observed during testing when applying multiple sensitivities simultaneously</li>
        </td>
  </tr>
  <tr>
    <td>B: Fully precomputed scenarios in Alteryx</td>
    <td>
      <li>Near instantenous PowerBI performance</li>
      <li>Cleaner model reduced DAX logic</li>
    </td>
    <td>
       <li>Near instantenous PowerBI performance</li>
      <li>Cleaner model reduced DAX logic</li>
    </td>
  </tr>
</table>



<h2>Program walk-through:</h2>

<p align="center">
Launch the utility: <br/>
<img src="https://i.imgur.com/62TgaWL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Select the disk:  <br/>
<img src="https://i.imgur.com/tcTyMUE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
