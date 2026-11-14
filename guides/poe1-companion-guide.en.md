# PoE1 Companion: User Guide

This guide goes from install to customizing your character to fixing problems. It matches the app as of 0.1.66. Prices and limits for outside services were checked on 2026-11-09. For what the app is and does, see the overview (poe1-companion-intro.en.md). If screens are easier than text, start with the [screen-by-screen setup guide](poe1-companion-setup-visual.en.md).

## 1. Install and first setup

1. Run the newest installer, `PoE1 Companion Setup <version>.exe` (https://github.com/ernestolee13/poe-companion-releases/releases/latest). It asks for administrator rights, because the Kakao client needs the same level.
2. PoE1 Companion starts in PoE1 mode. There is no game to choose.
3. Check the game log path. The app looks first and shows what it found. If it finds nothing, pick the file yourself. There is also an auto-detect button.
   - Steam: `Steam\steamapps\common\Path of Exile\logs\Client.txt`
   - Standalone: `Grinding Gear Games\Path of Exile\logs\Client.txt`
   - Kakao: under `Daum Games\Path of Exile\logs\`, either `KakaoClient.txt` or `Client.txt`
4. Pick your league. When a new league opens, refresh the list. League names come live from the trade site.
5. In Settings > Modules > Brain (chat), choose a preset (groq, gemini, openrouter, openai, deepseek, anthropic, ollama, or lm-studio) and paste your key. Press the connection test.
6. Save, then press the "Start" button at the top of the settings window. "Stop" in the same place stops it. Turn on "Start automatically on launch" under Settings > System > Startup and you don't need to press it.
7. Start the game. The companion reacts when you enter an area or level up.

Run the game in windowed or borderless mode.

In the game's UI options, turn on "Output all dialogue to chat". The companion then notices the league content you meet in a map (Einhar, Alva, an Abyss and so on) from the NPC lines. It keeps only which content it was, never the dialogue text. With the option off, only that feature is missing.

On first launch a "Getting started" checklist appears; the same list sits at the top of Settings > Character. It goes: brain key, game log, your character info (optional), a voice and hearing check (optional), and the appraisal hotkeys.

### Finding your way around Settings

- There are five tabs: Character, Modules, Tools, Game and System. Pick a tab in the left menu and its sections are listed underneath; click one to jump there.
- The status bar at the top shows Brain, Voice, Hearing, Search, Vision, Game log and Trade as a dot and a name. The dot shows the state; hover for the details.
- Fields you rarely touch are folded under "Advanced settings". Click to open.
- Memories, What I know about you, Player notes and Our record show a one-line summary; "Show details" opens them in a popup.
- The Game tab runs: Game log, My character, Build calculation engine (PoB), Trade site (login, realm, quick search panel), Item appraisal.
- A "Related:" link jumps to the matching field on another tab.

### What each module does, and what adding it improves

One brain key is enough to run the app. Everything else is optional and improves one part when you add it, mostly with free keys.

| Module | What it does | Without it | Free way to fill it |
|---|---|---|---|
| Brain (required) | All conversation and reasoning | No answers | A free Gemini or Groq key (below) |
| Voice | Reads answers aloud | The default edge voice (free, no key), noticeably robotic | A free Fish Audio key (below). Trial codes: pick from 12 Korean voices |
| Hearing | Turns your speech into text | Typing only | On by default as local recognition on this PC, no key. The model downloads once on first use |
| Web search | Finds current info such as build trends and patch news | Answers from your game log and prices only, says it doesn't know recent news | A free Tavily key, 1,000 searches a month (below) |
| Vision | Reads screenshots you paste | Can't see pictures | The brain's key plus an image-capable model name (for example Gemini flash-lite) |
| Jev (fast judge) | Decides in about 0.5 s whether to answer, acknowledge or stay quiet; finds its way on build sites | Answers everything at length; the brain does site navigation, more slowly | On automatically when the brain uses an OpenRouter key (about 0.0002 USD a decision, so a little credit is needed). Included in trial codes |
| Filler before replies | Picks the short filler line spoken while the answer is being made | A random prepared filler | Any OpenAI-compatible key |

### Where to get a free key (checked 2026-11-09)

- Groq: sign up without a card (console.groq.com/keys). The app's default model openai/gpt-oss-20b has a free limit of 30 requests per minute and 1,000 per day (2026-11-11). Llama 3.1 8B became paid-only, so do not type it into the model field.
- Google AI Studio: get a key without a card (aistudio.google.com/apikey). The app's default model gemini-3.5-flash-lite has a free limit of 15 requests per minute and 500 per day, and the 2.5 models are closed to new accounts (2026-11-11). Free-tier input may be used to improve Google products.
- OpenRouter: type a model name ending in ":free" into the model field. Limits are 20 requests per minute and 50 per day. Buy 10 or more credits once and the daily cap becomes 1,000.
- GCP $300 trial: does not work. Google's own page says the $300 credit cannot pay for the Gemini API in AI Studio, and Vertex AI excludes accounts created after 2026-11-16 (checked 2026-11-11).

Leave the model field empty to use the preset's recommended model.


### Web search: a free Tavily key (checked 2026-11-14)

Ask about build trends or patch news the app doesn't know, and it searches the web for the answer. Without a key, Search in the status bar at the top shows as off, and answers come from your game log and prices only. Finding build guides by name also uses this key. Trial codes don't include web search.

1. Sign up at tavily.com. The free plan gives 1,000 credits a month with no card; a basic search is 1 credit.
2. Copy the API key (starts with tvly-) from the dashboard.
3. In Settings > Modules > Search, turn on web search, set the preset to tavily, paste the key and save.

### If the key setup is a hassle: trial codes

If getting a key is more than you want to deal with, email help@vibestash.app with "trial code" in the subject. You get one code that covers the brain, the voice and speech recognition at once, worth about $10 to $20 of usage, enough for a few weeks with no setup. Codes are limited, one per person. Pick "Trial gateway" under Settings > Modules > Brain and paste the code into the key field.

### Voice: switch to Fish Audio's free model

With no key you get the edge-local voice, which sounds robotic. Sign up at fish.audio (no card), create a key under API Keys in your account menu, then in Settings > Modules > Voice (TTS) pick "Fish Audio" as the provider, paste the key, Test connection, Save. Leave the model and voice fields empty to use s2.1-pro-free and the recommended voice. On a trial code you can skip this. Fish's free offer is announced until 2026-11-30; after that the app falls back to edge-local by itself.

### What "Filler before replies" is

Further down the Modules tab, "Filler before replies" (formerly "Decisions (opener)") is a small model that picks the short opener the companion says while it builds the answer. With "Let a model pick the filler before replies" on and an OpenAI-compatible key in the API key field under "Advanced settings", it picks an opener that fits the moment; empty, one of the prepared openers is used at random. The answer itself is the same. You can leave it empty on day one.

## 2. How to talk to it

Pick the microphone mode in Settings > Modules > Hearing (STT).

- Always listening (default): sends each time you finish a sentence.
- Push to talk: listens only while you hold the mic button.
- Talk key (default: the backtick key): listens while you hold it and sends when you let go. Set "Talk key behaviour" in Settings > System > Shortcuts to "Press to start, press again to send" and one press starts listening, the next one sends; in that mode it sends on its own after 30 seconds.

A quiet room helps. While the companion is speaking, it only listens through a microphone with echo cancellation on. No microphone? Type your questions.

### Things to say

- Prices: "How many chaos is a divine?" or "How much is this item?"
- Right now: "Where am I?" or "Why did I just die?" (If the log does not say, it will not guess.)
- Builds: "Read this PoB link", "Where is my build weak?" or "What are my resists?"
- Reference builds: "Save this as a reference build called 'Gamer static' (link)" or "Compare me with Gamer static"
- Gear: "Plan upgrades to fix my resists with 10 divines" or "Find me an amulet for 5 divines"
- Info: "Find what changed in this patch" or "Tell me how this boss works."
- Farming: "What is a good way to earn chaos right now?"

When it does not know, it says so. It cannot know 3.30 mechanics before the patch notes exist. When the companion says "check the patch notes", that is what it means.

If a lookup runs long, the reply stops at about a minute with one line saying why. A reply that has already started speaking is never cut. Ask again a little later, or narrow the question.

## 3. Hotkeys

Change them in Settings > System > Shortcuts. Click the field, press your combination, and press Esc to cancel. Most combinations need Ctrl, Alt, or Shift.

| Action | Default |
| --- | --- |
| Quick appraisal (quick price panel) | Ctrl+D |
| Detailed appraisal | Ctrl+Alt+D |
| Talk key | Backtick key (listens while held) |
| Share screen (shows the companion your current screen) | PrintScreen, only while the game is in front |
| Show or hide the feed overlay | Set in Settings |
| Mute on or off | Set in Settings |
| Show or hide reference images 1 to 5 | Set in Settings |

The appraisal hotkeys work with your mouse over an item. The app presses Ctrl+C for you, then puts your old clipboard back. Turn on "only while the game window is in front" and it never sends keys to other apps. The other hotkeys only change what is on screen and send nothing to the game.

The app does not capture PrintScreen, so Windows' own PrintScreen still works. If another program already uses a combination, the app tells you and picks a fallback key.

## 4. Prices and trading

- Ctrl+D opens a quick search panel in the style of Awakened PoE Trade. Turn mod lines, sums, base type, corruption, item level, and rune sockets on or off and search again. While the panel answers, the companion stays quiet. You can turn the panel off with "Quick search panel (Ctrl+D)" in Settings > Game > Trade site.
- Ctrl+Alt+D gives a detailed breakdown of the same item. On a map it reads the dangerous mods and answers run, reroll or skip. With a build on record (a PoB link) it only counts the mods that hurt that build.
- Stash search strings: say "make me a search for maps without physical reflect or no regen, quantity over 80" and it returns a string for the stash search box. Copy and paste it yourself. The companion never types into the game. Mods that did not fit the search box limit are listed separately.
- Prices are in chaos. Items priced only in divines stay out of the chaos total.
- The whisper button on a listing copies the whisper to your clipboard. You paste it into the game chat yourself. The app never sends it for you.
- A price it could not check is reported as not found, never invented.
- Some days the trade site is slow or blocks requests, and prices will not load.

### Trade site login

In Settings > Game > Trade site, turn on "Use my trade site login" and press "Log in"; the in-app browser opens. Log in with your own account, Kakao or global. The app never sees your password and keeps only the login cookies, encrypted, on this PC.

- Once you log in, the login survives restarts and updates.
- If the site turns down a read (the login has lapsed), Trade in the status bar changes to "Not logged in" and the feed shows one notice. Log in again in the same place.
- "Load my character" reads your current character and builds your own PoB from it automatically, gear mods included. This works on the Kakao realm too. A PoB link you enter yourself takes priority.
- If your account name cannot be found, fill the account name field there (Name#1234).

### Gear upgrade plan

Give it a budget and it works out what your build is short of, then picks what to buy per slot.

1. Say a budget and a goal: "Plan upgrades to fix my resists with 10 divines".
2. From your PoB numbers it adds up how far you are short on fire, cold, lightning and chaos resistance and life. It leaves your uniques and any slot you ask it to keep alone and splits the budget starting from the weakest slots.
3. Searching the trade site takes several requests, so it shows the plan first and asks before searching. It suggests running a map or two meanwhile.
4. Say yes and it lists a pick per slot with the base, key mods, the price with its unit and a trade link, then checks the picks together in PoB. The "Buy" button on a feed card opens the trade site on the same search.

For one slot only, say "just the amulet, 5 divines". It searches right away without a plan. The shortfall comes from your build's PoB numbers, so enter a PoB link or log in to the trade site and load your character first.

### Crafting

Use it to decide whether a so-so rare is worth one more craft. Send the item with the price hotkey, then ask:

- "Chance of a resist if I exalt this?": it looks at the open prefix and suffix slots and computes the odds from the game's spawn weights. It also tells you that a resist already on the item can't roll again.
- "What about the bench?": it lists the bench crafts that fit and their cost (for example all elemental resistances 9 to 12% for 1 Chaos Orb).
- Value check: it prices the item as it is and as it would be with the new mod, with the same trade search, from the cheapest listings. Minus the exalt or bench cost, it tells you in numbers whether to sell now or craft first. When similar listings are few and the price jumps a lot, it says the estimate is uncertain.

Example (a rare Amethyst Ring with life, fire and cold resistance): an exalt lands a resist 10.75% of the time and the expected value is negative, so sell it; a bench all-elemental craft takes it to about 15 chaos, so that one is worth it.

- It covers the basic crafts for now: exalt, regal, augment, chaos, alchemy, essences, fossils and the bench. Harvest and influence-only mods are not in yet. Odds for Chaos or Alchemy on a fresh base are simulated and approximate.
- A mod that exists as both a prefix and a suffix (item rarity, for one) can be ambiguous; it tells you when that is the case. Copying with Ctrl+Alt+C in game settles it.

## 5. PoB builds

- Paste a share link into "PoB link of your current character" in Settings > Game > My character to register it as your current build. Leave it empty, log in to the trade site and press "Load my character", and the app builds a PoB from your character instead.
- Supported links: pobb.in, poe.ninja/pob, maxroll.gg/poe/pob, poedb.tw/pob.
- Build guide links work too. Give it a maxroll PoE1 build guide (maxroll.gg/poe/build-guides), a poe-vault or a mobalytics guide link and it finds the PoB inside. Finding a guide by name needs the web search key (Tavily); trial codes don't include web search.
- Turn on "Use the PoB calculation engine" in Settings > Game > Build calculation engine and the app downloads the PoB sources and LuaJIT once (about 250 MB, ten-odd seconds). After that, "what if I swap to this belt", "this gem instead of that one" or "if I take this node" get DPS and survivability deltas. Copy the item in game (Ctrl+C) before you ask.
- Builds with an Abyss timeless jewel cannot be loaded by the engine and get the summary comparison instead.
- Log in to the trade site in the app's browser and "my build", "my gear" or "my character" read your current character's gear and passives directly. A registered PoB link takes priority. If the account name cannot be found, fill the account name field under Settings > Game > Trade site (Name#1234).
- Stat questions such as "what are my resists?" are answered from PoB's numbers. It names all four resistances (fire, cold, lightning, chaos) and how far each is over the cap.

### Several named reference builds

Register the builds you want to follow under a name each, then compare by name.

- In chat: "Save this as a reference build called 'Gamer static' (link)".
- In settings: in Settings > Game > My character > Reference builds, write one per line as "name | link" and save. Builds registered in chat are listed under that field and saving the field keeps them.
- Compare: "Compare my build with Gamer static".
- Passives: "How do my passives differ from the reference?" or "What should I take next?" gives the node differences and the next nodes.
- What-ifs: "What if I take X and Y together?" calculates several changes at once in PoB.

### Finding a creator's PoB on YouTube

Say "Find 4Easy's static strike campaign PoB and save it as '4Easy campaign'" and it searches YouTube, then registers the PoB link from the video description as a reference build. YouTube search needs no key. A nickname may not be found, so use the channel name: the Korean nickname "포이지" finds the channel only as "4Easy".
- Passives and skill gems use the Kakao Korean names both ways. Only small unnamed nodes may come out in English.

## 6. Choosing a character model

Pick a mode in Settings > Character > Avatar.

- The default is the 2.5D character Hiyori (Live2D's free sample). On first launch you see the gear mascot; the first row of the "Getting started together" checklist, "Turn on the 2.5D character", asks for the Live2D terms once, downloads the Cubism Core and switches to Hiyori. In Settings, "Built-in: use Hiyori" restores it.
- Gear: the default mascot. The app falls back to it if a model fails to load.
- VRM (.vrm): Seed-san is built in. To use your own, choose a .vrm file in the path field.
- Live2D (.model3.json or .zip): Live2D Cubism Core is not bundled. Press "Enable Live2D support" and, if you agree, the app downloads it from the official address to your PC. If you pick a zip, the app unpacks it and finds the .model3.json.

In Appearance you set size (120 to 400 px) and idle opacity. Move the bar and you see it right away, but you must save to keep it. If the model has expressions or motions, open "Advanced" at the bottom of the Character tab; "Emotion mapping" there lets you assign them per emotion. Left empty, the app guesses from the names. I did not find a file size limit for VRM in the code. A very heavy model may run slowly.

### Where to find models and how to load them (as the sites looked on 2026-11-13)

**VRoid Hub (hub.vroid.com)**: the largest source of VRM models. Downloading needs a pixiv account.
1. On the list page open "Filter by conditions of use", tick "Third-party use: Allow", "Download: Allow" and "Avatar use: Allow", then Apply. Direct link: hub.vroid.com/en/models?is_downloadable=1&characterization_allowed_user=everyone
2. On a model page check that "Can you use this model?" says Yes and read the "Conditions of use" line: Avatar Use, Violent acts, Sexual acts, Corporate use, Individual commercial use, Redistribution, Alterations, Attribution. Avatar Use: Allow is what this app needs. If you plan to stream or record, look at Individual commercial use too. Attribution: Required means credit the creator.
3. "Use this model" takes you through the pixiv ID sign-in and gives you the .vrm file (VRM 0.0 or 1.0, both work).
4. In the app: Settings > Character > Avatar > Mode "VRM avatar", pick the .vrm with the browse button next to the path field, Save. The character window redraws at once; if the file cannot be loaded it falls back to the default mascot.

**BOOTH (booth.pm)**: has free VRM models too. booth.pm/en/search/VRM?max_price=0 shows 0 JPY items only, and the item page has a "Free Download" button. You still need a pixiv account, and the file stays in your Purchase History. Careful: the VRM search is full of VRChat-only avatars (unitypackage). Use only items whose file list contains a .vrm. Each shop has its own terms at the bottom of the item page.

**VRoid Studio**: make your own model and export a .vrm. The default presets are described as fine for commercial use; specially marked materials carry their own conditions.

**Live2D official samples (live2d.com/en/learn/sample)**: no login. About twenty models (Hiyori, Haru, Shizuku, Mark, Zundamon and more), each with a Download button. Read the "Free Material License Agreement" and the "Live2D Cubism Sample Data Terms of Use" first; Hatsune Miku and Unity-chan follow separate guidelines. The zip's runtime folder holds the .model3.json.
1. In the app: Settings > Character > Live2D support > "Enable Live2D support", then "Agree and download" in the dialog. Cubism Core is Live2D Inc. software, not bundled, and is fetched from the official address at this point.
2. Switch Mode to Live2D and pick the .model3.json or the downloaded zip; the app unpacks a zip and finds the .model3.json.

Tried for real (2026-11-13, Windows 11): a public sample .vrm entered in the path field renders in the character window after Save, and switching back to the bundled Seed-san renders too. Size and opacity survive a restart. In the current build (0.1.10) a VRM size change shows only after a restart; the next build fixes that.

Do not re-upload or redistribute someone else's model, altered or not, unless the conditions allow it.

## 7. Writing a personality

Pick a profile or create one in Settings > Character. Name and formality are in view; the personality, example lines, things to avoid and greetings open under "Advanced settings" in "Name & personality". The fields:

- Name.
- Personality and speech style: free text. It never outranks the factual rules. Up to 2,000 characters.
- Speech level: auto (read from your description), casual (banmal), or polite (jondaetmal). This matters for Korean voices.
- Example lines: a situation (up to 20 characters) and a line (up to 120 characters), one per row. Up to 12 rows. Leave numbers out, because the model may repeat an example number as if it were fact.
- Avoid list: up to 6 items, 30 characters each, split by commas.
- Greetings: one per line, up to 8, 300 characters each.

The whole card (description, examples, avoid list) reaches the model only up to 2,000 characters. If it runs long, example lines drop from the end, and 8 stay. Models follow a few real lines much better than adjectives.

You can also import a Character Card V2 or V3 (PNG or JSON) made elsewhere with "Import card". It is added as a new profile and your current one is untouched. The card's instructions, scenario, and lorebook are stored but not applied. Text over 2,000 characters is cut. Export is JSON.

Importing a character card, step by step:
1. A card is a PNG (the data hides inside the image) or a JSON file holding a personality, greetings and example lines. "Export character" in SillyTavern produces this format, and card-sharing communities hand out the same files. Some of those sites are mostly adult content; use their filters.
2. Open "Advanced" at the bottom of Settings > Character, then Character card > "Import card (PNG, JSON)", and pick the file.
3. A line "Added as a new profile: name (format)" and a thumbnail appear, and that profile becomes the active one. It survives a restart.
4. An English card comes in as English text. The companion still answers in the language you set, but the greeting plays as written, so edit the greeting field if you want. Descriptions over 2,000 characters are cut.

Tried for real (2026-11-13, Windows 11): importing a public sample card (Seraphina, V3 PNG) added the profile with one greeting and a thumbnail, and the next replies used that name.

The companion speaks the language you set in Settings (Korean or English). The examples below are written for an English-speaking companion; for a Korean one, write the same fields in Korean.

### Example 1: calm veteran (casual tone)

Text for the personality field:

```
A veteran exile who has played many leagues. Few words, calm.
Speaks first and short when things go wrong. Credits a good play quietly.
Says "I don't know" and suggests checking.
Casual tone, one or two sentences. No lectures.
```

Example lines (situation / line):

- Death / Down you go. Check your gear, then back in.
- Danger / Health is low. Pull back.
- Boss kill / Got it. Clean.
- No price / I haven't seen that price. I won't make one up.
- Level up / Level up. Let's look at your passives.
- Long silence / Quiet. Rest if you need to, call me when you want.
Avoid list: no spoilers, no unchecked prices, no long lectures, no emoji

### Example 2: upbeat trade-savvy friend (casual tone)

```
A lively friend who loves the trade site and prices. Gets excited about good drops.
Talks fast and bright, but believes numbers must be exact.
Admits it when a price has not been checked.
Casual tone, plenty of exclamations, never more than two sentences at a time.
When you fail, comforts first, then suggests a fix.
```

- Rare drop / Whoa, that looks good! Let's check the price.
- Death / Ouch, it's fine, it's fine. Days like this happen!
- Trade whisper / A whisper! A customer. Go check.
- No price / Couldn't get the price. I won't guess.
- Trade question / If you're in a hurry, pricing a bit lower works. Which do you prefer?
- Boss kill / Got him! That looked amazing!
- Long silence / Hey, still alive? It's so quiet I'm bored!
Avoid list: no spoilers, no unchecked prices, no long lectures, no emoji

### Example 3: dry, sarcastic strategist (formal tone)

```
A fast, dry strategist who jokes with a straight face.
Sarcastic but never crosses the line, and always adds something useful.
Formal tone with some distance, one or two sentences.
Shows little emotion, gives clear judgments. Says so when it doesn't know.
```

- Death / A foreseeable result. Check your resistances first.
- Danger / Health is gone. There is no reason to keep standing there.
- Rare drop / It looks usable. Check the price before you sell.
- No price / I could not verify that price. I do not state numbers I don't know.
- Build question / Gear first. Open resistances come before damage.
- Boss kill / Defeated. Not bad.
- Chat / I'm here. Tell me if you need something.
Avoid list: no spoilers, no unchecked prices, no long lectures, no emoji

All three fit the limits: each card body is far under 2,000 characters, there are no more than 12 example lines, situations are within 20 characters, lines within 120, and the avoid list has 4 items under 30 characters each.

### Choosing a speech level

- Casual reads like a friend. Polite keeps a distance and suits dry sarcasm.
- On auto, the app reads the level from your description. If unsure, set it yourself.
- Short banned phrases are followed better than long explanations.

## 8. Troubleshooting

| Symptom | What to check |
| --- | --- |
| Overlay is not visible | Switch the game to windowed or borderless mode. |
| Companion ignores the game | Check the log path in Settings > Game. For Kakao, pick whichever of KakaoClient.txt or Client.txt in the logs folder was changed most recently. Also confirm the app was started as administrator. |
| No answers | If the top button reads "Start", press it. Check the brain preset and key, then press the connection test. A 402 means a billing or credit problem, and a rejected key means a wrong key. You may also have used up a free limit. |
| No voice | With no key the app falls back to the edge-local voice. If there is still no sound, check mute and run the voice connection test. |
| Speech is misheard | Try a quieter room and use accurate mode (240 MB). If it still frustrates you, switch to OpenAI speech recognition. |
| Hotkey does nothing | Another program may use the same combination. Change it in the System tab. Also check the option that limits appraisal hotkeys to the game window. |
| New league not in the list | Refresh the league list or type the name yourself. |
| Price not found | Ask again in a moment. The trade site may be slow. |
| The reply stops at about a minute with a reason | The lookup ran long. Ask again a little later or narrow the question. |
| Trade shows "Not logged in" | The trade login lapsed. Log in again in Settings > Game > Trade site. |

### Reporting a bug

If the table does not help, use Settings > System > Report a bug.

1. Describe what happened in "What were you doing, and what happened?" and press "Build the report". It puts together the app version, a summary of your setup and your note.
2. Check it, copy it and paste it into the bug report channel on Discord. A long report is split into several copies. The app sends nothing by itself.
3. Use "Open log file (to attach)" and attach the log too. It shows where things got stuck and makes fixing much faster. API keys, trial codes and trade cookies are never written to the log.

If Discord is not your thing, email help@vibestash.app. The Discord server "PoE Companion" (https://discord.gg/cTN8FhmCjs) and the guides also open from Settings > System > Community and contact.

Log file: `%APPDATA%\@game-companion\desktop-poe1\logs\companion.log`
Data folder: `<your user folder>\.companion\poe1\` (kept apart from PoE2 data)

## 9. Privacy in short

Your API keys live only in a config file on your PC, and nothing is sent to us. The trade login cookies are kept encrypted on this PC too, and a bug report leaves only when you copy and paste it yourself. The only outside call the app makes on its own is the update check against GitHub. Whispers, chat lines, and your questions go to the chat model provider you picked. Free tiers may use your input for training. The overview has the details.

Contact: help@vibestash.app, Discord https://discord.gg/cTN8FhmCjs
