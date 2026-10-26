# paytm-autonomous-ai-teammate
AI teammate for merchant customer service: resolves issues end-to-end, takes actions across systems and escalates to humans only when needed. Paytm Build for India AI Hackathon, Track 3.

An AI teammate that handles merchant support end-to-end instead of only answering questions.

## Problem
Paytm Build for India AI Hackathon, Track 3: Autonomous AI Teammates. How can an AI independently resolve a customer-service workflow, take actions across systems, and escalate to humans only when needed?

## What it does
- Understands the merchant's issue and decides what to do
- Takes actions through tools: transaction lookup, settlement status, refunds
- Escalates to a human with a full summary when needed
- Shows resolved vs escalated metrics and an action audit log

## Guardrails
- Refunds above Rs 5,000 are blocked in code and must go to a human
- Only successful, not-yet-refunded transactions can be refunded
- Every action is logged
- Failures escalate instead of crashing

## Architecture
Merchant message -> Gemini LLM (decides) -> Tools (mock Paytm APIs) -> Reply, or Escalation to human queue

## Tech stack
Python, Google Gemini API (function calling), Streamlit

## Run locally
pip install -r requirements.txt
export GEMINI_API_KEY=your_key
streamlit run app.py

## Note
All Paytm systems are mocked for the demo. The tool functions can be swapped for real APIs.

## Demo
Link: 
