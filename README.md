Here is the complete `README.md` file for your project, updated with the correct image references you created.

-----

# Personal Productivity Concierge Agent 🤖📅

> **Automate your daily micro-decisions with a context-aware AI Agent.**

This project implements a **Personal Productivity Concierge** using the **Google Agent Development Kit (ADK)** and **Gemini 2.0 Flash Exp**. Unlike standard chatbots, this agent utilizes a tool-use architecture and a persistent "Memory Bank" to actively manage tasks, plan meals, and retrieve information, effectively acting as a proactive executive assistant.

-----

## 📖 Table of Contents

  - [Problem Statement](https://www.google.com/search?q=%23-problem-statement)
  - [Architecture](https://www.google.com/search?q=%23-architecture)
  - [Features](https://www.google.com/search?q=%23-features)
  - [Tech Stack](https://www.google.com/search?q=%23-tech-stack)
  - [Setup & Installation](https://www.google.com/search?q=%23-setup--installation)
  - [Usage Examples](https://www.google.com/search?q=%23-usage-examples)
  - [Future Roadmap](https://www.google.com/search?q=%23-future-roadmap)

-----

## 🧐 Problem Statement

Modern life involves a constant stream of administrative overhead—planning meals, remembering shopping lists, and organizing schedules. These "micro-decisions" lead to decision fatigue.

While specialized apps exist (recipe apps, to-do lists), they are fragmented and passive. This project solves that by creating a **Unified Concierge Interface** that bridges the gap between natural language intent and structured task execution.

-----

## 🏗 Architecture

The system uses a **Root Coordinator Agent** that analyzes user intent and delegates tasks to specialized tools. It maintains a stateful `MemoryBank` to remember context across conversation turns.

1.  **User Input:** Natural language request (e.g., "Plan a healthy week").
2.  **Concierge Agent:** Powered by **Gemini 2.0 Flash Exp**, it reasons about the request.
3.  **Tool Execution:**
      * **Meal Planner:** Deterministic logic for dietary structures.
      * **Task Manager:** CRUD operations for the To-Do list.
      * **Google Search:** Fetches real-time external info.
4.  **Memory Bank:** Stores generated plans and tasks for retrieval later.

-----

## ✨ Features

  * **🥗 Intelligent Meal Planning**
      * Generates structured meal plans based on dietary preferences (Healthy, Vegetarian, Quick).
      * Saves plans to memory for cross-referencing with shopping lists.
  * **✅ Contextual Task Management**
      * Add, List, and Complete tasks using natural conversation.
      * Extracts tasks implicitly from other contexts (e.g., extracting ingredients from a meal plan to add to a shopping list).
  * **🧠 Long-Term Memory**
      * Custom `MemoryBank` class allows the agent to recall previous interactions within the session.
  * **🔍 Web Search Integration**
      * Falls back to Google Search for queries requiring up-to-date real-world knowledge.

-----

## 🛠 Tech Stack

  * **Language:** Python 3.11+
  * **Framework:** [Google Agent Development Kit (ADK)](https://github.com/google/generative-ai-python)
  * **Model:** Google Gemini 2.0 Flash Exp
  * **Environment:** Kaggle Notebooks / Jupyter
  * **Key Libraries:** `google-genai`, `google-adk`, `dataclasses`

-----

## 🚀 Setup & Installation

### Prerequisites

  * A [Kaggle](https://www.kaggle.com/) account (or local Python environment).
  * A Google Cloud Project with the **Gemini API** enabled.
  * A Google API Key.

### Installation Steps

1.  **Clone/Open the Notebook:**
    Load `capstone-to-do-ai.ipynb` into your Kaggle environment.

2.  **Configure Secrets:**

      * Go to the **Add-ons** menu in Kaggle.
      * Select **Secrets**.
      * Add a new secret with the Label `GOOGLE_API_KEY` and your actual API key as the Value.

3.  **Install Dependencies:**
    The notebook uses the internal Kaggle environment. Ensure the internet is toggled **ON** in the notebook settings.

4.  **Run the Agent:**
    Execute Cells 1 through 6 sequentially.

      * *Note:* The final cell sets up the ADK interface but prevents the web server from running indefinitely to save your API quota.

-----

## 💡 Usage Examples

Once the agent is running, you can interact with it using natural language prompts:

**Scenario 1: Meal Planning**

> **User:** "I want to eat vegetarian this week. Can you plan my meals?"
>
> **Agent:** *Calls `meal_planner_tool(preferences="vegetarian")`, stores the plan, and presents the menu (Smoothie bowl, Veggie wrap, Lentil curry).*

**Scenario 2: Task Management**

> **User:** "That looks good. Add 'Buy lentils' to my to-do list."
>
> **Agent:** *Calls `task_manager_tool(action="add", task="Buy lentils")` and confirms the addition.*

**Scenario 3: Retrieval**

> **User:** "What do I have to do today?"
>
> **Agent:** *Calls `task_manager_tool(action="list")` and displays all pending tasks.*

-----

## 🔮 Future Roadmap

If I had more time, I would expand the project with:

1.  **Persistent Database:** Migrate `MemoryBank` from RAM to SQLite or ChromaDB for permanent storage.
2.  **Dynamic API Integration:** Connect the Meal Planner to the Spoonacular API for real-time recipes.
3.  **Calendar Sync:** Integrate Google Calendar API to schedule tasks automatically.
4.  **Mobile UI:** Deploy a Streamlit or Gradio frontend for mobile accessibility.

-----

## 📄 License

This project is created for the AI Agents Capstone.
Distributed under the MIT License.
