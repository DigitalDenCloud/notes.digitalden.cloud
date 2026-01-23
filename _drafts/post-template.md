# DigitalDen Post Template

This template captures your writing style, structure, and preferred use of Chirpy features. Use it as a reference when creating new posts.

---

## Front Matter Template

```yaml
---
title: "Post Title"
date: YYYY-MM-DD HH:MM:SS +/-TTTT
categories: [Primary Category, Secondary Category]
tags: [tag1, tag2, tag3, tag4]
mermaid: true                    # Include if using diagrams
math: true                       # Include if using equations
description: "A clear 1-2 sentence description. State what it is and set expectations."
image: 
  path: /assets/img/headers/header-image.webp
  lqip: data:image/webp;base64,YOUR_BASE64_STRING
---
```

### Front Matter Notes

**Title conventions:**
- Use sentence case
- Keep concise and descriptive
- Avoid em dashes in titles (use them rarely, if at all)
- Simple and direct: `"Potato Bun Journal"` not `"Potato Bun Journal — First Attempt"`

**Categories:**

Use one or two categories. The first describes the topic, the second adds specificity.

| First | Second | When to use | Example post |
|-------|--------|-------------|--------------|
| Nutrition | Recipe | Cooking, meals, food preparation | Potato buns, pan-seared chicken |
| Nutrition | Research | Food science, ingredient analysis, dietary changes | Supermarket bread |
| Training | Log | Snapshots, session records, weekly journals | Strength Snapshot |
| Training | Study | Tracking experiments, self-studies | Creatine study |
| Training | Programme | Training structure, periodisation | — |
| Video | Settings | Camera configuration, technical parameters | Low light gym filming |
| Video | Workflow | Editing process, software setup | After Effects workflow |
| Video | Gear | Equipment reviews, comparisons | — |
| Gaming | Journal | Personal reflections, nostalgia, experiences | Metal Gear Solid 3 |
| AWS | Generative AI | Bedrock, AI/ML projects | Building My First Bedrock Agent |
| AWS | Serverless | Lambda, API Gateway, Step Functions | — |

Single categories are fine when the second adds nothing useful.

**Tags:**
- Mix of broad and specific
- Include tools, technologies, and key concepts

| Category | Example tags |
|----------|--------------|
| Training | `Strength Training`, `Training Log`, `Personal Record`, `Recovery`, `Creatine` |
| Nutrition | `Meal Prep`, `Recipe`, `High Protein`, `Sourdough`, `Ultra-Processed Food` |
| Video | `Sony A6700`, `After Effects`, `Low Light`, `Gym Filming`, `Vertical Video` |
| Gaming | `PlayStation`, `Metal Gear Solid` |
| AWS | `Amazon Bedrock`, `Lambda`, `Serverless`, `Generative AI` |

**Description:**
- 1-2 sentences maximum
- State what it is directly
- Often includes what the post *is not* as much as what it is

---

## Writing Style Guide

### Core Principles

The writing should sound like an experienced practitioner documenting their own process, not trying to persuade or perform.

- Explain what happened, why it mattered, and what changed
- Use plain, precise language
- Maintain explicit cause-and-effect reasoning
- Avoid hype, motivation, or storytelling language
- Focus on observations, actions, and outcomes
- Keep the tone calm, reflective, and grounded

### Voice and Tone

**First person, direct:**
- "I chose..." not "X was chosen..."
- "This did not work" not "This approach proved unsuccessful"
- "The meat and method are where I want them" not "The meat and method are now consistent"

**Casual but precise:**
- Write like you are explaining to a friend, not writing a report
- Include personal touches where they add value
- Be specific about quantities, settings, and values

**Honest about uncertainty:**
- "I do not know if this will work"
- "Batch 2 will tell me if it actually works"
- "The kit lens limits low light performance"

**Show your preferences and opinions:**
- "This one tastes the best"
- "Standard burger buns are fine but nothing special"
- "I love this pan. I am always telling my friends about it."

