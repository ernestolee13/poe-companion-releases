# Third-Party Notices

This product isn't affiliated with or endorsed by Grinding Gear Games in any
way. Path of Exile is a trademark of Grinding Gear Games; game text and data
quoted below remain theirs.

이 제품은 Grinding Gear Games와 제휴 관계가 없으며 Grinding Gear Games의 보증을
받지 않았습니다. Path of Exile은 Grinding Gear Games의 상표입니다.

## AIRI (moeru-ai/airi)

Portions of `services/companion-core/src/vendor/airi/` are copied from
https://github.com/moeru-ai/airi at commit 8d2a1f71af6d508cf253b4aa6867bf2729b3a159 and modified as described
in each module's `VENDORED.md`.

Copyright (c) 2024-PRESENT Neko Ayaka

```
MIT License

Copyright (c) 2024-PRESENT Neko Ayaka

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

### Vendored modules

| Directory (under services/companion-core/src/vendor/airi/) | AIRI source |
| --- | --- |
| pipelines-audio | packages/pipelines-audio |
| stream-kit | packages/stream-kit |
| audio | packages/audio |
| vad | packages/stage-ui/src/workers/vad, packages/stage-ui/src/libs/audio/vad.ts |
| voice-activity | packages/stage-ui/src/libs/voice/voice-activity-plugin.ts |
| llm-marker-parser | packages/core-agent/src/runtime/llm-marker-parser.ts, response-categoriser.ts |
| emotions | packages/stage-ui/src/constants/emotions.ts |
| ccc | packages/ccc |

## Seed-san (bundled VRM avatar)

`apps/desktop/assets/Seed-san.vrm`: Seed-san, Copyright VirtualCast, Inc., licensed under the VRM Public License 1.0 (https://vrm.dev/licenses/1.0/). Credit notation is required. Redistribution and modification are allowed as stated in the license terms embedded in the VRM meta of the model file.

## Live2D support (opt-in avatar mode)

The desktop app bundles the following for the optional Live2D avatar mode
(`apps/desktop/renderer/live2d-stage.js`):

- pixi.js (MIT), https://github.com/pixijs/pixijs, and @pixi/unsafe-eval (MIT)
- pixi-live2d-display (MIT), https://github.com/guansss/pixi-live2d-display
- Live2D Cubism Web Framework, embedded in pixi-live2d-display, licensed under the
  Live2D Open Software License,
  https://www.live2d.com/eula/live2d-open-software-license-agreement_en.html

The Live2D Cubism Core (`live2dcubismcore.min.js`) is Live2D Inc. proprietary
software. It is not distributed with this application. When the user enables
Live2D support and agrees to the Live2D Proprietary Software License
(https://www.live2d.com/eula/live2d-proprietary-software-license-agreement_en.html),
the application downloads it from the official URL
(https://cubism.live2d.com/sdk-web/cubismcore/live2dcubismcore.min.js) onto the
user's own machine. No Live2D sample models are bundled.

## libuiohook (via uiohook-napi) — global hotkeys and key injection

`uiohook-napi` 1.5.5 (MIT, Copyright (c) 2020 Alexander Drozdov,
https://github.com/SnosMe/uiohook-napi) is the Node binding the desktop app
uses for the PrintScreen hook and for sending the game's Ctrl+Alt+C item copy.
It bundles `libuiohook` (Copyright (C) 2006-2023 Alexander Barker,
https://github.com/kwhat/libuiohook), which is licensed under the GNU Lesser
General Public License, version 3 or later. The library ships as a separately
linked native module (`uiohook.node` / `uiohook-napi` prebuilds), so it can be
replaced with a modified build of libuiohook without rebuilding the rest of
the application. The full LGPL-3.0 text is in `LICENSES/LGPL-3.0.txt`.

## sherpa-onnx and transformers.js — local speech recognition runtime

- `sherpa-onnx-node` 1.13.8 (Apache License 2.0, Copyright k2-fsa,
  https://github.com/k2-fsa/sherpa-onnx) runs the local speech-recognition
  model on the user's PC. It bundles ONNX Runtime (MIT, Microsoft).
- `@huggingface/transformers` 3.8.1 (Apache License 2.0, Hugging Face,
  https://github.com/huggingface/transformers.js) loads the end-of-speech
  detector (Silero VAD, MIT, https://github.com/snakers4/silero-vad) in the
  character window.

The Apache License 2.0 text is in `LICENSES/Apache-2.0.txt`. The speech models
themselves (SenseVoice-Small, Silero VAD) are not in the installer: the app
downloads them when the user turns the microphone on, and the download step
names each model and its license (SenseVoice-Small: Alibaba FunAudioLLM,
FunASR Model Open Source License 1.1, which requires keeping the source,
author and model name visible; Silero VAD: MIT).

## Exiled Exchange 2 (Kvan7/Exiled-Exchange-2) — Korean item-name data

`services/companion-core/src/games/poe2/i18n-ko/data.generated.ts` (`KO_ITEM_NAMES`)
is derived from `renderer/public/data/ko/items.ndjson` of
https://github.com/Kvan7/Exiled-Exchange-2 at commit
cca30662bf31eaf38bd711e2ec1a6b899a06c40e (regenerated by
`scripts/generate-poe2-ko-data.mjs`). Only data is used, no code. Item names
themselves are Grinding Gear Games game text.

The PoE2 data assets under `services/companion-core/src/games/poe2/domain/`
(`item-meta.generated.ts`, `stat-matchers.generated.ts`,
`item-bundles.generated.ts`, `data-assets.generated.ts`) are derived from the
same project's shipped data files (`data/{en,ko}/items.ndjson`,
`data/{en,ko}/stats.ndjson`, `data/item-drop.json(c)`) of Exiled Exchange 2
v0.16.3 (commit cca30662bf31eaf38bd711e2ec1a6b899a06c40e), regenerated by
`scripts/generate-poe2-data-assets.mjs`. The anoint oil order is the
`EMOTIONS` list from EE2's `renderer/src/web/price-check/filters/pseudo/anointments.ts`.
Item names, stat texts and icon URLs are Grinding Gear Games game data.

```
MIT License

