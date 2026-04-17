# GitProfolio

Transform your GitHub profile into a structured, enriched JSON portfolio.

GitProfolio extracts data from a GitHub profile, analyzes repositories, and outputs a clean JSON representation that can be used for portfolios, resumes, dashboards, or developer tools.

---

## ✨ Features

- 🔍 Fetch GitHub profile & repositories
- 🧠 Analyze repositories using:
  - README parsing
  - Tech stack detection
  - Live demo link extraction
- 📊 Score and rank projects using heuristics
- 🧹 Clean and normalize repository descriptions
- 🏆 Identify top projects automatically
- 🤖 AI-powered insights:
  - Visibility improvement tips
  - Project ideas
  - Metadata suggestions
  - Contribution targets
- 📦 Export structured JSON (copy/download)

---

## 🧱 Tech Stack

- **Framework:** Astro
- **Language:** TypeScript
- **APIs:**
  - GitHub REST API
  - OpenRouter (LLM integration)
- **Styling:** Custom CSS
- **Architecture:** Server-first API routes + component-based UI

---

## 📁 Project Structure

```

src/
components/ # UI components (ProfileCard, RepoCard, etc.)
layouts/ # Base layout
lib/ # Core logic (fetching, analysis, formatting)
pages/
api/ # Backend endpoints (scrape, ai-insights)
index.astro # Main UI
styles/ # Global styles

````

---

## ⚙️ How It Works

### 1. Data Fetching
- Fetches profile and repositories from GitHub API
- Handles pagination and rate limits

### 2. Repository Analysis
- Extracts:
  - Tech stack (languages + README keywords)
  - Live links (Vercel, Netlify, etc.)
  - README summaries & features

### 3. Enrichment Engine
- Scores repositories using:
  - Stars, forks
  - Recency
  - Description quality
- Penalizes forks and archived repos
- Selects top projects

### 4. Output Formatting
- Produces a structured JSON:
```json
{
  "profile": {},
  "repositories": [],
  "top_projects": []
}
````

### 5. AI Insights (Optional)

* Uses LLM to generate:

  * Visibility tips
  * Project ideas
  * Metadata improvements
  * Contribution suggestions

---

## 📡 API Endpoints

### `/api/scrape`

Generate portfolio JSON from GitHub username

**Request:**

```json
{
  "github_username": "username"
}
```

---

### `/api/ai-insights`

Generate AI insights based on extracted data

**Request:**

```json
{
  "profile": {},
  "repositories": []
}
```

---

## 🚀 Getting Started

### 1. Clone the repo

```bash
git clone https://github.com/yourusername/gitprofolio.git
cd gitprofolio
```

### 2. Install dependencies

```bash
npm install
```

### 3. Set environment variables

```env
GITHUB_TOKEN=your_github_token
OPENROUTER_API_KEY=your_openrouter_key
```

### 4. Run the app

```bash
npm run dev
```

---

## 🔑 Environment Variables

| Variable             | Description                      |
| -------------------- | -------------------------------- |
| `GITHUB_TOKEN`       | Increases GitHub API rate limits |
| `OPENROUTER_API_KEY` | Enables AI insights              |
| `OPENROUTER_MODEL`   | Optional custom LLM model        |

---

## 📊 Scoring Heuristic

```
score = stars×2 + forks×1.5 + recency + description_quality
```

Adjustments:

* Forked repos → penalized
* Archived repos → penalized

---

## 🎯 Use Cases

* Developer portfolio generation
* Resume automation
* GitHub analytics dashboards
* AI-based developer tooling
* Personal branding tools

---

## 📄 License

MIT License

---

## 💡 Inspiration

GitProfolio is built to bridge the gap between raw GitHub data and meaningful developer portfolios — turning scattered repositories into structured, actionable insights.
