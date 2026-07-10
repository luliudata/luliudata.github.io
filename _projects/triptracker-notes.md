---
title: "TripTracker Notes"
subtitle: "随行 Notes"
tagline: "A bilingual, privacy-first iOS travel planner with AI-generated itineraries."
order: 1
icon: /images/projects/triptracker-icon.png
app_store_url: "https://apps.apple.com/app/id6761017367"
github_url: "https://github.com/luliudata/triptracker-notes-app"
tech: "React Native 0.81 · Expo SDK 54 · React 19 · Google Gemini 2.5 Flash · Cloudflare Workers"
---

<p>
  <img src="{{ page.icon | relative_url }}"
       alt="TripTracker Notes app icon"
       width="120" height="120"
       style="border-radius: 22%; box-shadow: 0 2px 8px rgba(0,0,0,.08); float: right; margin: 0 0 1em 1.5em;">
</p>

A bilingual (English / 中文) **iOS travel planner and checklist** for
people who like their trips a little more organised — without giving
their data away. Built with React Native and Expo.

**Highlights**

- **Smart checklists** — visa, vaccines, packing, documents; group
  templates per destination type
- **AI itinerary planner** — Google Gemini 2.5 Flash via a Cloudflare
  Worker proxy, so your API key never lives on-device
- **Privacy-first** — all trip data stays in local storage; the app
  doesn't ship telemetry, accounts, or third-party analytics
- **Bilingual everywhere** — UI, dates, AI prompts and outputs all
  switch cleanly between English and Chinese

**Links** —
<a href="{{ page.app_store_url }}" rel="noopener">App Store</a> ·
<a href="{{ page.github_url }}" rel="noopener">GitHub</a>

<sub style="opacity: .6">
Tech: {{ page.tech }}
</sub>
