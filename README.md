# SecureX-Workflow-ThreatResponse-QuickSearchToCasebook
This workflow is a simple example of reporting on a searchable IoC using the SecureX Threat Response Enrich Observables API by enriching some additional information from the Threat Inteligences which are integrated with SecureX backend. The workflow will create reports of summary information related to Judgments, Indicators, and Sightings that can be responded to by Threat Inteligence for Observable Types supported by SecureX Threat Response API Endpoint /iroh/iroh-enrich/observe/observables Endpoint. The summary reported will be created as New SecureX Casebook and sent to the specified email address.

![workflow](img/workflow.png "workflow")

# Change Log
- Dec, 18, 2022 : Initial Release

# Requirements
The following system atomics are used by this workflow:
- Threat Response - Generate Access Token
- Threat Response - Enrich Observable
- Threat Response - Create Casebook
- Set Variables
- JSONPath Query
- Send Email

The following atomic actions must be imported before you can import this workflow:
- None

The targets and account keys listed at the bottom of the page
- Threat Response

# Workflow Steps
1. Get a token for the Umbrella Reporting API
2. Request DNS Event Details (specified Category ID, From Time, To Time, number of fetch events)
3. Check if the request was successful:
 - If it wasn’t, output an error and end the workflow
 - If it was:
   - Convert the statistics to a table
   - Loop through the table checking if any of the categories are in scope. If it is, add it to the Incident text
   - Convert JSON Text to XML
   - Convert XML to HTML Incident Message
4. Generate an access token for SecureX and create an incident to Ribbon Incident Manager

# Installation
1. Browse to your SecureX orchestration instance. This wille be a different URL depending on the region your account is in:
 - US: https://securex-ao.us.security.cisco.com/orch-ui/workflows/
 - EU: https://securex-ao.eu.security.cisco.com/orch-ui/workflows/
 - APJC: https://securex-ao.apjc.security.cisco.com/orch-ui/workflows/
2. Click on **Import** to import the workflow.
3. Select **Browse** from Import From
4. Open **SecureX-Workflow-Umbrella-EventReportToCasebook.json** and Copy text
5. Paste to **Paste JSON or upload the workflow to import** and click **Import**

![install](img/install.png "install")
