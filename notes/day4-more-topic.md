## Hallucination

## Definition:-llucination means when an AI model gives an answer that is confident but wrong, made-up, not supported by data, or factually incorrect.

Example:  
You ask: “Who invented the 9G network?”  
AI answers: “John Smith invented it in 2022.”  
(But 9G doesn’t exist → this is a hallucination.)

## Why Hallucinations Happen? (Causes)

1. Missing or unclear context

If your prompt is short or vague → AI guesses.

2. Over-creative instructions

When temperature is high or prompt says “be creative”.

3. Wrong assumptions inside the prompt

Example:
“Explain why the Sun is made of ice.”
AI may still answer → forced hallucination.

4. Long prompts exceeding context window

The model forgets old details → produces incorrect info.

5. No real-world lookup

AI cannot browse the internet unless allowed → relies on its training data and may guess.

## link -- https://www.linkedin.com/pulse/hallucinations-prompt-engineering-how-identify-avoid-them-kalluri/

## How to Reduce or Prevent Hallucinations

1. Give clear context (CRISPE method helps)

Context

Requirements

Instructions

Steps

Persona

Examples

2. Use “Don’t guess” instruction

3. Use Structured Output

```pgsql
Return output in JSON:
{ "title": "", "description": "" }
```

4. Lower temperature

5. Provide Examples (Few-Shot Prompts)

6. Use Verifiable Sources

Only answer using the facts provided below.
If not included, say "Not provided in context".

## Prompt Template to Avoid Hallucinations

```
You must not make up facts.
If the answer is not available in the context, reply: “I don’t know”.

Follow this output format strictly:
[output format here]

Context:
[Your data here]

Task:
[Your task here]
```
