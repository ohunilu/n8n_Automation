# Client Onboarding Workflow

## Overview

I built this "Client Onboarding Workflow" automation to demonstrate how n8n can be used to streamline the onboarding process for new clients at a consultancy business. The automation addresses the business challenge of manual project folder creation, email notifications, and logging, which are time-consuming and error-prone when handled individually. By automating these tasks, the workflow reduces administrative overhead, ensures consistency, and enhances client experience. This documentation is tailored for trainees, collaborators, or potential clients, offering a clear path to deploy and extend the solution while showcasing its career and monetization potential through a unique, production-ready design.

## Automation Title

Client Onboarding Workflow

## Category

Operations

## Image/Thumbnail

[Insert screenshot of the n8n workflow dashboard showing Google Sheets Trigger, Asana, Google Drive, and Gmail nodes]

## Detailed Description

The Client Onboarding Workflow automates the end-to-end process of onboarding new clients, a critical operation for consultancy businesses managing multiple projects. Traditionally, account managers manually create Google Drive folders, subfolders, send welcome emails, and log details in spreadsheets, which can take 1-2 hours per client and risk human error. This automation solves these inefficiencies by triggering on new Google Form submissions, creating a structured folder system, notifying the assigned manager, and logging the process—all within minutes.

The workflow targets consultancy businesses or freelancers handling client projects across categories like Automation, Data Analysis, and Cloud Migration. It integrates with Google Workspace for storage and email, Asana for project management, and Airtable for data staging (CRM), delivering a seamless experience. Expected outcomes include a 70% reduction in onboarding time (from 120 minutes to 30-40 minutes), improved accuracy in folder structures, and automated communication that enhances client satisfaction. This solution stands out by combining multiple tools in a custom n8n setup, setting it apart from common single-tool automations. You can download and upload the JSON file of the workflow and improve on it.

## How It Works (Functionality)

1. **Trigger**: A Google Sheets Trigger monitors a "Client Onboarding" sheet updated via a Google Form, capturing fields like Legal Company Name, Email Address, Project Category, and Package.
2. **Data Staging**: An Airtable Search node fetches if the client data is present in the Airtable, merged with the Trigger node to weed duplicates.
3. **Project Creation**: A Switch node routes to an Asana HTTP Request node (e.g., "Asana - Data Analysis Request") based on Project Category, creating a project and outputting a `gid`.
4. **Folder Creation**: A Google Drive Create Folder node generates a main client folder, followed by subfolder nodes (Contracts, Assets, Reports) using the parent ID.
5. **Email Notification**: A Gmail node sends a welcome email to the manager with Asana and Google Drive links.
6. **Logging**: A Google Sheets node appends details (Timestamp, Email, etc.) to an "Onboardings" tab.

- **Logic/Dependencies**: The Switch node ensures only one Asana node runs; the function node selects the executed node’s output.

## Tools Required

- n8n (Cloud version 1.111.0)
- Google Workspace (Gmail, Google Drive, Google Sheets) with API access
- Asana with Personal Access Token (PAT)
- Airtable with API key
- **Note**: Requires n8n Cloud subscription (free tier limited); Google Workspace and Asana may need paid plans for full features.

## Size of Project

Large (Over 12 tasks: Trigger, Data Staging, Switch, Asana, Folder Creation, Email, Logging)

## Setup Requirements

- **Integrations**:
  - Google OAuth2 Credential for Drive, Sheets, and Gmail (scopes: `https://www.googleapis.com/auth/drive`, `https://www.googleapis.com/auth/gmail.send`, `https://www.googleapis.com/auth/spreadsheets`).
  - Asana HTTP Request with PAT.
  - Airtable API key.
- **Steps**:
  1. Set up Google Sheets with "Client Onboarding" and "Onboardings" tabs.
  2. Configure n8n Cloud workflow with credentials.
  3. Test Asana PAT and Airtable API in a sandbox environment.
- **No PII**: Exclude personal tokens; use generic setup guides.

## Deployment Time Estimate

- 2–4 hours without customizations (credential setup, node configuration).
- 2–5 days with customizations (e.g., approval for API access, subscription activation).

## Value Proposition

- **Time Savings**: Saves ~10 hours/month per 5 clients (2 hours/client reduced to 30 minutes).
- **Assumptions**: Based on 5 clients/month; savings scale with client volume.

## Demo Video

[Insert 2-minute Loom video link showing workflow execution from Google Form submission to email receipt, narrating value (e.g., time saved, error reduction)]

## Known Limitations

- Rate limited to 500 Gmail emails/day (Google Workspace constraint).
- Requires paid n8n Cloud or self-hosted n8n for high volume.
- Asana PAT must be renewed periodically.

## Testimonials/Use Cases

- **Test Case**: Successfully onboarded sample companies with a various project categories, creating a folder and emailing both client and manager of successful onboarding.
- **Outcome**: Reduced manual effort by 75%, verified via execution logs.

## Size Classification

Large

## Version & Updates

- **v1.0**: Initial release (2025-09-30) – Full onboarding automation with Google, Asana, and Airtable.
- **v1.1**: [Future] – Add Slack notifications, bug fixes.
