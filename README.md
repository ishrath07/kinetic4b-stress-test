# kinetic4b-stress-test
Stress-testing Kinetic-4B on unseen Composio toolkits and multi-step tool-calling chains, with comparison against the Qwen3-4B base model.
# Kinetic-4B Stress Test: Unseen Toolkits + Multi-Step Chains

A focused evaluation of **Kinetic-4B** (`consciousengines/Kinetic-FC-LoRA`) on unseen Composio toolkits and multi-step tool-calling tasks, compared against the **Qwen3-4B-Instruct-2507** base model.

## Overview

This project stress-tests Kinetic-4B beyond the single-tool-call scenarios and toolkit coverage described in its training/evaluation context.

The evaluation targets two directions identified in Conscious Engines' "What's Next":

- Expanding training data beyond the top 20 toolkits
- Moving from single-tool-call evaluation to multi-step agent traces

The goal is to determine how well Kinetic-4B generalizes to **unseen tools** and whether it can reliably execute **multi-step tool-calling workflows**.

---

## What Is Evaluated?

The evaluation contains **16 tasks** in total:

### 1. Single-Tool-Call Tasks

10 tasks using Composio toolkits that were not among the toolkits listed in the Kinetic-4B blog post.

The listed trained toolkits include:

- Linear
- PagerDuty
- Airtable
- Calendly
- Intercom
- Twilio
- Figma
- Dropbox
- Zendesk
- Asana

The evaluation instead tests tool-calling generalization on unseen toolkits.

### 2. Multi-Step Tool-Calling Chains

6 multi-step tasks containing **2–3 tool calls each**.

These include the Stripe → Linear → Slack workflow described in Conscious Engines' retrieval blog post.

The evaluation checks whether Kinetic-4B can:

- Select the correct first tool
- Produce the correct sequence of tools
- Provide the required arguments
- Complete the entire chain in one generation
- Complete the chain step-by-step when intermediate tool results are provided

---

## Models Compared

### Kinetic-4B

```text
consciousengines/Kinetic-FC-LoRA