### Words and Phrases to Avoid

| Avoid | Use instead |
|-------|-------------|
| "The goal is..." | State the action directly, or "I wanted to..." |
| "Baseline" (outside AWS context) | "Starting point", "first batch", "where I started" |
| "Remaining variable" | "The part I have not figured out yet" |
| "Was chosen" / "Was selected" | "I chose" / "I picked" |
| "Consistent" (for quality) | "Tastes the best", "works well", "reliable" |
| "Optimal" / "Optimise" | "Better", "improve", "what works" |
| Em dashes (—) | Full stops or commas. Use em dashes rarely. |

### Sentence Structure

**Short paragraphs:** One idea per paragraph. Move on when the point is made.

**Let sentences flow naturally:**
Instead of choppy: "Fresh ones are not available in the UK. The only options are frozen imports."
Write: "Fresh ones are not available in the UK and the only options are frozen imports."

**Sentence fragments for emphasis (use sparingly):**
- "That's the meal."
- "Worth trying."
- "Seven days, seven vegetables."

**Lists converted to prose where possible:**
Instead of bullet points, use natural language: "My sites include digitalden.cloud for the main homepage, docs.digitalden.cloud for documentation, and gallery.digitalden.cloud for photography."

### Showing Your Process

**Include the human details:**
- "There is something satisfying about watching him pull at the ribeye steak and then feed it through the mincer."
- "I was short on time at points during this batch, which affected some decisions."
- "After watching a few YouTube videos, I realised I could make these myself."
- "That feeling of knowing you were about to sink into something for days."

**Name your sources and preferences:**
- Link to specific products you use
- Shout out shops and suppliers by name
- Explain why you chose them

**Show what you experimented with:**
- "I experimented with 100g patties but they were difficult to smash from frozen. 60g is more sensible."
- "Aperture priority is the go-to mode for video in mixed lighting. In a gym, it doesn't work."

**Be specific about quantities and values:**
- "Beat in 20g butter and 30g warm milk"
- "Baked for 16 minutes until golden"
- "Set manual white balance to 3000K"

### Cause and Effect

Always make the reasoning explicit:

**Good:**
> "The flavour really comes through on the smash, and because I only season with salt and pepper, you can tell when the beef is good."

**Good:**
> "Aperture priority mode with auto ISO causes exposure instability in gyms with uneven lighting. As the subject moves through the frame, the camera continuously adjusts ISO, resulting in visible brightness fluctuations during recording."

**Good:**
> "Warm potato absorbs fat and liquid better than cold dough does. When you mash butter and milk into hot potato, the starches swell and trap the fat."

**Avoid:**
> "This produces better results." (Why? How?)

### Connecting to Other Content

When relevant, link to related posts:
- "I already [avoid supermarket bread](/posts/why-i-dont-eat-supermarket-bread/){:target="_blank"} because of preservatives and additives."
- "You can read how I make the smash burger in detail [here](/posts/smash-burger/){:target="_blank"}."

---

## Post Structure Patterns

### Type 1: AWS Project Posts

*Example: "Building My First Bedrock Agent"*
*Categories: `[AWS, Generative AI]`*

Best for: AWS projects, technical builds, learning journeys

```markdown
---
[front matter]
---

Try the agent at [digitalden.cloud](https://digitalden.cloud){:target="_blank"}

<!--more-->

## Chapter 1: The Starting Point

[Context and what prompted this]

---

## Chapter 2: The Idea  

[What you decided to build and why]

---

[Continue with chapters as needed...]

---

## Future Vision

[What comes next]

---

[Call to action with link]
```

---

### Type 2: Living Document / Iterative Posts

*Example: "The Potato Bun", "A 12 Week Creatine Study"*
*Categories: `[Nutrition, Recipe]` or `[Training, Study]`*

Best for: Ongoing experiments, iterative recipes, progress tracking

