# Governance

`haskell-cryptography` (herein referred to as the "Organisation") is a GitHub organisation that aims to provide a support structure to open-source maintainers producing cryptography projects.

The Organisation has the following goals:

* Prevent situations where too few people are supporting critical projects for the ecosystem.
* Prevent having a closed group of people having too much control over every aspect of a project.
* To encourage and support part-time, niche contributors to the projects.
* To ensure continuity and stability through documentation, testing and benchmarking.
* To listen to the needs of the community and industrial users, and lowering the barrier to industrial adoption.
* To ensure that current security practices are easy for others and maintained whithin the ecosystem.
* To ensure timely update in the community package repository

Examples of situations that we aim to remediate to:

> A single maintainer doing all the “boring work” suddenly becomes unavailable for reasons outside of the project.

> A large number of people requesting a fix or feature not being listened to for personal disagreements with the core maintenance team.

> Somebody wanting to contribute a feature but not knowing where to begin, how to approach it, because it is not explained anywhere.

> A pull-request lands which creates massive performance regression when compiled with `-O2`, affecting a large number of downstream users.

> Losing adoption opportunities because the most popular options are too entrenched and are maintained by stubborn people.

> A security flaw is discovered by researchers and we need to urgently upgrade a project, in a possibly breaking way.

> A bug fix has been approved, merged, but not released.

---

This document elaborates on administrative and operational aspects of the Organisation, designed to serve and fullfill these goals as a priority.

## Administrative aspect

The Organisation's administrative aspects are handled by the Core Team. The Core team are also contributors to projects.

### Bylaws

1. Core Team members are expected to do various kind of tasks, from code contributions to handling administrative and interpersonal aspects.
2. Core Team members are expected to be available long-term, and it if it's not the case, the other Core Team members may temporarily or permanently reassign their position.
3. Core Team members may be required to do work when needed, especially in the case of security issues, compiler adoption, etc.
4. The Core Team has no fixed number of seats, the number varies according to the needs of the Organisation.

The non-Core Team contributors are not bound to these items. Non-Core Team contributors can make infrequent contributions, not maintain extended presence and are not subject to working on-demand.

### Selection process

To be a part of the Core Team, the candidate needs to have a history of contributing to the projects hosted by the Organisation

An Interim Core Team will be formed from an initial pool of volunteers.

### Substitutions and Replacements

Substitutions: Stepping-up for a fixed period of time when a Core Team member cannot fulfill their role;

Replacement: Being a permanent replacement for a Core Team member;

## Operational aspect

As an Organisation, `haskell-cryptography` concerns itself with two things:

1. Code production and maintenance
2. Services related to the code and users

### Code production

`haskell-cryptography` produces a series of projects related to cryptography.
Each project has a key person that is the main point of contact for the project,
handle inquiries from the core team and act as a leading force for the project,
proving feedback on submitted code and setting directions.

This role involves enacting the goals of the Organisation, and being in charge of the management of the project,
whithin the framework established by the guidelines published in the [haskell-cryptography/governance](https://github.com/haskell-cryptography/governance) repository.
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
