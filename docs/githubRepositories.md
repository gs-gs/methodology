# Repository and Teams Structure

## Github Teams

There will be four GitHub teams for each product with names & purpose as follows:
* {product}-contributors has members that have visibility of project code but cannot commit to master.  They must make pull requests on a repository in order to merge their code.  However contributors can create issues.
* {product}-maintainers has members that are authorised to approve pull requests to update master branch.  
* {product}-devops has members that are authorised to trigger deployments.  
* {product}-managers has members that have write access to the product level repository.

External developers (ie that are not cusotmer staff or onsite security cleared contractors) may only be members of the <product>-contributors team.  
* All users should use two-factor authentication.  

## Github Repositories

There will be one GitHub repository for each product that contains only product level documentation and issues and it will have the same name as the product (eg “appointments”).  This is essentially the “landing page” for each product.  In addition to this "root" repository for the project;

•	There will be two repositories for each product that are related to the devops framework:
  *  {product}-configuration that contains environment variables for each environment (integration, pre-production, production).  This is needed because the containerised deployment model will deploy exactly the same binary build to each environment where it is required.  Therefore the environment specific variables but be maintained separately and merged at deployment time.
  * {product}-infrastructure that contains the “infrastructure as code” scripts (whether using terraform.io or native AWS cloud formation) that describe the network and virtual host infrastructure for the product.  
  
•	There will be as many additional repositories as there are independently deployable units in the product.   In a similar way to teams, each will be named with the product name as the prefix and the deployment unit role as the suffix.  For example “appointments-api”.  The preferred role names are:
  * {product}-api for back-end Microservices.
  * {product}-ui for any front end user interface components that consume the services.
  * {product}-spec for the Microservice specification (eg swagger files), documentation, mocks, and tests.
  * {product}-app for any standalone app (eg native mobile) that consume the Microservices.
  * Others as required – with meaningful names.

Related (but separately deployable) units may be placed in the same repository but must be in different branches.  For example <product>-spec will typically contain three branches: “tests”, “mock”, and “spec”.

In no circumstances should separately deployable units be placed in the same branch of the same repository.  This causes a nightmare for change management in a continuous deployment framework.

## Making Commits

As implied by the github team roles and permission, the GoSource practice is that only customer stuff or onsite security cleared contractors can commit to master.  Therefore all other developers must work in local clones and make pull requsts to commit their code to master.  Aside from the security benefits, this is good working practice for distributed teams in any case.

### General commit rules

* please use short and descriptive commit messages [(nice guide)](https://chris.beams.io/posts/git-commit/). General rule - person with subject area knowledge shouldn't go inside the commit to understand what's been done.
* feel free to use rebase techniques in local forks before your commits are merged to the upstream
* while using GitHub configure your local git installation to pass correct username/email
* commits signature usage is encouraged, but still optional
* avoid merge commits when possible (use `git pull --rebase` or `git pull --ff-only` locally); rebasing the branch before merging to master may help as well.

## Open Source 

All repositories will be private (ie not visible to the general public) and the code is by default owned by the customer and not open source.  However, there are cases where the customer will want to contribute a product to open source and/or use an existing open source component.
* To contribute to the open source community, the customer will maintain a separate GitHub organisation and will clone any private repos that will be contributed to the dedicated open source github organisation.  This separation reduces risk of inadvertent open publishing and means that issues and discussions created during internal product development do not need to be published.
* To consume an open source product, the customer will clone the product to an internal repository of the same name.   This means that the customer can subsequently control deployable versions without risk of unexpected new contributions affecting customer products.

