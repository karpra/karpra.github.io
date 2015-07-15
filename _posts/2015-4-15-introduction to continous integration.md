---
layout: post
category : automation
tags : [concept]
---

## What is CI (Continous Integration)?

Continuous integration (CI) is the practice in software engineering, of merging all developer working copies into a single integrated Environment several times a day. The main aim of CI is to prevent integration problems, referred to as "integration hell" & to bring in governance of Software Development Life Cycle (SDLC) practices.

CI helps in agile adoption/methodology and is considered as an improvement over frequent integration.

## Why CI?

Any Application that goes through a development phase of SDLC adheres to multiple tools usage irrespective of number of developers in different geographies.Although its a good (or) best practice to adhere to these tools during the projects inception even if there is only one developer in the project.

1. Version Control Repository.
2. Integrated Development Environment.
3. Development.
4. Unit Testing.
5. Building & Deploying.

Developers take a copy of repository(base code) on their local machine and start developing , unit testing before the code 
When embarking on a change( add,updating or deleting) , a developer takes a copy of the current code base on which to work. As other developers submit changed code to the source code repository, this copy gradually ceases to reflect the repository code. Not only can the existing code base change, but new code can be added as well as new libraries, and other resources that create dependencies, and potential conflicts.

The longer a branch of code remains checked out, the greater the risk of multiple integration conflicts and failures when the developer branch is reintegrated into the main line. When developers submit code to the repository they must first update their code to reflect the changes in the repository since they took their copy. The more changes the repository contains, the more work developers must do before submitting their own changes.

Eventually, the repository may become so different from the developers' baselines that they enter what is sometimes referred to as "merge hell", or "integration hell",[2] where the time it takes to integrate exceeds the time it took to make their original changes. In a worst-case scenario, developers may have to discard their changes and completely redo the work.

Continuous integration involves integrating early and often, so as to avoid the pitfalls of "integration hell". The practice aims to reduce rework and thus reduce cost and time.

A complementary practice to CI is that before submitting work, each programmer must do a complete build and run (and pass) all unit tests. Integration tests are usually run automatically on a CI server when it detects a new commit.

Below is a typical CI Workflow 

![process]({{ site.baseurl }}/assets/images/01_16_2015_1.jpg)

## Conclusion




