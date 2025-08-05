# 🕰️ AI Timeline Generator SaaS

An AI-powered web app that lets users generate **interactive historical timelines** by simply describing what they want. Ideal for educators, students, journalists, content creators, and history enthusiasts.

---

## 🚀 Features

### 🔍 User Functionality
- Prompt-based timeline generation:  
  _e.g., "Show me key political events in Germany since 1945"_
- Interactive, scrollable timeline with:
  - Chronological events
  - Hover to view details
  - Shareable links
  - Export to PDF or CSV (Pro feature)
- Responsive, modern UI built with React
- Authentication (email or Google)
- Saved timelines dashboard

---

### 🧠 AI-Powered Timeline Generation

- Uses **OpenAI GPT-3.5** by default
- **GPT-4 available for Pro users**
- Structured output in JSON/Markdown for frontend rendering
- Intelligent summarization and date labeling of events

---

## 🏗️ Tech Stack

| Layer              | Tech Choice                          |
|--------------------|--------------------------------------|
| Frontend           | React + Tailwind CSS + TimelineJS    |
| Backend (API)      | Serverless (Vercel Functions or AWS Lambda) |
| AI Integration     | OpenAI GPT-3.5 & GPT-4                |
| Auth               | Supabase Auth / Clerk / Firebase     |
| Database           | Supabase / Firestore (for saved timelines) |
| Hosting            | Vercel / Netlify / Cloudflare Pages  |
| Payments           | Stripe                               |
| Caching (optional) | Redis or Supabase KV                 |

---

## 💰 Pricing Strategy

| Plan       | Price       | Features                                                   | AI Model  |
|------------|-------------|------------------------------------------------------------|-----------|
| Free       | $0          | 3 timelines/month, watermark, basic UI                     | GPT-3.5   |
| Starter    | $9/month    | 30 timelines/month, export to PDF, no watermark            | GPT-3.5   |
| Pro        | $29/month   | 100+ timelines/month, GPT-4, export options, sharing       | GPT-4     |
| Enterprise | Custom plan | Unlimited timelines, private deployment, custom branding   | GPT-4     |

🧠 *Note*: Rate limiting is abstracted through "timelines/month" instead of per-token usage to enhance user experience.

---

## 🌐 High Availability Architecture

This app is designed to stay online, even during backend outages.

### 🛡️ Strategy
- Primary backend: **Vercel serverless functions** or **FastAPI app**
- Fallback backend: **AWS Lambda function** (mirrors same functionality)
- Failover via:
  - **Cloudflare Workers** or
  - **API Gateway** with health checks + routing
- Stateless backend logic ensures easy fallback

### 🔁 Example Fallback Flow

