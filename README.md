# 💬 ELIZA Reimagined: A Rule-Based Chatbot Inspired by the 1960s Classic
*Exploring early conversational AI design through a modern lens.*

## Overview
This project revisits one of the earliest examples of human–computer conversation: **ELIZA**, the 1960s chatbot created by Joseph Weizenbaum at MIT.  
Rather than using modern generative models, this implementation recreates the **core rule-based logic** of ELIZA to simulate natural conversation—without any machine learning dependencies.

I built this project to understand how early conversational systems functioned, what made them feel “human,” and how they compare to modern large language models (LLMs).  
To jumpstart development, I consulted an LLM for **code structure ideas and regex logic**, then refined and implemented the final chatbot manually in Python.

---

##  Background
ELIZA was one of the first programs to demonstrate that *syntactic mimicry alone* could create the illusion of understanding.  
The original version, known as the *DOCTOR* script, parodied a Rogerian psychotherapist by reflecting users’ statements back in the form of open-ended questions.

This project reimplements those ideas in a lightweight, self-contained Python chatbot.

[Original Paper (Weizenbaum, 1966)](https://web.stanford.edu/class/cs124/p36-weizenabaum.pdf)

---

## Implementation Details
The chatbot is written entirely in **Python** within a Jupyter Notebook, using:
- Basic **string and regex pattern matching**
- Simple **response templates** and pronoun swapping
- Randomized selection among candidate replies for variety
- A looping input function for continuous conversation

The bot runs fully offline—no LLM APIs or pretrained models are used at runtime.

### Core Components
- `reflect()`: swaps first- and second-person pronouns (`I` → `you`, `my` → `your`, etc.)
- `analyze_input()`: uses keyword matching to determine the most relevant response pattern
- `respond()`: constructs a response based on reflection and keyword rules
- `run_eliza()`: main loop for interaction, ends when user types `quit`

---

## Example Interactions

### Session 1
Hello, I’ve been feeling tired lately.
ELIZA: Do you think coming here will help you not be tired?

I’m not sure.
ELIZA: Why do you think you are not sure?

Because I have too much work.
ELIZA: Tell me more about your work.

quit
ELIZA: Goodbye. Take care.

shell
Copy code

### Session 2
My friends don’t listen to me.
ELIZA: Do you think your friends should listen to you more?

Yes.
ELIZA: You seem quite certain.

shell
Copy code

### Session 3
I can’t focus when I study.
ELIZA: What would it mean to you if you could focus?

I guess I’d finally finish my projects.
ELIZA: Why is it important for you to finish your projects?

yaml
Copy code

These examples demonstrate the illusion of empathy through simple linguistic reflection and pattern substitution.

---

## Comparison to Modern LLMs
While modern models like GPT-4 or Gemini can maintain long, coherent dialogues, **ELIZA operates on pure surface-level cues**.  
It has no understanding of context or memory—it simply transforms input through predefined rules.  
However, even this limited system highlights how **structure and tone** alone can make a conversation feel meaningful.

Key contrasts:
| Aspect | ELIZA (1966-style) | Modern LLMs |
|--------|---------------------|--------------|
| Knowledge | None (rules only) | Learned from large text corpora |
| Understanding | Syntactic imitation | Semantic and contextual reasoning |
| State management | Stateless | Stateful memory and embeddings |
| Response generation | Deterministic templates | Probabilistic token prediction |

---

## Reflection & Insights
**What worked well**
- Simple regex patterns can surprisingly capture many conversational cues.  
- Adding randomness to responses prevents repetition and creates a sense of spontaneity.  
- Pronoun reflection contributes significantly to perceived empathy.

**What was limited**
- The bot often misinterprets complex sentences or multi-clause statements.  
- No long-term context or memory—each message is treated in isolation.  
- Keyword reliance can produce odd transitions when inputs deviate from expected phrasing.

**What would improve realism**
- A lightweight memory buffer to recall previous topics.  
- Context-aware pattern ranking (e.g., via TF–IDF or semantic similarity).  
- Tone adjustment or sentiment-driven response selection.

---

## Project Files
- `eliza_notebook.ipynb` — primary notebook containing implementation, testing, and commentary  
- `eliza_notebook.html` — rendered version with example runs  
- `ai_transcript.txt` — documentation of initial LLM-assisted brainstorming and debugging  

---

## Running the Chatbot

### Prerequisites
- Python 3.10+
- `re` (built-in)
- `random` (built-in)
- Jupyter Notebook

### Run locally
```bash
git clone https://github.com/cpawlenok/eliza-reimagined.git
cd eliza-reimagined
jupyter notebook
