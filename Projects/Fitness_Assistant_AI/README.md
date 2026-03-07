# 🤖 AI Fitness Coach – Fine-Tuned Language Model

**Personalized AI-driven workout plans using a fine-tuned OpenAI model.**

---

## 📌 Project Overview

This project fine-tunes an OpenAI language model to act as a **personalized fitness coach**.  
The AI generates structured workout plans tailored to user profiles, including **age, fitness level, and goals**.  

**Goal:** Demonstrate a full workflow from dataset preparation to model evaluation and visualization of performance metrics.

---

## 🎯 Objectives

- Fine-tune an OpenAI model to respond as a fitness coach  
- Generate personalized workout plans for diverse users  
- Evaluate outputs using token usage, accuracy, and simulated loss  
- Compare results between fine-tuned and base models  
- Create visual summaries for performance analysis  

---

## 📊 Dataset

**File:** `FitnessCoach-50.jsonl`  
**Format:** JSON Lines (`.jsonl`)  

Contains ~50 examples with:

- **System message:** AI role definition  
- **User prompt:** Workout request  
- **Assistant response:** Structured workout routine  

### Example Entry

```json
{
  "messages": [
    {"role": "system", "content": "You are a fitness coach AI."},
    {"role": "user", "content": "Generate a 5-day beginner workout plan."},
    {"role": "assistant", "content": "Day 1: Squats, Push-ups, Plank..."}
  ]
}
````

---

## 🛠 Environment Setup

**Dependencies:**

* Python ≥3.10
* `requests`
* `python-dotenv`
* `matplotlib`

**Load API Key:**

```python
from dotenv import load_dotenv
import os

load_dotenv("ApiKey.env")
API_KEY = os.getenv("OPENAI_API_KEY")
if not API_KEY:
    raise ValueError("OPENAI_API_KEY not found")
```

`ApiKey.env` example:

```
OPENAI_API_KEY=your_openai_api_key_here
```

---

## 🏋️ Workflow

1. **Dataset Upload:** Upload `FitnessCoach-50.jsonl` to OpenAI for fine-tuning.
2. **Fine-Tune Job Creation:** Configure training parameters:

```json
{
  "training_file": "file_id_here",
  "model": "gpt-4.1-2025-04-14",
  "hyperparameters": {"n_epochs": 3, "learning_rate_multiplier": 1.5},
  "suffix": "FitnessCoach-50"
}
```

3. **Monitor Training:** Poll OpenAI API until job status is `succeeded`.
4. **Evaluate Model:** Test fine-tuned outputs with prompts like:

* "Generate a 5-day beginner workout plan for a 30-year-old female."
* "Create a 3-day strength training plan for a 40-year-old male."
* "Suggest a low-impact workout for a 50-year-old beginner."

5. **Compute Metrics:**

* **Token Usage:** Number of tokens per prompt
* **Accuracy:** Checks if expected exercises appear (Squats, Push-ups, Lunges, Plank, Glute Bridge, Jumping Jacks)
* **Simulated Loss:** `1 - Accuracy`

6. **Compare Base vs Fine-Tuned Models:** GPT-4.1 and GPT-3.5 base vs fine-tuned versions

---

## 📈 Visualization

Metrics plotted using `matplotlib`:

* **Accuracy** (green)
* **Simulated Loss** (red)
* X-axis: Test prompts

Visualizations show performance across different prompts.

---

## 📝 Output

**Summary File:** `workout_finetune_summary.json`

Includes:

* Fine-tuned model name
* Test prompts and outputs
* Token usage
* Accuracy scores
* Simulated loss

---

## 🔮 Future Improvements

* Expand training dataset (1000+ examples)
* Include structured JSON outputs for exercises, sets, reps, and duration
* Add nutrition and recovery suggestions
* Automate evaluation with NLP metrics (BLEU, ROUGE)
* Deploy as web or mobile AI fitness coach app

---

## ⚖ Ethical Considerations

* **Privacy:** Dataset contains synthetic examples only
* **Safety:** Recommendations are general; users should consult a physician
* **Transparency:** Assumptions, training limitations, and outputs are documented
* **Responsible AI:** Avoid unsafe or harmful exercises

---

## 📂 Project Structure

```
AI-FitnessCoach/
│
├── data/          # JSONL training files
├── notebooks/     # Jupyter notebooks for evaluation and visualization
├── figures/       # Performance charts and plots
├── appendix/      # Additional analysis, code snippets
└── README.md
```

---

## 👤 Author

**Karthika Vellingiri**
Applied Data Science / AI Projects
DSC 680 / DSC 640 Coursework

**Tools Used:** OpenAI API, JSON, Matplotlib, Python (optional evaluation), Jupyter Notebook