```markdown
---
[front matter]
---

## Introduction

[What this is, why you are doing it, what to expect]

> **What this post covers**  
> [Scope and structure]
{: .prompt-info }

---

## Context

[Background information the reader needs]

You can read more about [related topic] [here](/posts/related-post/){:target="_blank"}.

---

## Batch 1

[Note any constraints: "I was short on time at points during this batch"]

### Ingredients

| Ingredient | Brand / Source | Amount |
|------------|----------------|--------|
| Flour | [M&S Canadian Very Strong](https://link.com){:target="_blank"} | 560g |
| Butter | [Kerrygold Unsalted](https://link.com){:target="_blank"} | 56g |

[Brief note on why you chose these]

### Nutrition per Serving

| Nutrient | Amount |
|----------|--------|
| Calories | ~X kcal |
| Protein | ~Xg |
| Carbohydrates | ~Xg |
| Fat | ~Xg |

---

### Method

#### Step 1: [Action]

[Instructions with specific values]

#### Step 2: [Action]

[Instructions]

> **[Term or technique]**  
> [Explanation]
{: .prompt-info }

---

### Observations

| Attribute | Observation |
|-----------|-------------|
| Texture | Soft, slightly dense |
| Structure | Strong, held up well |
| Size | 90g felt small |

[Brief interpretation]

---

### Notes for Next Batch

| Area | Adjustment |
|------|------------|
| Size | Increase to 105–110g |
| Potato | Try 150g mash for softer crumb |

[Explanation of reasoning]

---

## Summary

| Component | Specification |
|-----------|---------------|
| ... | ... |

---

*Documented [date]. More batches to follow.*
```

---

### Type 3: Technical Reference Posts

*Example: "Low Light Gym Filming", "After Effects Workflow"*
*Categories: `[Video, Settings]` or `[Video, Workflow]`*

Best for: Camera settings, software configuration, technical workflows

```markdown
---
[front matter]
---

## Overview

[What this is, the problem it solves, scope]

> **Scope**  
> [What this guide covers and what it does not]
{: .prompt-info }

---

## Equipment Reference

### [Component Category]

| Component | Specification |
|-----------|---------------|
| Camera body | Sony A6700 (APS-C, 26MP) |
| Lens | Sony 18-135mm f/3.5-4.5 OSS |

### [Settings Category]

| Setting | Value |
|---------|-------|
| Resolution | 4K (3840 × 2160) |
| Frame rate | 25fps |

### Why These Settings

**25fps** — Matches PAL standard for the UK/Europe. Also determines shutter speed baseline via the 180-degree rule.

**Cinetone** — Produces natural skin tones straight out of camera with minimal grading.

---

## [Core Technical Section]

### The Problem

[What goes wrong and why]

> **Symptom**  
> [What you see when this happens]
{: .prompt-warning }

### The Solution

[How to fix it with specific values]

| Parameter | Recommended Value | Notes |
|-----------|-------------------|-------|
| Mode | Manual (M) | Full control |
| Aperture | f/4.0 | Widest available |
| ISO | 640-1000 | Lock manually |

> **Procedure**  
> 1. Set manual exposure values  
> 2. Enable zebras at 100  
> 3. Frame the shot  
> 4. Adjust ISO until zebras disappear  
> 5. Lock settings and begin recording
{: .prompt-tip }

---

## Common Issues and Solutions

### Issue 1: [Problem Name]

**Symptom:** [What you see]  
**Cause:** [Why it happens]  
**Solution:** [How to fix it]

---

## Quick Reference Card

### Recommended Settings

| Parameter | Value |
|-----------|-------|
| Mode | Manual |
| Aperture | f/4.0 |
| Shutter | 1/25 |
| ISO | 640-1000 |

### Pre-[Task] Checklist

- [ ] [Check item]
- [ ] [Check item]
- [ ] [Check item]

---

*Technical reference document. Updated as new learnings are validated.*
```

---

### Type 4: Practical Recipe Posts

*Example: "Pan-Seared Chicken with Sautéed Vegetables"*
*Categories: `[Nutrition, Recipe]`*

