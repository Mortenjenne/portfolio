---
title: "miseOS"
date: 2026-02-05
draft: false
description: "In progress: a kitchen management system."
summary: "In progress: a kitchen management system fucused on workflow and resource optimization for a modern canteen."
featureimage: "img/projects/working-progress.svg"
showSummary: true
showDate: false
showReadingTime: false
showWordCount: false
showTaxonomies: false
---

## Kitchen Management Project Plan
Project: Portfolio
Semester: DAT 3rd Semester 2026
Focus: production-ready Java backend with workflow and resource optimization.

### Business Logic: The Creative Canteen
The system supports a modern canteen culture where quality comes from the chefs' ownership and creativity, while the head chef ensures coherence and cost control.

### 1. Section-based planning (bottom-up)
Instead of top-down control, four fixed sections submit their weekly plans independently:

- Sections: Hot, Cold/Starter, Salad, Bakery/Dessert.
- Workflow: a lead chef per section fills a consolidated weekly block and can propose dishes based on craft pride and surplus ingredients.
- Empty days: the system allows intentional gaps when a section lacks inspiration or awaits ingredient confirmation.
- Translation: an external API can translate the full weekly plan to English.

### 2. Head chef curation and verification
The head chef acts as editor and approver with the full overview:

- Combine section blocks into one complete weekly plan.
- Edit proposals (for example, if a week has too many heavy dishes).
- Fill gaps and ensure seasonal variation.
- Batch translation: once the plan is ready, DeepL API translates the entire week in one call. The head chef then verifies and adjusts the English text.

### 3. Takeaway and food waste reduction (reservation) - nice to have
To reduce waste, the kitchen can register surplus after lunch service:

- Reservation: guests can see surplus portions on the public menu and reserve a portion for pickup (no payment integration at first).
- Inventory control: counts down automatically so you cannot reserve what is not available.

### Extended flow
- Section proposals: chefs from each section submit weekly suggestions. The head chef assembles a master plan, which can be shown to staff who eat in the canteen as guest users.
- Ingredient ordering: each section attaches a shortage list for the next day's delivery. If a chef is missing items for a dish, they can add requests like 5 bunches of coriander or 2 crates of tomatoes. The system aggregates a single purchase list for the kitchen.


**Source Code:**
{{< github repo="Mortenjenne/miseOS" showThumbnail=true >}}