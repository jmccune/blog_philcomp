---
layout: post
title:  "Principled Development"
date:   2017-03-01 13:34:00 -0500
categories: best-practices development  architecture
---

### Architecture Principles ###

- Architects work between the boundaries of system components or [bounded contexts](https://martinfowler.com/bliki/BoundedContext.html).  They specify the zoning rules and laws, the communication, versioning, etc. requirements between these various portions of an application.

- Architects are responsible for technical governance: "Governance ensures that stakeholder needs, conditions and options are evaluated to determine balanced, agreed-on enterprise objectives to be achieved; setting direction through prioritization and decision making; and monitoring performance and compliance against agreed-on direction and objectives" [COBIT Governance]   While architects are responsible, they are not the only
ones involved in the governance-- as the organization and technical teams in particular are stakeholders
in that definition.



### Testing Principles ###

**Definition:** Testing asserts exactly which portions of a particular system run correctly (where correctly is defined only by a passing test and the particular implications of that test).

-    It is useful (and essential in large-systems) for regression testing, refactoring safety assurances during new development, and proportional confidence that delivery will be met successfully.   Another benefit is that allows the use of betas/latest-software-versions because all required use-cases (and possibly a new required feature-set) is demonstrably supported and passing.

- Testing at a minimum (MVP) does the sunny side case (showing that the system works as intended, producing
the expected output for the expected input).  These include the boundaries and significant variations of the expected inputs (is null allowed, what about empty for collections, the min, the max,  ascii & unicode character sets, repeated values, special values, etc. )

- Assuming you want to deliver more than correct software that works only in ideal/ivory tower situations, testing can & should test for problematic & error conditions for both functional & non-functional requirements.

	- These include both input & outputs that are _not_ expected. Does the system respond correctly or as expected to inputs that are not allowed (less than the minimum, greater than the maximum, an illegal character/value, ill-formatted input, non-existent input, missing required fields, etc).

	- Have scalability & performance concerns been addressed --
		is correctness preserved with multiple simultaneous requests, is the system responsive within acceptable timeframes when there are N simultaneous requests, and does it degrade/fail as
		desired as you approach the limits and go beyond them?

	- Is the system secured?  (against hacking/malicious inputs like "Drop Table", Buffer Overflows,etc.?
		Does the system allow authorized users and disallow unauthorized users?,
		is sensitive information found in the logs, etc.)

	- Is the system otherwise robust (No memory leaks,correctly expiring/removing cache entries,
		proper (data)store management -- avoiding filling hard-drives, databases  etc.)


- Level-Setting:  one _must_ pick and choose.
	_Testing everything is a bad idea._   You can have unit tests, component tests,
	integration tests, end-to-end tests, (and just to make sure you're thinking of these: browsers as
	a component, different browsers, and/or 3rd party componenets/systems & variations therein).
	Just in case it needs saying, one would test front-end code (javascript) similarly to the back-end unit & component tests.  When you multiply those across concerns of expected/unexpected inputs, security, scalability, & robustness...    You're not testing everything at every level.

	_You must pick and choose what makes sense and achieves what is necessary and desirable._


### Sources ###
  - [COBIT Governance] Control Objectives for Information and Related Technology


[COBIT Governance]: https://www.isaca.org/Pages/Glossary.aspx?tid=1443&char=G

