# sdl_requirements
Collection of requirements/technical tasks for new sdl_core features

The purpose of this document is to describe common approach to requirements creation, storing, changes and updates in sdl_requirements repository.

### Definitions and Abbreviations
|Definitions or Abbreviations|Description|
|:---------------------------|:----------|  
|Requirements| Requirements are the description of how a system should behave and the specification of what should be developed|
|TRS|Technical Requirement Specification. TRS contains detailed technical requirements specification. For detailed description refer to section Work Documents|
|Use case|Use case is a list of actions or event steps typically defining the interactions between a role (known in the Unified Modeling Language as an actor) and a system to achieve a goal. The actor can be a human or other external system.|
|User story|User story is an informal, natural language description of one or more features of a software system.|
|CRS|Customer Requirement Specification. CRS contains customer requirements to the software; customer requirements to project and process shall be contained in a project management plan (PMP). For detailed description refer to section Work Documents|
|CRQ|Change Request|

### Requirements Analysis Process (diagram)

### Roles and Responsibilities
| | |
|-|-|
|__Role__|**PM/TL**|
|__Responsibility__|Information regarding proposals which have to be implemented is sent to PM through Slack.|
|__Tasks__|Sending team estimations basing on proposal or detailed document for proposal to Customer. |
|__Role__|**Business Analyst**|
|__Responsibility__|Depending on proposal clarity set of user stories might be created.<br>User story is Requirement issue on GitHub that can be find here: https://github.com/smartdevicelink/sdl_requirements/issues.<br>In each requirement issue detailed document is linked with the use case, use cases reviewed by proposal author are merged in here: https://github.com/smartdevicelink/sdl_requirements/tree/master/detailed_docs <br> Basing on proposal or detailed document for proposal team makes estimations which are being sent to Customer.<br>Business Analyst is responsible for the eliciting, collecting, documenting, analyzing, prioritizing, tracing and maintaining all-level requirements throughout the project.<br>Participates in reviews of requirement’s artifacts.<br>Perform planning and estimation of own requirements management activities.|
|__Tasks__|- Elicit requirements using interviews, document analysis,use cases, scenarios, event lists, business analysis, task and workflow analysis, communication with stakeholders and team.<br> - Write requirements specifications according to project-specific templates, using natural language simply, clearly, unambiguously, and concisely.<br> - Decompose high-level requirements into functional requirements. <br> - Perform requirements analysis and verification, ensuring that requirement statements are complete, consistent, concise, comprehensible, traceable, feasible, unambiguous, and verifiable, and that they conform to standards.<br> - Manage requirements traceability information according to project-specific standards.<br> - Perform project related actions (estimations, planning, participation in audits etc.) on PM's delegation. <br> - Work with the project team and project manager to document the product's vision and the project's scope.|
|__Role__|**CCB**|
|__Responsibility__|Decides on accepting/rejecting requirements for further technical analysis from schedule.<br>Reviews and accepts changes to requirements’ baseline on the project.|
|__Tasks__||
|__Role__|**Domain Expert**<br> _NOTE: Architect, Test Engineer or Senior Developer may act as Domain Expert._|
|__Responsibility__|Drive technical solutions in frame of requirements analysis on the project.|
|__Tasks__||

### Process Activities

#### Preliminary Analysis

| | |
|-|-|
|__Inputs__| SDL evolution Proposal |
|__Start criteria__| Proposal(s) to be analyzed are received from Customer as a contractual part of the development project. |  
|__Action list__|Proposal review<br>review of existing requirements<br>discuss with team current implementation| 


#### Update/Create Use Case        
| | |
|-|-|
|__Inputs__| SDL evolution Proposal; existing requirements; Email/Slack message  with link to proposal|
|__Start criteria__| New requirements are analyzed briefly |  
|__Action list__|Proposal review<br>review of existing requirements<br>discuss with team current implementation|  
  


create the table with reqs/notes  
compily a list of questions to customer,  work on use case
сreated requirements and techtask issues


### Work Documents
* SDL evolution proposal
* Technical task issue
* Requirement issue
* Use case
* TRS

