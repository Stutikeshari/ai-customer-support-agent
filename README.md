AI Customer Support Agent

An AI-powered customer support agent built with Next.js, TypeScript, OpenAI, and function calling to process e-commerce refund requests according to a strict refund policy.

The application simulates a real customer-support workflow where an AI agent retrieves customer and order information, checks refund eligibility against predefined business rules, and provides an approval or denial response.

It also includes an admin dashboard for observing structured agent activity, tool calls, policy validation, errors, and final decisions.

Project Overview

The goal of this project is to build a vertical slice of an AI Customer Support Agent capable of handling e-commerce refund requests.

The agent does not make refund decisions based only on the LLM's response. Instead, the LLM dynamically calls backend tools, and the final refund decision is determined by deterministic refund-policy validation.

Main workflow
Customer
   ↓
Customer Chat UI
   ↓
Next.js API
   ↓
AI Agent
   ↓
Tool Calling
   ↓
Customer / Order / Policy Data
   ↓
Refund Eligibility Validation
   ↓
 ┌───────────────┐
 │               │
APPROVE         DENY
 │               │
 ↓               ↓
Refund         Reason for
Response       Rejection
 │               │
 └───────┬───────┘
         ↓
Customer Response

         +
         ↓

Admin Agent Logs
✨ Features
Customer Chat
Clean responsive customer-support interface
Customers can submit refund requests
AI agent understands the customer's request
Agent dynamically calls backend tools
Clear approval or denial response
Displays the reason when a refund is denied
AI Agent
Built using OpenAI function calling
Dynamically selects the appropriate tools
Retrieves customer information
Retrieves order information
Retrieves refund-policy rules
Validates refund eligibility
Produces a final customer-friendly response
Refund Policy Validation

The refund decision is handled by deterministic backend rules.

The AI agent cannot override the refund policy.

The system validates conditions such as:

Customer exists
Order exists
Order belongs to the customer
Order has been delivered
Refund request is within the allowed refund window
Product is refundable
Order has not already been refunded
Order does not already have a pending refund
Mock CRM

The application contains:

15 fictional customer profiles
Customer order history
Mock order information
Different refund scenarios

No real customer information is used.

Admin Dashboard

The admin dashboard provides structured observability into the agent workflow.

It can display:

Agent requests
Tool calls
Tool results
Customer/order identifiers
Policy validation
Success/failure status
Errors
Retry attempts
Final refund decisions

The logs are designed for observability and debugging and do not expose private chain-of-thought reasoning.

🛠️ Tech Stack
Technology	Purpose
Next.js	Frontend and API routes
React	UI components
TypeScript	Type safety
Tailwind CSS	Styling and responsive UI
OpenAI	LLM-powered agent
OpenAI Function Calling	Dynamic tool orchestration
Node.js	Backend runtime
Mock TypeScript Data	CRM and order database
Git / GitHub	Version control