Best for: Meals, recipes, routines with variations

```markdown
---
[front matter]
---

## Overview

[What this is in plain terms]

> **Good for**  
> [Who would find this useful, when to use it]
{: .prompt-info }

---

## Equipment

| Component | Specification |
|-----------|---------------|
| Pan | Stainless steel |
| Oil | Refined avocado oil (high smoke point) |

---

## Base Ingredients (Every Day)

| Ingredient | Amount | Notes |
|------------|--------|-------|
| Chicken breast | ~180–200g raw | Salt and pepper only |
| Butter | ~10g | Added in final 30 seconds |

[Note about what varies]

---

## Cooking Method

### Step 1: Prep

[Preparation instructions]

### Step 2: [Main Process]

[Core technique with specific values]

> **Why [specific choice]**  
> [Explanation of technique]
{: .prompt-info }

### Step 3: Finish

[Final steps]

---

## Dial Reference

| Phase | Setting | Duration |
|-------|---------|----------|
| Preheat | 5 | 2–3 min |
| Sear | 4 | 4 min + 3–4 min |
| Sauté | 3–4 | 3–5 min |

---

## The [X]-Day Rotation

[Why rotation matters]

### Day 1 — [Variation Name]

| Item | Amount | Cooking |
|------|--------|---------|
| Spinach | 70g | 45–60 sec at dial 3 |

**Key nutrients:** Iron, folate, magnesium, potassium.

**Nutritional function:** [Why this matters]

**Nutrition (full meal)**

| Macro | Value |
|-------|-------|
| Protein | ~46g |
| Carbohydrates | ~4g |
| Fat | ~24g |
| Calories | ~410 kcal |

---

## Quick Reference

| Day | Variation | Key Benefit |
|-----|-----------|-------------|
| 1 | Spinach | Iron, magnesium |
| 2 | Kale | Vitamin K, calcium |

---

## Notes

**[Term]:** [Definition or explanation]

---

## Summary

| Component | Specification |
|-----------|---------------|
| Protein source | 1 chicken breast (~45–47g protein) |
| Vegetable side | 70–100g, rotated daily |

[One-line summary]

---

*Documented [date].*
```

---

### Type 5: Research-Backed Personal Change

*Example: "Why I Don't Eat Supermarket Bread"*
*Categories: `[Nutrition, Research]`*

Best for: Explaining a decision with research context

```markdown
---
[front matter]
---

## Introduction

[What you changed and when]

[Brief context on what prompted the change]

> **What this post covers**  
> [Scope]
{: .prompt-info }

---

## Context

### [Background Topic]

[Research or data that informed your decision]

### [Specific Example]

[Your personal experience with the thing you changed]

---

## [The Problem / What You Found]

[Specific details, ingredient lists, data]

| Item | Detail | Concern |
|------|--------|---------|
| ... | ... | ... |

[Your interpretation, with cause-and-effect reasoning]

> **The question I started asking**  
> [The key question that changed your thinking]
{: .prompt-warning }

---

## What Changed for Me

### [Measurable Outcome]

| Marker | Before | After | Interpretation |
|--------|--------|-------|----------------|
| CRP | 2.8 | 1.2 | Reduced inflammation |

### [Behaviour Change]

[How you approach things now]

---

## [Your Current Approach]

### Criteria

[What you look for now — checklist format works well]

- [ ] Four to six ingredients
- [ ] No preservatives
- [ ] [Other criteria]

### [Specific Choices]

[Products, sources, suppliers with links]

---

## Summary

| Component | My Approach |
|-----------|-------------|
| [Thing] | [What you do now] |

[One-line summary of the outcome]

---

*Documented [date].*
```

---

### Type 6: Training Log / Snapshot

*Example: "Strength Snapshot — January 2026"*
*Categories: `[Training, Log]`*

Best for: Point-in-time records, training documentation

