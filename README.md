# 19KEYS × HIGH LVL — Second Brain

Single static file. No build step. Live at https://19keys2ndbrain.vercel.app/

## What's in the repo

```
index.html                 the whole site (CSS + HTML + JS in one file)
README.md
meetings/                  one file per meeting, downloadable from the Meetings tab
  2026-09-03_19Keys_x_BAmechi_Transcript.docx
  2026-09-06_Ethiopian_Crown_Council_Call_Internal_Debrief.pdf
docs/                      pre-reads and briefs linked from the site
  High_Lvl_x_19Keys_Strategy_Session_Agenda.docx
  High_Lvl_Network_Source_of_Truth_v1.docx
  AfricaPlus_x_Ethiopian_Crown_Partnership_Brief.pdf
```

## Deploy (already wired)

Every push to `main` redeploys on Vercel. Framework preset: Other. No build command, no output directory.

## Site map

| Nav | `id` | Purpose |
|---|---|---|
| 00 Now | `#now` | Three rocks + live countdowns (Oct 5, Sept 26, Black Friday, Ethiopia) |
| 01 Current Agenda | `#agenda` | Next sitting: run of show, 20-decision capture sheet (checkboxes), carried items, flags |
| 02 To-Dos | `#todos` | By owner: Keys / Antoine / B. Amechi, plus what gets delegated |
| 03 Meetings | `#meetings` | One `<details class="glass meet">` per meeting: summary + downloadable transcript |
| R1 Creator Growth | `#creator` | Challenge, Program, ladder, events |
| R2 Supermind | `#supermind` | Brand lock, five approved shows, budget, affiliates |
| R3 HLC | `#hlc` | Production Day, N+1, masterclass engine, Factory room |
| 04 High Lvl Network | `#network` | Slate, weekly grid, tiers, first hire |
| 05 Ziion.io | `#ziion` | Ziion vs Patreon, quota, hackathon |
| 06 19keys.com | `#site` | Funnel-readiness sections with owners and dates |
| 07 Project High Lvl | `#phl` | Black Friday / The High Lvl Million |
| 08 Africa+ | `#africa` | Crown Council status, Sept 26–27 NY, Sept 11 push, Jan trip, asks, risks |
| 09 16-Month Calendar | `#calendar` | Mirrors 19keys.com/vanta |

## How to update

### Add a meeting
1. Drop the transcript into `meetings/` named `YYYY-MM-DD_Short_Title.ext`.
2. In `index.html`, inside `<section id="meetings">`, add a new `<details class="glass meet reveal">` block **above** the previous one (newest first). Copy the Sept 3 block as the template: date in `.d`, title in `h6`, one-line subtitle in `p`, summary in `.sum`, download button(s) in `.dls`, then the Decided / Left open cards.
3. Remove `open` from the older block so only the newest opens by default.

### Change the agenda / decision sheet
Each decision is a `.glass.item` with a unique `data-id`. Checkmarks persist per device via `localStorage` under the key `enough-gold-items`. Keep `data-id` values stable so checks survive edits; use a new id for a new item.

### Update to-dos
`<section id="todos">` has three owner cards (Keys, Antoine, B. Amechi). Each line is `<li><span>Task<em>DATE</em></span></li>`.

### Countdowns
Dates live in the `map` object at the bottom of the `<script>`. Change the ISO dates there.

### Brand tokens
CSS variables at the top of `<style>`: `--red` (pop), `--gold` / `--gold2` (19KEYS archive gold accents), `--oxblood`, glass and ink. Brand font for eyebrows and section numbers is Michroma (Google Fonts). Body stays Inter Tight / Manrope / JetBrains Mono so the look Keys approved does not change.

## Reference sites
- 19keys.com/creator → creatorgrowth-alpha.vercel.app (Challenge, Program, calendar)
- 19keys.com/vanta (calendar)
- superminddeck.vercel.app/#p-shows-new (approved Supermind shows)
- asupermind.com (Supermind store)
- 19keys.com (all current links)
- 19keys.com/africa → africaplus.vercel.app
