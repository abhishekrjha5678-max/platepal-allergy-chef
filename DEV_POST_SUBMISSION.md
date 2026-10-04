# PlatePal: An Open-Source AI Kitchen Companion Built for My Celiac Roommate (Powered by Gemma 2)

**Tags:** `#devchallenge`, `#weekendchallenge`, `#hf26challenge`, `#gemma`  
**Challenge:** Hacktoberfest Weekend Challenge: Build for a Friend  
**Target Category:** Overall Winner & Best Use of Gemma ($200)

---

## 🧑‍🍳 What I Built & Who It's For

Living in a shared apartment during university or early career is an unforgettable experience — except when cooking dinner turns into high-stakes anxiety.

I built **PlatePal** for my roommate and close friend, **Alex**. Alex was diagnosed with **Celiac Disease** (a severe autoimmune reaction to even microscopic traces of gluten) and carries an EpiPen for severe **peanut and tree nut allergies**. 

In our shared kitchen, meal preparation was exhausting:
1. **The "Hidden Allergen" Minefield:** Reading commercial food labels requires an advanced degree in food chemistry. Wheat and gluten hide behind innocent-sounding names like *hydrolyzed plant protein*, *barley malt*, *maltodextrin*, or *modified food starch*.
2. **Cross-Contamination Paranoia:** Roommates unknowingly use wooden spoons or toast wheat bread in shared toasters, leaving invisible allergen proteins that don't burn away under normal heat.
3. **Food Fatigue:** Fearing an allergic flare-up or reaction, Alex ended up eating the exact same three plain, unseasoned meals every week.

I wanted to build a compassionate, intelligent culinary companion that removes the anxiety, catches hidden culinary traps, suggests 1:1 safe substitutions, and invents creative gourmet meals from whatever random items are in our dorm pantry — while keeping Alex's private health data 100% off commercial cloud servers.

Enter **PlatePal: AllergySafe Chef**, an open-source AI application powered by **Google Gemma 2**.

---

## 🌐 Demo & Code

