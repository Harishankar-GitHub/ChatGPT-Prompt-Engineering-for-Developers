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

### 🔍 Section 4: Inferring

**Notebook**: [`4_inferring.ipynb`](4_inferring.ipynb)

This section explores how to use LLMs to infer information from text, including sentiment analysis, emotion detection, and topic extraction. The examples demonstrate analyzing product reviews and news articles.

#### 🎯 Use Cases: Sentiment Analysis & Topic Extraction

The notebook covers two main use cases:
- Analyzing product reviews for sentiment and emotions
- Extracting topics from news articles and creating alerts

#### 😊 Sentiment Analysis

**Basic Sentiment Detection:**
- Determine if text is positive or negative
- Get detailed sentiment explanations or single-word answers
- Useful for understanding customer satisfaction

**Structured Output:**
- Request specific formats (e.g., "positive" or "negative")
- Makes results easy to process programmatically
- Enables automated sentiment tracking at scale

#### 💭 Emotion Detection

**Identify Multiple Emotions:**
- Extract a list of emotions from text (e.g., happy, satisfied, impressed)
- Limit the number of emotions for focused analysis
- Format as comma-separated lists for easy parsing

**Detect Specific Emotions:**
- Check for particular emotions like anger, frustration, or joy
- Get yes/no or true/false responses
- Useful for flagging reviews that need immediate attention

#### 🏷️ Information Extraction

**Extract Structured Data:**
- Pull specific information like product names and company names
- Format as JSON for easy integration with applications
- Handle missing information gracefully (use "unknown" as default)

**Example Extractions:**
- 📦 Product/item purchased
- 🏢 Company/brand name
- 📍 Locations, dates, or other entities

#### 🎯 Multiple Tasks at Once

**Combine Multiple Inferences:**
- Perform sentiment analysis, emotion detection, and information extraction in a single prompt
- Request JSON output with multiple keys (Sentiment, Anger, Item, Brand)
- More efficient than making separate API calls
- Reduces processing time and costs

**Example Combined Output:**
```json
{
  "Sentiment": "positive",
  "Anger": false,
  "Item": "lamp",
  "Brand": "Lumina"
}
```

#### 📰 Topic Inference

**Identify Topics in Text:**
- Extract main topics from articles or long-form content
- Specify the number of topics to identify
- Format as comma-separated lists for easy processing

**Topic-Based Alerts:**
- Create news alerts for specific topics of interest
- Check if predefined topics appear in new content
- Return binary indicators (0 or 1) for each topic
- Automate content filtering and notification systems

**Example Application:**
- 🚨 Alert system for monitoring specific topics (e.g., "NASA", "employee satisfaction")
- 📊 Content categorization and routing
- 🔔 Automated notifications based on topic presence

#### 💡 Key Learnings

**Best Practices:**
- 🎯 Specify output format clearly (single word, JSON, list, etc.)
- 🔄 Combine multiple inference tasks in one prompt for efficiency
- 📋 Use structured formats (JSON) for easy programmatic processing
- ⚡ Request concise responses to reduce token usage
- 🎚️ Set limits on list items (e.g., "no more than five emotions")

**Practical Applications:**
- 📊 Customer feedback analysis and sentiment tracking
- 🚨 Automated alert systems for specific topics
- 🏷️ Content categorization and tagging
- 📈 Brand and product mention monitoring
- 💬 Social media monitoring and analysis
- 🎯 Routing customer reviews to appropriate departments

**Advantages Over Traditional ML:**
- ⚡ No need to train custom models for each task
- 🚀 Quick deployment with just prompt engineering
- 🔧 Easy to modify and adapt to new requirements
- 📊 Handle multiple tasks with a single model

---

### 🔄 Section 5: Transforming

**Notebook**: [`5_transforming.ipynb`](5_transforming.ipynb)

This section explores how to use LLMs for text transformation tasks including language translation, spelling and grammar checking, tone adjustment, and format conversion.

#### 🎯 Use Cases: Text Transformation Tasks

The notebook demonstrates various transformation capabilities:
- 🌍 Language translation and detection
- 🎭 Tone and style adjustment
- 🔀 Format conversion between data structures
- ✍️ Spelling and grammar correction

#### 🌍 Translation

**🗣️ Basic Translation:**
- Translate text between languages (e.g., English to Spanish, French, Chinese)
- ChatGPT is trained on sources in many languages
- Simple and effective for common translation tasks

**🔍 Language Detection:**
- Identify the language of a given text
- Useful for routing and preprocessing multilingual content
- Supports major world languages

**🌐 Multiple Language Translation:**
- Translate to multiple languages simultaneously
- Example: Translate to French, Spanish, and English pirate 🏴‍☠️
- Efficient for creating multilingual content

