# AMS_Project-
Enterprise Automation &amp;  Application Maintenance on Customer Service Transformation 
                                     Project Technical Overview
Project 	Enterprise Automation &  Application Maintenance on Customer Service Transformation 

Domain	Transportation, Logistics & Package Delivery

Business Applications	Care Agent Onboarding Portal
CATS – Customer Appeals Tracking System
Delivery Delay Automation
Delivery Approach	Agile / Scrum 
Modules	ITSM,ITOM, CSM, Scoped Applications, Agent Workspace, Flow Designer, IntegrationHub, AI Agents, Virtual Agent, Knowledge Management, SecOps / SIR, ATF
System Interfaces	Voyage, Scripted REST APIs, REST/SOAP APIs, MID Server, OAuth 2.0, Personal Access Tokens
Technical Implementation Stack	JavaScript, GlideRecord, Script Includes, Business Rules, UI Actions, UI Builder, React.js, HTML 
Application Lifecycle Management	Azure DevOps, GitLab/Git Source Control, CI/CD, App Repository, Update Sets, Change Management
Security & Compliance	ACLs, Role-Based Access Control, OAuth 2.0, Scoped Application Security
Testing & Validation 	Automated Test Framework (ATF), Integration Testing, Regression Testing

 Project Summary
The project focuses on modernizing business operations through ServiceNow by automating manual processes, improving case management, streamlining integrations, and enhancing user experience. The solution uses scoped applications, workflows, APIs, AI-assisted capabilities, security controls, and automated deployment processes to support efficient, secure, and scalable enterprise operations.
Business Goals
•	Automate Care Agent onboarding and bulk provisioning to shorten time-to-productivity.
•	Provide CATS agents with a centralized workspace for escalated customer cases and interaction history.
•	Integrate ServiceNow with enterprise logistics systems such as Voyage through secure REST-based services.
•	Use Playbooks, Flow Designer, IntegrationHub, and AI Agents to standardize and accelerate case handling.
•	Strengthen role-based access through ACLs and OAuth 2.0 controls for sensitive agent and customer information.
•	Improve deployment quality through Git-based source control, Azure DevOps pipelines, App Repository publishing, and ATF.
•	Reduce manual cross-team coordination through event-driven automation and monitored integrations.
Project Scope and Workstreams

Workstream	Business Purpose	Key ServiceNow Capabilities	Developer Contribution
Care Agent Onboarding Portal	Automate onboarding and agent provisioning	Scoped App, Service Portal/UI Builder, REST API, Scheduled Jobs, Script Actions, ACLs	Portal design, ingestion automation, user provisioning, validations, security
CATS – Escalated Case Management	Manage high-visibility customer appeals and escalations	CSM, Agent Workspace, Playbooks, Flow Designer, Knowledge, Virtual Agent, AI Agents	Workspace development, case workflows, integrations, guided resolution, AI-assisted actions
Voyage Integration	Synchronize escalated case and logistics context	Scripted REST API, OAuth 2.0, IntegrationHub, MID Server	API design, payload validation, error handling, reusable Script Includes
Delivery Delay Automation	Automate delay detection, impact calculation, and cross-instance status updates	Custom Tables, Flow Designer, AI Agent Studio, scripted logic, analytics	Workflow orchestration, record updates, monitoring, anomaly handling
DevOps / Release Engineering	Standardize secure and auditable deployments	GitLab/GitHub, Azure DevOps, App Repository, ATF, Change Management	Pipeline integration, automated validation, release traceability, promotion controls

Care Agent Onboarding Portal
Business Problem
Care Agent onboarding required repeated manual data entry, user setup, access validation, and coordination across teams. The objective was to replace fragmented onboarding activities with a controlled ServiceNow scoped application and portal experience.
Solution Design
•	Built the onboarding solution as a scoped application to isolate configuration and reduce cross-scope conflicts.
•	Created responsive portal/UI components using UI Builder, Service Portal, JavaScript, HTML, CSS, Bootstrap, and React.js where applicable.
•	Implemented a custom REST ingestion path for daily Care Agent text files.
•	Used Scheduled Jobs and Script Actions to process inbound records, validate data, provision users, and update existing agent records.
•	Applied ACLs and role-based controls so only authorized support and administrative users could access sensitive onboarding data.
•	Used Flow Designer for notifications, approvals, SLA-related activities, and downstream follow-up actions.
•	Validated critical onboarding logic and regression scenarios through Automated Test Framework(ATF). 
 
