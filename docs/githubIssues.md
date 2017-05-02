# Project Management with GitHub Issues

Github issues are the heart of the work management of agile delivery.  They are also the placeholders for the formal record of “conversations” with stakeholders about requirements (Epics & stories).  The following conventions must be observed:

## Project Level Views

The root **project** repository contains all Epics, Stories, and project level tasks.  It provides a single point where the business scope and delivery status of the project can be tracked.  This repository has project level milestones.

* One organisation level GitHub “project” will be used for scrum/Kanban style delivery management of each DIBP product and will have the same name as the product (eg “appointments”.  Although github allows projects at either org or repository level, org level projects are preferred because they can aggregate issues from multiple repos.
  * The Kanban columns will typically be “backlog”, “not-started”, “in-progress”, “done”.
  * All issues dragged onto the Kanban must have an assignee (apart from “backlog”).

* Issues are maintained (mostly) in the root repository which will have:
  * [standard milestones](https://github.com/gs-gs/sample-project/milestones?direction=asc&sort=due_date&state=open) reflecting delivery phases defined by the [DTA Servie Standard](https://www.dta.gov.au/standard/service-design-and-delivery-process/).  Post go live milestones will be used to manage ongoing releases with milestone names reflecting the major.minor release version.  For example “release 1.2”.
  * A set of [standard tags](https://github.com/gs-gs/sample-project/labels) colour coded - blue stuff is to-do, green stuff is who you are doing it for, yellow stuff is where you are doing it, red stuff is panic, grey stuff is not very interesting yet.
  * Epics (very high level groups of features) recorded as an issue with tag “epic” without a milestone.  Epics are closed when the full scope of stories are defined.
  * All Stories are recorded as issues with tag “story” and an associated milestone.   All stories must follow the agile story structure “As a {role], I need a {feature} so that I can {outcome}".   
  * Stories are closed when a full set of testable scenarios are defined and the corresponding BDD tests are passing in the lowest environment.  A story can be closed before production release because the release indicator is the milestone.
  * Every story should also reference the epic of which it is a part (eg “Epic #12”).  The references from the story will automatically display against the epic – which is a nice way to show the scope of the epic in terms of included stories.
  * Any number of comments will typically be appended to the story as business and technical stakeholders interact to elaborate the story.  The story ticket is the formal record of these conversations.  So any slack /skype chat that impacts a story should be summarised as a comment against the story.

## Component Level Views

Each project will have one or more repositories for each separately deployable component.  This is usually the focus areas for a specific developer.  The component repositories contain the specific techncial tasks that will implement stories and contain any bugs that are specific to the component.

* Issues in the component reposiutories are only of type "task" or bug" (TAGs)
* Tasks are closed when successfully deployed (ie passing all BDD tests) to the lowest environment.
* Bugs are closed when the fix is verified by the tester that reported it.
* There is no use for milestones or project kanbans in the component repositories.

