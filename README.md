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
