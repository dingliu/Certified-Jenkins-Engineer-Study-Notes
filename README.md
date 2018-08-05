# Certified Jenkins Engineer (CJE) Exam Study Notes <!-- omit in toc -->

- [Key CI/CD/Jenkins Concepts](#key-cicdjenkins-concepts)
    - [Continuous Delivery/Continuous Integration Concepts](#continuous-deliverycontinuous-integration-concepts)
    - [Jobs](#jobs)
    - [Builds](#builds)
    - [Source Code Management](#source-code-management)
    - [Testing](#testing)
    - [Notifications](#notifications)
    - [Distributed Builds](#distributed-builds)
    - [Plugins](#plugins)
    - [Jenkins Rest API](#jenkins-rest-api)
    - [Security](#security)
    - [Fingerprints](#fingerprints)
    - [Artifacts](#artifacts)
    - [Using 3rd party tools](#using-3rd-party-tools)
    - [Installation Wizard](#installation-wizard)
- [Jenkins usage (features and functionality)](#jenkins-usage-features-and-functionality)
    - [Jobs](#jobs-1)
    - [Builds](#builds-1)
    - [Source Code Management](#source-code-management-1)
    - [Testing](#testing-1)
    - [Notifications](#notifications-1)
    - [Distributed Builds](#distributed-builds-1)
    - [Plugins](#plugins-1)
    - [CI/CD](#cicd)
    - [Jenkins Rest API](#jenkins-rest-api-1)
    - [Security](#security-1)
    - [Fingerprints](#fingerprints-1)
    - [Artifacts](#artifacts-1)
    - [Alerts](#alerts)
- [Building Continuous Delivery (CD) Pipelines](#building-continuous-delivery-cd-pipelines)
    - [Pipeline Concepts](#pipeline-concepts)
    - [Upstream and downstream](#upstream-and-downstream)
    - [Triggering](#triggering)
    - [Pipeline (formerly known as "Workflow")](#pipeline-formerly-known-as-workflow)
    - [Folders](#folders)
    - [Parameters](#parameters)
    - [Promotions](#promotions)
    - [Notifications](#notifications-2)
    - [Pipeline Multibranch and Repository Scanning](#pipeline-multibranch-and-repository-scanning)
    - [Pipeline Global Libraries](#pipeline-global-libraries)
- [CD-as-Code Best Practices](#cd-as-code-best-practices)

## Key CI/CD/Jenkins Concepts

### Continuous Delivery/Continuous Integration Concepts

- Define continuous integration, continuous delivery, continuous deployment
    - [Continuous Integration](https://www.martinfowler.com/articles/continuousIntegration.html)
      > Continuous Integration is a software development practice where members of a team integrate their work frequently, usually each person integrates at least daily - leading to multiple integrations per day.
    - [Continuous Delivery](https://martinfowler.com/bliki/ContinuousDelivery.html)
      > Continuous Delivery is a software development discipline where you build software in such a way that the software can be released to production at any time.
    - Continuous Deployment
      > Continuous deployment goes one step further than continuous delivery. With this practice, every change that passes all stages of your production pipeline is released to your customers. There's no human intervention.
- [Difference between CI and CD](https://www.atlassian.com/continuous-delivery/ci-vs-ci-vs-cd)
  > **CI**- The developer's changes are validated by creating a build and running automated tests against the build.
  >
  > **CD**- An extension of continuous integration to make sure that you can release new changes to your customers quickly in a sustainable way. 
- [Stages of CI and CD](https://www.michielrook.nl/2018/01/typical-ci-cd-pipeline-explained/)
    - **CI**
        - Code checkout
        - Code analysis, linting
        - Compile
        - Unit test
        - Integration test
        - Package artifacts
        - Publish artifacts
    - **CD**
        - Provision environments
        - Deploy artifacts to environments
        - Performing tests
            - Automated UI test
            - Performance and load test
            - Smoke test
            - Acceptance test
        - Manual release to production (Optional, for Continuous Delivery)
        - Monitoring and telemetry
- [Continuous delivery versus continuous deployment](https://puppet.com/blog/continuous-delivery-vs-continuous-deployment-what-s-diff)
  > **Continuous delivery**- a software development discipline where you build software in such a way that the software can be released to production at any time. Every change is delivered to a staging environment using complete automation. It can be deployed to production with a push of a button when the business is ready.
  >
  > **Continuous deployment**- the next step of continuous delivery: Every change that passes the automated tests is deployed to production automatically.

### Jobs

- What are jobs in Jenkins?
  > [**Jobs** are actually **projects** in Jenkins now.](https://stackoverflow.com/questions/17902242/difference-between-jenkins-job-and-project)
- Types of jobs
    - Freestyle
    - Maven
    - Pipline
    - Multi-configuration
    - Multibranch pipeline
    - External job
- Scope of jobs (**Can't find this item**)

### Builds

- [What are builds in Jenkins?](https://wiki.jenkins.io/display/JENKINS/Building+a+software+project)
- What are build steps, triggers, artifacts, and repositories?
    - **Build steps** are the basic building blocks for the Jenkins freestyle build process. They are what let you tell Jenkins exactly how you want your project built
    - **Triggers** are how you tell Jenkins when to kick off a build
    - **Artifacts** are files which are associated with a single build. Artifacts can be used to represent data created as a side-effect of running a Jenkins build.
- Build tools configuration
    - [YouTube- Jenkins using global tools configuration & java_ant_git_tutorial_job](https://www.youtube.com/watch?v=cE-tG8ccHK8)

### Source Code Management

- What are source code management systems and how are they used?
    - [Wikipedia- Version Control](https://en.wikipedia.org/wiki/Version_control)
- Cloud based SCMs
  > GitHub, Bitbuckte, AWS CodeCommit, and etc.
- Incremental updates vs. clean check out
  > **Incremental build**: if it doesn't think it needs to rebuild a project, it won't. It may also use partially-built bits of the project if they haven't changed
  >
  > **Clean solution** will remove the build artifacts from the previous build
- Checking in code
  > To **check in** (ci or, [commit](https://en.wikipedia.org/wiki/Commit_(revision_control))) is to write or merge the changes made in the working copy back to the repository. The terms 'commit' and 'checkin' can also be used as nouns to describe the new revision that is created as a result of committing.
- Infrastructure-as-Code
  > **[Infrastructure as code (IaC)](https://en.wikipedia.org/wiki/Infrastructure_as_Code)** is the process of managing and provisioning computer data centers through machine-readable definition files, rather than physical hardware configuration or interactive configuration tools
- Branch and Merge Strategies
  > [ABCs of a Branching and Merging Strategy](https://www.cmcrossroads.com/article/abcs-branching-and-merging-strategy) is a good article. The most commonly used strategies are [Gitflow](https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow) and [GitHub Flow](https://guides.github.com/introduction/flow/)

### Testing

- Benefits of testing with Jenkins
  > Test Automation software is the best way to increase the effectiveness, efficiency and coverage of your software testing. ... Once automated tests are created they can easily be repeated and they can be extended to perform tasks impossible with manual testing (see also [Top 10 Benefits of Automated Testing](https://saucelabs.com/blog/top-10-benefits-of-automated-testing))
- Define unit test, smoke test, acceptance test, automated verification/functional tests

### Notifications

- Types of notifications in Jenkins
- Importance of notifications

### [Distributed Builds](https://wiki.jenkins.io/display/JENKINS/Distributed+builds)

- What are distributed builds?
- Functions of masters and agents

### [Plugins](https://jenkins.io/doc/book/managing/plugins/)

- What are plugins?
- What is the plugin manager?

### Jenkins Rest API

- How to interact with it
- Why use it?

### Security

- Authentication versus authorization
- Matrix security
- Definition of auditing, credentials, and other key security concepts

### Fingerprints

- What are fingerprints?
- How do fingerprints work?

### Artifacts

- How to use artifacts in Jenkins
- Storing artifacts

### Using 3rd party tools

- How to use 3rd party tools

### Installation Wizard

- What is the Jenkins Installation Wizard?
- How to use the Wizard?
- Which configurations are covered by the Installation Wizard?

## Jenkins usage (features and functionality)

### Jobs

- Organizing jobs in Jenkins
- Parameterized jobs
- Usage of Freestyle/Pipeline/Matrix jobs
    - Matrix jobs are **Multi-configuration projects** now

### Builds

- Setting up build steps and triggers
- Configuring build tools
- Running scripts as part of build steps

### Source Code Management

- Polling source code management
- Creating hooks
- Including version control tags and version information

### Testing

- Testing for code coverage
- Test reports in Jenkins
- Displaying test results
- Integrating with test automation tools
- Breaking builds

### Notifications

- Setup and usage
- Email notifications, instant messaging
- Alarming on notifications

### Distributed Builds

- Setting up and running builds in parallel
- Setting up and using SSH agents, JNLP agents, cloud agents
- Monitoring nodes

### Plugins

- Setting up and using Plugin Manager
- Finding and configuring required plugins

### CI/CD

- Using Pipeline (formerly known as "Workflow")
- Integrating automated deployment
- Release management process
- Pipeline stage behavior

### Jenkins Rest API

- Using REST API to trigger jobs remotely, access job status, create/delete jobs

### Security

- Setting up and using security realms
- User database, project security, Matrix security
- Setting up and using auditing
- Setting up and using credentials

### Fingerprints

- Fingerprinting jobs shared or copied between jobs

### Artifacts

- Copying artifacts
- Using artifacts in Jenkins
- Artifact retention policy

### Alerts

- Making basic updates to jobs and build scripts
- Troubleshooting specific problems from build and test failure alerts

## Building Continuous Delivery (CD) Pipelines

### Pipeline Concepts

- Value stream mapping for CD pipelines
- Why create a pipeline?
- Gates within a CD pipeline
- How to protect centralized pipelines when multiple groups use same tools
- Definition of binary reuse, automated deployment, multiple environments
- Elements of your ideal CI/CD pipeline - tools
- Key concepts in building scripts (including security/password, environment information, etc.)

### Upstream and downstream

- Triggering jobs from other jobs
- Setting up the Parameterized Trigger plugin
- Upstream/downstream jobs

### Triggering

- Triggering Jenkins on code changes
- Difference between push and pull
- When to use push vs pull

### Pipeline (formerly known as "Workflow")

- Benefits of Pipeline vs linked jobs
- Functionalities offered by Pipeline
- How to use Pipeline
- Pipeline stage view

### Folders

- How to control access to items in Jenkins with folders
- Referencing jobs in folders

### Parameters

- Setting up test automation in Jenkins against an uploaded executable
- Passing parameters between jobs
- Identifying parameters and how to use them: file parameter, string parameter
- Jenkins CLI parameters

### Promotions

- Promotion of a job
- Why promote jobs?
- How to use the Promoted Builds plugin

### Notifications

- How to radiate information on CD pipelines to teams

### Pipeline Multibranch and Repository Scanning

- Usage of Multibranch jobs
- Scanning GitHub and BitBucket Organization
- Scanning basic SCM repositories

### Pipeline Global Libraries

- How to share code across Pipelines
- Usages of the Shared Libraries
- Interaction with Folders and Repository scanning
- Security and Groovy sandbox

## CD-as-Code Best Practices

- Distributed builds architecture
- Fungible (replaceable) agents
- Master-agent connectors and protocol
- Tool installations on agents
- Cloud agents
- Traceability
- High availability