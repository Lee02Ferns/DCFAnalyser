<h1>DCF (Discounted Cash Flow) & Impairment Analyser</h1>

<h2>Description</h2>
The DCF (Discounted Cash Flow) analyser is a financial model analyser designed to support impairment testing by enabling auditors and finance stakeholders to assess the sensitivity of cash generating units (CGUs) by adjusting varying assumptions.
<br />

<h2>Executive Summary</h2>

This solution highlights a scalable Power BI-driven solution designed to support impairment testing through sensitivity analysis of cash generating units (CGUs). The analyser standardises complex client cash flow models into a template, enables interactive sensitivity scenario exploration, and provides clear visibility into headroom and impairment risk while remaining performant and maintainable with larger client datasets.

The solution was created using multiple tools. Alteryx was used to perform initial transformations and sensitivity scenario generation, while Power BI is leveraged as an analytical and visualisation layer using field parameters, calculation groups, and a star schema semantic model to allow users to interact with cash flow assumptions. This design balances analytical flexibility with engine and memory constraints commonly encountered in large financial models.

Beyond technical delivery, the solution was developed in close collaboration with senior audit stakeholders to align with real world audit testing workpapers and testing procedures. Key outcomes included reduced manual excel model rework, faster sensitivity assessment, and improved consistency across engagements. The case study demonstrates principal level strengths in analytical architecture, performance trade off evaluation, stakeholder alignment, and delivery of governed, production ready BI solutions.


<h2>Languages and Utilities Used</h2>

- <b>Excel: (Standardised input and error handling validation)</b>
- <b>Alteryx: (Data transformation, sensitivity scenario generation)</b>
- <b>PowerBI: (Visual layer, Semantic modelling, DAX, calculation groups)</b> 



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

A structured excel template is used to collect client cash flow assumptions.
<ul>
  <li>Contains standardised cash flow categories</li>
  <li>Built in data validation rules for data type and completeness</li>
  <li>Designed to minimise downstream transformation issues</li>
</ul>

<h4>Cash Flow Template</h4>
<img width="687" height="682" alt="01_CashFlowTemplate" src="https://github.com/user-attachments/assets/6dde5ec9-1c8f-4818-b5af-fc04889d6ac4" />

<h4>CGU Master Template</h4>
<img width="694" height="473" alt="02_SiteDetailsTemplate" src="https://github.com/user-attachments/assets/de22784c-12f1-4876-9922-d379127ebfdc" />


<h2>Data Transformation Layer (Alteryx)</h2>

Alteryx is used as the primary transformation solution due to:
<ul>
  <li>Transparent and auditable workflows</li>
  <li>Strong error handling and validation capabilities</li>
  <li>Ability to create Alteryx apps a seamless and professional method to ingest and transform the data for preparers</li>
</ul>




Responsibilities of this layer include:
<ul>
  <li>Normalising input data formats</li>
  <li>Generating upper and lower sensitivity scenarios</li>
  <li>Producing a clean analytical dataset optimised for PowerBI</li>
</ul>

<img width="1530" height="628" alt="03_AlteryxWorkfow" src="https://github.com/user-attachments/assets/e3dfab11-ee71-4369-8f33-d092942b7bd7" />

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
      <li>Near instantaneous PowerBI performance</li>
      <li>Cleaner model reduced DAX logic</li>
    </td>
    <td>
       <li>Limited sensitivity flexibility due to number of potential sensitivity combinations</li>
      <li>Any additional scenarios would require reprocessing</li>
    </td>
  </tr>
    <tr>
    <td>C: Hybrid Approach</td>
    <td>
      <li>Use Alteryx to generate bounded sensitivity combinations per component</li>
      <li>Use Power BI as a filtering and aggregation engine via user selected filter parameters</li>
    </td>
    <td>
      <li>Data model configuration across both PowerBI and Alteryx</li>
        </td>
  </tr>
</table>

