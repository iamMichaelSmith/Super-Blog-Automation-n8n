# Super Blog Automation  
**Automated Research-Driven Blog Generation System**

---

## Project Overview

A stakeholder required a reliable system that could automatically generate **credible, research-informed blog content** and deliver it for review **without manual intervention**. The content needed to remain **contextually relevant**, **research-grounded**, and **production-ready**, while minimizing human time spent on drafting, formatting, and sourcing.

**Super Blog Automation** was designed to solve this by combining **AI orchestration**, **external research tools**, and **email automation** into a single end-to-end workflow using **n8n**.

The result is a system that produces **structured blog articles based on real research inputs** and sends the final output **directly to email for stakeholder approval**.

![n8n Super Blog Automation](n8n%20Super%20Blog%20Automation%20-%20n8n.png)
---

## What You Need to Run This

To import and execute this workflow, you will need access to the following services and credentials.

### Required Services

- **n8n** (Cloud or self-hosted)
- **OpenAI API Key**  
  Used for planning, keyword extraction, section writing, editing, and title generation.
- **Tavily API Key**  
  Used for web research and source discovery.
- **Perplexity API Key**  
  Used for contextual research grounding and structured research summaries.
- **Gmail OAuth Credentials**  
  Used to email the completed blog to stakeholders.

### Optional Services

- **SerpAPI Key**  
  Provides additional search coverage. Helpful but not required if Tavily and Perplexity are sufficient.

---

## Setup and Installation

1. **Import the workflow**
   - Open n8n
   - Go to **Workflows → Import from file**
   - Select the provided workflow JSON

2. **Attach credentials**
   - OpenAI credentials on all OpenAI nodes
   - Tavily credentials on Tavily nodes
   - Perplexity credentials on Perplexity nodes
   - Gmail OAuth credentials on the Gmail node
   - Optional SerpAPI credentials if enabled

3. **Configure email delivery**
   - Update the Gmail node with your preferred recipient address

4. **Run a test**
   - Execute the workflow
   - Submit the form with a topic, tone, audience, and notes
   - Confirm the final blog arrives via email

---

## Security Notes

This repository intentionally excludes all sensitive information.

- No API keys are stored
- No Gmail OAuth tokens are included
- All credentials must be added manually after import
- Email addresses are placeholders only

This follows best practices for **secure automation workflows** and **public repositories**.

---

## Business Problem

Manual blog creation introduced several challenges:

- Inconsistent research quality
- High time cost for drafting and formatting
- Difficulty scaling content production
- No standardized process for source validation
- Delays in stakeholder review cycles

The stakeholder needed a solution that:

- Reduced human involvement
- Ensured research-backed content
- Produced consistent structure and tone
- Delivered outputs directly to decision makers

---

## Solution Summary

**Super Blog Automation** is an **event-driven automation workflow** that:

1. Collects structured input from a stakeholder
2. Performs external research using search APIs
3. Generates SEO-aware blog content using LLM orchestration
4. Assembles the final article in HTML
5. Emails the result automatically for review

The system functions as a **content production pipeline**, not just a text generator.

---

## Key Technologies Used

- **n8n** – Workflow orchestration
- **OpenAI GPT Models** – Content generation and editing
- **Tavily** – Web research
- **Perplexity** – Contextual research grounding
- **SerpAPI** – Supplemental search coverage
- **Gmail API** – Automated delivery
- **JSON Structured Outputs** – Reliability and automation safety

---

## High-Level Architecture

The workflow follows a modular pipeline:

**Input → Research → Planning → Writing → Assembly → Delivery**

Each stage is isolated to improve **debuggability**, **scalability**, and **maintainability**.

---

## Node-by-Node Breakdown

### 1. Form Trigger (Input Layer)
Captures structured stakeholder requirements including topic, tone, audience, and notes.

---

### 2. Research Tools (Data Enrichment Layer)
Uses Tavily, Perplexity, and optional SerpAPI to provide real-world context and reduce hallucinated content.

---

### 3. Blog Agent (Planning Layer)
Generates a logical table of contents with narrative flow and a strong opening hook.

---

### 4. Keyword Extractor (SEO Layer)
Produces primary and secondary keyword lists derived strictly from research outputs.

---

### 5. Project Planner (Data Structuring Layer)
Converts the outline into machine-readable JSON sections for reliable automation.

---

### 6. Split Out (Parallelization Layer)
Processes each blog section independently to enable scalable writing.

---

### 7. Research Team (Content Generation Layer)
Writes clean HTML content per section using research grounding and formatting rules.

---

### 8. Merge and Aggregate (Assembly Layer)
Recombines all written sections while preserving order and structure.

---

### 9. Editor (Final Composition Layer)
Assembles the final blog, improves readability, injects SEO keywords, adds backlinks, and builds the Sources section.

---

### 10. Title Generator (Presentation Layer)
Creates an engaging, tone-matched, question-style blog title.

---

### 11. Email Delivery (Distribution Layer)
Emails the completed blog to stakeholders for immediate review.

---

## Why This Matters for Employers

This project demonstrates production-level automation skills including:

- Workflow orchestration
- LLM orchestration with structured outputs
- External API integration
- Parallel processing patterns
- Modular system design
- Business-driven automation thinking
- Secure credential handling

This is a **repeatable, real-world automation system**, not a demo.

---

## Final Summary

**Super Blog Automation** addresses a real business challenge using modern automation principles. It demonstrates how AI, research APIs, and workflow orchestration can be combined into a **scalable, production-ready content pipeline**.

This project reflects my approach to automation:  
**clear inputs, controlled outputs, modular design, and business-first thinking**.
