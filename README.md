# FinSwarm

**FinSwarm** is an AI-powered, goal-driven financial learning and decision-intelligence platform built for **financial inclusion, transparency, and education**.

It helps users **learn how to think about financial decisions**, not what decisions to make.

> 🚫 No advice.  
> 🚫 No predictions.  
> 🚫 No money handling.  

This repository contains the **locked MVP implementation** for **Microsoft Imagine Cup 2026**.

---

## 🔍 What Problem FinSwarm Solves

Most beginners struggle with:
- Financial jargon
- Hidden risks
- Misconceptions
- Knowing *what to learn next*

FinSwarm solves this by:
- Creating **time-bound learning roadmaps**
- Teaching concepts in **simple, explainable language**
- Proactively surfacing **insights and misconceptions**
- Maintaining **strict safety and policy boundaries**

---

## 🎯 What FinSwarm Does (MVP Scope)

### ✅ It DOES
- Create a **personalized financial learning plan**
- Teach concepts via **chat-based tutoring**
- Track learning progress and phases
- Push **proactive insights** like:
  - Concept connections
  - Common misconceptions
  - “You should understand this now” prompts
- Provide **source-backed explanations** (RBI, SEBI, textbooks)

### ❌ It DOES NOT
- Recommend investments
- Predict markets or returns
- Show charts or price data
- Track or execute financial actions
- Give financial advice

This scope is **intentional and judge-safe**.

---

## 🧠 Core User Flow

1. User sets:
   - Financial learning goal
   - Duration (weeks / months)
2. System generates:
   - Phase-wise learning roadmap
3. User learns via chat
4. System:
   - Tracks progress
   - Pushes proactive insights asynchronously

> Chat is the **interface**, not the product.

---

## 🧩 Multi-Agent Architecture (MVP)

### Agents Used

1. **Orchestrator Agent**
   - Controls end-to-end flow
   - Enforces safety rules
   - Calls all other agents

2. **Goal Planner Agent**
   - Inputs: Goal + Duration
   - Outputs: Phase-wise learning plan

3. **Curriculum Builder Agent**
   - Breaks phases into learning units
   - Defines concept dependencies

4. **Knowledge Agent (RAG)**
   - Azure AI Search + Azure OpenAI
   - Retrieves explanations and sources

5. **Tutor Agent**
   - Converts knowledge into beginner-friendly lessons
   - Uses analogies and step-by-step reasoning

6. **Proactive Insight Agent**
   - Pushes contextual insights based on:
     - Learning stage
     - Chat history
     - Common confusion patterns

7. **Safety & Policy Agent**
   - Blocks advice, predictions, and execution language

---

## 🔄 End-to-End Flow

```text
User Goal
   ↓
Goal Planner Agent
   ↓
Curriculum Builder
   ↓
Learning Roadmap (DB)
   ↓
User Chat
   ↓
Orchestrator
   ├── Knowledge Agent (RAG)
   ├── Tutor Agent
   ├── Tutor Agent
   ├── Safety Agent
   └── Proactive Insight Agent (async)
   ↓
Frontend Insight Cards
```


---

## 🖥️ Frontend (MVP)

**Three-screen design only**

### 1. Goal Setup
- Goal input
- Duration selector

### 2. Learning Dashboard
- **Left:** Learning roadmap
- **Center:** Chat interface
- **Right:** Proactive insights (key differentiator)

Each insight card includes:
- Explanation
- Source link
- “Ask more” CTA

---

## 🗄️ Minimal Database Schema

- **User**
- **Goal**
- **Learning State**
- **Chat History**
- **Insight Log**

Designed for clarity and continuity, not analytics bloat.

---

## ☁️ Microsoft Tech Stack

- **Azure OpenAI** → All agents
- **Azure AI Search** → RAG pipeline
- **Azure Functions** → Orchestration
- **Azure Machine Learning** → Risk logic
- **Azure SQL / Cosmos DB** → State storage
- **Next.js** → Frontend
- **Vercel / Azure Static Web Apps** → Hosting


---

## 📁 Repository Structure

```yaml
frontend/
orchestrator/
agents/
  goal_planner/
  curriculum_builder/
  knowledge/
  tutor/
  proactive/
  safety/
data/
  docs/
  schemas/
```

---

## 📜 Disclaimer

FinSwarm is not a financial advisor.
It provides educational decision support only and does not offer investment advice, recommendations, or execution capabilities.
