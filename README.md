# ContentForge AI

**v1.0 · AI Content Suite**

ContentForge is a free, browser-based AI agent for YouTube video generation, anime content creation, social media growth, and SEO traffic strategy. It runs entirely in a single HTML file — no server, no login, no install required.

---

## Features

### 5 Specialised AI Modes

| Mode | What it does |
|---|---|
| 📺 **YouTube** | Viral titles, thumbnail concepts, full video scripts, SEO descriptions, channel growth tactics |
| ⛩️ **Anime** | Episode outlines, character design briefs, world-building, power systems, dramatic dialogue |
| 📱 **Social Media** | TikTok/Reels scripts, Instagram captions, hashtag strategy, content calendars |
| ✍️ **Script** | Full narrated scripts with B-roll cues, SFX notes, on-screen text directions, runtime estimates |
| 📈 **SEO & Traffic** | Keyword research, CTR optimisation, cross-platform funnels, Shorts growth strategy |

### AI Model Support

| Model | Provider | Key Required |
|---|---|---|
| Pollinations | Free proxy | ❌ No key needed |
| GPT-4o | OpenAI | ✅ API key |
| Claude Sonnet | Anthropic | ✅ API key |
| Gemini Pro | Google | ✅ API key |

API keys are stored locally in your browser (`localStorage`) and never sent to any third-party server.

---

## Getting Started

1. Download `contentforge.html`
2. Open it in any modern browser (Chrome, Firefox, Edge, Safari)
3. Start chatting — no setup needed

The app runs on **Pollinations (free)** by default. No account, no API key, no cost.

---

## Switching Models

Click the model chip in the header or the **AI Model** button in the sidebar to open the model switcher. To use GPT-4o, Claude Sonnet, or Gemini Pro, paste your API key into the field — it saves automatically to your browser.

---

## Switching Modes & Personas

- **Mode tabs** (top of the chat area): YouTube · Anime · Social Media · Script · SEO & Traffic
- **Sidebar personas**: clicking a persona auto-switches to its matching mode and updates the suggestion chips

---

## Suggestion Chips

Each mode shows quick-start prompts below the chat. Click any chip to instantly send that prompt to the AI. Suggestions update automatically when you switch modes.

---

## Keyboard Shortcuts

| Key | Action |
|---|---|
| `Enter` | Send message / generate |
| `Shift + Enter` | New line in input |

---

## File Structure

ContentForge is a **single self-contained HTML file**:

```
contentforge.html
├── CSS — layout, sidebar, chat bubbles, mode tabs, modal, responsive rules
├── HTML — sidebar, header, mode tabs, message area, suggestion chips, input box
└── JavaScript
    ├── Model definitions & key storage
    ├── Mode system prompts (5 modes)
    ├── Suggestion chips per mode
    ├── API providers (Pollinations, OpenAI, Anthropic, Google)
    ├── Message rendering & response formatting
    └── Sidebar, persona, and UI helpers
```

---

## API Details

### Free (Default) — Pollinations

```
POST https://text.pollinations.ai/openai
```

OpenAI-compatible proxy. No CORS issues, no key, no rate-limit sign-up required.

### OpenAI

```
POST https://api.openai.com/v1/chat/completions
Model: gpt-4o
```

### Anthropic

```
POST https://api.anthropic.com/v1/messages
Model: claude-sonnet-4-20250514
```

### Google

```
POST https://generativelanguage.googleapis.com/v1beta/models/gemini-1.5-pro:generateContent
```

---

## Customisation

All system prompts live in the `MODE_PROMPTS` object in the `<script>` block. Edit any prompt to specialise ContentForge for your niche, tone, or platform.

```js
const MODE_PROMPTS = {
  youtube: `Your custom YouTube prompt here...`,
  anime:   `Your custom anime prompt here...`,
  social:  `...`,
  script:  `...`,
  seo:     `...`,
};
```

Suggestion chips per mode are in `MODE_SUGGESTIONS` — same structure, one array per mode.

---

## Browser Compatibility

| Browser | Support |
|---|---|
| Chrome / Edge | ✅ Full |
| Firefox | ✅ Full |
| Safari (iOS & macOS) | ✅ Full |
| Mobile browsers | ✅ Responsive layout |

---

## Privacy

- No data is sent to any ContentForge server (there isn't one)
- API keys are stored only in your browser's `localStorage`
- Conversations exist only in memory and are cleared on page refresh or "New Chat"
- All API calls go directly from your browser to the chosen AI provider

---

## License

MIT — free to use, modify, and distribute.

---

*Built on the ARIA v3.2 framework · ContentForge v1.0*