After several performance testing scenarios and discussion with stakeholders, option C was chosen as the final approach since it preserved near instantaneous performance of option B whilst providing full flexibility of option A all whilst avoiding excessive strain on functionality and performance.

<h2>PowerBI Schematic Model Design</h2>

A star schema was adopted to support clear table relationships and filtering of fact and dimension tables.

<h3>Core structure</h3>
<li>Dim_CGU_Master: Qualitative attributes per CGU</li>
<li>Fact_CashFlow_Component: List of cashflow adjusted sensitivity values containing the base value and sensitivity value. A separate table for each cash flow component</li>

<br>

<img width="1031" height="368" alt="04_DataTableModel" src="https://github.com/user-attachments/assets/c469031c-9620-4a33-b76d-ad05e0a64d05" />

<h3>Advanced PowerBI modelling techniques applied</h3>
<li>Field parameters to allow dynamic selection of sensitivity values</li>
<li>Disconnected calculated tables to configure advanced visuals</li>
<li>Calculation groups to reduce measure duplication and improve future maintenance</li>

<h2>Data Quality, Validation and Governance</h2>
Data reliability was prioritised throughout the ETL process:
<li>Excel validations prevent invalid or incomplete population of template</li>
<li>Alteryx workflows contained error handling to raise anomalies and block errors further in pipeline</li>
<li>Base model results were reconciled against client’s model to ensure accuracy and completeness</li>
<li>Detailed model and measure documentation for audit transparency and future handover</li>

Regarding data privacy, reports are published to secure workspaces with role-based security to ensure client confidential reports remain secure.

<h2>Visual Design & User Experience</h2>

The report experience was designed in close collaboration with audit teams and executives.

<h3>Key Design Principles</h3>
<li>Immediate visibility of base vs sensitivity impacts</li>
<li>Clear RAG indicators for impairment risk</li>
<li>Use of bookmarks to ensure minimal and seamless page navigation</li>
<li>Drill-through capability for detail level investigation</li>

<h3>Core Pages</h3>

<li>Landing Page: Navigation and configuration starting point</li>
<li>Overview Page: Headroom/Impairment KPI summary with base vs sensitivity scenario comparison</li>
<li>Sensitivity Configuration Page: Field parameter driven adjustments</li>

![DCFANALYSER](./assets/07_SliderFunctionality_small.gif)

<li>Drill Through Page: Detail page accessible from other main pages for further granular level investigation</li>


<h2>User Navigation Story</h2>

A typical user workflow would involve:
<ol>
  <li>User reviews base case result on overview page</li>
  <li>High risk CGUs are identified via the RAG and conditional KPI visuals</li>
  <li>User navigates to sensitivity configuration and applies adjustments</li>



  
  <li>Results update instantaneously whilst also showing base case as comparison</li>
  <li>User drills through to detail level page to perform audit procedures and gather evidence</li>
</ol>

<h2>Outcomes & Impact</h2>
<li>Reduced dependency on bespoke client excel models</li>
<li>Enable rapid exploration of sensitivity scenarios</li>
<li>Delivery of performant and scalable PowerBI model</li>
<li>Established foundation for future integration with Microsoft Fabric and advanced analytic capabilities</li>

<h2>Challenges & Lessons Learned</h2>

<h3>Data Model Architecture</h3>
During early stages, there was an assumption all logic could be performed in DAX. However, during testing, it was discovered this resulted in significant impacts on visual loading and functionality. The learning here was to offload intensive calculations upstream in the pipeline where possible, using PowerBI primarily as a visual layer.

<h3>Stakeholder Feedback and Alignment</h3>

Early engagement with audit partners and managers ensured the solution was supported with real testing and feedback rather than building a solution not suited for audit testing.

<h2>What I would do differently</h2>
<li>Test memory usage and performance impacts earlier to avoid modelling revisions</li>
<li>Explore calculation groups earlier to simplify initial DAX design and avoid revisions</li>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
