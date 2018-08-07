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
  > **Unit test**- a software testing method by which individual units of source code, sets of one or more computer program modules together with associated control data, usage procedures, and operating procedures, are tested to determine whether they are fit for use. ([Wikipedia](https://en.wikipedia.org/wiki/Unit_testing))
  >
  > **Smoke test** is preliminary testing to reveal simple failures severe enough to, for example, reject a prospective software release. ([Wikipedia](https://en.wikipedia.org/wiki/Smoke_testing_(software)))
  >
  > **Acceptance test**- a formal testing with respect to user needs, requirements, and business processes conducted to determine whether a system satisfies the acceptance criteria and to enable the user, customers or other authorized entity to determine whether or not to accept the system. ([Wikepedia](https://en.wikipedia.org/wiki/Acceptance_testing))
  >
  > **Functional test** is a quality assurance (QA) process and a type of black-box testing that bases its test cases on the specifications of the software component under test. ([Wikipedia](https://en.wikipedia.org/wiki/Functional_testing))

### Notifications

- Types of notifications in Jenkins
  > Email, RSS, IM (IRC, Slack, and etc.), HTTP call
- Importance of notifications
  > Better visibility, more transparent, faster feedback loop, continuous improvement, and etc.

### [Distributed Builds](https://wiki.jenkins.io/display/JENKINS/Distributed+builds)

- What are distributed builds?
  > The reason being that workloads are often best "farmed out" to distributed servers. This may be for scale, or to provide different tools, or build on different target platforms. Another common reason for remote agents is to enact deployments into secured environments (without the master having direct access).
- Functions of masters and agents
  > A "**master**" operating by itself is the basic installation of Jenkins and in this configuration the master handles all tasks for your build system.
  > 
  > An **agent** is a computer that is set up to offload build projects from the master and once setup this distribution of tasks is fairly automatic. 

### [Plugins](https://jenkins.io/doc/book/managing/plugins/)

- What are plugins?
  > Jenkins defines extensibility points, which are interfaces or abstract classes that model an aspect of a build system. Those interfaces define contracts of what need to be implemented, and Jenkins allows plugins to contribute those implementations.
- What is the plugin manager?
  > The Web UI to manage Jenkins plugins.

### [Jenkins Rest API](https://wiki.jenkins.io/display/JENKINS/Remote+access+API)

- How to interact with it
  > BASH (curl), PowerShell (Invoke-WebRrequest or Invoke-RestMethod), web client, etc.
- Why use it?
  > Interact with Jenkins programmatically


### Security

- [Authentication versus authorization](https://stackoverflow.com/questions/6556522/authentication-versus-authorization)
- [Matrix security](https://wiki.jenkins.io/display/JENKINS/Matrix-based+security)
- Definition of auditing, credentials, and other key security concepts
  > An **IT audit** is the examination and evaluation of an organization's information technology infrastructure, policies and operations. Information technology audits determine whether IT controls protect corporate assets, ensure data integrity and are aligned with the business's overall goals.
  > 
  > **Credentials** refer to the verification of identity or tools for authentication. They may be part of a certificate or other authentication process that helps confirm a user’s identity in relation to a network address or other system ID.
  > [Other key security concepts from Wikipedia](https://en.wikipedia.org/wiki/Information_security#Key_concepts)

### Fingerprints

- What are [fingerprints](https://wiki.jenkins.io/display/JENKINS/Fingerprint)?
  > Jenkins supports file fingerprinting to track interdependencies of artifacts in different projects.
- How do fingerprints work?
  > The fingerprint of a file is simply a MD5 checksum. Jenkins maintains a database of md5sum, and for each md5sum, Jenkins records which builds of which projects used. This database is updated every time a build runs and files are fingerprinted.

### Artifacts

- How to use artifacts in Jenkins
  > 1. Archive artifacts in upstream projects: In the Jenkins project (or job) configuration, create a **Post Build Action**, select **Archive the artifacts**, also in **General** section, set the **Permission to Copy Artifact**
  > 2. Use the archived artifacts in downstream projects: In the Jenkins project (or job) configuration, create a **Build step**, select **Copy artifacts from another project**
- Storing artifacts
  > It is being archived on the master server (even if the build were on a slave) in the following folder:
  >
  > `$JENKINS_HOME/jobs/<job>/builds/<build>/archive`
  >
  > But you can configure a different location using the 'Advanced' setting of the job (where you can set a different workspace folder) or using plugins that are made for this purpose such as Copy Artifact Plugin ([Stack Overflow](https://stackoverflow.com/questions/35890952/where-are-jenkins-artifacts-located))

### Using 3rd party tools

- How to use 3rd party tools
  > Not very sure what is the scope of 3rd party tools. A lot of plugins provide integration with 3rd party tools. Also 3rd party tools can use Jenkins Rest API or Jenkins CLI to work with Jenkins.

### Installation Wizard

- What is the Jenkins Installation Wizard?
  > It is the [post-installation setup wizard](https://jenkins.io/doc/book/installing/#setup-wizard). It takes you through are a few quick "one-off" steps to unlock Jenkins, customize it with plugins and create the first administrator user through which you can continue accessing Jenkins.
- How to use the Wizard?
- Which configurations are covered by the Installation Wizard?
  > Unlock Jenkins by providing the Administrator password. Customizing Jenkins with plugins. Creating the first administrator user

## Jenkins usage (features and functionality)

### Jobs

- Organizing jobs in Jenkins
  > **[Views](https://www.cloudbees.com/blog/organizing-jobs-views-instead-folders-just-my-grandma)** (my view or custom view) and **folders** are the ways to organize projects
- Parameterized jobs
  > Use **[parameterized build](https://wiki.jenkins.io/display/JENKINS/Parameterized+Build)**, The parameters are available as environment variables.
  > The **[Parameterized Trigger Plugin](https://wiki.jenkins.io/display/JENKINS/Parameterized+Trigger+Plugin)** lets you trigger new builds when your build has completed, with various ways of specifying parameters for the new build.
- Usage of Freestyle/Pipeline/Matrix jobs
    > Matrix jobs are [**Multi-configuration projects**](https://wiki.jenkins.io/display/JENKINS/Building+a+matrix+project) now.
    >
    > **Freestyle** projects are good start point and can be treated as an empty template.
    > [**Pipeline**](https://jenkins.io/doc/book/pipeline/) in Jenkins is a suite of plugins that supports implementing and integrating continuous delivery pipelines into Jenkins. Pipeline provides an extensible set of tools for modeling simple-to-complex delivery pipelines "as code" via the Pipeline DSL.

### Builds

- Setting up build steps and triggers
  > In **freestyle** projects, build steps are defined in configuration (build section). In **pipeline** projects, build steps are defined by Pipeline DSL.
  >
  > Build [**triggers**](https://stackoverflow.com/a/47758526) are defined in the project configuration (**Build Triggers** section). The triggers can be another upstream project, a schedule, a SCM hook, polling SCM changes, or an API call.
- Configuring build tools
  > You can configure build tools in **Manage Jenkins, Global Tools Configuration**.
  > 
  > There are sections for **Maven**, **JDK**, **Git**, **Gradle**, **Ant**, **Docker**, and etc.
- Running scripts as part of build steps
  > In **freestyle** projects, you can select running scripts as a build step.
  >
  > In **pipeline** projects, you can run scripts via the **`sh`** directive.

### Source Code Management

- Polling source code management
  > The schedule of polling SCM can be defined with [cron job syntax](http://www.adminschoice.com/crontab-quick-reference) (with minor difference) with additional time zone specificcation)
- Creating hooks
  > There is [a great tutorial](https://www.atlassian.com/git/tutorials/git-hooks) from Atlassian, the maker of Bitbucket, on Git hooks.
- Including version control tags and version information
  > [_How do you achieve a numeric versioning scheme with Git_](https://softwareengineering.stackexchange.com/questions/141973/how-do-you-achieve-a-numeric-versioning-scheme-with-git) from Stack Overflow

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