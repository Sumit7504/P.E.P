## Prompt Types (Zero-Shot, Few-Shot, CoT)

## Zero-Shot Prompting

You give no example.
You only give instructions.
AI must figure out everything itself.

## Zero-Shot Prompt

```
Generate a professional Features section using React and TailwindCSS.
Include four features, each with an icon, title, and a short description.
Make the design fully responsive and follow clean UI best practices.
Return only the React component code.
```

## Few-Shot Prompting

You give examples first, then ask AI to follow the same style.

```
Example 1:
Prompt: Create a simple card component using React and Tailwind.
Output: <div className="p-4 shadow rounded bg-white">Card Content</div>

Example 2:
Prompt: Create a button component with a blue background and hover effect.
Output: <button className="bg-blue-600 px-4 py-2 text-white rounded hover:bg-blue-700">Click</button>

Now follow the same style and create a responsive navbar using React and Tailwind.
Return only the code output.
```

```<nav className="flex items-center justify-between p-4 bg-white shadow">
  <h1 className="text-xl font-semibold">Brand</h1>
  <ul className="hidden md:flex gap-6 text-gray-700">
    <li>Home</li>
    <li>Features</li>
    <li>Pricing</li>
    <li>Contact</li>
  </ul>
  <button className="md:hidden p-2 border rounded">☰</button>
</nav>
```

## Chain-of-Thought (CoT)

You ask AI to think step by step.
More reasoning → better accuracy.

Write a Chain-of-Thought prompt to generate a user authentication flow.

```
Think step-by-step and generate a complete user authentication flow.
1. First explain the components needed (Login form, Register form, API handlers, validation).
2. Then generate React + Tailwind code for Login and Register components.
3. Finally generate Node.js API routes for login and register.

Show the reasoning, then show the final code output separately.
```

### output

```
Reasoning:
1. We need two components and two API routes.
2. Forms must include validation and responsive UI.
3. Backend should hash passwords and validate input.

Final Output:
[React Login Component Code...]
[React Register Component Code...]
[Node.js API Code...]
```
