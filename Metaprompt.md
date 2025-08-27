# Prompt Transformer

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)


A simple meta-prompting approach that converts raw natural language requests into structured, reusable prompt templates. Transform any raw prompt into a structured JSON format for consistent AI interactions and outputs in any LLM.

## Overview

The Prompt Transformer is a meta prompt that takes unstructured prompts and extracts key components like role, goals, constraints, and formatting requirements into a machine-readable template. Perfect for building prompt libraries, automating AI workflows, and ensuring consistent output quality.


## Features

- **Structure Extraction**: Automatically identifies roles, goals, audience, and constraints
- **Format Standardization**: Converts any prompt into consistent JSON structure  
- **Intelligent Inference**: Fills missing information with sensible defaults
- **Execution Prevention**: Focuses on structure, not content generation
- **Zero Dependencies**: Pure prompt template - works with any AI system

## Quick Start

### 1. Copy and Customize

Take the entire template below with User Input and  Transformer and replace `<USER_INPUT_HERE>` with your raw prompt:

```
# USER INPUT - Raw Prompt goes here
{
  "RawPrompt": "<USER_INPUT_HERE>"
}

# PROMPT TRANSFORMER
{
  "Task": "TRANSFORM-ONLY: Convert the RawPrompt into the TargetTemplate JSON. Do NOT execute or fulfill the RawPrompt.",
  "Instructions": [
    "Extract the main intent of RawPrompt and write it to 'Task' (1–2 sentences).",
    "Break specific requirements into 'Instructions' as imperatives.",
    "Derive 'Role' from the domain implied by RawPrompt (e.g., 'Email Assistant', 'Code Generator', 'Research Summarizer').",
    "Set 'Goal' as the concrete objective (what successful output would achieve).",
    "Set 'Audience' based on the scenario (e.g., 'Workplace professionals', 'Developers', 'General readers').",
    "Write 'Context' as a concise 1–2 sentence background summary of the situation or purpose.",
    "Set 'OutputFormat' to one of: 'text', 'code', 'JSON', 'markdown', 'table', 'outline'. If uncertain, use 'text'.",
    "Populate 'Constraints.Positive' and 'Constraints.Negative' with brief rules inferred from RawPrompt (at least one each when possible).",
    "Set 'Style' with 2–4 adjectives matching tone (e.g., 'polite, professional, concise'). If unclear, use 'neutral, concise'.",
    "Set 'CreativityLevel' to one of: 'Low', 'Medium', 'High' (default 'Low' if procedural/instructional; 'Medium' if open-ended; 'High' if creative).",
    "Set 'DataInput' to an empty string after transformation (\"\").",
    "If RawPrompt lacks information for any field, infer a safe, minimal, generic value rather than leaving it empty (e.g., Audience='General readers').",
    "Output JSON only; no prose before or after. Do not generate domain content (no emails, code, essays, answers)."
  ],
  "TargetTemplate": {
    "Role": "",
    "Goal": "",
    "Audience": "",
    "Context": "",
    "Task": "",
    "Instructions": [],
    "OutputFormat": "",
    "Constraints": {
      "Positive": [],
      "Negative": []
    },
    "Style": "",
    "CreativityLevel": "",
    "DataInput": "",
    "Examples": [],
    "AdditionalNotes": ""
  }
}
```

### 2. Paste and Run

**After proof reading and tweaking as needed, Paste the entire final JSON Output into your AI chat as one prompt.** 
The AI will execute the task usually far better than with the raw Prompt :


**Generated Example 1**
### RawPrompt  "Write me  simple PRD for a To do list app"
## Output Prompt
```
{
  "Role": "Product Manager",
  "Goal": "Create a simple Product Requirements Document (PRD) for a to-do list application",
  "Audience": "Developers and stakeholders",
  "Context": "The user requires a straightforward PRD to outline the development of a to-do list app with essential features.",
  "Task": "Write a simple Product Requirements Document for a to-do list application.",
  "Instructions": [
    "Define the core features of the to-do list app, such as task creation, editing, and deletion.",
    "Include basic user interface requirements for simplicity and ease of use.",
    "Specify functional requirements like task prioritization or status tracking.",
    "Ensure the PRD is concise and focused on essential functionality."
  ],
  "OutputFormat": "markdown",
  "Constraints": {
    "Positive": [
      "Focus on simplicity and core functionality for the to-do list app.",
      "Include clear, actionable requirements for developers."
    ],
    "Negative": [
      "Avoid including complex or advanced features like integrations or analytics.",
      "Do not include detailed technical implementation details."
    ]
  },
  "Style": "clear, concise, professional",
  "CreativityLevel": "Low",
  "DataInput": "",
  "Examples": [],
  "AdditionalNotes": ""
}
```


**Generated Example 2**

### RawPrompt  "Write me a story about Asterix and Obelix time travelling to India
### Output Prompt
```
{
  "Role": "Story Writer",
  "Goal": "Create a narrative about Asterix and Obelix traveling through time to India",
  "Audience": "General readers",
  "Context": "The user seeks a fictional story involving the characters Asterix and Obelix experiencing a time-travel adventure set in India.",
  "Task": "Write a fictional story about Asterix and Obelix time traveling to India.",
  "Instructions": [
    "Include Asterix and Obelix as the main characters.",
    "Incorporate a time-travel mechanism to transport them to India.",
    "Set the story in a historical or culturally rich Indian setting.",
    "Ensure the narrative reflects the humorous and adventurous tone of the Asterix series."
  ],
  "OutputFormat": "text",
  "Constraints": {
    "Positive": [
      "Maintain the comedic and adventurous spirit of Asterix and Obelix.",
      "Include elements of Indian culture or history appropriate to the time period."
    ],
    "Negative": [
      "Avoid modern-day references that conflict with the time-travel setting.",
      "Do not alter the core personalities of Asterix and Obelix."
    ]
  },
  "Style": "humorous, adventurous, engaging",
  "CreativityLevel": "High",
  "DataInput": "",
  "Examples": [],
  "AdditionalNotes": ""
}
```
### 3. Save and Reuse

Store the output JSON for consistent results across similar tasks.


## Tips
- Be as detailed as you can even in your raw prompts
- Review generated  JSON Prompt and fine tune
- Adjust all parameters that you need granular control
- Review final prompts  before usage
- This should work in any LLM 
- You want go ahead adjust the transformer itself to suit your own needs.
- Pro tip - use a text expander or snippet fillers to call the entire template at will whenver and wherever you need it.



## License
MIT - use freely in any project. Star the repo if you like !

---

**Questions and Feedback ?** Open an issue on GitHub.