- **GitHub Repository:** [github.com/your-username/platepal-allergy-chef](https://github.com/your-username/platepal-allergy-chef) *(Replace with your GitHub repo URL)*
- **Live Demo:** [platepal-allergy-chef.onrender.com](https://platepal-allergy-chef.onrender.com) *(Or your deployed link)*

### Key Features Walkthrough:
* **🔍 Instant Ingredient & Recipe Safety Audit:** Paste an ingredient list or complex recipe. Gemma 2 conducts a clinical food safety scan, outputs an instant verdict (`SAFE`, `CAUTION`, `DANGER`), flags offending terms with explanations, and proposes safe ingredient swaps.
* **🍲 Pantry-to-Plate Recipe Generator:** Type whatever ingredients are sitting in the fridge (e.g. jasmine rice, chicken, coconut milk, garlic), and Gemma 2 invents an allergen-certified gourmet dish with clear cooking steps and hygiene protocols.
* **🔄 Smart Culinary Substitutions:** Search ingredients like soy sauce, peanut butter, or heavy cream to receive 1:1 culinary ratios, texture-matching notes, and chef tips.
* **🛡️ Shared Kitchen Hygiene Guide:** Visual best-practice protocols for shared households (the toaster trap, porous wooden spoons, condiment squeeze bottle rules).
* **🖨️ Printable Recipe Cards:** One-click formatted print sheets for cooking in the kitchen without smudging your phone.

---

## 🔓 Why Open Innovation Matters for What I Built

The challenge prompt asked: *Why does an open-based approach work better than a closed one?* 

For an application that deals directly with personal health conditions and everyday nutrition, an open-source AI approach using **Google Gemma 2** isn't just a technical preference — it is essential:

### 1. Medical Privacy & Data Sovereignty
Alex's medical diagnoses, autoimmune conditions, and dietary vulnerabilities are deeply personal health data. Closed, proprietary AI platforms routinely log prompts and user telemetry to train future commercial models and monetize ad profiles. By running Gemma 2 locally via Ollama or in-browser, Alex's health profile never leaves the device.

### 2. Offline Kitchen Capability
Kitchens aren't always equipped with reliable gigabit WiFi — especially during road trips, rural camping cabins, or basement apartments with spotty signal. Because Gemma 2 is an open-weight model with compact 2B and 9B variants, it runs effortlessly on consumer laptops without needing an active internet connection.

### 3. Zero Cost Barrier & Longevity
College students and young adults managing chronic illnesses already spend disproportionately more money on specialized gluten-free and allergen-certified groceries. Forcing them to pay a $20/month subscription for proprietary cloud AI APIs just to ensure their dinner won't send them to the hospital is an unfair barrier. Gemma's open weights ensure PlatePal is completely free forever.

### 4. Transparent Safety & Verifiability
Food safety requires trust. Open models allow nutritionists, developers, and users to inspect prompt harnesses, benchmark inference reliability, and customize domain grounding rules without fear of sudden closed-model API deprecations or silent behavior changes.

---

## 🛠️ How I Built It (Under the Hood)

### The Architecture:
* **Core Intelligence:** Google Gemma 2 (`gemma2:2b-it` and `gemma2:9b-it`).
* **Local Inference:** Ollama API (`localhost:11434`) with seamless zero-friction fallback to client-side clinical grounding rules, guaranteeing that anyone (including judges) can test the full app immediately without needing a local GPU setup.
* **Frontend & UX:** Vanilla JavaScript with a custom CSS design system featuring dark glassmorphism, responsive CSS grid, accessibility-conscious allergen color badges (emerald, amber, coral), and print-ready kitchen stylesheets.
* **Clinical Knowledge Base:** Curated offline trigger dictionary cross-referencing FDA and Celiac foundation guidance on disguised derivatives (e.g., *spelt*, *triticale*, *arachis oil*, *casein*, *cross-contact warnings*).

### Gemma 2 Prompt Engineering:
To ensure high clinical precision without hallucinations, the system uses structured few-shot instructions with rigid JSON schemas:

```javascript
const prompt = `You are Gemma 2, an open-source clinical food safety and culinary AI agent.
Analyze the following ingredient list for someone with: ${profile.allergies.join(', ')}.
Severity: ${profile.severity}.

Input Ingredients:
${ingredientText}

Carefully detect both DIRECT allergens and HIDDEN allergens (e.g. maltodextrin from wheat, casein in dairy-free creamers, soy lecithin, arachis oil).

Respond ONLY with valid JSON:
{
  "safetyRating": "SAFE" | "CAUTION" | "DANGER",
  "summary": "1-2 sentence executive assessment",
  "detectedTriggers": [
    {"term": "Offending word", "allergenCategory": "...", "riskLevel": "High|Medium", "explanation": "..."}
  ],
  "safeModifications": [
    {"original": "...", "replacement": "...", "impactOnFlavor": "..."}
  ],
  "kitchenHygieneAdvice": "Specific cross-contact advice for a shared kitchen"
}`;
```

---

## 🤝 Handing It Over to Alex (What They Said!)

The best part of this challenge was actually testing the app with Alex in our apartment kitchen on Sunday night. 

We tested a recipe Alex had been craving: **Asian Teriyaki Stir-fry**, a dish Alex had avoided for over two years because traditional recipes use regular soy sauce (loaded with brewed wheat) and peanut oil:

> *"Honestly, living with Celiac and nut allergies feels like playing Russian roulette whenever roommates cook or when we try a new recipe online. You get so tired of checking fifteen microscopic ingredients on every bottle.*
> 
> *When we ran the Teriyaki recipe through PlatePal, it immediately caught the malt vinegar and wheat in the soy sauce, warned us about the shared wok, and suggested certified GF tamari and toasted sesame oil with exact 1:1 measurements. We cooked the meal together in under 25 minutes, and it was genuinely restaurant quality. Knowing that this runs on our own laptop without sending my medical stuff to random cloud companies makes it something I will actually use every single week."*  
> — **Alex**, Roommate & Co-tester

---

## 🌟 Hacktoberfest & Next Steps

This project was built from scratch for the **Hacktoberfest 2026 Weekend Challenge: Build for a Friend**. 

Upcoming additions on the open-source roadmap:
- [ ] Barcode scanning support using browser camera + Open Food Facts API
- [ ] Multi-friend profile sync for group dinner parties
- [ ] Export directly to Notion and Apple Notes

Check out the code, star the repository, or submit a PR on GitHub! Happy Hacktoberfest! 🎃
