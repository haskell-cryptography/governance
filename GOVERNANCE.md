# Governance

`haskell-cryptography` (herein referred to as the "Organisation") is an organisation that aims to provide a support structure to open-source maintainers producing projects wrapping or implementing cryptography.

The Organisation has the following goals:

* Prevent situations where too few people are supporting critical projects for the ecosystem.
* Prevent having a closed group of people having too much control over every aspect of a project.
* To encourage and support part-time and occasional contributors to the projects.
* To ensure continuity and stability through documentation, testing and benchmarking.
* To listen to the needs of the community and industrial users, and lower the barrier to industrial adoption.
* To ensure that current security practices are easy for others and maintained within the ecosystem.
* To ensure timely updates are published in community package repositories, such as Hackage.

Examples of situations that we aim to avoid:

> A single maintainer doing all the “boring work” suddenly becomes unavailable for reasons outside of the project.

> A large number of people requesting a fix or feature not being listened to due to personal disagreements with the maintenance team.

> Somebody wanting to contribute a feature but not knowing where to begin, or how to approach it, because it is not explained anywhere.

> A pull request lands which creates massive performance regression when compiled with `-O2`, affecting a large number of downstream users.

> Losing adoption opportunities because the most popular options are too entrenched and are maintained by opinionated maintainers who are not open to outside suggestions from users.

> A security flaw is discovered by researchers and we need to urgently upgrade a project, in a possibly breaking way.

> A bug fix has been approved and merged, but not released.

---

This document elaborates on administrative and operational aspects of the Organisation, designed to serve and fullfill these goals as a priority.

## Administrative aspect

The Organisation's administrative aspects are handled by the Core Team. The Core team are also contributors to projects.

### Bylaws

1. Core Team members are expected to do various kind of tasks, from code contributions to handling administrative and interpersonal aspects.
2. Core Team members are expected to be available long-term. If this becomes impossible, the other Core Team members may have to temporarily or permanently take over the work of the member who is absent.
3. Core Team members may be required to do work when needed, especially in the case of security issues, compiler upgrades, etc.
4. The Core Team has no fixed number of seats, the number varies according to the needs of the Organisation.

The non-Core Team contributors are not bound by these bylaws. Non-Core Team contributors can make infrequent contributions, not maintain extended presence and are not subject to working on-demand.

### Selection process

To be a part of the Core Team, the candidate needs to have a history of contributing to the projects hosted by the Organisation.
An Interim Core Team will be formed from an initial pool of volunteers.

### Substitutions and Replacements

Should a Core Team member be unable to fulfill their role, the Core Team has the ability to have someone else step-up for a fixed period of time ("substitution"),
or bring a more permanent member to the team as one member leaves ("replacement").

## Operational aspect

As an organisation, `haskell-cryptography` concerns itself with two things:

1. Code production and maintenance
2. Services related to the code and users

### Code production

`haskell-cryptography` produces a series of projects related to cryptography.
Each project has a key person that is the main point of contact for the project,
handles inquiries from the core team and acts as a leading force for the project,
proving feedback on submitted code and setting directions.

This role involves enacting the goals of the Organisation, and being in charge of the management of the project,
within the framework established by the guidelines published in the [haskell-cryptography/governance](https://github.com/haskell-cryptography/governance) repository.
The key person is autonomous but accountable for the project. This doesn't prevent a decision process that involves multiple parties in a "flat"
governance structure for a project, but the key person is the one person that is in charge of making these decisions official,
answering for them and enforcing them.

### Services related to the code and users

As a support structure for open-source maintainers, `haskell-cryptography` has the ability to host projects of the Haskell ecosystem related to cryptography,
should their maintainer decide that this is the best course of action for their project.
By transferring a project to the organisation, the authors of a project do not implictly relinquish their permissions, authorship and ownership
of the project, and benefit from the collaborators of the organisation to help them with tasks they need help with.

Projects can be donated for ongoing maintenance and improvement, or to seek new leadership. 
The organisation intends to allow package maintainers to maintain control of their packages, if they wish to, while making it easier to bring together
effort to improve the state of cryptography in the Haskell ecosystem.
In the interest of keeping a healthy and secure ecosystem, the Core Team will have to perform some tasks on projects that were transferred to the Organisation.
These tasks, like merging patches or publishing new releases on Hackage, may take priority over the specific ideas of the original authors of the projects.
We acknowledge that the authors have insights that we lack and know their domains better than the Core Team may; but in the interest of the ecosystem,
the needs of our contributors and users may outweigh the ideals of the original authors.

As such, upload permissions on Hackage shall be given with at least one member of the Core Team, who is not also the original author of the project.

This is a flexible policy and consensus with the authors will always be preferred.