Copyright (c) 2020 Alexander Drozdov

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

The other generated tables come from Grinding Gear Games' public trade API
(`/api/trade2/data/stats` on www.pathofexile.com and poe.kakaogames.com) and
the game's ItemClasses table (via the LocalIdentity/poe2-data export).
`services/companion-core/src/games/poe2/pob-names.generated.ts` (Korean names
of passive keystones/notables and active skills, generated by
`scripts/generate-poe2-pob-names.mjs`) comes from the game's PassiveSkills and
ActiveSkills tables through the same export. All of it is Path of Exile 2 game
data © Grinding Gear Games.

## RePoE (repoe-fork) — crafting option data

`services/companion-core/src/games/poe2/mod-pool.generated.ts` is generated by
`scripts/generate-poe2-mod-pool.mjs` from the RePoE PoE2 export
(https://github.com/repoe-fork/poe2, pinned commit in the generated header).
The tables are Path of Exile 2 game data © Grinding Gear Games, extracted by
RePoE; the RePoE tooling is MIT licensed:

```
MIT License

Copyright (c) 2016 brather1ng

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

## Path of Building Community (PoE2 and PoE1) and LuaJIT — downloaded calculation engine

Nothing from these projects ships in the installer. On first use the
collector downloads the Path of Building for the game it runs (PoE2 or PoE1)
into its data directory (`<data>/pob-engine`, one folder per edition),
verifies every file against pinned hashes, and runs it as a separate
process to calculate DPS/EHP changes for item swaps
(`services/companion-core/src/games/poe/pob-engine*.ts`).

- Path of Building Community (PoE2), v0.23.1, commit
  `7d6f530cbdab20389ff8bc6ba97a37ac27f74e41`
  (https://github.com/PathOfBuildingCommunity/PathOfBuilding-PoE2). Only the
  Lua calculation sources, passive-tree data and runtime Lua libraries are
  fetched. MIT License:

```
Copyright (c) 2016 David Gowor

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

- Path of Building Community (PoE1), v2.67.2, commit
  `b32759ab0f31a1c8499a0d420cb0f0633d4fe478`
  (https://github.com/PathOfBuildingCommunity/PathOfBuilding). Only the Lua
  calculation sources (plus one JSONC data file), passive-tree data, the
  legion timeless jewel lookup tables (stored decompressed) and runtime Lua
  libraries are fetched. MIT License with the same copyright line,
  "Copyright (c) 2016 David Gowor", and the same text as above (its
  LICENSE.md also lists the licenses of the libraries PoB's own runtime
  bundles).

  PoB's bundled Lua libraries carry their own headers inside the downloaded
  files: dkjson, xml, sha1 and sha2 are MIT-style; base64.lua ("Lua 5.1+
  base64 v3.0 (c) 2009 by Alex Kloss") is LGPL 2, downloaded unmodified as a
  separate file from PoB's repository (corrected 2026-11-09; it was listed as
  MIT-style before).

- LuaJIT 2.1 (build 2.1.1744318430) from conda-forge
  (https://anaconda.org/conda-forge/luajit). MIT License:

```
LuaJIT -- a Just-In-Time Compiler for Lua. https://luajit.org/

Copyright (C) 2005-2025 Mike Pall. All rights reserved.

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

[ LuaJIT includes code from Lua 5.1/5.2, which has this license statement: ]

Copyright (C) 1994-2012 Lua.org, PUC-Rio.
(MIT license; full text in the downloaded package's info/licenses/COPYRIGHT)
```

- Windows only: the Microsoft Visual C++ runtime DLLs (`vcruntime140.dll`,
  `vcruntime140_1.dll`, `msvcp140.dll`) are taken from the same PoB commit's
  `runtime/` folder, where PoB redistributes them under the Visual C++
  Redistributable terms.
