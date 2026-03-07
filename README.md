# ChatGPT Prompt Engineering for Developers - Learning Notes

<div align="center">
  <img src="https://img.shields.io/badge/OpenAI-412991?style=for-the-badge&logo=openai&logoColor=white" alt="OpenAI"/>
  <img src="https://img.shields.io/badge/ChatGPT-74aa9c?style=for-the-badge&logo=openai&logoColor=white" alt="ChatGPT"/>
  <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" alt="Python"/>
  <img src="https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white" alt="Jupyter"/>
</div>

<br/>

This repository documents my learnings from the [ChatGPT Prompt Engineering for Developers](https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/) course by DeepLearning.AI.

## 📚 Course Overview

This course teaches prompt engineering concepts using the OpenAI library in Python, with hands-on exercises in Jupyter notebooks. The focus is on writing effective prompts for large language models to achieve desired outputs.

## 🎯 What I've Learned

### ⚙️ Setup and Configuration
- How to use the OpenAI library (both version 0.27.0 and 1.0.0)
- Setting up and configuring API keys from OpenAI
- Loading environment variables using `python-dotenv`
- Creating helper functions for chat completions using `gpt-3.5-turbo` model

---

## 📖 Course Sections

### 📝 Section 1: Guidelines for Prompting

**Notebook**: [`1_guidelines_for_prompting.ipynb`](1_guidelines_for_prompting.ipynb)

#### 🎨 Prompting Principles

The course covers two main principles for effective prompting:

#### 💡 Principle 1: Write Clear and Specific Instructions

Clear and specific instructions guide the model toward the desired output and reduce irrelevant or incorrect responses. Note that clear doesn't mean short - longer prompts often provide more clarity and context.

##### Tactics for Principle 1:

**Tactic 1: Use Delimiters**

Use delimiters to clearly indicate distinct parts of the input. Examples include:
- Triple backticks: ` ``` `
- Triple quotes: `"""`
- Angle brackets: `< >`
- XML tags: `<tag> </tag>`
- Colons: `:`

This helps prevent prompt injection and clearly separates instructions from content.

**Tactic 2: Ask for Structured Output**

Request output in specific formats such as:
- JSON
- HTML
- Other structured formats

This makes it easier to parse and use the model's response in your applications.

**Tactic 3: Check Whether Conditions Are Satisfied**

Ask the model to verify if conditions are met before proceeding with a task. For example:
- Check if text contains instructions before reformatting
- Provide alternative responses when conditions aren't met (e.g., "No steps provided")

**Tactic 4: Few-Shot Prompting**

Provide examples of successful task execution before asking the model to perform the task. This helps the model understand the desired style, format, or approach.

Example: Show a conversation pattern between a child and grandparent, then ask the model to continue in the same style.

#### 🧠 Principle 2: Give the Model Time to "Think"

Rushing to conclusions can lead to reasoning errors. Give the model time to work through problems step-by-step.

##### Tactics for Principle 2:

**Tactic 1: Specify the Steps Required**

Break down complex tasks into a sequence of steps:
1. Define each step clearly
2. Ask for specific outputs at each stage
3. Request separation between steps (e.g., line breaks)
4. Specify output format (e.g., JSON with specific keys)

This structured approach helps the model organize its reasoning process.

**Tactic 2: Instruct the Model to Work Out Its Own Solution**

Before evaluating someone else's solution:
- Ask the model to solve the problem independently first
- Then compare its solution with the provided solution
- Only then make a judgment about correctness

This prevents the model from being biased by the provided solution and leads to more accurate evaluations.

#### ⚠️ Model Limitations

**Hallucinations**
- Models can generate plausible-sounding but incorrect or fabricated information
- Example: The model might describe a non-existent product in detail
- Always verify critical information, especially for real-world applications

---

## 💻 Practical Implementation

All concepts are demonstrated in Jupyter notebooks with working code examples:
- [`1_guidelines_for_prompting.ipynb`](1_guidelines_for_prompting.ipynb) - Complete implementation of both principles and all tactics

## ✨ Key Takeaways

- Clear and specific prompts are more effective than vague ones
- Longer prompts with context often produce better results
- Structured outputs make responses easier to use programmatically
- Breaking tasks into steps improves reasoning quality
- Models need to work through problems themselves for accurate evaluations
- Always be aware of model limitations like hallucinations

## 🔧 Technical Details

- **Model**: `gpt-3.5-turbo`
- **Temperature**: 0 (for consistent, deterministic outputs)
- **API**: OpenAI Chat Completions endpoint
- **Development Environment**: Jupyter Notebook
- **Python Libraries**: 
  - `openai` (versions 0.27.0 and 1.0.0)
  - `python-dotenv` (for environment variable management)
  - `typing-extensions`, `pydantic` (dependencies)
