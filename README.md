<div align="center">

# 🛒 GVCH Bot
### Grab VR Creation Hub — Discord Bot

[![Discord](https://img.shields.io/badge/Discord-Grab%20VR%20Marketplace-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.gg/NEWPxW6urB)
[![Node.js](https://img.shields.io/badge/Node.js-18%2B-339933?style=for-the-badge&logo=nodedotjs&logoColor=white)](https://nodejs.org)
[![Discord.js](https://img.shields.io/badge/Discord.js-v14-5865F2?style=for-the-badge&logo=discord&logoColor=white)](https://discord.js.org)
[![Built with Claude](https://img.shields.io/badge/Built%20with-Claude%20by%20Anthropic-D97757?style=for-the-badge&logo=anthropic&logoColor=white)](https://anthropic.com)
[![Status](https://img.shields.io/badge/Status-Live-2dc653?style=for-the-badge)]()

A fully custom Discord marketplace bot built from scratch for the **Grab VR** community. Handles the full creator economy — listings, hiring, reputation, payments, disputes, and more.

*This repository contains documentation only. Source code is private.*

</div>

---

## 📋 Overview

The **Grab VR Creation Hub** is an independent community server for Grab VR creators looking to earn off their hard-work. The GVCH Bot is the main power source for the marketplace - it makes a clear way for members to properly communicate their needs without hard manual work. It has an automated system that tracks jobs, reputation and a full on heirachy system with badges and perks (such as reduced cooldown in `/bump` cmds)

---

## ✨ Features

### 🏪 Marketplace Listings
- **`/forhire`** — 10-step guided DM flow for creators to post their services, including category, pricing, payment methods, portfolio links, and best level showcase
- **`/lookingfor`** — 7-step DM flow for clients to post job requests with budget, payment terms, and job type
- **`/sellcreation`** — Post paid Grab VR creations with image previews and buy buttons
- **`/freecreation`** — Post free creations for the community
- **`/editlisting`** — Re-run the full DM flow to update an existing listing in-place
- **`/bump`** — Re-post your most recent listing to the top of the channel (cooldown varies by role tier)

### 🧵 Hire & Apply Thread System
- Clicking **💼 Hire Creator** or **📩 Apply** opens a **Discord modal** collecting project details, portfolio links, budget, and availability.
- A **private thread** is automatically created with both parties and the filled intake form posted as the first message
- Built-in **✅ Job Done** (requires both parties to confirm) and **⚠️ Raise Dispute** buttons
- Escrow reminders, auto-close warnings, and listing expiry notifications via automated interval checks

### ⭐ Reputation & Job Tracking
- Full star rating system (1–5 stars + optional comment) sent via DM after job completion
- Job history tracking, completed jobs and disputes logged per user
- `/reputation` and `/jobhistory` commands for public profile lookups
- Milestone DMs on 1st, 5th, 10th, and 25th completed job
- Rating milestone DMs on 1st, 5th, and 10th perfect 5-star review

### 🏅 Badge & Tier System
Every listing displays a **🏅 Badges** field showing the poster's earned roles as emoji icons:

| Badge | Role | How to Earn |
|-------|------|-------------|
| `<:staff:>` | Moderator | Assigned by owner |
| `<:SI:>` | Scam Investigator | Assigned by owner |
| `<:creator:>` | Verified Creator | Apply via `/requestverify` |
| `<:youtube:>` | GVCH Ambassador | Promote server + apply via `/ambassador` |
| `<:serverbooster:>` | Server Booster | Boost the Discord server |
| 🥉🥈🥇 | Client Rank | Auto-assigned at 1, 3, and 7 completed hires |

### 🔍 Search & Discovery
- **`/search`** — keyword and category search across all active listings
- Results ranked: Verified Creators → Ambassadors → Boosters → everyone else
- **`/verified`** — rich per-creator cards showing avatar, star rating, job count, active listing links, and client rank badge
- **`/subscribe`** / **`/unsubscribe`** — DM alerts for new listings in chosen categories

### 🛡️ Moderation & Safety
- **`/verify`** — grant or remove Verified Creator status + role + DM notification
- **`/blacklist`** — block users from posting listings
- **`/deletelisting`** — remove any listing with mod log
- **`/modclientrank`** — manually assign client ranks
- **`/modambassador`** — approve or deny Ambassador applications
- 🚩 Report button on every listing with cooldown to prevent abuse
- Dispute system logs to a private mod channel
- All mod commands hidden from non-mods via `setDefaultMemberPermissions(0)`

### 🤖 Ambassador Program
- **`/ambassador`** — opens a 4-field modal (platform, proof link, reach, reason)
- Applications sent to mod log for review
- Approved ambassadors receive role, DM with full perks list, and badge on all listings
- Perks include: 15-minute bump cooldown, listing pin priority, early feature access, content resharing

### 📊 Server Stats & Automation
- **`/stats`** — live server-wide statistics calculated from active maps
- Weekly digest posted every Sunday noon UTC
- Showcase channel with post-job prompts for both parties
- Welcome/leave embeds with member count
- Category subscription alerts via DM

### 💾 Persistent Storage
All data survives bot restarts via JSON file storage:
- Reputation and ratings
- Job history
- Verified/blacklisted users
- Active listings
- Client history
- Category subscriptions
- Server stats

---

## 🔧 Tech Stack

| Technology | Usage |
|-----------|-------|
| **Node.js** | Runtime |
| **Discord.js v14** | Discord API wrapper |
| **REST API** | Slash command registration |
| **JSON (fs)** | Persistent data storage |
| **dotenv** | Environment variable management |

---

## 📐 Architecture Highlights

- **Modal-first flows** — Hire/Apply buttons trigger Discord modals collecting structured data before thread creation, ensuring both parties arrive informed
- **Session-based DM flows** — multi-step listing creation handled via in-memory session maps with 10-minute timeouts and progress bars
- **Dynamic cooldown system** — bump and listing cooldowns vary by role tier (Ambassador → Booster → standard)
- **Two-party job confirmation** — Job Done requires both participants to confirm before finalising, preventing accidental closes
- **Automated interval workers** — escrow reminders (30min), auto-close warnings (1hr), listing expiry (1hr), weekly digest (Sunday noon UTC)
- **Global error handling** — all interactions wrapped in try/catch, unhandled rejections caught globally to prevent crashes

---

## 👤 About the Developer

Built and maintained by **resterphobic_gd** - Verified Grab VR Creator with 40+ verified levels, VRML Orion Drift team owner, and former Head Administrator of the Penguin Paradise Pro League (500+ members).

> *"I built this bot (with the help of my beautiful and amazing [Claude, by Anthropic](https://anthropic.com)) because the Grab VR community needed an actually trustworthy marketplace for creators all around, looking for a way to get their creations out there"*

---

## 🔗 Links

- **Discord Server:** [Join the Grab VR Creation Hub](https://discord.gg/NEWPxW6urB)
- **Grab VR:** [grabvr.quest](https://grabvr.quest)
- **Built with:** [Claude by Anthropic](https://anthropic.com)

---

<div align="center">
<sub>This is an independent community project. Not affiliated with or endorsed by Grab VR or its developers.</sub>
</div>
