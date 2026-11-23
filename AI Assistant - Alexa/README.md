# Alexa – AI Project Manager

Alexa is an AI-powered project management assistant built using **n8n and Google Gemini**, designed to manage emails, calendar events, and structured database operations through natural language conversations.

It integrates Gmail, Google Calendar, Airtable, and Google Search to retrieve information and execute tasks through an AI Agent with conversational memory and intelligent tool calling.

## Features

### 1. AI-Powered Assistant
- Understands natural language requests.
- Uses Google Gemini to process user instructions.
- Selects the appropriate tools based on the user's intent.
- Maintains conversational context using Simple Memory.

### 2. Gmail Integration
- Search and retrieve emails.
- Find emails by sender, subject, or keywords.
- Send emails when explicitly requested.
- Draft emails without sending them.

### 3. Google Calendar Integration
- Retrieve existing calendar events.
- Check upcoming meetings and availability.
- Create new calendar events.
- Check for scheduling conflicts before creating events.

### 4. Airtable Database Management

Manages an educational database containing four main entities:

- **Courses:** Course details, topics, difficulty levels, tracks, and prerequisites.
- **Instructors:** Names, contact information, expertise, and assigned courses.
- **Resources:** Learning materials, links, versions, and associated courses.
- **Course Prerequisites:** Relationships between courses and their required prerequisites.

**Database Operations:**
- Search and retrieve records.
- Create new records.
- Update existing records.
- Delete records.
- Manage relationships between courses, instructors, and resources.

### 5. Web Search
- Integrates Google Search through SerpApi.
- Retrieves external information when required.
- Distinguishes external search results from information stored in Airtable.

### 6. Reliability & Safety
- Uses actual Airtable Record IDs for update and delete operations.
- Avoids duplicate records.
- Requests clarification when multiple records match.
- Uses the correct tool for each operation.
- Never invents information or confirms actions without successful execution.
- Uses the Africa/Cairo timezone for date and time operations.

## Workflow Architecture

1. The user sends a message through the n8n Chat Interface.
2. The AI Agent (Alexa) processes the request using Google Gemini.
3. Simple Memory provides relevant conversational context.
4. Alexa identifies the appropriate service and selects the required tool.
5. The connected service executes the requested operation.
6. Alexa processes the tool result and responds to the user.

## Technologies & Integrations

- **n8n:** Workflow automation and orchestration.
- **Google Gemini:** Large Language Model (LLM).
- **AI Agent:** Intelligent decision-making and tool calling.
- **Simple Memory:** Conversational context management.
- **Gmail:** Email management.
- **Google Calendar:** Event and schedule management.
- **Airtable:** Database and relationship management.
- **SerpApi:** Google Search integration.

## Setup Instructions

1. Import the workflow JSON file into n8n.
2. Configure Google Gemini credentials.
3. Connect Gmail and Google Calendar accounts.
4. Configure Airtable credentials and database tables.
5. Set up the SerpApi API key.
6. Test the assistant through the n8n Chat Interface.

**Note:** Credentials and sensitive configuration details are not included in this repository. Users must configure their own credentials before running the workflow.

## Project Goal

To build an intelligent AI project manager that centralizes email communication, calendar scheduling, database management, and information retrieval through a single conversational interface.
