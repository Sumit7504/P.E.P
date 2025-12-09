# Day 1 — Prompt Engineering Foundations

## What Is Prompt Engineering?

**Prompt Engineering = the process of designing structured instructions that guide AI models to produce accurate, controlled, and reliable outputs.**

It is a skill used to:

- Generate code (React, Next.js, Node.js)
- Debug applications
- Build AI agents and workflows
- Generate UI, APIs, SQL, documents, content
- Automate tasks in web applications

## link -- https://aws.amazon.com/what-is/prompt-engineering/

## Why Prompt Engineering Matters for Web Full-Stack Developers

AI is now part of:

- UI generation (React components)
- Backend logic generation
- API design & documentation
- Database schema generation
- Code reviews & debugging
- SEO content for websites
- Automating workflows

Prompt Engineering is the **2nd skill** after programming.

---

## Understanding How LLMs Think (Simple Explanation)

LLMs (GPT, Claude, Gemini, Llama):

- Do not “think”—they predict the _next best word_
- Understand context from your prompt
- Follow patterns, examples, rules you give
- Perform better when instructions are clear and structured

This is why prompts must be like **clean code**.

## link -- https://aws.amazon.com/what-is/large-language-model/

## The Three Prompt Roles

### 1️⃣ **System Prompt** (Brain Setup)

Sets:

- Behavior
- Tone
- Restrictions
- Rules

Example:

> You are an expert React developer. Use clean code and Tailwind.

---

### 2️⃣ **Developer Prompt** (Internal Instructions)

Hidden from user.  
Used for app logic, constraints.

Example:

> Do not hallucinate.  
> Use JSON output only.

---

### 3️⃣ **User Prompt** (Actual Request)

Example:

> Generate a responsive navbar in React + Tailwind.

---

## 🏗️ Basic Prompt Structure (Very Important!)

[Role / Context]
[Task]  
[Requriment]  
[Constraints]-- limitation or restriction  
[Output Format]  
[Example] (optional)

### ✔ Exercise 1 — React Component Prompt

Question--
Write a prompt to generate a **responsive login form** using React + Tailwind.

Answer--
[Task]Build a fully responsive login form using React and Tailwind CSS.  
[Requriment]It should include email, password, remember me checkbox, and a submit button.  
[Constraints]The layout must be centered and mobile friendly.  
[Output]Use clean JSX and do not add unnecessary components.

question--
Write a prompt to generate a responsive navbar with a hamburger menu using React + Tailwind.

Answer--
Generate a responsive navbar using React and Tailwind CSS.  
Include a logo, 3 navigation links, and a hamburger menu for mobile screens.  
Navbar should collapse into a menu drawer on small screens.  
Return clean JSX only.

Question--
Write a prompt to generate a todo app UI with add/delete functionality.

Answer--
Create a simple todo app UI using React and Tailwind CSS.

Features:

- Add task
- Delete task
- Display list of tasks  
  Code must include useState hooks and clean JSX.
  Make the UI centered and minimal.

### ✔ Exercise 2 — Backend Prompt

Question--
Write a prompt to generate a Node.js API route for user registration.

Answer--  
[Role]Act as a senior Node.js developer.  
[Task]Generate a complete API route for user registration using Express.js.

[Requirements]

- Accept username, email, and password in the request body
- Hash the password securely (use bcrypt)
- Validate email format
- Return JSON response with success or error message
- Include error handling and proper HTTP status codes
- Provide clean, commented code

[Output] only code inside a single fenced code block.

### ✔ Exercise 3 — Debug Prompt

Write a prompt to fix an error in a Next.js component.

[Role]Act as an expert Next.js developer.  
[Task]Debug the following component and fix all errors.

[Requirements]

- Identify syntax or runtime errors
- Ensure proper React hooks usage
- Correct JSX and props issues
- Keep functionality intact
- Explain briefly what was fixed

[Output] only the corrected code in a fenced code block

[Example]

```code
import React, { useState } from 'react';

function Counter() {
const [count, setCount] = useState;

return (
<div>
<h1>Count: {count}</h1>
<button onClick={() => setCount(count + 1)}>Increment</button>
</div>
)
}

export default Counter;
```

[correct-code] --

```code
import React, { useState } from 'react';

function Counter() {
// Fixed: useState must be called as a function with initial value
const [count, setCount] = useState(0);

return (
<div>
<h1>Count: {count}</h1>
<button onClick={() => setCount(count + 1)}>Increment</button>
</div>
);
}

export default Counter;
```
