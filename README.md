# Sales Rep Reallocation & Scenario Versioning

**Internship Documentation Only**

## Overview

During my **Summer 2025 internship at LINEN.Cloud**, an AI-driven sales operations platform, I worked on a cross-functional project focused on solving a common but high-impact challenge in sales organizations: **how to reallocate accounts when sales coverage changes** due to rep turnover, territory shifts, or capacity imbalances.

LINEN.Cloud is a no-code platform that helps organizations manage sales planning, team hierarchies, territories, performance goals, and account assignments. The platform integrates with systems such as Salesforce to help ensure accounts are assigned correctly and sales operations data stays aligned.

My work focused on extending this foundation with a **sales rep reassignment and scenario planning experience** that combined data analysis, AI-powered assistance, interactive dashboards, and version-controlled experimentation. The goal was to help sales operations users make reassignment decisions **more efficiently, understand the reasoning behind different options, and safely experiment before finalizing changes**.

> **Confidentiality Note:** This repository contains **documentation only**. The original source code, proprietary datasets, internal business logic, and company information are not included here.

---

## The Problem

When a sales rep leaves or account coverage changes, reallocating their accounts is rarely as simple as assigning everything to another person. Sales operations teams need to balance multiple factors at once, including:

- A rep's industry knowledge or specialization
- Reasonable account load and capacity
- Geographic or territory alignment
- Historical performance
- Client and rep fit
- Existing account coverage
- Potential downstream effects of reassignment decisions

These decisions can become especially difficult when teams are working with large datasets and need to compare multiple possible outcomes.

Without the right tooling, reassignment planning can become manual, difficult to validate, and hard to reverse. Users needed a way to **test "what-if" scenarios, use analytical and AI-assisted insights, manually adjust recommendations, and preserve the history of their decisions**.

---

## Users & Use Cases

**Primary users:** Sales Operations and Revenue Operations managers

### Key Needs

- Quickly test "what-if" reassignment scenarios
- Identify potential rep-account matches using data-driven factors
- Use AI assistance to summarize or interpret information
- Combine automated recommendations with human judgment
- Manually adjust assignments when business context requires it
- Track how decisions change over time
- Compare scenarios before committing to one
- Preserve the reasoning and history behind changes
- Experiment without accidentally overwriting the original dataset

---

## My Role & Ownership

I contributed as a **Data Analyst Intern with a strong product and AI focus**, working across data analysis, application functionality, user experience, and stakeholder communication.

My work centered on the **scenario management, versioning, analytics, and AI-assisted experience** of the tool.

### Key Areas of Ownership and Contribution

- Designed **versioned scenario workflows** so each reassignment state could be saved, revisited, compared, and reverted
- Defined data structures that paired each scenario with **metadata, timestamps, assumptions, and edit history**
- Supported **safe experimentation** by separating scenario changes from the original dataset
- Helped design and implement the **Streamlit web interface** used to interact with the reassignment and analytics functionality
- Implemented an **AI Chat Assistant** within the application to provide users with AI-powered assistance while working with sales operations data
- Integrated **LangChain and OpenAI's GPT-4o** into the application to support AI-assisted interactions and summaries
- Connected AI functionality to the broader dashboard experience rather than treating it as a standalone chatbot
- Helped surface AI-generated information alongside **data-driven dashboards and reassignment workflows**
- Worked with structured sales data to support analytical comparisons between reps, accounts, workload, territory, and performance
- Translated technical and analytical concepts into workflows that made sense for **sales operations users and non-technical stakeholders**
- Documented application workflows, scenario history, and version lineage so users could understand **what changed and why**

---

## Solution Summary

The resulting application brought together **data analysis, interactive dashboards, AI assistance, manual reassignment, and scenario versioning** into one workflow.

Users could:

1. Analyze existing sales rep and account information
2. Review rep performance, workload, territory, and account characteristics
3. Generate or evaluate potential reassignment options
4. Use an **AI-powered assistant** to interact with information and generate summaries
5. Manually adjust assignments based on business knowledge
6. Save the resulting state as a distinct scenario
7. Track changes through metadata and edit history
8. Compare different scenarios before making a final decision
9. Revert to earlier versions when necessary

This allowed AI and analytics to **support human decision-making rather than replace it**. Users could consider automated insights while still applying their own knowledge of territories, customers, capacity, and business priorities.

---

## AI-Powered Functionality

A major part of the project was incorporating **AI functionality directly into the web application**.

### AI Chat Assistant

The application included an **AI Chat Assistant** designed to make sales operations data easier to interact with and understand.

I worked with **LangChain and OpenAI's GPT-4o** to incorporate AI-powered interactions into the Streamlit application.

The assistant was designed to help users:

- Ask questions about the available sales information
- Generate AI-assisted summaries
- Interact with analytical results using natural language
- Understand information without having to manually inspect every data field
- Use AI assistance alongside the existing dashboard and reassignment workflows

The AI functionality was intentionally integrated into the larger application experience. Instead of requiring users to leave the dashboard and use a separate AI tool, the assistant was available within the same environment where they were already analyzing accounts and making reassignment decisions.

### AI + Data + User Workflow

The project also explored how AI could work alongside traditional analytical tools.

The overall experience combined:

**Structured Data → Analytics → AI Assistance → Human Review → Scenario Creation → Version Comparison**

This approach allowed AI-generated insights and summaries to become another input into the decision-making process while keeping the user in control of the final reassignment.

---

## How It Works

At a conceptual level, the workflow followed this pattern:

### 1. Load the Initial Dataset

The application begins with an account-to-rep dataset containing information used to evaluate account coverage and reassignment options.

### 2. Analyze Sales Coverage

The application surfaces relevant factors such as:

- Industry specialization
- Geographic alignment
- Rep workload
- Historical performance
- Account and rep fit

These factors could be used to understand existing coverage and evaluate potential reassignment options.

### 3. Interact with AI-Assisted Functionality

Users could access the **AI Chat Assistant** from within the application to ask questions, interact with information, and generate AI-assisted summaries.

The AI functionality was implemented using **LangChain and OpenAI's GPT-4o** and integrated into the Streamlit interface.

### 4. Apply Reassignment Changes

Users could evaluate suggested options and make their own adjustments based on business context.

This supported a combination of:

- Data-driven analysis
- AI-assisted interpretation
- Automated or suggested reassignment logic
- Manual user decisions

### 5. Save the State as a Scenario

Each reassignment state could be saved as its own version rather than overwriting the original data.

A saved scenario included:

- Current assignment data
- Scenario metadata
- Assumptions or notes
- Timestamps
- Edit history

### 6. Compare and Review Scenarios

Users could review different versions to understand:

- What changed
- Which accounts moved
- How assignments evolved
- Why a particular scenario was created
- Which version they wanted to continue working from

### 7. Revert When Necessary

Because scenarios were preserved independently, users could return to an earlier state rather than losing previous work.

---

## Scenario Versioning & Data Lineage

One of the main design challenges was making experimentation **safe and traceable**.

Rather than overwriting the existing dataset every time a user made a change, the application treated each state as a separate scenario.

Conceptually:

```text
Original Dataset
      │
      ├── Scenario 1
      │      ├── Changes
      │      └── Metadata
      │
      ├── Scenario 2
      │      ├── Changes
      │      └── Metadata
      │
      └── Scenario 3
             ├── Changes
             └── Metadata
