SFCC CD Project Milestones


Created by John Wetherill
Mar 01, 20232 min read
7 people viewed
Phases and Milestones
Phase 1 - Testing Sandboxes
The goal of this phase is to provide an automated way for QA testers to create a new Salesforce ODS (on-demand sandbox) that has the minimally required configuration and data to allow a given branch to be deployed and tested with the storefront.

 

Milestone 0 - Preparation/Onboarding
Access for team members: (see SFCC CD Team Page)

GitHub

CircleCI

Jira

Confluence

Artifactory

Slack

Google Docs

SFCC development and staging environments

Infrastructure:

Create code repos for CircleCI jobs or use existing if appropriate

Figure out how to change/test code quickly for the CircleCI jobs

How difficult is it to unit test CircleCI jobs? Integration test?

Configure and setup SFCC CLI, evaluate its capabilities

 

Milestone 1 - Proof of Concept (1 sprints)
Create a job in CircleCI that does the following:

Uses the SFCC CLI to integrate with the Salesforce instances

Creates a log entry for each of the following operations including the date/time:

Authenticate

‘auth:*’ and/or `client:auth:*’ commands

Create ODS

‘sandbox:create’ command

Import any configuration or job as an example of the process

‘instance:import’ command (most likely, but not 100% here)

Import any chunk of data as an example of the process

‘data:upload’ command

Deploy any code version

‘code:deploy’ command

Activate any code version

‘code:activate command

Delete ODS

‘sandbox:delete’ command

Milestone 2 - Sandbox Initialization (1 sprint)
Create SFCC jobs in appropriate realms to back up required configuration and data, in order to allow for CircleCI job to use it for sandbox initialization

Expand the proof of concept CircleCI job to do the following:

Import configuration/jobs required to run the storefront

Import minimal dataset required to run the storefront

Milestone 3 - Automated Testing (½ sprint)
Ensure that LambdaTest can run against the auto-created ODS and has similar functional results as running against the dev or staging realms

This may require white-listing or authenticating to the realm is some way – Chandler Forrest is working on this for the staging environment, so the fix he determines will likely work here as well.

(Optional bonus points) Create a CircleCI job that can trigger a run of the automated testing against the auto-createdODS from LambdaTest

Milestone 4 - User Interface (tbd)
Create a way for users to provide the required data and then run the CircleCI job

(Optional bonus points) - Create a Slack chatbot that can do this

Phase 2 - Promotion to Development
The goal of this phase is to automate the merging of code and configuration from an arbitrary branch into the SFCC development realm.

Phase 3 - Promotion to Staging
The goal of this phase is to automate the merging of code and configuration from an arbitrary branch into the SFCC staging realm.

 

Must support merging/deployment to any environment (development, staging, production), which controls replication to other realms

Phase 4 - Promotion to Production
The goal of this phase is to automate the merging of code and configuration from an arbitrary branch into the SFCC production realm.
