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

**🔖 Tactic 1: Use Delimiters**

Use delimiters to clearly indicate distinct parts of the input. Examples include:
- Triple backticks: ` ``` `
- Triple quotes: `"""`
- Angle brackets: `< >`
- XML tags: `<tag> </tag>`
- Colons: `:`

This helps prevent prompt injection and clearly separates instructions from content.

**📊 Tactic 2: Ask for Structured Output**

Request output in specific formats such as:
- 📄 JSON
- 🌐 HTML
- 📋 Other structured formats

This makes it easier to parse and use the model's response in your applications.

**✅ Tactic 3: Check Whether Conditions Are Satisfied**

Ask the model to verify if conditions are met before proceeding with a task. For example:
- ✔️ Check if text contains instructions before reformatting
- ❌ Provide alternative responses when conditions aren't met (e.g., "No steps provided")

**📚 Tactic 4: Few-Shot Prompting**

Provide examples of successful task execution before asking the model to perform the task. This helps the model understand the desired style, format, or approach.

💬 Example: Show a conversation pattern between a child and grandparent, then ask the model to continue in the same style.

#### 🧠 Principle 2: Give the Model Time to "Think"

Rushing to conclusions can lead to reasoning errors. Give the model time to work through problems step-by-step.

##### Tactics for Principle 2:

**📝 Tactic 1: Specify the Steps Required**

Break down complex tasks into a sequence of steps:
1. 📌 Define each step clearly
2. 🎯 Ask for specific outputs at each stage
3. ➡️ Request separation between steps (e.g., line breaks)
4. 📋 Specify output format (e.g., JSON with specific keys)

This structured approach helps the model organize its reasoning process.

**🔍 Tactic 2: Instruct the Model to Work Out Its Own Solution**

Before evaluating someone else's solution:
- 🧮 Ask the model to solve the problem independently first
- ⚖️ Then compare its solution with the provided solution
- ✅ Only then make a judgment about correctness

This prevents the model from being biased by the provided solution and leads to more accurate evaluations.

#### ⚠️ Model Limitations

**🚨 Hallucinations**
- Models can generate plausible-sounding but incorrect or fabricated information
- 💡 Example: The model might describe a non-existent product in detail
- 🔍 Always verify critical information, especially for real-world applications

---

### 🔄 Section 2: Iterative Prompt Development

**Notebook**: [`2_iterative_prompt_development.ipynb`](2_iterative_prompt_development.ipynb)

This section demonstrates the iterative process of analyzing and refining prompts to generate marketing copy from a product fact sheet. The key lesson is that prompt development is rarely perfect on the first try - it requires experimentation and refinement.

#### 🎯 Use Case: Generate Marketing Product Description

The practical example involves creating a marketing description for a mid-century inspired office chair based on a technical fact sheet containing specifications like materials, dimensions, construction details, and options.

#### 🔧 Iterative Refinement Process

The notebook demonstrates how to identify and fix common issues through prompt iteration:

**❌ Issue 1: The Text is Too Long**

Problem: Initial prompt generates overly lengthy descriptions

✅ Solution: Add specific length constraints to the prompt
- Limit the number of words (e.g., "Use at most 50 words")
- Can also limit sentences or characters
- Be specific about the desired length to control output

**❌ Issue 2: Text Focuses on the Wrong Details**

Problem: Generated description doesn't emphasize aspects relevant to the target audience

✅ Solution: Specify the intended audience and focus areas
- Identify the target audience (e.g., furniture retailers vs. consumers)
- Ask the model to focus on specific aspects (e.g., materials and construction for technical audiences)
- Include specific details like product IDs when needed
- Tailor the technical depth based on audience expertise

**❌ Issue 3: Description Needs a Table of Dimensions**

Problem: Information needs to be presented in a structured format

✅ Solution: Request specific formatting and data organization
- Ask the model to extract specific information (e.g., dimensions)
- Request structured formats like tables with specific columns
- Specify the format (e.g., 📄 HTML for web use)
- Provide detailed instructions about table structure (column names, units, title)
- Request output in formats ready for production use (HTML with proper tags like `<div>`, `<table>`)

#### 💡 Key Learnings

**🔁 The Iterative Process:**
1. ▶️ Start with a basic prompt
2. 🔍 Analyze the output to identify issues
3. ✏️ Clarify instructions to address specific problems
4. 🔄 Refine and test again
5. 🔁 Repeat until the output meets requirements

**✨ Best Practices:**
- 📏 Be specific about length constraints (words, sentences, or characters)
- 👥 Define your target audience clearly
- 🎯 Specify which details to emphasize or include
- 📊 Request structured formats when needed (JSON, HTML, tables)
- 🧪 Iterate based on output analysis rather than trying to perfect the prompt immediately
- 🔬 Test and refine prompts systematically

**🚀 Practical Applications:**
- 📝 Generating marketing copy from technical specifications
- 👔 Creating audience-specific content variations
- 📋 Extracting and formatting structured data
- 🌐 Producing production-ready formatted output (HTML, etc.)

---

### 📄 Section 3: Summarizing

**Notebook**: [`3_summarizing.ipynb`](3_summarizing.ipynb)

This section explores how to use LLMs to summarize text with a focus on specific topics or aspects. The practical examples use product reviews from an e-commerce site to demonstrate different summarization techniques.

#### 🎯 Use Case: Summarizing Product Reviews

The examples demonstrate summarizing customer reviews for different stakeholders (shipping department, pricing department, etc.) to extract relevant insights efficiently.

#### 📝 Summarization Techniques

**📏 Summarize with Length Limits**

Control the output length by specifying constraints:
- Set word limits (e.g., "in at most 30 words")
- Can also use sentence or character limits
- Helps create concise summaries suitable for dashboards or reports

**🚚 Summarize with Focus on Specific Topics**

Tailor summaries for different audiences and purposes:

**Focus on Shipping and Delivery:**
- Extract information relevant to logistics teams
- Highlight delivery times, shipping issues, and packaging quality
- Useful for operational feedback

**💰 Focus on Price and Value:**
- Extract pricing-related feedback for pricing departments
- Identify perceived value and price sensitivity
- Helps inform pricing strategy decisions

**⚠️ Note:** Summaries may include some unrelated topics even when focused on specific aspects.

#### 🔍 Extract vs. Summarize

**"Extract" for Precision:**
- Use "extract" instead of "summarize" for more focused results
- Pulls only the relevant information without additional context
- More precise when you need specific data points
- Better for filtering out unrelated information

**"Summarize" for Context:**
- Provides a condensed version with broader context
- May include related but not directly relevant information
- Better for general overviews

#### 📊 Summarizing Multiple Reviews

**Batch Processing:**
- Process multiple reviews efficiently using loops
- Generate consistent summaries across large datasets
- Useful for analyzing customer feedback at scale
- Can create dashboards or reports from bulk review data

**Example Applications:**
- 🛍️ E-commerce review analysis
- 📦 Logistics feedback extraction
- 💵 Pricing insights gathering
- ⭐ Customer sentiment tracking

#### 💡 Key Learnings

**Best Practices:**
- 🎯 Specify the target audience or department for focused summaries
- 📏 Set clear length constraints for consistent output
- 🔍 Use "extract" for precision, "summarize" for context
- 🔄 Process multiple items in batches for efficiency
- 📌 Focus on specific aspects (shipping, pricing, quality) based on needs

**Practical Applications:**
- 📊 Creating executive summaries from long documents
- 🛒 Analyzing customer feedback at scale
- 📈 Generating insights for different departments
- 📝 Condensing technical documentation
- 💬 Processing large volumes of text data efficiently

---

## 💻 Practical Implementation

All concepts are demonstrated in Jupyter notebooks with working code examples:
- [`1_guidelines_for_prompting.ipynb`](1_guidelines_for_prompting.ipynb) - Two core prompting principles with tactics and model limitations
- [`2_iterative_prompt_development.ipynb`](2_iterative_prompt_development.ipynb) - Iterative refinement process for generating marketing copy
- [`3_summarizing.ipynb`](3_summarizing.ipynb) - Text summarization techniques with focus on specific topics

## ✨ Key Takeaways

- Clear and specific prompts are more effective than vague ones
- Longer prompts with context often produce better results
- Structured outputs make responses easier to use programmatically
- Breaking tasks into steps improves reasoning quality
- Models need to work through problems themselves for accurate evaluations
- Always be aware of model limitations like hallucinations
- Prompt development is an iterative process - rarely perfect on the first try
- Analyze output and refine prompts systematically based on specific issues
- Be explicit about length constraints, target audience, and desired focus areas
- Request specific formats (HTML, tables, JSON) for production-ready outputs
- Use "extract" for precision and "summarize" for broader context
- Tailor summaries to specific audiences and departments for actionable insights
- Process multiple items in batches for efficient large-scale analysis

## 🔧 Technical Details

- **Model**: `gpt-3.5-turbo`
- **Temperature**: 0 (for consistent, deterministic outputs)
- **API**: OpenAI Chat Completions endpoint
- **Development Environment**: Jupyter Notebook
- **Python Libraries**: 
  - `openai` (versions 0.27.0 and 1.0.0)
  - `python-dotenv` (for environment variable management)
  - `typing-extensions`, `pydantic` (dependencies)
  - `IPython.display` (for rendering HTML in notebooks)
