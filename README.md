# TaskFlow - AI-Powered Todo App

**Name:** [YOUR NAME]  
**UMID:** [YOUR UMID]

---

## Feature Added: AI-Powered Task Suggestions

When adding a new todo, clicking the **Suggest** button uses the Gemini AI model to generate 3–5 actionable subtasks or next steps for completing that task. Each suggestion appears as a clickable chip below the input row — click any chip to instantly add it as a todo item with automatic AI categorization.

---

## How to Install and Run

### Prerequisites
- Python 3.10+
- Node.js 18+
- A free Google Gemini API key from [aistudio.google.com/apikey](https://aistudio.google.com/apikey)

### Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/giparraguirre/Coding-Warmup-Extra-Credit.git
   cd Coding-Warmup-Extra-Credit
   ```

2. **Install Jac**
   ```bash
   pip install jaseci
   ```

3. **Set your API key** (in the same terminal you will run the app)
   ```bash
   export GOOGLE_API_KEY="your-google-api-key-here"
   ```

4. **Start the app**
   ```bash
   jac start main.jac
   ```

5. **Open your browser** and navigate to [http://localhost:8000](http://localhost:8000)

6. **Create an account** using the signup form, then start adding todos.

---

## How the Feature Works

When a user types a todo title and clicks **Suggest**, the frontend spawns the `GetSuggestions` walker on the backend. This walker calls `suggest_subtasks()` — a `by llm()` function that uses the Gemini AI model to generate 3–5 short, actionable subtasks for the given title. The suggestions are returned to the frontend and displayed as clickable purple chips below the input. Clicking a chip adds it as a full todo (with AI auto-categorization) and removes it from the suggestion list.

### Relevant Code Locations

| File | What it contains |
|------|-----------------|
| `main.jac` | `suggest_subtasks()` — the `by llm()` AI function; `GetSuggestions` walker |
| `frontend.cl.jac` | Suggest button UI, suggestion chips display, `suggestions` and `suggestionsLoading` state |
| `frontend.impl.jac` | `getSuggestions` and `addSuggestion` implementations that call the backend |
| `styles.css` | `.btn-suggest`, `.suggestion-chip`, `.suggestions-container` styles |
