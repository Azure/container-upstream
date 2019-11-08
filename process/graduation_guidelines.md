# Azure Container Upstream Graduation Guidelines v0.1
The Azure Container Upstream Graduation Guidelines owes much of its basis on two existing documents,
[CNCF Graduation Criteria](https://github.com/cncf/toc/blob/fc161c13a86ba022277a906a10ff51a568406f7c/process/graduation_criteria.adoc) 
and [.NET Foundation Project Maturity Profile](https://github.com/dotnet-foundation/project-maturity-model/blob/65fdfa43d7e68845bd65638c378cf834d7158b90/maturity-profiles.md). The goal of this document is to describe the process and 
minimum bar for each increasing level of project maturity to both provide a
goal for the project maintainers, but also to set expectations for consumers of these
projects.

## Process

Each project in Container Upstream (AzCU) has an associated maturity level. A proposed AzCU project 
should enter at the project's preferred maturity level. If the project originates within the AzCU 
group, then it should begin at the Sandbox Stage. If a joining project originates outside of the 
AzCU group, the preferred maturity level of the project must meet a 2/3 supermajority vote by the 
AzCU technical oversight committee (TOC). If the vote tally can not be met at the preferred 
maturity level, each previous level will receive a vote until a 2/3 supermajority is met. If the 
project does not receive enough votes at the Sandbox stage, the project is rejected.

Each project in AzCU will participate in a quarterly review by the TOC. The review will assess the 
project's maturity level as well as its community momentum. A 2/3 supermajority vote is required to 
graduate to the next maturity level. If the project is no longer needed or has become obsolete, the 
TOC can also vote with a 2/3 supermajority to archive the project.

For a project that has reached the "Graduation Stage" and would benefit from a more neutral home in 
a community foundation, the option of project donation is an option.

![AzCU Maturity Process](../images/maturity-diagram.png)

## Sandbox Stage
Sandbox projects are "early stage" projects that warrant experimentation. The project should be 
beneficial to Azure and the Cloud Native community, open to contributions from the public and have 
well-founded aspiration.

The AzCU Sandbox is the entry point for early stage projects and has the following goals:
- Encourage public visibility of experiments or other early work that can add value to the mission 
  of AzCU, Cloud Native in Azure and its impact on the larger Cloud Native community.
- Facilitate alignment with existing projects within Azure as well as the larger community
- Remove obstacles to adoption and contribution by ensuring projects adhere to Microsoft Open Source
  Guidelines, code of conduct and IP policy requirements
  
### Entry Requirements
- Required backing of at least one member of the product management
- Display of the AzCU "Sandbox" badge on website / readme
- Draft project proposal for review and approval by TOC
  - A great example is the [CNCF Project Proposal Process](https://github.com/cncf/toc/blob/fc161c13a86ba022277a906a10ff51a568406f7c/process/project_proposals.adoc)
  - TODO: create our own project proposal process based on the CNCF project proposal process
- Begin working toward achieving [Core Infrastructure Initiative Best Practices Badge](https://bestpractices.coreinfrastructure.org/)
  - Must have 
    - Gated PRs with unit tests
    - MSFT code of conduct
    - LCA bot enabled

## Incubating Stage
An Incubating project is one that has met all of the requirements of the Sandbox stage and is 
showing accelerating adoption.

### Entry Requirements
- Minimum of 3 engaged users using the project in a production or pre-production environment
- Minimum of 2 maintainers
- Full due diligence of the TOC
  - A great example is the [CNCF Due Diligence Guidelines](https://github.com/cncf/toc/blob/fc161c13a86ba022277a906a10ff51a568406f7c/process/due-diligence-guidelines.md)
  - TODO: create our own DD guidelines based on the CNCF DD guidelines
- Demonstrate a substantial ongoing flow of commits and merged contributions
- Have a healthy number of issues and pull requests from external contributors
- Set a clear, documented versioning scheme
- Show significant progress toward achieving [Core Infrastructure Initiative Best Practices Badge](https://bestpractices.coreinfrastructure.org/)
  - Must have 
    - Unit tests and integration tests covering a majority of the codebase
    - Linting
    - Static analysis (where appropriate)
    - An initial security review
    - Contributing guide
    - Issue and PR templates
    - Public project board with prioritization
    - Milestones for releases
- Telemetry for errors and general usage
  - If not possible, provide reasoning for why

## Graduation Stage
Graduation Stage project is one that has met all of the requirements of the Incubation stage and has
reached a level of maturity and polish which will delight users.

### Entry Requirements
- Minimum of 30 engaged users using the project in production
- Minimum of 4 maintainers (at least one from outside AzCU)
- Semester project road map published and updated
- Full due diligence of the TOC with an eye to any misalignment
- Have achieved and maintained a [Core Infrastructure Initiative Best Practices Badge](https://bestpractices.coreinfrastructure.org/)
  - Must have
    - Load tests and performance tests
  - Bonus for achieving Silver or higher
- Full security review and threat analysis with the Azure Green / Red teams
- Explicitly define a project governance and committer process. This preferably is laid out in a 
  GOVERNANCE.md file and references an OWNERS.md file showing the current and emeritus committers.
- Have a public list of project adopters for at least the primary repo (e.g., ADOPTERS.md or logos 
  on the project website). For a specification, have a list of adopters for the implementation(s) 
  of the spec.
- SLA / SLO guidance
- Support with ICM on-call rotations
- Telemetry and Metrics for errors and general usage
  - Define a set of KPIs with a dashboard
  - Setup alerting for anomalous value ranges
  - If not possible, provide reasoning for why

## Donation Stage
The Donation Stage is intended to be after the Graduation Stage for projects which would benefit 
from a more neutral home such as a community foundation. 

For example, CNCF describes a neutral home as follows:
A neutral home for your project increases the willingness of developers from other companies and 
independent developers to collaborate, contribute, and become committers. Neutrality requires that 
projects contribute their trademark to CNCF so that:

- No company is favored over any other
- CNCF ensures project governance is transparent and fair for everyone.

Some projects which are not directly tied to Azure may warrant such a graduation so they can gain 
more adoption through increased neutrality and governance.