```markdown
---
[front matter]
---

## Introduction

[What this is and why you are writing it now]

[Set expectations: "This isn't a transformation story. It's a physical inventory."]

---

## The Numbers

### [Category]

| Item | Value | Notes |
|------|-------|-------|
| ... | ... | ... |

---

## [Daily/Weekly Journal if applicable]

### [Day/Entry]

**Context:** [Sleep, nutrition, conditions]

**What happened:** [Observations]

**How it felt:** [Subjective reflection, 2-3 sentences]

---

## What Affected [Outcome]

| Factor | Observation | Impact |
|--------|-------------|--------|
| ... | ... | ... |

---

## Summary

| Item | Value |
|------|-------|
| ... | ... |

---

*Documented [date]. For the record.*
```

---

### Type 7: Personal Journal / Reflection

*Example: "Metal Gear Solid 3 — Snake Eater Remastered"*
*Categories: `[Gaming, Journal]`*

Best for: Personal reflections, nostalgia, experiences

```markdown
---
[front matter]
---

[Optional: embedded media like Spotify]

## [Opening Section Title]

[Personal narrative — what happened, what it meant]

[Include specific details: dates, prices, places, feelings]

---

## [Next Section]

[Continue the reflection]

---

*[Optional closing line]*
```

**Characteristics:**
- More narrative than other post types
- Specific personal details: "£40", "15 year old kid", "Saturday afternoon"
- Emotional honesty: "That same childhood feeling. The one where you want to get home and disappear into a game."
- No tables or technical structure unless relevant
- Journal as second category is appropriate here

---

## Chirpy Features Usage

### Prompts

**Tip (`.prompt-tip`):** Procedures, recommendations

```markdown
> **Procedure**  
> 1. Set manual exposure values  
> 2. Enable zebras at 100  
> 3. Frame the shot
{: .prompt-tip }
```

**Info (`.prompt-info`):** Context, scope, explanations, rationale

```markdown
> **What this post covers**  
> The smash burger context, first batch method, observations, and notes for the next iteration.
{: .prompt-info }
```

```markdown
> **Why refined avocado oil**  
> High smoke point (~250–270°C), neutral flavour, stable at searing temperatures.
{: .prompt-info }
```

```markdown
> **Scope**  
> This guide focuses on solo documentation filming with a fixed tripod position.
{: .prompt-info }
```

**Warning (`.prompt-warning`):** Symptoms, pitfalls, key questions

```markdown
> **Symptom**  
> Footage alternates between bright and dark within a single take.
{: .prompt-warning }
```

```markdown
> **The question I started asking**  
> If real bread needs four ingredients and goes stale in three days, why am I eating something with ten ingredients that lasts a week?
{: .prompt-warning }
```

**Danger (`.prompt-danger`):** Critical errors (use rarely)

---

### Tables

**Equipment/settings:**

```markdown
| Component | Specification |
|-----------|---------------|
| Camera body | Sony A6700 |
| Lens | Sony 18-135mm f/3.5-4.5 |
```

**Ingredients with links:**

```markdown
| Ingredient | Brand / Source | Amount |
|------------|----------------|--------|
| Flour | [M&S Canadian Very Strong](https://link.com){:target="_blank"} | 560g |
```

**Parameters with notes:**

```markdown
| Parameter | Value | Notes |
|-----------|-------|-------|
| Shutter | 1/25 | See shutter speed section |
| ISO | 640-1000 | Lock manually |
```

**Troubleshooting:**

```markdown
### Issue 1: Exposure Fluctuation

**Symptom:** Brightness changes mid-take  
**Cause:** Auto ISO enabled  
**Solution:** Switch to manual, lock ISO
```

---

### Links

**External links (open in new tab):**

```markdown
[Link text](https://example.com){:target="_blank"}
```

**Internal links (same tab):**

```markdown
[Related post](/posts/post-slug/)
```

**Shout out sources:**

```markdown
I get my beef from [Notting Hill Fish + Meat Shop](https://nottinghillfishshop.co.uk/){:target="_blank"}.
```

---

## Section Patterns

