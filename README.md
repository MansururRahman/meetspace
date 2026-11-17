# MeetSpace

A single-page landing site for booking consultations on enterprise AI, software architecture, and technology strategy. Visitors pick a consultation topic and book a time through an embedded [Calendly](https://calendly.com) calendar.

## Features

- One static `index.html` file: no build step and no dependencies to install
- Three consultation topics (AI & LLM Strategy, Software Architecture, Enterprise Advisory), each with its own duration
- Choosing a topic updates the booking summary and loads that topic's Calendly event
- Works on phones as well as desktops, and respects the reduced-motion setting

## Getting started

Open `index.html` in a browser, or serve the folder locally:

```
python -m http.server 8000
```

Then visit http://localhost:8000.

## Connecting Calendly

The calendar shows a placeholder until you add a real Calendly link. In the `<script>` block at the bottom of `index.html`, set your public event URL:

```js
const CALENDLY_URL = "https://calendly.com/your-name/consultation";
```

To use a different Calendly event for each topic, set the URLs in `EVENT_URLS`. Each key must match the `data-topic` value on its topic button exactly:

```js
const EVENT_URLS = {
  "AI & LLM Strategy": "https://calendly.com/your-name/ai-strategy",
  "Software Architecture": "https://calendly.com/your-name/architecture",
  "Enterprise Advisory": "https://calendly.com/your-name/advisory"
};
```

## Deployment

The site is a single static file, so any static host works, including GitHub Pages, Netlify, Vercel, and Cloudflare Pages.
