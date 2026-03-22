# STOICUS — Seek Wisdom from the Ancients

A purpose-built Stoic Philosophy chatbot where you consult **Marcus Aurelius**, **Seneca**, or **Epictetus** — each with a distinct voice, personality, and depth of character.

**Live Demo →** [your-vercel-url.vercel.app]

---

## Why Stoicism?

Stoic philosophy is having a cultural moment — Ryan Holiday, Tim Ferriss, half of Silicon Valley — but the original texts (Meditations, Letters to Lucilius, the Discourses) remain dense and intimidating. The idea: make the actual philosophers accessible as living, breathing mentors. Not a generic "ask about Stoicism" bot, but one where choosing **Epictetus** vs **Seneca** feels meaningfully different.

---

## What I Built

A single-page chatbot with three distinct philosopher personas, each engineered differently:

| Philosopher | Voice | Source Texts |
|---|---|---|
| **Marcus Aurelius** | Quiet authority, personal vulnerability, direct | Meditations |
| **Seneca** | Warm, witty, literary, self-aware | Letters to Lucilius, On the Shortness of Life |
| **Epictetus** | Blunt, demanding, zero patience for excuses | Discourses, Enchiridion |

---

## Design Decisions

**Aesthetic**: Ancient Rome meets luxury editorial. Dark marble feel with gold accents, Cinzel (Roman inscription font) for headings, Cormorant Garamond for body text, IM Fell English (a genuine Renaissance typeface) for italic flourishes.

**First impression**: A dramatic landing screen with a quote and a single CTA — "Begin Consultation" — before you ever see the chat. Sets the tone immediately.

**Loading state**: "Contemplating…" with a slow pulsing dot animation. Feels like the philosopher is actually thinking, not buffering.

**Empty state**: 4 categorized prompt starters ("On Purpose", "On Anger", "On Failure", "On Virtue") — helps users who don't know where to start.

**Error state**: "The oracle is silent" — maintains the thematic voice even in failure.

**Philosopher switching**: Choosing a different philosopher clears the conversation — intentional, since each has a fundamentally different philosophy and mixing them mid-thread creates incoherence.

---

## Tech Stack

- **Vanilla HTML/CSS/JS** — no framework overhead, ships as a static file
- **Anthropic Claude API** — `claude-opus-4-5` for response quality
- **Vercel** — static file deploy, zero config

---

## Deploying to Vercel

1. Drop `stoicus.html` into a new folder and rename to `index.html`
2. Push to GitHub
3. Import repo to [vercel.com](https://vercel.com) — it detects static HTML automatically
4. Deploy. Done.

Users enter their own Anthropic API key in the browser (stored in localStorage). For a production version you'd proxy through a Vercel serverless function to protect the key.

---

## Running Locally

```bash
# Just open the file — no build step needed
open stoicus.html
```

Enter your Anthropic API key when prompted. The key is stored in localStorage and never leaves your browser.

---

## AI Usage

Built with Claude (Anthropic) for:
- System prompt engineering for each philosopher persona
- UI code generation
- Iterative refinement of the loading/error/empty states

Every prompt was manually reviewed and tested against the actual Stoic texts to ensure the voice felt authentic. The system prompts went through ~6 iterations to get the tone balance right between philosophical depth and conversational warmth.