**👔 Formal vs. Informal Translation:**
- Request both formal and informal forms
- Important for culturally appropriate communication
- Example: Formal "usted" vs. informal "tú" in Spanish

**🌐 Universal Translator:**
- Practical application for multinational companies
- Process messages in multiple languages automatically
- Translate IT support requests from various languages to English
- Batch process multiple messages efficiently
- Example languages: 🇫🇷 French, 🇪🇸 Spanish, 🇮🇹 Italian, 🇵🇱 Polish, 🇨🇳 Chinese

#### 🎭 Tone Transformation

**✨ Adjust Writing Style:**
- Transform casual/slang language to professional business tone
- Convert between different writing styles (formal, informal, technical)
- Adapt content for different audiences

**Example:**
- 😎 Slang: "Dude, This is Joe, check out this spec on this standing lamp."
- 💼 Business: Professional letter format with appropriate greeting and closing

#### 🔀 Format Conversion

**📊 Convert Between Data Formats:**
- Transform data structures (JSON to HTML, CSV to JSON, etc.)
- Describe input and output formats in the prompt
- Generate formatted output ready for use

**Example Applications:**
- 📄 JSON to HTML table conversion
- 📋 Dictionary to formatted table with headers
- 🎨 Add styling and structure to data presentations
- 🔄 Convert between markup languages

**🖥️ Rendering Output:**
- Use `IPython.display` to render HTML, Markdown, JSON
- Visualize transformed content directly in notebooks
- Verify formatting before production use

#### ✍️ Spelling and Grammar Check

**📝 Proofreading:**
- Use "proofread" or "proofread and correct" instructions
- Detect and fix common grammar errors
- Handle spelling mistakes and typos