Outcome
The automated onboarding approach reduced manual onboarding lead time by approximately 40% according to the current resume metrics, helping new Care Agents become productive faster while reducing repetitive administrative work.
CATS – Customer Appeals Tracking System
Business Problem
CATS supports escalated, high-visibility customer cases that require structured investigation, access to logistics context, consistent resolution steps, and coordination with downstream operations teams. The goal was to give agents one controlled workspace instead of requiring them to move between disconnected tools.
Agent Workspace and Case Experience
•	Configured a dedicated Agent Workspace to centralize case details, customer/account context, interactions, related tasks, knowledge, and integration results.
•	Designed Playbooks to guide agents through investigation, evidence review, customer communication, escalation, resolution, and closure steps.
•	Developed reusable UI actions, Business Rules, Script Includes, and client/server logic for case-specific behaviors.
•	Configured Customer Service Management account/contact models and branded customer-facing experiences where required.
•	Integrated Knowledge Management and Virtual Agent capabilities to improve self-service and surface relevant resolution content.
AI Agent and Agentic Workflow Design
•	Implemented AI-assisted workflows to retrieve shipment and customer case context.
•	Analyzed historical escalations and resolution patterns to support recommended next-best actions.
•	Identified relevant Knowledge Articles for agents during case handling.
•	Created follow-up tasks for operations, customer service, and logistics support teams when additional action was required.
•	Applied ACL and role checks around AI-enabled capabilities to prevent unauthorized access to sensitive information.
 
Voyage Integration
A custom Scripted REST API was designed to exchange escalated case and logistics information between ServiceNow and Voyage. OAuth 2.0 / token-based authentication, payload validation, reusable integration logic, and controlled error handling were used to keep the interface secure and supportable.
Delivery Delay Automation
The provided project source describes a logistics automation scenario in which separate Logistics, Retail, and Delivery ServiceNow instances created communication delays and manual coordination when a route exceeded its ETA window. The solution automated delay detection, impact calculation, and target-instance status updates.
Source-Defined Problem
•	Delivery delays were recorded but not consistently communicated to the target instance.
•	Dispatch statuses were not automatically updated.
•	Manual coordination created bottlenecks and SLA violations.
•	The business needed real-time delay calculations, automated status propagation, financial-impact tracking, and auditable orchestration.

Source-Defined Architecture

Instance	Primary Role	Implementation Elements
Logistics	Initiates route execution	Flow/orchestration trigger; route execution request
Retail	Calculates ETA and penalty impact	Custom scripted logic, flow variables, AI Agent analysis
Delivery	Updates delivery execution status	GlideRecord update logic and target-record status update

The source also identifies a custom Delivery Delay table, an AI role named “Delivery Delay Analyzer,” scripted status-update logic, integration credentials, and monitoring for repeated failures.

Delivery Delay Automation Workflow
 
End-to-end workflow showing webhook intake, AI Agent input retrieval, MCP calculation, Script Include impact computation, validation/approval, dispatch status update, and webhook response.


 Agentic MCP Architecture
 
High-level architecture showing the ServiceNow instance, AI agents, internal MCP server  and external MCP services supporting rerouting, dispatching, and inventory-management use cases.
End-to-End Flow
•	Receive the route/delivery event and retrieve the required inputs.
•	Evaluate ETA variance and delivery-window conditions.
•	Calculate penalty or business-impact values when the delivery is late.
•	Persist or update the Delivery Delay record.
•	Invoke the target update step to synchronize delivery execution status.
•	Monitor integration/system logs for patterns such as record-not-found responses or 502 failures.
•	Raise proactive alerts for recurring anomalies and preserve audit data for troubleshooting.
Source-Reported Results
•	Average dispatch update time reduced from approximately 20 minutes to under 3 seconds.
•	Manual entry was eliminated across the three participating departments.
•	The source reports full synchronization across Logistics, Retail, and Delivery for the implemented scenario.
•	AI-enhanced monitoring helped detect recurring failure patterns earlier.
•	Data consistency improved across participating instances.
Screenshot	Description
 	AI Agent Prompt – 
