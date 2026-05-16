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
