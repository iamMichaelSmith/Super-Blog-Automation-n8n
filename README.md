Super Blog Automation
Automated Research-Driven Blog Generation System
Project Overview

A stakeholder required a reliable system that could automatically generate credible, research-informed blog content and deliver it for review without manual intervention. The content needed to remain contextually relevant, research grounded, and production ready, while minimizing human time spent on drafting, formatting, and sourcing.

Super Blog Automation was designed to solve this by combining AI orchestration, external research tools, and email automation into a single end to end workflow using n8n.

The result is a system that produces structured blog articles based on real research inputs and sends the final output directly to email for stakeholder approval.

What You Need To Run This

To import and execute this workflow, you will need access to the following services and credentials.

Required

n8n (Cloud or self-hosted)

OpenAI API key
Used for planning, keyword extraction, writing sections, editing, and title generation.

Tavily API key
Used for web research and source discovery.

Perplexity API key
Used for research grounding and structured research summaries.

Gmail OAuth credentials (or Gmail node configured in n8n)
Used to email the finished blog to a recipient.

Optional

SerpAPI key
Used for additional search coverage. Helpful but not required if Tavily and Perplexity are sufficient.

Setup and Installation

Import the workflow JSON into n8n:

Workflows → Import from file → select the workflow JSON

Attach credentials inside n8n:

OpenAI credential on all OpenAI nodes

Tavily credential on Tavily nodes

Perplexity credential on Perplexity nodes

Gmail OAuth credential on the Gmail node

Optional SerpAPI credential if enabled

Update recipient email:

Change the Gmail node Send To field to your preferred approval address

Run a test:

Execute workflow

Submit the form with a topic, tone, audience, and notes

Confirm the email arrives with the final blog HTML

Security Notes

This repo intentionally excludes private data.

No API keys are stored

No Gmail OAuth tokens are stored

Workflow exports should remove credentials blocks before publishing to GitHub

Replace any personal emails with placeholders before sharing

Business Problem

Manual blog creation introduced several issues:

Inconsistent research quality

High time cost for drafting and formatting

Difficulty scaling content production

No standardized process for source validation

Delays in stakeholder review cycles

The stakeholder needed a solution that:

Reduced human involvement

Ensured research-backed content

Produced consistent structure and tone

Delivered outputs directly to decision makers

Solution Summary

Super Blog Automation is an event-driven automation workflow that:

Collects structured input from a stakeholder

Performs external research using search tools

Generates SEO aware blog content using LLM orchestration

Assembles the final article in HTML

Emails the result automatically for stakeholder review

The system acts as a content production pipeline, not just a text generator.

Key Technologies Used

n8n for workflow orchestration

OpenAI GPT models for content generation and editing

Tavily for web research

Perplexity for contextual research grounding

SerpAPI for supplemental research coverage

Gmail API for automated delivery

JSON structured outputs for reliability and automation safety

High-Level Architecture

The workflow is modular and follows a clear pipeline pattern:

Input → Research → Planning → Writing → Assembly → Delivery

Each stage is isolated, making the system easier to debug, scale, and extend.

Node by Node Breakdown
1. Form Trigger

Purpose: Captures stakeholder requirements.
What it does: Collects topic, tone, audience, and notes in a structured input format.

2. Research Tools

Purpose: Provide factual grounding and reduce hallucinated content.
Tools: Tavily, Perplexity, optional SerpAPI.
What they do: Search relevant web sources, provide current context, and supply research material that guides the content pipeline.

3. Blog Agent

Purpose: Create a narrative structure for the blog.
What it does: Produces a logical table of contents that flows naturally and starts with a hook designed for the target audience.

4. Keyword Extractor

Purpose: Extract SEO relevant keywords based on research output.
What it does: Produces primary and secondary keyword lists with formatting constraints to support search intent and on page SEO consistency.

5. Project Planner

Purpose: Convert the blog outline into machine readable JSON.
What it does: Transforms the outline into structured sections with clear titles and descriptions, enabling repeatable automation.

6. Split Out

Purpose: Process each blog section independently.
What it does: Creates one item per section to support scalable section writing.

7. Research Team

Purpose: Write the final content for each section.
What it does: Uses research tools for grounding, outputs HTML, follows tone and audience rules, and generates clean structured section content.

8. Merge and Aggregate

Purpose: Recombine all written sections.
What it does: Merges parallel section outputs, aggregates section content, and preserves ordering for coherent assembly.

9. Editor

Purpose: Assemble and polish the final blog.
What it does: Adds an intro hook, improves flow, injects SEO keywords, enforces output formatting and constraints, adds backlinks, and builds the final Sources section.

10. Title Generator

Purpose: Create a compelling title aligned with the stakeholder voice.
What it does: Generates a question style title matching tone and audience.

11. Email Delivery

Purpose: Deliver the final output to stakeholders.
What it does: Emails the completed HTML blog using the generated title as the subject, enabling immediate review without logging into n8n.

Why This Matters for Employers

This project demonstrates production-relevant automation and workflow engineering skills:

Workflow orchestration and event-driven automation

LLM orchestration with structured outputs and constraints

API integration across multiple services

Modular pipeline design and separation of concerns

Scalable processing using split and merge patterns

Output validation and production-minded delivery workflows

This is a repeatable automation system that aligns technical execution with business goals.

Final Summary

Super Blog Automation was built to address a real business need by combining research tooling, AI generation, and workflow automation. It demonstrates a structured approach to building scalable pipelines with clear inputs, controlled outputs, and stakeholder delivery built in.