**❌ Common Error Types:**
- Subject-verb agreement errors
- Homonyms (its/it's, their/there/they're, your/you're)
- Effect vs. affect
- Spelling mistakes

**✨ Advanced Proofreading:**
- Combine proofreading with style improvements
- Make text more compelling or professional
- Apply style guides (📚 APA, MLA, Chicago, etc.)
- Target specific reading levels (🎓 advanced, 📖 general, 🔤 beginner)

**🔴 Redlines Library:**
- Visualize changes between original and corrected text
- Show deletions and additions in markdown format
- Useful for reviewing edits and understanding corrections
- Helps learn from mistakes

**🎯 Enhanced Corrections:**
- ✅ Proofread + improve tone
- 📋 Apply specific style guides
- 📄 Format output (markdown, HTML, etc.)
- 👥 Tailor for target audience

#### 💡 Key Learnings

**✨ Best Practices:**
- 🌍 Leverage multilingual capabilities for translation tasks
- 🎯 Specify both input and output formats clearly for conversions
- ✍️ Use "proofread and correct" for grammar checking
- 🎨 Combine multiple transformations in one prompt (proofread + tone + style)
- 📊 Request specific output formats (markdown, HTML) for easy rendering
- 🔄 Process multiple items in batches for efficiency

**🚀 Practical Applications:**
- 🌐 Multilingual customer support and communication
- 📧 Email and document tone adjustment
- 📊 Data format conversion for reports and dashboards
- ✅ Automated proofreading and editing
- 📝 Content adaptation for different audiences
- 🎓 Style guide compliance (APA, MLA, etc.)
- 🔄 Batch processing of multilingual content

**⚡ Advantages:**
- 🎯 No need for separate translation, grammar, or formatting tools
- 🚀 Single model handles multiple transformation tasks
- 🔧 Easy to customize for specific requirements
- 💰 Cost-effective compared to multiple specialized services

---

### 📧 Section 6: Expanding

**Notebook**: [`6_expanding.ipynb`](6_expanding.ipynb)

This section explores how to use LLMs to expand short text into longer, more detailed content. The primary use case is generating customized customer service email responses based on customer reviews and sentiment.

#### 🎯 Use Case: Automated Customer Service Emails

The notebook demonstrates how to:
- Generate personalized email responses to customer reviews
- Tailor responses based on sentiment (positive, negative, neutral)
- Include specific details from the original customer message
- Maintain appropriate tone and professionalism

#### 📝 Customized Email Generation

**🤖 AI Customer Service Assistant:**
- Act as a customer service AI assistant
- Generate email replies to valued customers
- Thank customers for their reviews
- Address concerns based on sentiment

**📊 Sentiment-Based Responses:**

**😊 Positive/Neutral Sentiment:**
- Thank the customer for their positive feedback
- Acknowledge specific details they mentioned
- Reinforce positive experience

**😞 Negative Sentiment:**
- Apologize for the customer's experience
- Show empathy and understanding
- Suggest reaching out to customer service for resolution
- Address specific concerns mentioned in the review

#### 🎨 Key Techniques

**✨ Use Specific Details:**
- Extract and reference specific points from customer reviews
- Show that you've read and understood their feedback
- Makes responses feel personalized, not generic
- Builds customer trust and satisfaction

**💼 Professional Tone:**
- Write in a concise and professional manner
- Maintain appropriate formality
- Sign emails appropriately (e.g., "AI customer agent")
- Balance friendliness with professionalism

**🎲 Temperature Parameter:**
- Use `temperature=0` for consistent, deterministic responses
- Use higher temperature (e.g., `temperature=0.7`) for more varied responses
- Higher temperature adds creativity and variation
- Useful for generating multiple response options

#### 🔄 Combining Previous Concepts

**Integration with Earlier Sections:**
- 🔍 Use sentiment from **Section 4: Inferring** to determine response type
- 📝 Apply techniques from **Section 1: Guidelines** for clear instructions
- 🎭 Leverage **Section 5: Transforming** for tone adjustment
- Demonstrates how different prompting techniques work together

**Workflow Example:**
1. 📥 Receive customer review
2. 🔍 Infer sentiment (positive/negative/neutral)
3. 📧 Generate appropriate email response
4. ✅ Include specific details from review
5. 📤 Send personalized response

#### 💡 Key Learnings

**✨ Best Practices:**
- 🎯 Define clear role and task for the AI (customer service assistant)
- 📊 Use sentiment analysis to guide response type
- 📝 Instruct model to use specific details from input
- 💼 Specify desired tone (concise, professional, empathetic)
- ✍️ Include signature and closing for complete emails
- 🎲 Experiment with temperature for response variation

**🚀 Practical Applications:**
- 📧 Automated customer service email responses
- 💬 Social media response generation
- 📝 Personalized thank you notes
- 🎓 Educational feedback to students
- 📢 Marketing email personalization
- 🤝 Follow-up communications
- 💼 Business correspondence automation

**⚡ Advantages:**
- ⏱️ Save time on repetitive email writing tasks
- 🎯 Ensure consistent quality and tone across responses
- 📈 Scale customer service operations efficiently
- 💰 Reduce costs while maintaining personalization
- 🔄 Generate multiple response variations quickly
- 🌍 Can be combined with translation for multilingual support

**🎓 Learning Point:**
- Expanding is the opposite of summarizing
- Takes brief input and generates detailed, contextual output
- Particularly powerful for customer-facing communications
- Combines multiple prompting techniques learned in previous sections

---

## 💻 Practical Implementation

All concepts are demonstrated in Jupyter notebooks with working code examples:
- [`1_guidelines_for_prompting.ipynb`](1_guidelines_for_prompting.ipynb) - Two core prompting principles with tactics and model limitations
- [`2_iterative_prompt_development.ipynb`](2_iterative_prompt_development.ipynb) - Iterative refinement process for generating marketing copy
- [`3_summarizing.ipynb`](3_summarizing.ipynb) - Text summarization techniques with focus on specific topics
- [`4_inferring.ipynb`](4_inferring.ipynb) - Sentiment analysis, emotion detection, and topic extraction
- [`5_transforming.ipynb`](5_transforming.ipynb) - Language translation, tone adjustment, format conversion, and grammar checking
- [`6_expanding.ipynb`](6_expanding.ipynb) - Generating detailed customer service emails from brief reviews

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
- Combine multiple inference tasks in one prompt to reduce API calls and costs
- Specify output formats clearly for easy programmatic processing
- LLMs can perform sentiment analysis and topic extraction without custom training
- Single LLM can handle translation, tone adjustment, format conversion, and grammar checking
- Leverage multilingual capabilities for global applications
- Combine multiple transformations (proofread + tone + style) in one prompt for efficiency
- Expanding is the opposite of summarizing - generates detailed content from brief input
- Temperature parameter controls response variation and creativity
- Combine techniques from multiple sections for powerful workflows (infer + expand)

## 🔧 Technical Details

- **Model**: `gpt-3.5-turbo`
- **Temperature**: 0 (for consistent, deterministic outputs)
- **API**: OpenAI Chat Completions endpoint
- **Development Environment**: Jupyter Notebook
- **Python Libraries**: 
  - `openai` (versions 0.27.0 and 1.0.0)
  - `python-dotenv` (for environment variable management)
  - `typing-extensions`, `pydantic` (dependencies)
  - `IPython.display` (for rendering HTML, Markdown, JSON in notebooks)
  - `redlines` (for visualizing text differences and edits)
