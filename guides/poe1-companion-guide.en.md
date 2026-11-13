# PoE1 Companion: User Guide

This guide goes from install to customizing your character to fixing problems. Prices and limits for outside services were checked on 2026-11-09. For what the app is and does, see the overview (poe1-companion-intro.en.md). If screens are easier than text, start with the [screen-by-screen setup guide](poe1-companion-setup-visual.en.md).

## 1. Install and first setup

1. Run the newest installer, `PoE1 Companion Setup <version>.exe` (https://github.com/ernestolee13/poe-companion-releases/releases/latest). It asks for administrator rights, because the Kakao client needs the same level.
2. PoE1 Companion starts in PoE1 mode. There is no game to choose.
3. Check the game log path. The app looks first and shows what it found. If it finds nothing, pick the file yourself. There is also an auto-detect button.
   - Steam: `Steam\steamapps\common\Path of Exile\logs\Client.txt`
   - Standalone: `Grinding Gear Games\Path of Exile\logs\Client.txt`
   - Kakao: under `Daum Games\Path of Exile\logs\`, either `KakaoClient.txt` or `Client.txt`
4. Pick your league. When a new league opens, refresh the list. League names come live from the trade site.
5. In Settings > Modules > Brain (chat), choose a preset (groq, gemini, openrouter, openai, deepseek, anthropic, ollama, or lm-studio) and paste your key. Press the connection test.
6. Save and start the game. The companion reacts when you enter an area or level up.

Run the game in windowed or borderless mode.

In the game's UI options, turn on "Output all dialogue to chat". The companion then notices the league content you meet in a map (Einhar, Alva, an Abyss and so on) from the NPC lines. It keeps only which content it was, never the dialogue text. With the option off, only that feature is missing.

On first launch a "Getting started" checklist appears: brain key, game log, your character info (optional), and a voice check (optional).

### Where to get a free key (checked 2026-11-09)

- Groq: sign up without a card (console.groq.com/keys). The app's default model openai/gpt-oss-20b has a free limit of 30 requests per minute and 1,000 per day (2026-11-11). Llama 3.1 8B became paid-only, so do not type it into the model field.
- Google AI Studio: get a key without a card (aistudio.google.com/apikey). The app's default model gemini-3.5-flash-lite has a free limit of 15 requests per minute and 500 per day, and the 2.5 models are closed to new accounts (2026-11-11). Free-tier input may be used to improve Google products.
- OpenRouter: type a model name ending in ":free" into the model field. Limits are 20 requests per minute and 50 per day. Buy 10 or more credits once and the daily cap becomes 1,000.
- GCP $300 trial: does not work. Google's own page says the $300 credit cannot pay for the Gemini API in AI Studio, and Vertex AI excludes accounts created after 2026-11-16 (checked 2026-11-11).

Leave the model field empty to use the preset's recommended model.

### If the key setup is a hassle: trial codes

If getting a key is more than you want to deal with, email help@vibestash.app with "trial code" in the subject. You get one code that covers the brain, the voice and speech recognition at once, worth about $10 to $20 of usage, enough for a few weeks with no setup. Codes are limited, one per person. Pick "Trial gateway" under Settings > Modules > Brain and paste the code into the key field.

### Voice: switch to Fish Audio's free model

With no key you get the edge-local voice, which sounds robotic. Sign up at fish.audio (no card), create a key under API Keys in your account menu, then in Settings > Modules > Voice (TTS) pick "Fish Audio" as the provider, paste the key, Test connection, Save. Leave the model and voice fields empty to use s2.1-pro-free and the recommended voice. On a trial code you can skip this. Fish's free offer is announced until 2026-11-30; after that the app falls back to edge-local by itself.

### What "Decisions (opener)" is

Further down the Modules tab, "Decisions (opener)" is a small model that picks the short opener the companion says while it builds the answer. Switched on with an OpenAI-compatible key under "Advanced", it picks an opener that fits the moment; empty, one of the prepared openers is used at random. The answer itself is the same. You can leave it empty on day one.

## 2. How to talk to it

Pick the microphone mode in Settings > Modules > Hearing (STT).

- Always listening (default): sends each time you finish a sentence.
- Push to talk: listens only while you hold the mic button.
- Talk hotkey (default: the backtick key): press once to start listening, press again to send. It sends on its own after 30 seconds.

A quiet room helps. While the companion is speaking, it only listens through a microphone with echo cancellation on. No microphone? Type your questions.

### Things to say

- Prices: "How many chaos is a divine?" or "How much is this item?"
- Right now: "Where am I?" or "Why did I just die?" (If the log does not say, it will not guess.)
- Builds: "Read this PoB link" or "Where is my build weak?"
- Info: "Find what changed in this patch" or "Tell me how this boss works."
- Farming: "What is a good way to earn chaos right now?"

When it does not know, it says so. It cannot know 3.30 mechanics before the patch notes exist. When the companion says "check the patch notes", that is what it means.

## 3. Hotkeys

Change them in Settings > System > Hotkeys. Click the field, press your combination, and press Esc to cancel. Most combinations need Ctrl, Alt, or Shift.

| Action | Default |
| --- | --- |
| Quick price panel | Ctrl+D |
| Detailed appraisal | Ctrl+Alt+D |
| Talk toggle | Backtick key |
| Share screen (shows the companion your current screen) | PrintScreen, only while the game is in front |
| Show or hide the feed overlay | Set in Settings |
| Mute on or off | Set in Settings |
| Show or hide reference images 1 to 5 | Set in Settings |

The appraisal hotkeys work with your mouse over an item. The app presses Ctrl+C for you, then puts your old clipboard back. Turn on "only while the game window is in front" and it never sends keys to other apps. The other hotkeys only change what is on screen and send nothing to the game.

The app does not capture PrintScreen, so Windows' own PrintScreen still works. If another program already uses a combination, the app tells you and picks a fallback key.

## 4. Prices and trading

- Ctrl+D opens a quick search panel in the style of Awakened PoE Trade. Turn mod lines, sums, base type, corruption, item level, and rune sockets on or off and search again. While the panel answers, the companion stays quiet. You can turn the panel off in Settings > Tools.
- Ctrl+Alt+D gives a detailed breakdown of the same item. On a map it reads the dangerous mods and answers run, reroll or skip. With a build on record (a PoB link) it only counts the mods that hurt that build.
- Stash search strings: say "make me a search for maps without physical reflect or no regen, quantity over 80" and it returns a string for the stash search box. Copy and paste it yourself. The companion never types into the game. Mods that did not fit the search box limit are listed separately.
- Prices are in chaos. Items priced only in divines stay out of the chaos total.
- The whisper button on a listing copies the whisper to your clipboard. You paste it into the game chat yourself. The app never sends it for you.
- A price it could not check is reported as not found, never invented.
- Some days the trade site is slow or blocks requests, and prices will not load.

## 5. PoB builds

- Paste a share link into the PoB field in Settings > Game > My character to register it as your current build. Other links you paste into chat are treated as reference builds.
- Supported links: pobb.in, poe.ninja/pob, maxroll.gg/poe/pob, poedb.tw/pob.
- Turn on Settings > Character > PoB calculation engine and the app downloads the PoB sources and LuaJIT once (about 250 MB, ten-odd seconds). After that, "what if I swap to this belt", "this gem instead of that one" or "if I take this node" get DPS and survivability deltas. Copy the item in game (Ctrl+C) before you ask.
- Builds with an Abyss timeless jewel cannot be loaded by the engine and get the summary comparison instead.
- Log in to the trade site in the app's browser and "my build", "my gear" or "my character" read your current character's gear and passives directly. A registered PoB link takes priority. If the account name cannot be found, fill the account name field under Settings > Character > My character (Name#1234).
- Crafting odds: copy the item and ask "chance of fire resistance if I exalt this"; it computes from the mod pool and spawn weights. Odds for Chaos or Alchemy on a fresh base are simulated and approximate, and influence and fossil-only mods are left out.
- Passives and skill gems use the Kakao Korean names both ways. Only small unnamed nodes may come out in English.

## 6. Choosing a character model

Pick a mode in Settings > Character > Avatar.

- Gear: the default mascot. The app falls back to it if a model fails to load.
- VRM (.vrm): Seed-san is built in. To use your own, choose a .vrm file in the path field.
- Live2D (.model3.json or .zip): Live2D Cubism Core is not bundled. Press "Enable Live2D support" and, if you agree, the app downloads it from the official address to your PC. If you pick a zip, the app unpacks it and finds the .model3.json.

In the look settings you set size (120 to 400 px) and idle opacity. Move the bar and you see it right away, but you must save to keep it. If the model has expressions or motions, "Emotion mapping" lets you assign them per emotion. Left empty, the app guesses from the names. I did not find a file size limit for VRM in the code. A very heavy model may run slowly.

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

Pick a profile or create one in Settings > Character. The fields:

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
2. Settings > Character > Character card > "Import card (PNG, JSON)" and pick the file.
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
| No answers | Check the brain preset and key, then press the connection test. A 402 means a billing or credit problem, and a rejected key means a wrong key. You may also have used up a free limit. |
| No voice | With no key the app falls back to the edge-local voice. If there is still no sound, check mute and run the voice connection test. |
| Speech is misheard | Try a quieter room and use accurate mode (240 MB). If it still frustrates you, switch to OpenAI speech recognition. |
| Hotkey does nothing | Another program may use the same combination. Change it in the System tab. Also check the option that limits appraisal hotkeys to the game window. |
| New league not in the list | Refresh the league list or type the name yourself. |
| Price not found | Ask again in a moment. The trade site may be slow. |

Log file: `%APPDATA%\@game-companion\desktop-poe1\logs\companion.log`
Data folder: `<your user folder>\.companion\poe1\` (kept apart from PoE2 data)

## 9. Privacy in short

Your API keys live only in a config file on your PC, and nothing is sent to us. The only outside call the app makes on its own is the update check against GitHub. Whispers, chat lines, and your questions go to the chat model provider you picked. Free tiers may use your input for training. The overview has the details.

Contact: help@vibestash.app
