# 🤖 Shopify AI Product Concierge & Smart Finder (OS 2.0)

A native, zero-dependency natural-language shopping assistant section built for Shopify Online Store 2.0. Helps shoppers discover products using conversational queries and intent (budget, recipient, use-case).

---

## 🏗️ Architecture & Security

### Why Client-Side Theme Code Cannot Directly Hold AI API Keys
Shopify theme Liquid and JavaScript are completely exposed in the customer's browser. Hardcoding an OpenAI or Claude API key in a theme script allows anyone to extract the key via browser DevTools and misuse it.

### How This Section Operates:
1. **Default Mode (Zero Setup Cost):** The section routes customer queries through Shopify's native **Predictive Search API** (`/search/suggest.json`) using pre-selected intent chips and natural keywords. It delivers sub-second results with zero ongoing API costs.
2. **Production LLM Setup (Optional Proxy):** For true conversational LLM matching, the front-end fetch in this section is designed to point to a secure serverless edge worker (e.g., Cloudflare Workers or Vercel Edge Function). The worker securely holds the LLM API key, queries product embeddings via the Shopify Storefront API, and returns recommendations back to this UI container.

---

## 🚀 Key Features
- **Natural Language Discovery:** Pre-configured prompt chips and query inputs.
- **Zero Heavy Libraries:** Built entirely in Vanilla JavaScript and scoped CSS.
- **No Monthly App Subscriptions:** Replaces expensive third-party quiz apps.
- **Fully Customizable:** Adjust headings, colors, and prompt suggestions directly in the Theme Customizer.

---

## 🛠 Installation
1. Copy `sections/ai-product-concierge.liquid` into your theme's `/sections` folder.
2. In the Shopify Theme Editor, click **Add section** $\rightarrow$ select **AI Product Concierge**.
