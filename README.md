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

## Key CI/CD/Jenkins Concepts

### Continuous Delivery/Continuous Integration Concepts

- Define continuous integration, continuous delivery, continuous deployment
    - [Continuous Integration](https://www.martinfowler.com/articles/continuousIntegration.html)
    - [Continuous Delivery](https://martinfowler.com/bliki/ContinuousDelivery.html)
    - Continuous Deployment
- [Difference between CI and CD](https://www.atlassian.com/continuous-delivery/ci-vs-ci-vs-cd)
- [Stages of CI and CD](https://www.michielrook.nl/2018/01/typical-ci-cd-pipeline-explained/)
- [Continuous delivery versus continuous deployment](https://puppet.com/blog/continuous-delivery-vs-continuous-deployment-what-s-diff)

### Jobs

**Jobs** are actually **projects** in Jenkins now.

- What are jobs in Jenkins?
- Types of jobs
- Scope of jobs

### Builds

- What are builds in Jenkins?
- What are build steps, triggers, artifacts, and repositories?
- Build tools configuration

### Source Code Management

- What are source code management systems and how are they used?
- Cloud based SCMs
- Incremental updates vs. clean check out
- Checking in code
- Infrastructure-as-Code
- Branch and Merge Strategies

### Testing

- Benefits of testing with Jenkins
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