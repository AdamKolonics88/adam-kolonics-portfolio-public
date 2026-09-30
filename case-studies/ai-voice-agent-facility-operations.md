# AI Voice Agent for Facility Operations

**Status:** In development
**Tools:** Vapi, Twilio, Google Apps Script, read-only ServiceChannel integration
**Diagram:** [architecture](../diagrams/ai-voice-agent-architecture.md)

## 1. Context

Open facility work orders often wait on four answers from a vendor: when they will arrive, how they will get access, whether parts are available, and whether the job is closed out. Getting those answers means repetitive phone calls.

## 2. Business Problem

Phone follow-up takes staff time, and answers end up as free-text notes. The goal is to collect the same four answers in the same structure every time, and to put them in front of a person who decides what happens next.

## 3. My Role and Ownership

I am designing the workflow: which work orders are read, what the agent asks, what information is captured, how the result is structured for review, and where the system stops and a person takes over.

## 4. Solution Design

- **Work-order intake:** open ServiceChannel work orders are read through a read-only integration.
- **Call:** a voice agent built on Vapi, with Twilio telephony, calls the facility vendor and asks for ETA, access, parts, and closeout information.
- **Orchestration:** Google Apps Script runs the steps.
- **Output:** each call produces a structured call outcome for human review.

Two boundaries shape the design. The integration only reads work orders; nothing is written back. And the agent does not decide anything; it collects information for a person to act on.

## 5. Workflow / Architecture Overview

Read open work orders → place the call → capture the four answers → structure the outcome → human review. See the [diagram](../diagrams/ai-voice-agent-architecture.md).

## 6. Governance, Privacy, and Controls

- Read-only access to work orders.
- Design principle: an unclear or incomplete answer goes to a person as-is rather than being filled in by the model.
- Design principle: capture only what the four questions need.

## 7. Testing and Release Readiness

The project is in development. This case study describes the design and makes no claim about test results or live use.

## 8. Outcome

In development. What exists today is the workflow design: a defined call flow, a structured output for review, and the read-only and human-review boundaries.

## 9. What I Would Improve or Explore Next

Define acceptance criteria for the captured answers, for example a check that each of the four fields is present or explicitly marked unknown, before any wider use.

## 10. Public-Safe Disclosure

This case study is intentionally anonymized. It describes the workflow design, delivery approach, and governance considerations without disclosing confidential business information, internal URLs, personal data, source exports, or proprietary configurations.
