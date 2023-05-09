# Governance

This document describes how the Liberal contribution governance structure is implemented in the Tinkerbell community.

## What is Liberal contribution?

Under a liberal contribution model, the people who do the most work [in the prescribed way] are recognized as most influential, but this is based on current work and not historic contributions.
Major project decisions are made based on a consensus seeking<sup>[1],[2]</sup> process (discuss major grievances) rather than pure vote, and strive to include as many community perspectives as possible.
Popular examples of projects that use a liberal contribution model include Node.js and Rust<sup>[3]</sup>.

## Community Roles

This doc outlines the various roles in the Tinkerbell community.

One of the overarching goals of having different roles in the community is to make sure to "allow good changes to enter the code with a minimum of fuss"<sup>[4]</sup>.
The following criteria is to be used when considering an individual for a role.

- a pattern of good judgement in regard to the code bases and to oneself
- demonstrated history of "playing nice" in the community
- amount and consistency of contributions and activity

| Role        | Responsibilities                                                  | Requirements                                                                                                                          | Defined by                                  |
| ----------- | ----------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------- |
| Contributor | Submit contributions                                              | Signed DCO                                                                                                                            | Registered GitHub User                      |
| Member      | Issue and discussion administration, PR reviewer                  | History of activity, good judgement, contribution in the community and the repositories, and sponsored by 2 Reviewers                 | Tinkerbell GitHub org member                |
| Reviewer    | Review code for quality and correctness                           | Same as Member, shows leadership in the community and the repositories, and sponsored by a Approver/Maintainers                       | .github/settings.yml file, reviewer entry   |
| Approver    | Right to make changes to the code bases, merge pull requests, etc | Same as Reviewer, shows leadership in the community and the repositories, and sponsored by an Approver/Maintainer                     | .github/settings.yml file, approver entry   |
| Maintainer  | Voting privileges (when required), sets direction and priorities  | Same as Approver, demonstrated responsibility and excellent technical judgement for the project, and voted in by existing Maintainers | .github/settings.yml file, maintainer entry |

## Member

Members are continuously active contributors in the community.
They can have issues and PRs assigned to them and pre-submit tests are automatically run for their PRs.
Members are expected to remain active contributors to the community.

**Defined by:** Member of the Tinkerbell GitHub organization

### Requirements

- Enabled [two-factor authentication] on their GitHub account
- Have made multiple contributions to the project or community. Contributions may include, but are not limited to:
  - Authoring or reviewing PRs on GitHub
  - Filing or commenting on issues on GitHub
  - Contributing to community discussions (e.g. meetings, Slack, email discussion forums)
- Subscribed to [tinkerbell-contributors@googlegroups.com]
- Actively contributing to 1 or more repository.
- Sponsored by 2 Reviewers. **Note the following requirements for sponsors**:
  - Sponsors must have close interactions with the prospective member - e.g. code/design/proposal review, coordinating on issues, etc.
  - Sponsors must be reviewers, approvers, or maintainers in at least 1 .github/settings.yml file in any repo in the [Tinkerbell org].
  - Sponsors should strive to be from multiple member companies to demonstrate integration across community.
