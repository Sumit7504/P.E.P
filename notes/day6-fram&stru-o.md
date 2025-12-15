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

```
{
"componentName": "LoginForm",
"files": ["Login.jsx", "styles.css"],
"description": "Responsive login form",
"code": "<code here>"
}
```

## Exercises

Exercise 1 — JSON Structured Output (Ask AI to return a login form in JSON format).

```
Generate a responsive login form.

Return output ONLY in JSON:
{
  "component": "",
  "description": "",
  "tailwindClasses": [],
  "jsxCode": ""
}
Do not include any extra text.
```

Exercise 2 — Prompt for API Generation(Use RACE framework to generate Node.js API).

```
Role:
You are an experienced backend developer.

Action:
Generate a Node.js API route for user registration.

Context:
Use Express.js with MongoDB.
Include password hashing and basic validation.

Expectation:
Return clean, production-ready code.
Use async/await.
Add comments explaining key parts.
Do not include extra explanations outside code.
```

- output

```
app.post("/register", async (req, res) => {
  const { email, password } = req.body;

  if (!email || !password) {
    return res.status(400).json({ message: "Missing fields" });
  }

  const hashedPassword = await bcrypt.hash(password, 10);

  await User.create({ email, password: hashedPassword });

  res.status(201).json({ message: "User registered successfully" });
});
```
