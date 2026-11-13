# Proxy Planner — Zenless Zone Zero

A mobile-friendly ZZZ showcase reader, build checker and farming planner.

## Use the app

Open GitHub Pages: https://huanbaoquach74-cloud.github.io/proxy-planner/

1. Enter a ZZZ UID and sync the public Enka Showcase.
2. Select an Agent. Its W-Engine and six Drive Discs appear inside that Agent's dossier.
3. Build Coach automatically compares the equipped 4-piece/2-piece sets, Disc 4/5/6 main stats, substat lines and W-Engine against the locally bundled sourced guide.
4. Enter Battery Charge, available minutes and material notes only if you want a personal farming schedule.
5. Switch UID to use a separate local profile on this device.

## Automatic build guide coverage

The initial sourced guide library covers Velina, Phoenix, Pyrois, Jane, Grace, Nicole and Koleda. Recommendations are bundled in `build-guides.json`, with source links and patch/review notes. Unknown Agents are not assigned guessed builds; their dossier reports that a verified guide is not yet bundled.

The checker evaluates:
- recommended 4-piece and 2-piece Drive Disc set combinations;
- main-stat families on slots 4, 5 and 6;
- the presence of guide-priority substats;
- the equipped W-Engine against the guide's signature recommendation;
- published endgame stat benchmarks, where the source provides them.

This is a rule-based checker, not yet a live generative-AI service. It does not invent a stat score or claim that a disc is mathematically optimal. Team composition, mindscape, rotation, W-Engine refinement and stat breakpoints can change recommendations.

## Data limits

Enka's public ZZZ Showcase provides Agent, W-Engine, skill and Drive Disc equipment data, but not a complete final in-game stat sheet, account inventory, material counts, Battery Charge or free-time availability. The stat calculator reconstructs a baseline from the documented data and formulas; some equipment scaling is explicitly approximate. Therefore:
- Current gear and disc recommendations are checked automatically from Enka.
- Current ATK, AP, AM, CR, CD, PEN Ratio and Energy Regen are estimated from Agent base/growth/promotion/core stats, W-Engine, and all six Drive Discs. Enka-documented approximate scaling is used for W-Engine and Drive Disc main stats; disc substat values use their PropertyLevel roll count.
- The calculated panel is an equipment-derived baseline, not a perfect copy of the in-game character sheet: Drive Disc set bonuses, conditional W-Engine passives, team buffs and combat-state effects are not yet applied. Use it as a transparent estimate, not a guaranteed exact match.
- Battery Charge, free time and material notes remain user-entered inputs for the schedule.
- Farming stages are shown only where the bundled guide source verifies them; otherwise the app says the stage is unverified.

## Privacy

- No HoYoverse password, cookie or login token is requested.
- UID profiles, notes, checklist state, resource inputs and cached Showcase responses stay in this browser's local storage.
- Data is not synced between devices or uploaded to a Proxy Planner account.
- Enka responses are cached according to the API `ttl`; public relay availability is not guaranteed.

## Sources

- Enka.Network ZZZ API documentation: https://github.com/EnkaNetwork/API-docs/blob/master/docs/zzz/api.md
- Build guide references are linked per Agent inside Build Coach. The bundled recommendations are cross-checked from public sources such as Prydwen, ZZZBuild, Icy Veins, GuildMeta, Kayco and Games.gg.

## Development notes

The app is hosted as a static GitHub Pages site. No API key is embedded in the frontend. A future generative AI feature would require a secure backend to protect its API key and should be added only after the deterministic build data and calculations are validated.
