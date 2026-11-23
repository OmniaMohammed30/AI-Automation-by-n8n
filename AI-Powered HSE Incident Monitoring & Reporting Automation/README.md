# AI-Powered HSE Incident Monitoring & Reporting Automation

An automated HSE incident monitoring and reporting system built using **n8n, Microsoft Outlook, and AI Agents**.

The system monitors incoming emails, identifies incident reports, extracts structured incident information, analyzes patterns across multiple incidents, and automatically generates and delivers comprehensive HTML reports.

## Key Features

### 1. Automated Email Monitoring
- Retrieves emails from Microsoft Outlook Inbox and Junk folders.
- Supports scheduled execution and manual testing.
- Processes emails within the configured reporting period.
- Accepts emails regardless of sender.

### 2. Data Processing & Incident Detection
- Cleans HTML email content and normalizes text.
- Validates email data and removes duplicate messages.
- Filters emails based on the reporting period.
- Identifies whether incident reports are available.

### 3. AI-Powered Incident Analysis

Uses an AI Agent to extract structured information from incident reports, including:
- Incident date and type.
- Severity level.
- Incident location.
- Injuries and people involved.
- Root causes.
- Corrective actions.
- Incident status.

Missing information is marked as `Not specified` to avoid generating unsupported details.

### 4. Cross-Incident Analysis
Analyzes multiple incident reports to identify:
- Incident distribution by severity, type, and location.
- Repeated causes, locations, and equipment.
- Emerging safety risks and patterns.
- High-severity and recurring-risk alerts.
- 3–5 actionable safety recommendations.

### 5. Automated Reporting & Notifications
- Generates structured HTML incident analysis reports.
- Sends reports through Gmail.
- Sends a separate notification when no incidents are detected.

## Workflow Architecture

1. Scheduled or manual trigger starts the workflow.
2. Microsoft Outlook retrieves emails from Inbox and Junk.
3. JavaScript processes, cleans, validates, and filters the collected emails.
4. An IF node determines whether incident reports are available.
5. If incidents are found, the AI Agent extracts information and performs cross-incident analysis.
6. The results are formatted into an HTML report.
7. Gmail automatically delivers the report.
8. If no incidents are found, a separate notification is sent.

## Technologies & Tools

- **n8n:** Workflow automation and orchestration.
- **Microsoft Outlook:** Email retrieval and monitoring.
- **AI Agent / LLM:** Incident information extraction and analysis.
- **JavaScript:** Data cleaning, validation, and processing.
- **Structured Output Parser:** Consistent AI-generated report structure.
- **Gmail:** Automated report delivery.

## Testing Scenarios

The workflow is designed to handle different scenarios, including:
- Multiple incident reports.
- No incidents found.
- Missing incident information.
- Emails from different senders.
- Emails outside the reporting period.
- Emails containing attachments.
- Long email bodies.

## Setup Instructions

1. Import the workflow JSON file into n8n.
2. Configure Microsoft Outlook credentials.
3. Configure the AI model and required credentials.
4. Configure Gmail credentials.
5. Set the reporting period and schedule.
6. Test the workflow using the manual trigger.

**Note:** Credentials and sensitive configuration details are not included in this repository. Users must configure their own credentials before running the workflow.

## Project Goal

To automate HSE incident monitoring, reduce manual email review, identify recurring safety risks, and provide structured insights that support better safety analysis and decision-making.
