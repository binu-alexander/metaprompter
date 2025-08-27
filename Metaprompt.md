# Prompt Transformer

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![GitHub stars](https://img.shields.io/github/stars/binu-alexander/metaprompter)
![GitHub issues](https://img.shields.io/github/issues/binu-alexander/metaprompter)

A simple meta-prompting approach that converts natural language requests into structured, reusable prompt templates. Transform any raw prompt into a standardized JSON format for consistent AI interactions.

## Overview

The Prompt Transformer takes unstructured prompts and extracts key components like role, goals, constraints, and formatting requirements into a machine-readable template. Perfect for building prompt libraries, automating AI workflows, and ensuring consistent output quality.

Turn informal messy prompts into structured templates.

Transform "Write me a professional email declining a meeting" into a reusable JSON template with role, constraints, style, and format specifications. Perfect for building consistent AI workflows.



- Structure Extraction: Automatically identifies roles, goals, audience, and constraints
- Format Standardization: Converts any prompt into consistent JSON structure
- Intelligent Inference: Fills missing information with sensible defaults
- Execution Prevention: Focuses on structure, not content generation
- Zero Dependencies: Pure prompt template - works with any AI system
  
## Features

- **Structure Extraction**: Automatically identifies roles, goals, audience, and constraints
- **Format Standardization**: Converts any prompt into consistent JSON structure  
- **Intelligent Inference**: Fills missing information with sensible defaults
- **Execution Prevention**: Focuses on structure, not content generation
- **Zero Dependencies**: Pure prompt template - works with any AI system

## Quick Start

### 1. Copy and Customize

Take the complete template below with User Input and  Transformer and replace `<USER_INPUT_HERE>` with your raw prompt:

```
# USER INPUT
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

**Paste the entire customized template into your AI chat as one message.** The AI will output structured JSON:

```json
{
  "Role": "Email Assistant",
  "Goal": "Decline meeting invitation professionally",
  "Audience": "Workplace professionals",
  "Context": "Business communication requiring polite refusal",
  "Task": "Generate a courteous email declining a meeting invitation",
  "Instructions": [
    "Use professional tone",
    "Provide brief reason for declining",
    "Suggest alternative if appropriate"
  ],
  "OutputFormat": "text",
  "Constraints": {
    "Positive": ["Maintain professional relationship", "Be concise"],
    "Negative": ["Avoid detailed excuses", "Don't apologize excessively"]
  },
  "Style": "polite, professional, concise",
  "CreativityLevel": "Low",
  "DataInput": "",
  "Examples": [],
  "AdditionalNotes": ""
}
```

### 3. Save and Reuse

Store the output JSON for consistent results across similar tasks.

## Use Cases
Perfect for prompt libraries, API integration, A/B testing, documentation, and team standardization.
Customize the transformer itself for more specific use cases.


## Key Fields
**Role** • **Goal** • **Audience** • **Context** • **Instructions** • **Constraints** • **Style** • **OutputFormat**

## Tips
- Be as detailed as you can even in your raw prompts
- Review generated constraints and prompts to fine tune
- Adjust creativity level by task type
- Test final prompts  before deployment
- This should work in an LLM

## License
MIT - use freely in any project. Star the repo if you like !

---

**Questions and Feedback ?** Open an issue on GitHub.
