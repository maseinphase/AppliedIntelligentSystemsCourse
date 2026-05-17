# Wild Bee Sighting Agent: A Case Study in Agentic AI

Welcome to the lab for **Lecture 7: Agentic AI in Data Science**. This project demonstrates the transition from traditional "Passive" Language Models to "Active" Agentic workflows using local biodiversity data from Kufstein.

## Project Overview
The goal of this project is to answer the question: *"Which wild bee species can I likely observe today in Kufstein?"*

To do this, we compare two approaches:
1.  **Variant 1 (Standalone):** A standard LLM (Qwen/Gemini) that relies only on its training data.
2.  **Variant 2 (Agentic):** An AI Agent that uses **SmolAgents** to dynamically fetch real-time weather, query historical sighting records (GBIF), and applies a Random Forest model.

---

## Project Structure

### Core Notebooks & Scripts
- `AgenticAI_demo.ipynb`: The main lecture notebook containing the comparative demonstration.

### Data Environment (`data/`)
- `gbif_sightings.csv`: Historical wild bee observations within 5km of FH Kufstein.
- `weather_data.csv`: Historical meteorological data (Temp, Rain, Wind) for the observation dates.
- `gbif_wildbee_families_taxon_keys.txt`: Reference list of the 7 primary wild bee families.

---

## Setup Instructions

### 1. Environment Configuration
Create a virtual environment and install the required Data Science and AI libraries:
```bash
python -m venv venv
source venv/bin/activate  # macOS/Linux
# venv\Scripts\activate   # Windows
pip install -r requirements.txt
```

### 2. API Credentials
Copy the template and add your keys:
```bash
cp .env.example .env
```
- **HF_TOKEN**: Required for accessing Qwen via the Hugging Face Hub.
- **GOOGLE_API_KEY**: Required for the Gemini Reasoning Engine (optional).

---

## 🧠 Key Learning Objectives

### The ReAct Pattern
Observe how the Agent uses the **Think-Action-Observation** loop. It doesn't just guess; it:
1.  **Thinks** about the need for local context (date, weather).
2.  **Acts** by calling external APIs.
3.  **Observes** the data and refines its plan.

---

## How to Run

Open `AgenticAI_demo.ipynb` and execute the cells sequentially. Ensure your VS Code kernel is set to the `venv` you created.

---
**Course:** Applied Intelligent Systems  
