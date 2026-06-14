# NewsCrawl

# Autonomous Macro-Finance & Tech Intelligence Pipeline

An automated, framework-free data engineering pipeline that ingests raw macroeconomic and technological syndication feeds, orchestrates them through an array sanitation layer, normalizes the payloads using Generative AI semantic analysis, and delivers high-density, scannable terminal-style intelligence dashboards directly to Discord.

---

## 📋 System Summary

This project removes the manual overhead of monitoring global tech shifts and market updates. Built completely on a native web stack without heavy third-party runtime frameworks, the architecture utilizes serverless micro-orchestration to fetch, clean, categorize, and summarize complex unstructured news data on a scheduled cron routine. The final intelligence output is structurally optimized for mobile and desktop readability using advanced Markdown layout layers.

---

## 🚀 Key Features

* **Multi-Source Ingestion Grid:** Parallel streaming from high-signal syndication nodes including Hacker News, TechCrunch, and Yahoo Finance Commodities feeds.
* **Deterministic Quota Enforcement:** A low-overhead array processor that enforces a strict ceiling of the top 5 articles per platform to eliminate information fatigue.
* **Semantic Taxonomy Router:** Integrates Gemini LLM via targeted system prompts to map unstructured data streams into distinct analytical buckets (*Artificial Intelligence*, *Cybersecurity*, *Global Macro & Commodities*).
* **Automated Data Normalization:** Standardizes multi-source string formats, stripping HTML fragments, resolving XML entity bloating, and escaping problematic symbols natively.
* **High-Density Discord Interface:** Transforms plain text walls into an interactive dashboard using native Markdown tricks like visual anchors (`###`), metadata badges (`` ` ``), and subtext strings (`-#`).

---

## 🛠️ Technical Specifications & Architecture

### Core Engineering Stack
* **Orchestration Engine:** n8n (Self-Hosted / Cloud Ecosystem)
* **Processing Environment:** Node.js Runtime Environment
* **Data Transformation Layer:** Vanilla JavaScript (ES6+)
* **Inference Layer:** Gemini Pro Flash API Model
* **Notification Terminal:** Discord Webhooks API Layer

### System Data Pipeline Flow
[ Ingestion Grid: RSS ] ──► [ Gateway Merge Node ]
│
▼
[ JS Data Sanitation ] (Clamps to Top 5 / Source)
│
▼
[ Gemini Inference ] (Applies Taxonomy & Prompts)
│
▼
[ Discord Notification ] (Delivers Scannable UI)

## 💻 Code Architecture Highlights

### Array Isolation & Sanitation Layer
The system drops external frame libraries, utilizing a raw iterative loop to clean string tables, dynamically check origins by inspecting destination strings, and enforce explicit payload quotas:

```javascript
// Data filtering logic from the primary data cleaning step
let hnCount = 0, tcCount = 0, yahooCount = 0, displayCount = 1;

for (const item of articles) {
    let link = item.json.link || "";
    
    // Enforce high-signal volume restrictions per domain
    if (link.includes("ycombinator.com") && hnCount++ >= 5) continue;
    if (link.includes("techcrunch.com") && tcCount++ >= 5) continue;
    if (link.includes("yahoo.com")      && yahooCount++ >= 5) continue;

    // String normalization and entity scrubbing
    let cleanTitle = item.json.title.trim()
        .replace(/&amp;/g, '&')
        .replace(/&quot;/g, '"')
        .replace(/&#x27;/g, "'");
    
    // Builds consolidated context block for the downstream LLM...
}
###Prompt Engineering Layer
The backend utilizes a strict, zero-filler System Prompt that forces the LLM to output consistent metadata blocks without conversational padding:
