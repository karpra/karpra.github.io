---
layout: post
category : devops
tagline: "Supporting tagline"
tags : [intro,automation]
---

# Whats is Devops?

Development & Operations teams forging together is devops. When i say that let me explain the typical
lifecyle activities of development team and operations team in getting any solution or application 
up & running available for the business to start using internally or externally (enterprise,b2b,b2c or consumer market).

Business typically are sponsors of any application or solution developed using a given platform ( eg : -python,php,java 
or .net etc) to solve a given business problem. Now comes project inception & companies bring in different set of teams
who for practical purposes have worked as seperate business unit within same organization who come together to solve 
a combined task towards a result oriented goal.

Development team starts developing the application which goes through typical SDLC process from Business Requirement
defining the functional requirement of the application which believe it or not is always constantly changing business
constantly pushes the changes & change management is unavoidable and this it not something new. Operations team are responsible to deliver a infrastructure for the application to be hosted and running in an stable environment for maximum uptime , throughput & performance defined by the SLA requirements of the application.

Business has always demanded these things : - 

*   Application Development to be agile and nimble enough to constant changes in requirement.
*   Operations team to deliver consistent stable runtime environment to host the application efficiently.
  
## Delivery Model

Traditional Delivery Model is time consuming and problematic on top it much easier for application development team to be nimble
but compromises quality of operations teams delivery for a stable enviornment. Either they need to choose to keep an older / unneeded infrastructure not being able to support runtime capability of application hosting (or) be adaptable to the change which has huge cost associated and time consuming.

Software Delivery Model came with Agile methodology to support such changing app development / infrastructure change support system. Agile did solve in tracking progress which is quiker and faster was able to deliver quantifiable results in application development or product development. Since Agile demanded quicker wins in measurable progress now industry came up with Continous Integration & Continous Delivery for quicker wins for business to support the demands.


Agile Methodology demanded few qualities of delivery process to be injected with to support the ever demanding landscape fo changes.

1. *Continous Integration* - Its a way software development is buildable / repeatable & automated in process of integration solution delivered constantly for deployment ready enviornment.
2. *Continous Delivery* - This enables IT both dev and ops to have repeated stable environment for business to use by infrastructure supporting the needs of application to be deployed in runtime.
3. *Release Management* - 

## Organizational Challenges.

Today dev & ops team work seperately to deliver the value business demands. Business always views IT function as one department , though in reality its operated seperately and two teams within IT department. When the dev team is notified of changes to app development they go through process of change management and push in changes to their software delivery. Ops teams are notified later even if they are proactively notified of app development changes most likely they understand the changes in their infrastructure later & this leads to blame game between dev versus ops team not fulfilling the business needs on time or quality.


## Tools

Continous Integration is predominately owned by dev team & Continous Delivery is worked out between release team and ops team.

Few examples of tools are

### Continous Integration
1. Jenkins
2. Hudson ( a fork of jenkins)
3. Cruise Control
4. Travis CI
5. BuildBot

### Continous Delivery( dev ops tools)
1. Chef
2. Puppet Labs
3. SaltStack
4. Ansible

## Conclusion
DevOps improves the overall stability of your system, because there are more capable eyes on the effect of various changes. Because features can be more quickly delivered, there are less large upgrades that require downtime. Instead, changes are delivered in smaller, more manageable pieces that may not require downtime at all.









