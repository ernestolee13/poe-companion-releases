# PoE1 Companion: Overview

A voice companion that sits beside you while you play Path of Exile 1. It is a Windows desktop app, built to be ready for the 3.30 "Covens of Umbra" league (starts 2026-11-13 11:00 PST). Every price and limit in this document was checked on 2026-11-09. Services change their terms often, so look again on the provider's site before you sign up.

## What it is

The companion reads your game log (Client.txt), so it knows where you are, when you level up, when you die, and when a whisper comes in. You can talk to it or type. It answers with a voice and a speech bubble.

It never plays for you. No clicking, no key presses, no automatic trading. It shows up on screen, tells you things, and helps you think.

## What it does

- Reacts to entering an area, level-ups, deaths, whispers, and accepted trades, and remembers them.
- Answers price questions in chaos, using poe.ninja and the official trade site.
- Hover over an item and press Ctrl+D for a quick price panel. Ctrl+Alt+D gives a detailed appraisal. Korean items from the Kakao client work too.
- Reads shared PoB links (pobb.in, poe.ninja/pob, maxroll.gg/poe/pob, poedb.tw/pob) and talks about the build from its summary.
- Looks up guides, patch notes, and poedb pages.
- Lets you pick its name, speech style, personality, and look (a 3D VRM model, among others).

## What it does not do

- The PoB calculation engine does not run for PoE1 yet. There are no DPS or survivability numbers, only a read of the build summary.
- No crafting odds. For crafting questions it answers from general knowledge only.
- There are no Korean passive or skill name tables, so it sometimes uses the English names.
- It does not know 3.30 mechanics until the patch notes are out. When it is unsure, it says so and suggests checking the notes.
- No auto-trading, auto-clicking, or macros.

## What you need

- A Windows PC and a PoE1 client (Steam, standalone, and Kakao all work).
- Run the game in windowed or borderless mode. The overlay cannot show over true fullscreen.
- One chat model key (see the free options below). A microphone is optional.

Installer: `PoE1 Companion Setup 0.1.0.exe`
Download: [download link]

The installer asks for administrator rights, because the Kakao client runs as administrator and the app needs the same level. PoE1 Companion runs in PoE1 mode from the first start, and it installs side by side with PoE2 Companion without sharing settings or history.

## Start for free

You need one chat model key. Voice output and speech recognition are free by default.

### Chat model (Settings > Modules > Brain)

| Option | Card | Limits and conditions (checked 2026-11-09) |
| --- | --- | --- |
| Groq free tier | No | Limits differ per model, and Groq's docs point to the limits page in your console for your plan. Third-party pages put the larger chat models at about 1,000 requests per day. When you hit the cap, it stops for the day. |
| Google AI Studio (Gemini) | No | Input and output tokens are free on the free tier for the Flash models. Per-minute and per-day limits vary by model; Google's docs point to the rate limit page in AI Studio. Google's pricing page says content sent on the free tier is used to improve Google products. |
| OpenRouter ":free" models | No | Only models with ":free" in the name. 20 requests per minute, 50 per day. Buy 10 or more credits once and the daily cap goes to 1,000. |
| GCP $300 trial | Yes | Sign-up needs a payment method. The app has no Vertex preset, so you would set up a compatible endpoint and authentication yourself. It is the hardest route. The amount and duration could not be confirmed on Google's page (commonly stated: $300 for 90 days). |

For a first try, pick Groq or Gemini. Sign-up takes a few minutes. Paste the key into Settings and press the connection test.

You can also run a local model (Ollama or LM Studio). No key needed, but you have to start the local server first.

### Voice (Settings > Modules > Voice)

The default is Fish Audio's `s2.1-pro-free` model. Get a key from a Fish Audio account and paste it in. As of 2026-11-09 it needs no card and has no hard character cap, only a fair use policy. It is best effort with no guarantee, and Fish says requests may be used to improve their model. The end date of the free offer is stated inconsistently, so it could not be confirmed.

With no key, the app switches to the free edge-local voice by itself. It sounds a little less natural, but it works. That voice is Microsoft's online service too, so the text it reads goes over the internet.

### Speech recognition (Settings > Modules > Hearing)

The default is local recognition on your own PC. No key, no fee, and your voice stays on the machine. The first run downloads a model once (240 MB for accurate mode, 76 MB for light mode). If Korean keeps getting misheard, consider the paid option below.

## What upgrading costs

All optional. You pay only for what you use.

| Item | Price (checked 2026-11-09) |
| --- | --- |
| OpenAI speech recognition | gpt-4o-mini-transcribe about $0.003 per minute, whisper $0.006 per minute. OpenAI's own pricing page would not open, but several price trackers agree on these numbers. Ten hours of actual speech is about $1.80 at the mini rate. |
| Fish Audio paid | Pay as you go. A secondary source says about $15 per million UTF-8 bytes (a Korean character is 3 bytes). Not confirmed in the official docs. |
| Paid chat models | OpenAI, Anthropic, DeepSeek and others are selectable. Check each provider's price page. |

Cloud recognition is usually better at Korean, but local recognition is enough to start. Try the free setup first and switch only if it bothers you.

## Privacy

- Your API keys are stored only in a config file on your own PC. Nothing is sent to us. Apart from the optional trial gateway the app has no server of ours; the only outside call of its own is the update check against GitHub.
- Your questions, whispers, chat lines, and item text go to the chat model provider you picked. Their terms apply.
- One exception is a trial token ("Trial gateway"). Your questions then pass through a gateway the developer runs, on their way to Anthropic. The gateway does not store or log what you say; it keeps only usage numbers per token (tokens used and cost). Put in your own key instead and the gateway is not involved.
- Free tiers may use your input to improve or train their models. Do not say anything sensitive.
- Text for speech goes to the voice service you picked. With local recognition, your microphone audio never leaves the PC.
- Price lookups go to the official trade site and poe.ninja.

## Contact

help@vibestash.app
