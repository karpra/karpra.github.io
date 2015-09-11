---
layout: post
category : automation
tagline : integration
tags : [concept]
---

## What is CI (Continous Integration)?

Continuous integration (CI) is the practice in software engineering, of merging all developer working copies into a single integrated Environment several times a day. The main aim of CI is to prevent integration problems, referred to as "integration hell" & to bring in governance of Software Development Life Cycle (SDLC) practices.

CI helps in agile adoption/methodology and is considered as an improvement over frequent integration.

## Why CI?

Any Application that goes through a development phase of SDLC adheres to multiple tools usage irrespective of number of developers in different geographies.Although its a good (or) best practice to adhere to these tools during the projects inception even if there is only one developer in the project.

1. Version Control Repository(VCS).
2. Integrated Development Environment (IDE).
3. Build Script.
4. Development.
5. Unit Testing.
6. Building & Deploying.

Developers take a copy of repository(base code) on their local machine and start developing , unit testing before the code 
is checked in the version control system.

Below is a typical CI Workflow 

![process]({{ site.baseurl }}/assets/images/01_16_2015_1.jpg)

Typically CI Server is scheduled to run nightly builds & deploys to the runtime enviroment ( application server) or any runtime environment hosting the source code artifacts. Apart from the nightly builds it does have feature to initiate a build on the fly once the developer checkin the code into VCS.

CI Server checks out the proect repository(source code, unit test scripts,build scripts) from the VCS & uses the build script to compile the source code and then build the artifact. In the process of CI pipeline it would then deploy to the runtime environment & go ahead with Unit testing the artifact & catalogue the report of success of failure in the CI dashboard.

We can configure the CI Server to send out alerts or reports of the build to the email or messaging system of the team responsible for the build. This helps in the local copy of the source code checked in and tested & ready for QA team to exercise overall integrated testing of the application.

Generally each developer before checkin the work to VCS,do a complete build and run (and pass) all unit tests. Integration tests are usually run automatically on a CI server when it detects a new commit.

## Conclusion

Continuous integration help in detecting the broken build scenarios early, also makes sure all local copies are always checked in VCS project repository eliminating any code or data loss. It aids in faster code building and deployment with less human error & avoid "integration hell", it reduces the "merge hell" by detecting early in the cycle than too late and too many files or repositories to merge.

Continuous integration involves integrating early and often, so as to avoid the pitfalls of "integration hell". The practice aims to reduce rework and thus reduce cost and time.