Shows the final AI Agent prompt configuration used to parse ETA, delivery window, and penalty rate inputs before calling the MCP tool.
 	AI Agent Configuration – Displays the step-by-step AI Agent Studio configuration, including role statement, agent steps, and connected MCP reference.
 	AI Agent Test Output – Displays the AI Agent execution results, including calculated impact, status update to “Dispatched,” and successful MCP-to-table record validation.
 	AI Agent Tools – Displays the configuration of tools connected to the Route Decision Agent within AI Agent Studio, including the MCP for route validation and the Script Include for automated decision logic execution.


Consolidated Technical Architecture
•	Experience Layer: Agent Workspace, UI Builder, Service Portal, Virtual Agent, reusable UI components.
•	Application Layer: Scoped Applications for Care, CATS, and supporting logistics automation.
•	Workflow Layer: Flow Designer, Playbooks, Script Actions, Scheduled Jobs, SLA and notification logic.
•	Intelligence Layer: AI Agents / agentic workflows, Now Assist / Generative AI, knowledge recommendations, case summarization and next-best-action assistance.
•	Integration Layer: Scripted REST APIs, REST/SOAP services where required, IntegrationHub, MID Server, OAuth 2.0, Personal Access Tokens.
•	Data/Security Layer: CSM data model, custom tables, ACLs, role-based security, audit history, Change Requests.
•	Engineering Layer: Git-based source control, Azure DevOps CI/CD, App Repository, Update Sets where appropriate, ATF.



Data Model and Logic

Filed 	Type 	Description
route_id	Integer	Unique delivery route identifier
status	String	Current delivery state
eta_minutes	Integer	Time in minutes for ETA
stockout_penalty_rate	Decimal	Cost impact rate for delays
calculated_impact	Decimal	Computed penalty value
instance_name	String	Source instance of record
last_updated	Date/Time	Audit trail field for change tracking







Screenshot	Description
 	Delivery Delay Table – Displays stored logistics records containing ETA minutes, delivery window hours, penalty rates, and calculated impact values used by the AI Agent for delay analysis.
 	Supply Agreement Table – Contains supplier, route, and contractual terms data referenced by the AI Agent during route validation and decision-making.

AI Agent Configuration
AI Agent Name: CATS Case Assistant
Goal: Analyze escalated customer cases, retrieve shipment and case context, identify relevant knowledge, and recommend next-best actions for the agent.
Steps implemented in AI Agent Studio:
1.	Retrieve customer, case, shipment, and escalation details.
2.	Analyze case history, priority, and related shipment information.
3.	Identify relevant Knowledge Articles and similar resolution patterns.
4.	Recommend next-best actions for the support agent.
5.	Create follow-up tasks for Operations, Customer Service, or Logistics when required.
6.	Update case information and support customer communication based on the recommended action.

 
 
Delivery Delay Analyzer Configuration
AI Agent Name: Delivery Delay Analyzer
Goal: Analyze delivery delays and determine the appropriate priority and next action based on ETA deviation, route conditions, and business impact.
Steps implemented in AI Agent Studio:
1.	Retrieve delivery, route, and incident details through configured inputs.
2.	Analyze ETA deviation against the expected delivery window.
3.	Evaluate route conditions and potential penalty or business impact.
4.	Determine the delay severity using configured evaluation criteria.
5.	Recommend an escalation, rerouting, or automated status-update path.
6.	Trigger follow-up actions such as record updates, task creation, and notifications.
 

MCP Orchestration and AI Agent Logic
The orchestration was built in AI Agent Studio and controlled using MCP integration steps.
1.	Step 1 – execute_route: Initiates the delivery route.

2.	Step 2 – notify_delivery_delay: Calculates ETA variance and penalty rate.

3.	Step 3 – update_execution_status: Updates the delivery record in the target instance.
Key Script Logic
(function(inputs) {
  var routeId = parseInt(inputs.route_id);
  var status = inputs.status || 'pending';
  
  var gr = new GlideRecord('x_snc_ups_de_0_delivery_delay');
  gr.addQuery('route_id', routeId);
  gr.query();
  if (gr.next()) {
    gr.status = status;
    gr.update();
    return { success: true, updated: gr.getUniqueValue() };
  } else {
    return { success: false, error: 'Record not found' };
  }
})(inputs);
 