### Opening Hooks

**Direct statement:**
> "One chicken breast, seared in a stainless steel pan, with a vegetable side sautéed in the same pan straight after. That's the meal."

**Problem statement:**
> "If your gym relies on overhead fluorescents with no natural light, it's low light — and most commercial gyms fall into this category."

**Current state:**
> "I have been refining my smash burger setup over the past few months. The meat and method are where I want them. The bun is the part I have not figured out yet."

**What changed:**
> "I stopped eating supermarket bread a year ago."

**Snapshot framing:**
> "This post is a snapshot. A record of where I am physically in January 2026."

**Nostalgia/reflection:**
> "Metal Gear Solid 3: Snake Eater was released on PlayStation 2 in the UK on 4 March 2005. I bought it on launch day from GAME. £40. I was a 15 year old kid."

### Scope Blocks

```markdown
> **Scope**  
> This guide focuses on solo documentation filming with a fixed tripod position. It does not cover multi-camera setups, gimbal work, or professional production workflows.
{: .prompt-info }
```

```markdown
> **What this isn't**  
> This is not a supplement endorsement. Not a transformation narrative. It's a personal log tracking whether creatine makes a measurable difference under real-world conditions.
{: .prompt-info }
```

### Closing Signatures

**Living documents:**
```markdown
*Documented January 2026. More batches to follow.*
```

**Technical references:**
```markdown
*Technical reference document. Updated as new learnings are validated.*
```

**Snapshots:**
```markdown
*Documented [date]. For the record.*
```

**Recipes/guides:**
```markdown
*Documented [date].*
```

---

## Content Principles

### Show Your Thinking

- What you tried
- Why it did or did not work
- What you will try next

### Be Specific

Instead of: "I adjusted the settings"
Write: "Set manual white balance to 3000K"

Instead of: "Add some butter"
Write: "Add ~10g butter (Kerrygold or similar)"

Instead of: "Cook until done"
Write: "4 min + 3–4 min at dial 4"

### Name Your Sources

Link to products, shops, and suppliers. Explain why you chose them:
- "I get my beef from [Notting Hill Fish + Meat Shop](https://link.com){:target="_blank"}. I have tried a lot of butchers and this one tastes the best."
- "I chose Canadian very strong flour for gluten development. Kerrygold for flavour."

### Include the Human Details

- "There is something satisfying about watching him pull at the ribeye steak and then feed it through the mincer."
- "I love this pan. I am always telling my friends about it."
- "That feeling of knowing you were about to sink into something for days."
- "Holding the disc still felt different. That old sense of ownership."

### Acknowledge Limitations

- "I was short on time at points during this batch"
- "The kit lens limits low light performance"
- "I don't know how long this lasts. I don't know if I'll be hitting these numbers at 40."

### Connect to Future Work

- "More batches to follow"
- "Updated as new learnings are validated"
- "v1.0 is just the beginning"

---

## Quick Reference: Post Checklist

Before publishing:

- [ ] Front matter complete (title, date, categories, tags, description, image)
- [ ] LQIP generated for header image
- [ ] Categories: first = topic, second = specificity (or single if nothing to add)
- [ ] Description is clear and accurate
- [ ] Horizontal rules between major sections
- [ ] Tables aligned and readable
- [ ] External links have `{:target="_blank"}`
- [ ] Products and sources linked where relevant
- [ ] Images have size classes (`.w-50`, `.w-75`)
- [ ] Prompts used appropriately (tip/info/warning/danger)
- [ ] No overuse of em dashes
- [ ] Active voice throughout ("I chose" not "was chosen")
- [ ] Cause-and-effect reasoning explicit
- [ ] Specific values, not vague descriptions
- [ ] Closing signature appropriate to post type

---

## Example Front Matters

### Living Document / Recipe

