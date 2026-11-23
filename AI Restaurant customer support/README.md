# Restaurant AI Agent & Stock Management System

An AI-powered restaurant automation system built using **n8n**, integrating customer support, order management, and inventory tracking through Telegram bots and AI Agents.

The project consists of two interconnected workflows that automate the restaurant's customer interactions and internal stock management processes.

## Project Overview

### 1. Restaurant AI Agent

A Telegram-based AI assistant that receives customer messages and automatically handles different types of interactions.

**Key Features:**

- **Message Classification:** Uses an LLM Chain to classify incoming messages into three categories:
  - General Messages
  - Order Requests
  - Restaurant-Related Questions

- **Dynamic AI Prompts:** Each message category is handled using a dedicated prompt to guide the AI Agent's responses and actions.

- **RAG-Based Knowledge Base:** Integrates Supabase Vector Store as a knowledge retrieval tool, allowing the AI Agent to retrieve relevant information from uploaded restaurant documents.

- **Restaurant Information Retrieval:** Uses the knowledge base to answer questions about the restaurant, including its menu, prices, and other restaurant-related information.

- **Automated Order Management:** When a customer wants to place an order, the AI Agent collects the required customer information and order details.

- **Google Sheets Integration:** Stores customer orders and their information in Google Sheets.

- **Order Confirmation:** Sends a confirmation message to the customer after successfully recording the order.

### 2. Stock Management Automation

An interconnected Telegram-based workflow designed to manage restaurant inventory and track order statuses.

**Key Features:**

- Receives order IDs and status updates from restaurant staff through Telegram.
- Identifies the corresponding order in Google Sheets.
- Automatically updates order statuses from `Pending` to either `Done` or `Cancel`.
- When an order is marked as `Done`, the system automatically deducts the corresponding item quantities from the restaurant's inventory.
- Maintains inventory records to support stock tracking and management.

## System Integration

The two workflows work together to create an automated restaurant management system:

1. Customers interact with the Restaurant AI Agent through Telegram.
2. The AI Agent processes requests, retrieves restaurant information, and records new orders.
3. Orders are initially stored with a `Pending` status.
4. Restaurant staff send the order ID and its final status through the Stock Management Telegram bot.
5. The system updates the order status.
6. If the order is completed, the corresponding quantities are deducted from the inventory automatically.

## Technologies & Tools

- **n8n:** Workflow automation and orchestration.
- **Telegram Bot API:** Customer and staff interaction.
- **LLMs:** Message classification and AI-powered responses.
- **AI Agents:** Intelligent decision-making and tool execution.
- **RAG (Retrieval-Augmented Generation):** Context-aware information retrieval.
- **Supabase Vector Store:** Restaurant knowledge base and vector search.
- **Google Sheets:** Order management and inventory tracking.

## Project Architecture

The solution combines AI-powered customer interaction with rule-based operational automation, reducing manual work in order processing and inventory management.

## Setup Instructions

1. Import the workflow JSON files into n8n.
2. Configure your Telegram bot credentials.
3. Connect your LLM provider.
4. Configure Supabase and upload your restaurant knowledge-base documents.
5. Connect the required Google Sheets documents.
6. Test both workflows and their integration.

**Note:** API credentials and sensitive configuration details are not included in this repository. Users must configure their own credentials before running the workflows.

## Project Goal

To build an integrated restaurant automation solution that improves customer experience, streamlines order processing, and automates inventory updates while reducing manual operational tasks.
