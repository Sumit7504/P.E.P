# Day 2 — LLM Foundations for Prompt Engineering

## 1. Tokens — The Building Blocks of Prompts

- **Definition:** A token is a piece of text that AI models read or generate. It could be a word, part of a word, or punctuation.
- **Example:** `"Hello World!"` → 3 tokens (`Hello`, `World`, `!`)
- **Why it matters:**
  - Determines prompt length
  - Affects API cost
  - Limits how much context the model can use

**Tip:** Keep prompts clear and concise to reduce tokens.

## link -- https://learn.microsoft.com/en-us/ai-builder/licensing-prompt-tokens

---

## 2. Models — Choose the Right LLM

- **GPT-3 / GPT-3.5:** Good for general tasks, cheaper, limited context
- **GPT-4:** Better reasoning, larger context window
- **Claude / LLaMA / Mistral:** Alternative models with unique strengths
- **Specialized models:** For code generation, embeddings, or agents

**Key takeaway:** Select a model based on:

1. Task complexity
2. Required reasoning
3. Cost & speed

---

## 3. Temperature — Control Creativity

- **Definition:** Controls randomness of AI output (range 0–1).Use low temperature for math/facts, high for creative writing.
  - `0` → deterministic, precise
  - `0.5` → balanced creativity
  - `1` → very creative, unpredictable

**Example:**

- Temp 0 → Strict, factual code
- Temp 1 → Creative UI/UX ideas or multiple solutions

---

## 4. Context Window — How Much AI Can Remember

- **Definition:** Max number of tokens AI can read + generate in one session
- GPT-3: ~4k tokens
- GPT-4: ~8k–32k tokens
- **Importance:**
  - Long documents require chunking
  - Avoid losing instructions
  - Helps design multi-step prompts

## link -- https://www.ibm.com/think/topics/context-window

---

## 5. Practical Day 2 Exercises

### Exercise 1 — Token Awareness

- Count tokens for:  
  `"Generate a responsive navbar using React and Tailwind for a mobile-first website."`
- Predict how many tokens the model sees.

Answer -- Approximate tokens = 14–16

### Exercise 2 — Temperature Experiment

- Use the prompt “Generate a login form using React and Tailwind.” to generate a login form
- Test with temperature 0, 0.5, 1
- Observe differences in AI outputs

Temperature = 0

```reactjs
function Login() {
  return (
    <div className="flex items-center justify-center h-screen">
      <form className="w-80 p-4 border rounded">
        <input className="w-full mb-3 p-2 border rounded" placeholder="Email" />
        <input className="w-full mb-3 p-2 border rounded" type="password" placeholder="Password" />
        <button className="w-full p-2 bg-blue-600 text-white rounded">Login</button>
      </form>
    </div>
  );
}
```

Temperature = 0.5

```reactjs
function Login() {
  return (
    <div className="min-h-screen flex items-center justify-center bg-gray-50">
      <form className="bg-white shadow-lg p-6 rounded-xl w-96">
        <h2 className="text-2xl font-semibold mb-4 text-center">Welcome Back</h2>
        <input className="w-full p-2 border rounded-lg mb-4" placeholder="Email address" />
        <input className="w-full p-2 border rounded-lg mb-4" type="password" placeholder="Password" />
        <button className="w-full py-2 bg-indigo-600 text-white rounded-lg">Sign In</button>
      </form>
    </div>
  );
}
```

Temperature = 1

```function Login() {
  return (
    <div className="min-h-screen flex items-center justify-center bg-gradient-to-br from-purple-500 to-blue-600">
      <form className="backdrop-blur-lg bg-white/20 shadow-2xl p-8 rounded-2xl w-[28rem] text-white">
        <h1 className="text-4xl font-bold mb-6 text-center">Login Portal</h1>
        <input className="w-full py-3 px-4 mb-5 rounded-xl bg-white/30 placeholder-white" placeholder="Email" />
        <input className="w-full py-3 px-4 mb-5 rounded-xl bg-white/30 placeholder-white" type="password" placeholder="Password" />
        <button className="w-full py-3 rounded-xl bg-black/30 hover:bg-black/50">Continue</button>
      </form>
    </div>
  );
}
```

### Exercise 3 — Context Window Awareness

- Create a 500+ word prompt:
  `I want you to act as a senior AI developer and generate a full responsive modern landing page using React and TailwindCSS. The page should include the following sections: Hero section, Features, Testimonials, Pricing, Footer, and a contact form. Make sure the design is clean, minimalistic, and mobile-first. The hero section should include a large headline with a compelling subtext and a call-to-action button. The features section should include at least four features, each with an icon, title, and short description. The testimonials section should include at least three testimonials with user names, profile pictures, and short quotes. The pricing section should have three pricing tiers: Basic, Pro, and Enterprise. Each tier should include its own feature list and a sign-up button. The footer should include navigation links, copyright text, and social media icons.`

  `In addition, structure your code in a clean component-based format. Each section should be placed in a separate file such as Hero.jsx, Features.jsx, etc. Use Tailwind's utility classes. Use proper typography, spacing, and layout best practices. The output should be clean and easy to understand. You may also generate sample text or placeholder text for the content. Continue generating code until the entire landing page is complete. Do not skip any section. Make sure each component contains responsive design behavior for tablet and mobile devices. If possible, suggest improvements to the design system and reusable UI components that can be extracted into a shared folder. Also list possible UI variants or improvements that can be made using Tailwind.`

- Test if the model handles it
  `Your prompt is extremely long → this is a perfect example for (Context Window + Chunking).`

`If I generate the entire landing page + separate components + improvements + design system in one single message, the output may exceed message limits.`

- Practice splitting long prompts into chunks
  `Chunk = small group of words used together with one meaning.`

## Your Prompt Converted Into Chunks

1. Role Chunk  
   Act as a senior AI developer.

2. Task Chunk  
   Generate a fully responsive modern landing page using React + TailwindCSS.

3. Required Sections Chunk  
   The landing page must include:

- Hero Section
- Features Section
- Testimonials Section
- Pricing Section
- Contact Form
- Footer

4. Design Requirements Chunk  
   Follow these design rules:

- Clean and minimalistic
- Mobile-first design
- Proper spacing, typography, and layout
- Tailwind utility classes only

5. Hero Section Chunk  
   Hero must contain:

- Large headline
- Compelling sub-text
- Primary call-to-action button

6. Features Section Chunk  
   Include four features:

- Each has an icon
- Title
- Short description

7. Testimonials Section Chunk  
   Include at least 3 testimonials:

- User name
- Profile picture
- Short quote

8. Pricing Section Chunk  
   Create 3 pricing tiers:

- Basic
- Pro
- Enterprise

Each tier contains:

- Feature list
- Sign-up button

9. Footer Section Chunk  
   Footer must include:

- Navigation links
- Social media icons
- Copyright text

10. Component Structure Chunk  
    Each section must be a separate React component:

- Hero.jsx
- Features.jsx
- Testimonials.jsx
- Pricing.jsx
- Contact.jsx
- Footer.jsx

11. Code Cleanliness Chunk  
    Use a clean component-based structure.
    Use placeholder/sample text where needed.
    Ensure full responsiveness for mobile and tablet.

12. Design System Suggestions Chunk  
    Suggest improvements for:

- Design system
- Reusable UI components
- Shared folder structure
- UI variants using Tailwind utilities

---

## Key Takeaways

1. Tokens control cost, length, and clarity
2. Model selection is task-specific
3. Temperature balances creativity vs. accuracy
4. Context window determines how much AI can remember
5. Proper use = clean, accurate, reliable prompts
