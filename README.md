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

