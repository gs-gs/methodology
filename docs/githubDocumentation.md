# Project Documentation

High quality product documentation is critical for the sustainability of the product.  The documentation should also be current at any time (ie no shelf-ware documents that just gather dust).  This means that the documentation should not be repetitive or verbose.  It exists to give new project team members a sound understanding of product requirements, solution architecture, and operational information.   The issues (eg epics & stories) form part of the documentation.  The code itself is also part of the documentation.  Therefore the wiki content should not repeat information that is already in a story ticket and should not elaborate detailed technical information that is equally easily discovered from the code.  

The readme.md page in the GitHub product repo (or the home page in the confluence product wiki) should contain the following sections & content:

* Overview – a heading with the following sub-items:
  * Project on a page – a link to the standard one-page format for an agile project description.
  * Goals and Measures – a link to a page that defines the success criteria for the product (usually in terms of user uptake, cost reduction, business outcome improvement) and how they will be measured.  Ideally the measures are built into the product as live instrumented dashboards.
  * Supporting Documents – a link to a page that contains any supporting documents which may be internal or external.
  * Glossary – a link to a page that contains a list of terms relevant to the product and their definitions.

* Business Requirements – a heading with the following sub-items
  * User Roles – a link to a page that list of all user roles with a statement of need and an indication of volumetrics for each role.
  * Current Journey Map – a link to a current state overarching view of the business domain.  This is a standard format layout poster with stages (value chain) as columns with with user experience (roles, doing, thinking, feeling) as rows.
  * Future Journey Map – a link to a future state view of the business domain after delivery of the digital product.
  * Epics – a link to the Github/JIRA issues list that represents all the epics.
  * Stories – a link to the GitHub/JIRA issues list that represents all the stories 
  * MVP Definition – a link to a page that describes the thinking and evidence for the scope of the minimum viable product that will be the first beta release. 

* Solution Architecture – a heading with the following sub-items
  * System Context Model – a link to a page shoing a high level component architecture diagram and interfaces with external systems & users.
  * Wireframes and Mockups – a link to a page that contains a set of wireframes for each UI.  As the project progresses, these wireframes will typically get replaced with design mockups.
  * Data Model – a link to a page that contains a logical E-R (Entity relation) model for all the key entities in the domain, including the properties of each entity.  This is often the source for a quick admin tool implementation.
  * Service Model – a link to a swagger-aglio generated suite of Microservice API documentation that defines the interfaces that the product will expose.  
  * Security Model – a link to a page that described the security framework for the product including (as a minimum) the authentication model, the permissions for each role, and what key application events will be logged.  Note that network security concerns are normally part of the devops framework and technology stack pattern and so need not be included here.
  * State Lifecycle Models – a link to a page that contains a state lifecycle diagram for any of the entities in the data model that include a concept of status and actions that can changes the status. 

* Test Framework – a heading with the following sub-items
  * Test Data Management – a link to a page that describes how test data will be created & managed managed in each environment.
  * BDD Test Cases – a link to a page that lists the BDD sceanrios.  Often these will be documented in a formal language (eg gherkin) and maintained as repository files – so this page should just link to the files with a few words of description.

* System Operations – a heading with the following sub-items
  * DevOps Framework – a link to a page the describes how developers should build their code (eg to docker containers) and how release managers should approve releases (eg via Jenkins dashboard).
  * System Access – a link to a page the lists the access URLs (and, where appropriate test user account credentials) for the product. For each environment.

* Project Management – a heading with the following sub-items
  * Methodology - a link to a page describing the project management practices (collaboration tools, issue management, etc)
  * Raw List of Issues – a link to a page with links to issues with various filters.
  * Kanban view of stories – a link to the current Kanban (eg github project view).
  * Milestones – a link to the milestones summary which should show scope and % complete for each milestone.


