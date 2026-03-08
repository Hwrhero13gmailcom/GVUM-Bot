# Changelog

All notable changes to the GVUM Bot are documented here.

---

## [1.3.0] — 2025
### Added
- **Ambassador Program** — `/ambassador` modal application flow, `/modambassador` approve/deny/remove, ambassador badge on listings, 15-minute bump cooldown for ambassadors
- **Scam Investigator role** — `<:SI:>` badge support on listings
- **Moderator badge** — `<:staff:>` badge on listings for mod team members
- **🏅 Badges field** on all listing embeds — shows earned role icons only, no labels
- **Intake modal on Hire/Apply** — before a thread opens, clicker fills out a structured form (portfolio, experience, rate, availability for creators / project, level link, budget, deadline for clients)
- **Dynamic listing cooldown** — enabled for all users, reduced for boosters (15 min) and ambassadors (15 min) vs standard (60 min)

### Fixed
- `getListingColor` missing from build — restored
- `getClientRank` / `getClientRankBadge` missing from build — restored
- `postedBadges` declared in wrong scope — moved to confirm block
- `Unknown Interaction (10062)` crash on mod commands — added `deferReply` to `/modclientrank`, `/verify`, `/blacklist`, `/deletelisting`, `/modambassador`
- Bot crashing on unhandled Discord API errors — added global `unhandledRejection` and `client.on("error")` handlers

---

## [1.2.0] — 2025
### Added
- **Server Booster perks** — booster badge on listings, 30-minute bump cooldown, priority in search results above regular members, showcase posts pinned 48 hours
- **Listing cooldown enabled** — non-boosters prompted with tier upgrade hint on cooldown message
- **Search priority ranking** — Verified Creators → Ambassadors → Boosters → everyone else
- **`isBooster` / `isAmbassador` stored on session** at listing creation time
- **`buildAuthorName()`** helper — cleans up author line to username only
- **`buildBadgesField()`** helper — assembles badge icons in fixed order

---

## [1.1.0] — 2025
### Added
- **Client Rank System** — 🥉 Starter (1 hire), 🥈 Regular (3 hires), 🥇 Top Client (7 hires), auto-assigned by bot
- **`/modclientrank`** — manually set client ranks
- **`/clienthistory`** — client rank card with progress bar to next rank
- **`checkClientRankUp()`** — fires after job completion, assigns role and DMs employer
- **Verified Creator badge system** — gold listing colour, `<:creator:>` badge, search priority
- **`/requestverify`** — Discord modal form (Grab VR account, proof link, reason)
- **`/ambassador`** placeholder groundwork
- **Bump fix** — new message ID re-registered in listings map after bump

---

## [1.0.0] — 2025
### Initial Release
- `/forhire` 10-step DM flow
- `/lookingfor` 7-step DM flow
- `/sellcreation` and `/freecreation` DM flows
- Private thread system with Job Done two-party confirmation
- Dispute system with mod log routing
- Star rating system via DM after job completion
- Reputation map with `/reputation` command
- Job history tracking with `/jobhistory`
- Milestone DMs (1st, 5th, 10th, 25th job / rating)
- `/search` with keyword and category filters
- `/verified` creator directory
- `/subscribe` / `/unsubscribe` category DM alerts
- `/bump` with 1-hour cooldown
- `/mylistings` jump links
- `/editlisting` re-run flow
- `/stats` live server statistics
- `/ping` latency and uptime
- `/blacklist` and `/deletelisting` mod commands
- Weekly digest to digest channel every Sunday
- Showcase channel post-job prompts
- Welcome and leave embeds
- Persistent JSON storage surviving restarts
- Global error handling preventing bot crashes