- **[Open an issue]() [membership request] against the Tinkerbell/org repo**
  - Ensure your sponsors are @mentioned on the issue
  - Complete every item on the checklist ([preview the current version of the template](https://github.com/kubernetes/org/blob/main/.github/ISSUE_TEMPLATE/membership.yml))
  - Make sure that the list of contributions included is representative of your work on the project.
- Have your sponsoring reviewers reply confirmation of sponsorship: `+1`
- Once your sponsors have responded, your request will be reviewed by the [Tinkerbell GitHub Admin team]. Any missing information will be requested.

### Responsibilities and Privileges

- Can be assigned to issues and PRs; people can ask members for reviews with a `/cc @username`.
- Responsive to issues and PRs assigned to them
- Active owner of code they have contributed (unless ownership is explicitly transferred)
  - Code is well tested
  - Tests consistently pass
  - Addresses bugs or issues discovered after code is accepted
- Members can do `/lgtm` on open PRs.
- Tests can be run against their PRs automatically. No `/ok-to-test` needed.
- Members can do `/ok-to-test` for PRs that have a `needs-ok-to-test` label, and use commands like `/close` to close PRs as well.

___

## Reviewer

Reviewers are able to review code for quality and correctness on some part of the Tinkerbell project. They are knowledgeable about both the codebase and software engineering principles.

**Defined by:** _reviewers_ entry in the .github/settings.yml file in the repo owned by the Tinkerbell project.
Reviewer status is scoped to the repo/code in the Tinkerbell org.

### Requirements

The following applies to the repo or part of the codebase for which one would be a Reviewer in a .github/settings.yml file.

- Primary reviewer for at least 3 non-trivial PRs to the codebase; for example, spelling corrections are trivial, internal construct refactors are non-trivial.
- Knowledgeable about the codebase
- Sponsored by an Approver/Maintainer
  - With no objections from another Approver/Maintainer
  - Done through PR to update the .github/settings.yml file
- May either self-nominate, be nominated by a Approver/Maintainer

### Responsibilities and Privileges

The following apply to the repo or the part of the codebase for which one would be a reviewer in a .github/settings.yml file.

- Tests are automatically run for Pull Requests from members of the Tinkerbell GitHub organization
- Reviewer role may be a precondition to accepting large code contributions
- Responsible for project quality control via code reviews
  - Focus on code quality and correctness, including testing
  - Focus on design principles
- Expected to be responsive to review requests as per community expectations
- Assigned PRs to review related to area of expertise
- Assigned bugs related to area of expertise
- May get a badge on PR and issue comments

___

## Approver

Approvers are able to review code for quality and correctness on some part of Tinkerbell. They are knowledgeable about both the codebase and software engineering principles.

**Defined by:** _approvers_ entry in the .github/settings.yml file in the repo owned by the Tinkerbell project.
Approver status is scoped to the repo/code in the Tinkerbell org.

> Note: Acceptance of code contributions requires at least one Approver/maintainer in addition to the assigned reviewers.

### Requirements

The following applies to the repo or part of the codebase for which one would be a Approver in a .github/settings.yml file.

- Reviewer for at least 1 month
- Shallow understanding of the technical goals and direction of the repository
- Shallow understanding of the technical domain of the repository
- Reviewed or merged at least 3 substantial PRs to the codebase such as significant re-design or whole new features
- Nominated by a repo maintainer
  - With no objections from another repo maintainers
  - Done through PR to update the .github/settings.yml file

### Responsibilities and Privileges

The following apply to the repo or the part of the codebase for which one would be a Approver in a .github/settings.yml file.

- Approver status may be a precondition to accepting large code contributions
- Demonstrate sound technical judgement
- Responsible for project quality control via code reviews
- Focus on holistic acceptance of contribution such as dependencies with other features, backwards / forwards compatibility, API and flag definitions, etc
- Expected to be responsive to review requests as per community expectations
- Mentor contributors and reviewers
- May approve code contributions for acceptance

___

## Maintainer

Maintainers are the technical authority for a repository in the Tinkerbell project. They _MUST_ have demonstrated both good judgement and responsibility towards the health of that repository. Maintainers _MUST_ set technical direction and make or approve design decisions for their repository - either directly or through delegation of these responsibilities.

**Defined by:** _maintainers_ entry in the .github/settings.yml file in the repo owned by the Tinkerbell project.
Maintainer status is scoped to the repo/code in the Tinkerbell org.

### Requirements

Maintainers of a repository are typically limited to a relatively small group of decision makers and updated as fits the needs of the repository.

The following apply to the repository for which one would be an owner.

- Approver for at least 2 months
- Deep understanding of the technical goals and direction of the repository
- Deep understanding of the technical domain of the repository
- Sustained contributions to design and direction by doing all of:
  - Authoring and reviewing proposals
  - Initiating, contributing and resolving discussions (emails, GitHub issues, meetings)
  - Identifying subtle or complex issues in designs and implementation PRs
- Directly contributed to the repository through implementation and / or review

### Responsibilities and Privileges

The following apply to the repository for which one would be an owner.

- Make and approve technical design decisions for the repository.
- Set technical direction and priorities for the repository.
- Define milestones and releases.
- Mentor and guide Approvers, reviewers, and contributors to the repository.
- Ensure continued health of repository
  - Adequate test coverage to confidently release
  - Tests are passing reliably (i.e. not flaky) and are fixed when they fail
- Ensure a healthy process for discussion and decision making is in place.
- Work with other repository owners to maintain the project's overall health and success holistically

___

## Admin

Admins are the GitHub Administrators for the Tinkerbell project.

**Defined by:** _[owner](https://github.com/orgs/tinkerbell/people?query=role%3Aowner)_ role in the Tinkerbell GitHub organization.

### Requirements

This team is responsible for holding Org Owner privileges over the Tinkerbell org.

- Nominations to this team will come from the Maintainers and require confirmation from the Maintainers and Approvers before taking effect.
- Maintain active membership in the Tinkerbell community.

### Responsibilities and Privileges

Admins are responsible for:

- Administrative tasks in the Tinkerbell Github organization
- Being the point of contact with the CNCF (the CNCF calls this group "maintainers", see [here](https://github.com/cncf/foundation/blob/main/project-maintainers.csv))

Some administrative responsibilities are handled by contributors that do not meet the typical maintainer requirements with regard to code review and contributions. These contributors are nonetheless recognized and extended admin access as is necessary to fulfill the needs of the community including infrastructure, operational, security, and billing functions. These admins may require, for example, GitHub owner access, access to credentials, and CNCF maintainers list access.

---

## Role Fast Tracking

In certain circumstances it may be appropriate to fast track individuals into elevated roles. 

An individual to be fast tracked _should_ satisfy one or more of the following criteria:

- Has contributed substantially to the project and shown good judgment as determined by existing maintainers.
- Has demonstratable knowledge in closely related projects that translates to the target project. For example, Kubernetes controller knowledge may translate between projects.
- Meets all the requirements of roles with lesser responsibilities. For example, a fast track to Approver may occur if an individual meets all the Reviewer and Approver requirements in a short space of time (typically less than the timelines outlined for each role).

An individual to be fast tracked _must_ have expressed support from existing maintainers or admins from the Tinkerbell org.

___

## Inactive members

> This inactive members section follows the guideline defined in the Kubernetes community<sup>[5]</sup>

_Members are continuously active contributors in the community._

A core principle in maintaining a healthy community is encouraging active
participation. It is inevitable that people's focuses will change over time and
they are not expected to be actively contributing forever.

However, being a member of the Tinkerbell GitHub organization comes with
an [elevated set of permissions]. These capabilities should not be used by those
that are not familiar with the current state of the Tinkerbell project.

Therefore members with an extended period away from the project with no activity
will be removed from the Tinkerbell Github Organization and will be required to
go through the org membership process again after re-familiarizing themselves
with the current state.

### How inactivity is measured

Inactive members are defined as members of the Tinkerbell Organization
with **no** contributions across any repos within 8 months. This is
measured by the CNCF [DevStats project].

**Note:** Devstats does not take into account non-code contributions. If a
non-code contributing member is accidentally removed this way, they may open an
issue to quickly be re-instated.

After an extended period away from the project with no activity
those members would need to re-familiarize themselves with the current state
before being able to contribute effectively.

[1]: https://producingoss.com/html-chunk/consensus-democracy.html
[2]: https://en.wikipedia.org/wiki/Consensus-seeking_decision-making
[3]: https://opensource.guide/leadership-and-governance/#what-are-some-of-the-common-governance-structures-for-open-source-projects
[4]: https://producingoss.com/html-chunk/Approvers.html
[5]: https://github.com/kubernetes/community/blob/master/community-membership.md
