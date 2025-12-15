## Why Prompt Frameworks Matter

Frameworks:

reduce hallucinations  
improve clarity  
make prompts reusable  
are used by teams, not individuals

## Prompt Frameworks

CRISPE Framework

```
Context:
You are building a SaaS landing page.

Role:
Act as a senior React developer.

Instructions:
Generate a responsive pricing section.

Steps:
1. Use Tailwind
2. Include 3 plans
3. Mobile-first design

Persona:
Clean, modern, enterprise-level UI

Examples:
Basic, Pro, Enterprise
```

RACE Framework

```
Role: AI frontend engineer
Action: Create a login page
Context: React + Tailwind
Expectation: Clean UI, responsive, accessible
```

PASTEL Framework

```
| P | Persona |
| A | Audience |
| S | Scope |
| T | Tone |
| E | Examples |
| L | Limitations |
```

Used in UX, content, product prompts.

COSTAR Framework

```
| C | Context |
| O | Objective |
| S | Style |
| T | Tone |
| A | Audience |
| R | Response Format |
```

## Structured Output (VERY IMPORTANT)

- Unstructured Output (Bad)
  Here is your code and explanation mixed together...

- Structured Output (Professional)

{
"componentName": "LoginForm",
"files": ["Login.jsx", "styles.css"],
"description": "Responsive login form",
"code": "<code here>"
}
