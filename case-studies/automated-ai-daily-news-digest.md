# Automated AI Daily News Digest

**Type:** Independent project
**Tools:** Python, GitHub Actions, Google Gemini API, PostgreSQL, Resend
**Diagram:** [architecture](../diagrams/daily-news-digest-architecture.md)

## 1. Context

I wanted one daily email with the most relevant AI news from a set of selected sources, with short summaries I could trust.

## 2. Business Problem

A daily digest only works if it arrives every day, arrives once, and summarizes what the sources actually say. One missed day showed that the first version did not guarantee the first two.

## 3. My Role and Ownership

I built and operate the pipeline, and I diagnosed and fixed the missed-delivery incident. I used AI assistance to write code, and tests to verify it.

## 4. Solution Design

- **Scheduling:** GitHub Actions runs the pipeline on a schedule.
- **Ranking:** stories from the selected sources are collected and ranked.
- **Summaries:** the Google Gemini API writes summaries grounded in the source articles.
- **Storage:** PostgreSQL supports the pipeline's data handling.
- **Delivery:** Resend sends the email.

## 5. Workflow / Architecture Overview

Scheduled run → collect and rank stories → write source-grounded summaries → check whether today's digest was already sent → send. A catch-up schedule re-runs a missed day. See the [diagram](../diagrams/daily-news-digest-architecture.md).

## 6. Governance, Privacy, and Controls

Summaries are written from the source articles, not from the model's general knowledge. No keys, source lists, recipient data, or logs are published here.

## 7. Testing and Release Readiness

After the missed delivery, I added three changes:

- **Idempotent sends:** a re-run cannot send the same day's digest twice.
- **Catch-up scheduling:** a missed run is picked up later.
- **Automated tests** for this delivery behavior.

## 8. Outcome

The digest runs on a schedule, and delivery now has a guard against duplicates, a recovery path for missed runs, and tests that cover both.

## 9. What I Would Improve or Explore Next

Add an alert when a scheduled run fails, so a missed day is noticed before the catch-up run.

## 10. Public-Safe Disclosure

This case study is intentionally anonymized. It describes the workflow design, delivery approach, and governance considerations without disclosing confidential business information, internal URLs, personal data, source exports, or proprietary configurations.
