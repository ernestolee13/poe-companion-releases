# PoE1 Companion: Overview

A voice companion that sits beside you while you play Path of Exile 1. It is a Windows desktop app, built to be ready for the 3.30 "Covens of Umbra" league (starts 2026-11-13 11:00 PST). Every price and limit in this document was checked on 2026-11-09. Services change their terms often, so look again on the provider's site before you sign up.

## What it is

The companion reads your game log (Client.txt), so it knows where you are, when you level up, when you die, and when a whisper comes in. You can talk to it or type. It answers with a voice and a speech bubble.

It never plays for you. No clicking, no key presses, no automatic trading. It shows up on screen, tells you things, and helps you think.

## What it does

- Reacts to entering an area, level-ups, deaths, whispers, and accepted trades, and remembers them.
- Answers price questions in chaos, using poe.ninja and the official trade site.
- Hover over an item and press Ctrl+D for a quick price panel. Ctrl+Alt+D gives a detailed appraisal. Korean items from the Kakao client work too.
- Press Ctrl+Alt+D on a map and it reads the dangerous mods (reflect, reduced maximum resistances, no regeneration and the like) and says run, reroll or skip. Ask "build me a search for maps without reflect, quantity 80 or more" and it writes a string you can paste into the stash search box. Korean client, Korean string.
- Reads shared PoB links (pobb.in, poe.ninja/pob, maxroll.gg/poe/pob, poedb.tw/pob). With the PoB calculation engine on (a one-time download of about 250 MB) it gives DPS and survivability deltas for an item swap, a gem swap or a passive.
- Log in to the trade site inside the app with your own account (Kakao or global) and it can read your current character's gear and passives without a PoB export, for "how is my build" or "what am I missing". It also builds your own PoB from the character automatically, gear mods included. The login survives restarts. Read only, nothing is written to your account.
- Gear upgrade plans: say "plan upgrades to fix my resists with 10 divines" and it works out from your PoB numbers how far you are short on the four resistances and life, keeps your uniques and locked slots, and splits the budget over the weakest slots. It asks before searching; say yes and it picks listings per slot with prices and trade links, then checks them together in PoB.
- Register several reference builds by name ("save this as a reference build called 'Gamer static'") and compare by name, including passive differences, the next nodes to take, and what-ifs such as "what if I take X and Y together".
- Finds a creator's PoB: "find 4Easy's static strike campaign PoB and save it" registers the PoB link from the video description as a reference build. Build guide links from maxroll, poe-vault and mobalytics are read for their PoB too.
- Crafting odds: ask "chance of fire resistance if I exalt these gloves" and it computes from the mod pool and spawn weights. Exalted, Regal and Augmentation are exact; Chaos, Alchemy, essences and fossils are simulated.
- Remembers when you reached each act, lab attempts and campaign time, so "faster than my last character?" has an answer. It also writes stash search strings.
- Looks up guides, patch notes, and poedb pages.
- Lets you pick its name, speech style, personality, and look (a 3D VRM model, among others).

## What it does not do

- The PoB engine cannot load builds with an Abyss timeless jewel (Amanamu, Kurgal and so on); those fall back to the summary comparison. The 3.30 tree arrives after PoB itself updates.
- Crafting odds cover the plain prefix and suffix pool only. Influence, fossil-only and bench mods are left out, so real odds can be lower, and the answer says so.
- Small unnamed passive nodes may be read in English.
- It does not know 3.30 mechanics until the patch notes are out. When it is unsure, it says so and suggests checking the notes.
- No auto-trading, auto-clicking, or macros.

## What you need

- A Windows PC and a PoE1 client (Steam, standalone, and Kakao all work).
- Run the game in windowed or borderless mode. The overlay cannot show over true fullscreen.
- One chat model key (see the free options below). A microphone is optional.

Installer: `PoE1 Companion Setup <version>.exe` (the newest one on the releases page)
Download: https://github.com/ernestolee13/poe-companion-releases/releases/latest

The installer asks for administrator rights, because the Kakao client runs as administrator and the app needs the same level. PoE1 Companion runs in PoE1 mode from the first start, and it installs side by side with PoE2 Companion without sharing settings or history.

## Start for free

If getting a key is a hassle, there are trial codes. Email help@vibestash.app and you get one code that covers the brain, the voice and speech recognition at once, worth about $10 to $20 of usage, one per person. Below is the do-it-yourself free route.

You need one chat model key. Voice output and speech recognition are free by default.

### Chat model (Settings > Modules > Brain)

| Option | Card | Limits and conditions (checked 2026-11-09) |
| --- | --- | --- |
| Groq free tier | No | Limits differ per model, and Groq's docs point to the limits page in your console for your plan. Third-party pages put the larger chat models at about 1,000 requests per day. When you hit the cap, it stops for the day. |
| Google AI Studio (Gemini) | No | Input and output tokens are free on the free tier for the Flash models. Per-minute and per-day limits vary by model; Google's docs point to the rate limit page in AI Studio. Google's pricing page says content sent on the free tier is used to improve Google products. |
| OpenRouter ":free" models | No | Only models with ":free" in the name. 20 requests per minute, 50 per day. Buy 10 or more credits once and the daily cap goes to 1,000. |
| GCP $300 trial | Yes | Does not work. Google's own page (checked 2026-11-11) says the $300 credit cannot pay for the Gemini API in AI Studio, and the Vertex AI route excludes accounts created after 2026-11-16. |

For a first try, pick Gemini (AI Studio). Sign-up takes a few minutes, and the app's default model gemini-3.5-flash-lite has a free limit of 15 requests per minute and 500 per day (AI Studio rate limit page, 2026-11-11). Groq's free tier gives openai/gpt-oss-20b 30 requests per minute and 1,000 per day; the former default Llama 3.1 8B became paid-only. Paste the key into Settings and press the connection test.

You can also run a local model (Ollama or LM Studio). No key needed, but you have to start the local server first.

### Voice (Settings > Modules > Voice)

The default is Fish Audio's `s2.1-pro-free` model. Get a key from a Fish Audio account and paste it in. As of 2026-11-09 it needs no card and has no hard character cap, only a fair use policy. It is best effort with no guarantee, and Fish says requests may be used to improve their model. The free offer runs until 2026-11-30 according to fish.audio/developers (checked 2026-11-11). After that the app switches to the free edge-local voice by itself.

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
- Price lookups go to the official trade site and poe.ninja. Finding a PoB on YouTube goes to YouTube, and reading a build guide goes to that guide's site.
- You log in to the trade site yourself in the in-app browser. The app never sees your password and keeps only the login cookies, encrypted, on this PC.
- A bug report is never sent by the app. It leaves only when you check it and copy and paste it yourself. API keys, trial codes and trade cookies are never written to the log file.

## Contact

- Email: help@vibestash.app
- Discord "PoE Companion": https://discord.gg/cTN8FhmCjs (questions, bug reports, trial codes)
