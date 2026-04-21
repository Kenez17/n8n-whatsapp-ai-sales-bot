# 🤖 AI-Powered WhatsApp Sales Assistant (n8n Workflow)

This repository contains the exported **n8n workflows** for a fully automated, AI-driven WhatsApp sales assistant. The system integrates the Meta/WhatsApp Cloud API, Google Vertex AI (for intent classification and conversational responses), and Airtable (as a dynamic product database).

## 🚀 Features & Architecture

This proof-of-concept demonstrates advanced n8n capabilities, moving beyond simple triggers into complex AI routing and dynamic database queries.

- **Meta API Verification:** Secure webhook endpoint to handle Meta's `hub.challenge` verification and filter out invalid requests.
- **Intent Classification:** Uses Google Vertex AI to deterministically classify if a user is interested in buying a product or just chatting.
- **Dynamic Inventory Search:** Automatically queries an Airtable database based on the specific product keyword extracted by the AI.
- **Conversational AI Sales Agent:** Crafts human-like, persuasive, and short responses using Structured JSON Output, ensuring the bot always attempts to close the sale naturally.
- **Fail-safes & Memory:** Implements simple window memory for conversational context and structured output parsers to avoid AI hallucinations.

## 📂 Files Included

1. `Meta-Whatsapp-CLEAN.json`
   * Handles the initial webhook validation from Meta.
   * Extracts the sender's phone number and message body.
   * Forwards valid payloads to the main processing workflow via an internal HTTP Request.
   
2. `Ventas-Automaticas-Basico-CLEAN.json`
   * The core logic engine.
   * Contains the AI Agents (Vertex AI), Airtable integration, data aggregation, and the outgoing WhatsApp API node.

## 🛠️ How to Use (For Clients & Reviewers)

To test or implement this workflow in your own n8n instance:
1. Download the JSON files and import them into your n8n workspace.
2. Replace the placeholder credentials (`YOUR_WEBHOOK_ID`, `YOUR_BASE_ID`, `YOUR_CREDENTIAL_ID`, etc.) with your actual API keys and internal IDs.
3. Connect your WhatsApp Cloud API, Airtable, and Google Cloud (Vertex AI) accounts using n8n's credential manager.

*Note: All sensitive data, phone numbers, Ngrok URLs, and API keys have been completely removed from these files for security purposes.*

---
**Looking for a custom n8n integration?** I specialize in Business Process Automation, APIs, and AI workflows. Feel free to reach out on Upwork!