```yaml
---
title: "The Potato Bun"
date: 2026-01-23
categories: [Nutrition, Recipe]
tags: [Recipe, Smash Burger, Bread, Baking, High Protein]
description: "Documenting homemade potato buns built for smash burgers. First attempt at baking from scratch."
image: 
  path: /assets/img/headers/potato-bun-header.webp
  lqip: data:image/webp;base64,...
---
```

### Technical Reference

```yaml
---
title: "Low Light Gym Filming"
date: 2026-01-04
categories: [Video, Settings]
tags: [Sony A6700, Sony 18-135mm, Low Light, Gym Filming, Technical Reference]
description: "Technical reference for filming strength training in low light gym environments. Covers camera settings, exposure management, and common issues."
image: 
  path: /assets/img/headers/gym-filming.webp
  lqip: data:image/webp;base64,...
---
```

### Workflow

```yaml
---
title: "After Effects Workflow — Vertical 4K Gym Videos"
date: 2026-01-18
categories: [Video, Workflow]
tags: [After Effects, Video Editing, Gym Filming, Sony A6700, Vertical Video]
description: "A baseline After Effects workflow for vertical gym videos. Marker-driven rep counters, cinematic motion, and export settings that survive platform compression."
image: 
  path: /assets/img/headers/after-effects.webp
  lqip: data:image/webp;base64,...
---
```

### Practical Recipe

```yaml
---
title: "Pan-Seared Chicken with Sautéed Vegetables"
date: 2026-01-06
categories: [Nutrition, Recipe]
tags: [Meal Prep, Recipe, High Protein]
description: "A simple pan-seared chicken breast with a rotating sautéed vegetable side. Seven days, seven vegetables — high protein, nutrient-dense, low carb."
image: 
  path: /assets/img/headers/chicken-breast.webp
  lqip: data:image/webp;base64,...
---
```

### Research-Backed Change

```yaml
---
title: "Why I Don't Eat Supermarket Bread"
date: 2026-01-10
categories: [Nutrition, Research]
tags: [Sourdough, Ultra-Processed Food, Nutrition, Gut Health, Bread]
description: "A year without supermarket bread. Why I switched to sourdough, what ingredient labels revealed, and how freezing fits into my daily routine."
image: 
  path: /assets/img/headers/sourdough-header.webp
  lqip: data:image/webp;base64,...
---
```

### Training Log

```yaml
---
title: "Strength Snapshot — January 2026"
date: 2026-01-03
categories: [Training, Log]
tags: [Strength Training, Training Log, Personal Record]
description: "A documentary snapshot of where I'm at physically in January 2026 — 78kg, 35 years old, and the strongest I've been."
image: 
  path: /assets/img/headers/strength-snapshot.webp
  lqip: data:image/webp;base64,...
---
```

### Training Study

```yaml
---
title: "A 12 Week Creatine Study"
date: 2026-01-04
categories: [Training, Study]
tags: [Creatine, Strength Training, Recovery, Personal Study, Training Log]
mermaid: true
description: "A 12 week personal study tracking the effects of creatine supplementation on strength, recovery, and training performance."
image: 
  path: /assets/img/headers/muscle.webp
  lqip: data:image/webp;base64,...
---
```

### Personal Journal

```yaml
---
title: "Metal Gear Solid 3 — Snake Eater Remastered"
date: 2026-01-10
categories: [Gaming, Journal]
tags: [PlayStation, Metal Gear Solid, Gaming]
description: "A childhood game, remastered. 20 years later, I'm playing it again."
image: 
  path: /assets/img/headers/snake-eater.webp
  lqip: data:image/webp;base64,...
---
```

### AWS Project

```yaml
---
title: "Building My First Bedrock Agent"
date: 2025-12-14
categories: [AWS, Generative AI]
tags: [AWS, Generative AI, Serverless, Lambda, Amazon Bedrock, API Gateway]
mermaid: true
description: "What began as a simple Amazon Bedrock agent demo evolved into a real, production agent running on my own website."
image: 
  path: /assets/img/headers/agent-design.webp
  lqip: data:image/webp;base64,...
---
```

---

*Template version 5.0 — January 2026*