Payload JSON Configuration – Shows the MCP tool setup with request and response payloads used to validate routes and update delivery records.

 
Successful MCP Execution – Displays the MCP tool successfully executing the update request, confirming route decision processing and record validation.
 
AI-Enhanced Monitoring and Error Handling
A secondary AI Agent monitors MCP logs and ServiceNow system logs for recurring error patterns such as “Record not found” or 502 failures.
•	Collects error messages via Flow API call

•	Feeds data into AI Agent Studio for pattern learning

•	Flags anomalies and generates a proactive alert
 
Example of Failed Request Log – Shows the MCP execution error output during a failed route update attempt, useful for debugging payload or instance configuration issues.
Results:
•	Average dispatch update time reduced from 20 minutes to under 3 seconds.
•	Manual entry has been eliminated across all three departments.
•	100% synchronization between Logistics, Retail, and Delivery systems.
•	Early anomaly detection via AI monitoring reduced repeat failures.
•	Data consistency improved across all instances
 
Comparison of 502 Failure vs Success – Displays the difference between a failed MCP request (502 error) and a successful execution, showing how payload validation and instance targeting affect response outcomes.
 
Record Update Audit Log – Shows the system audit trail confirming the record update, including the status change to “dispatched” after successful MCP processing.
Security and Compliance
•	Implemented table-, record-, and field-level ACLs to enforce least-privilege access.
•	Separated application logic in scoped applications to reduce unintended cross-scope access.
•	Secured inbound and outbound integrations using OAuth 2.0 and token-based authentication.
•	Applied additional security controls around AI-enabled workflows so retrieved context and generated actions remained within authorized data boundaries.
•	Linked release artifacts with Change Requests to preserve audit traceability for production deployments.
•	Used controlled service accounts/integration users with only the permissions needed by each interface.
Release Management
•	Used CI/CD pipelines for automated validation and promotion, reducing risk from manual deployment activity.
•	Published scoped applications to the ServiceNow App Repository and promoted approved versions across environments.
•	Maintained Change Request linkage for production releases and audit evidence.
•	Built ATF coverage for critical integration, case management, and scoped application behaviors.
•	Performed pre-release validation, defect triage, post-deployment smoke testing, and rollback/fail-safe checks.
Key Learnings 
Lesson	Takeaway
Instance targeting is explicit	Make sure your Bearer Auth token is associated with the correct “instance”
Cross-scope ACLs matter	Keep permissions scoped properly to avoid query blocks
AI Agents amplify insight	Automating error categorization accelerates fixes
GlideRecord precision	Data type consistency prevents silent failures

Future Enhancements and Optimization Opportunities
i.	Predictive ETA Forecasting
   Integrate an ML model using AWS SageMaker or ServiceNow’s AI Controller to predict delays based on traffic,  weather, and driver performance.
ii.	Intelligent Root Cause Analysis
   Use Predictive Intelligence clustering to detect recurring delivery bottlenecks across  regions.
iii.	Dynamic Workflow Reassignment
    Enable AI Agents to auto-reroute or reassign deliveries based on real-time conditions.
iv.	Autonomous MCP Healing
    Implement an AI layer that replays failed MCP transactions and auto-retries failed  updates without human input.
v.	Visualization Dashboards
    Deploy Performance Analytics dashboards showing real-time delivery status, average ETA deviation, and SLA compliance metrics.

Conclusion
The project modernized key business processes by combining ServiceNow automation, integrations, AI-assisted workflows, and secure application design. The Care Agent Onboarding Portal reduced manual onboarding effort and improved user provisioning, while CATS provided a centralized workspace for managing escalated customer cases with guided resolution and AI-supported recommendations. The Delivery Delay Automation solution improved logistics coordination through automated delay detection, impact analysis, and status synchronization. Together, these solutions created a scalable and secure ServiceNow platform that improves operational efficiency, user experience, and enterprise-wide process visibility.


<img width="522" height="629" alt="image" src="https://github.com/user-attachments/assets/32fc7b31-9198-491c-8b93-68d85fe420e7" />
