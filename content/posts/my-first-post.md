---
title: "Why I'm Building MiseOS "
date: 2026-01-30
draft: false
description: "After 20 years in professional kitchens, I'm building the tool I always wished existed."
tags: ["miseOS", "project", "portfolio", "kitchen-tech", "mvp", "backend"]
categories: ["Project Log"]
series: ["MiseOS Development"]
series_order: 1
---

I spent the last week talking to former colleagues from my 20 years in the kitchen industry. Not for nostalgia—though there was plenty of that—but to validate an idea that's been nagging at me for years.

**Professional kitchens in 2026 still plan their menus in Word documents.**

Let that sink in for a moment. We're talking about operations that serve hundreds of meals daily, coordinate multiple stations, and manage complex inventory. And they're doing it with loose notes, Word templates, and the occasional lost sticky note.

## Menu Planning in Many Operations

Many canteens and restaurants emphasize that cooks should propose dishes they want to present to customers. This is arguably the strongest creative process in a kitchen: when a worker takes inspiration—from a restaurant visit, something seen online, or a conversation with a local farmer—and transforms that vision into something real for their guests.

This creative ownership is what keeps talented cooks engaged. It's the difference between "I'm just following recipes" and "I'm crafting experiences."

But here's the problem.

## The Chaos Nobody's Solving

Here's how this beautiful creative process actually works in practice:

A cook at the cold station gets inspired. Maybe it's a seasonal asparagus dish they saw at a restaurant, maybe it's a farmers market discovery. They scribble it down on a note. If they're feeling organized, they type it into a Word doc. Then they walk over to the kitchen chef to discuss ingredients.

The pastry section does the same thing. So does the hot station.

By the end of the week, the kitchen chef has:
- A pile of paper scraps
- Three different Word docs with conflicting version numbers  
- A mental map of who asked for what ingredients
- No clear way to consolidate orders across stations

**This is insane.**

![Frustrated Chef](/img/blog/frustrated-chef.png "Notes everywhere, no system in place")

The creative process is brilliant. The execution? A mess.

## Enter MiseOS

"Mise en place is the religion of all good line cooks." — Anthony Bourdain

![Anthony Bourdain Mise en Place](/img/blog/bourdain.jpg "Mise en place is a state of mind")

In Kitchen Confidential, Bourdain describes mise en place as more than just chopped onions; it’s a state of mind. It’s the gathering and preparation of everything you need before you start. If your mise is messy, your service will be a disaster.

I’m building MiseOS to bring that same philosophy to the digital side of the kitchen. While a cook's physical station might be perfectly prepped with salt, pepper, and prep-containers, their "digital station"—the menus, orders, and communication—is often a total mess of sticky notes and old Word docs.

MiseOS isn't just a tool; it's the "Operating System" for your kitchen's organization. It connects creative menu planning with operational ingredient management in one fluid motion.

Here's the core workflow:

1. Cooks submit weekly menu proposals from their stations (Hot, Cold, Pastry, etc.)
2. They request specific ingredients right then and there
3. The kitchen chef sees everything in one place and approves the plan
4. Centralized ordering happens based on actual needs, not guesswork

No more lost notes. No more "Did you order the saffron?" followed by awkward silence. No more retyping the same menu into three different systems.

## Building a Real Backend in 10 Weeks

This is part of my 3rd semester portfolio project. The goal is clear:

**Weeks 1-10:** Build a production-ready RESTful backend API in Java  
**Weeks 11-14:** Build a React frontend that consumes it

This isn't a toy project. By week 10, I need:
- Authentication & authorization (JWT)
- Database persistence (JPA)
- External API integration
- Validation & error handling
- Integration tests
- Deployment pipeline
- Actual users with different roles and permissions

Then I get 4 weeks to build a React frontend with routing, CSS modules, CI/CD via GitHub Actions, and deployment to Digital Ocean with Docker Compose and Caddy.

No pressure, right?

## The MVP (Weeks 1-10)

So what will MiseOS v1 actually deliver?

### Core Features:

**User Management & Roles**
- Head Chef: Full menu control, approval authority, shopping list generation
- Line Cooks: Station-specific menu suggestions, ingredient requests
- Guests (public): View current menu, no authentication required

**Weekly Menu Planning**
- Line cooks suggest dishes for their station (Salad, Cold/Starter, Hot, Bakery)
- Head Chef reviews, approves, rejects, or edits suggestions
- Final approved menu becomes the active weekly menu

**Ingredient Request Workflow**
- Line cooks submit ingredient requests tied to approved dishes
- Head Chef reviews and approves requests
- System aggregates approved requests into a shopping list

**Public Menu Display**
- Current week's menu visible without login
- Multilingual support (Danish/English via translation API)
- Allergen information clearly marked
- Mobile-friendly view for guests

**External Integration**
- Translation API (DeepL/Google Translate/LibreTranslate) for menu items and descriptions

That's the foundation. Clean workflow, clear roles, solves the core problem.

## The Nice-to-Have List

Here's what I'm *not* building in v1, but absolutely want to add once the MVP is stable:

**Weather integration**
- Pull weather forecasts via API
- Suggest menu adjustments based on temperature(e.g., lighter dishes on hot days)
- LLM API to suggest seasonal dishes based on weather trends

**Customer statistics**
- Track number of guests served per day
- How many guests were served during the same week last year

**Menu signs**
- Show menu signs by exporting to external display systems using APIs like ScreenCloud

**Guest meeting integration (Pronestor)**
- Dashboard for handling internal meetings
- Sections based meeting notes

**Other Features**
- Takeaway order management
- Recipe scaling calculator
- Nutrition information display

Some of these will definitely get built if there's time in the 10 weeks. Others will have to wait for v2.

The beauty of building with clean architecture? These features can plug in later without breaking what's already working.

## Open for Extension, Closed for Modification

If you know SOLID principles, you know where I'm going with this.

The architecture I'm building is designed to be **open for extension**—new features can be added without rewriting the core. But it's **closed for modification**—the MVP functionality stays stable.

Think of it like building a house. I'm not going to install the swimming pool before the foundation is poured. But I *am* making sure the plumbing and electrical can handle it when the time comes.

The nice-to-haves aren't abandoned. They're just waiting for their turn.

## What's Next?

I've set up the GitHub repository and written a proper README that explains the vision. 

Next week gets technical: designing the data model, structuring JPA entities, and figuring out how menu proposals should flow from cook to kitchen chef. There are some interesting challenges ahead—like how to handle ingredient requests that span multiple menus, or what happens when a cook wants to modify a proposal that's already been approved.

But first, the database schema. Everything else builds on that foundation.

This is going to be fun.

---

*This is part 1 of my MiseOS development log. Follow along as I build a tool for professional kitchens, one commit at a time.*