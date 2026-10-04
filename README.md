# 🥗 PlatePal: AllergySafe Chef
### *An Open-Source AI Kitchen Companion Built for a Friend*

![PlatePal Banner](assets/cover.jpg)

[![Hacktoberfest 2026](https://img.shields.io/badge/Hacktoberfest-2026-blueviolet?style=for-the-badge&logo=hacktoberfest)](https://hacktoberfest.com/)
[![Powered by Gemma 2](https://img.shields.io/badge/Model-Google%20Gemma%202-emerald?style=for-the-badge&logo=google)](https://ai.google.dev/gemma)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)

> **Submission for Hacktoberfest Weekend Challenge: Build for a Friend**  
> **Categories:** Overall Grand Prize & Best Use of Google Gemma ($200)

---

## 📖 The Story: Why We Built This

Living with severe food allergies isn't just an inconvenience — it's an everyday minefield. 

This project was built for my roommate and close friend, **Alex**. Alex lives with **Celiac Disease** (strict autoimmune gluten intolerance) and severe **tree nut and peanut allergies**. Cooking together in a shared university apartment was always nerve-wracking:
- **Hidden Triggers:** Commercial food labels often disguise allergens under obscure chemical names (e.g. *hydrolyzed wheat protein*, *maltodextrin*, *arachis oil*, *casein*).
- **Cross-Contamination Anxiety:** Shared toasters, wooden cutting boards, and condiment jars risk microscopic cross-contact.
- **The "Boring Food" Fatigue:** Overwhelmed by restrictive diets, Alex often resorted to the same 3 bland meals.

**PlatePal** is an empathetic open-source AI agent powered by **Google Gemma 2** designed to remove food anxiety from the kitchen, audit ingredients for hidden traps, invent gourmet allergen-free recipes from random pantry items, and guide roommates on clean kitchen hygiene.

---

## ✨ Features

- 🔍 **Allergen & Hidden Trigger Scanner:** Paste any ingredient list, food package label, or restaurant menu. Gemma 2 performs a clinical food-safety audit, identifying both obvious and sneaky derivative allergens with an instant safety rating (`SAFE`, `CAUTION`, `DANGER`).
- 🔄 **Intelligent Safe Substitutions:** Need to replace soy sauce, wheat flour, heavy cream, or eggs? Get 1:1 culinary ratios, texture balancing tips, and prep guidance.
- 🍲 **Pantry-to-Plate Recipe Generator:** Enter whatever ingredients are sitting in your fridge, and Gemma 2 invents an allergen-certified gourmet meal tailored to your friend's profile.
- 🛡️ **Roommate Kitchen Hygiene & Cross-Contact Guide:** Actionable safety protocols for shared dorms/apartments (toaster safety, porous cookware warnings, condiment squeeze bottle rules).
- 🖨️ **Printable Kitchen Recipe Cards:** One-click print-optimized recipe sheets for hands-free cooking in the kitchen.

---

## 🧠 Why Open-Source AI (Google Gemma) Matters

For an application handling intimate personal health conditions and daily nutrition, closed proprietary AI APIs fall short:

1. **🔒 Medical & Health Data Sovereignty:** Friends shouldn't have to surrender their medical diagnoses and chronic dietary constraints to closed cloud providers to be profiled by commercial advertisers. Gemma 2 can run 100% locally on the user's laptop.
2. **📶 Offline Kitchen Reliability:** Cooking often happens in cabins, dorms with spotty WiFi, or basement kitchens. Running Gemma 2 locally via Ollama ensures safety checks work with zero internet connection.
3. **💸 Zero Subscription Paywall:** A friend shouldn't need a $20/month AI subscription just to safely eat dinner. Gemma's open weights make safety accessible to any student or family for free forever.
4. **⚖️ Open Weight Inspectability:** Open weights allow community nutritionists and clinicians to inspect, benchmark, and fine-tune food safety reasoning models without hidden black-box drift.

---

## 🚀 Quick Start

### 1. Run Directly in Any Browser (Zero Setup)
No installation required! Simply open `index.html` in your favorite web browser or start a local server:

```bash
# Using Python
python -m http.server 3000

# Or using Node
npx serve .
```
Navigate to `http://localhost:3000`.

### 2. Connect to Local Gemma 2 via Ollama (Optional)
If you want to run Google's open-weight Gemma 2 model locally:

1. Install [Ollama](https://ollama.ai).
2. Pull and start Gemma 2:
   ```bash
   ollama run gemma2:2b
   ```
3. Set your CORS headers if needed:
   ```bash
   # Linux/macOS
   OLLAMA_ORIGINS="*" ollama serve
   # Windows (PowerShell)
   $env:OLLAMA_ORIGINS="*"; ollama serve
   ```
4. In PlatePal, click **⚙️ AI Settings** and choose **Local Ollama**.

---

## 🛠️ Tech Stack

- **AI Model:** Google Gemma 2 (`gemma2:2b` / `gemma2:9b` open weights)
- **Local AI Orchestration:** Ollama API & client-side grounding rules
- **Frontend:** Vanilla HTML5, Modern CSS Design System (Glassmorphism, Dark UI, Responsive Grid)
- **Deployment:** Render (`render.yaml` ready) & GitHub Pages compatible

---

## 🤝 Handing It Over to Alex (User Feedback)

> *"Before PlatePal, cooking in our shared apartment felt like playing Russian roulette with dinner. Having an assistant that immediately catches things like malt extract in sauces or tells my roommates why they can't use the same wooden spoon for their pasta has been a total game-changer. Plus, the coconut aminos skillet recipe was actually restaurant quality."*  
> — **Alex**, Roommate & Co-tester

---

## 📄 License

Distributed under the **MIT License**. See `LICENSE` for more information.
Part of **Hacktoberfest 2026**!
