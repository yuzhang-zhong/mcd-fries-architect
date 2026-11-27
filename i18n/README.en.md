<div align="center">

# FriesCraft

**English** · [简体中文](../README.md)

**One fry falls over. Three might become your first tower.**

[![No build step](https://img.shields.io/badge/Setup-No_build_step-0f766e)](#run-locally)

[Run locally](#run-locally) · [Game modes](#pick-a-mode) · [Watch the demo](../assets/fry-builder-demo.mp4) · [Optional MCP](../MCP_INTEGRATION.md) · [简体中文](../README.md)

</div>

A 3D building game where fries and nuggets become structures that can tip, slide, and collapse. Built with Three.js and cannon-es as a [single HTML application](../index.html), with desktop and touch controls.

<p align="center"><a href="../assets/fry-builder-demo.mp4"><img src="../assets/fry-builder-keyframes.jpg" width="900" alt="Keyframes from the existing showcase video"></a></p>

The existing video mixes creative food imagery with a game segment. Select the image to watch it.

## Pick a mode

| Mode | What to try |
| --- | --- |
| Gallery | Explore and edit 12 preset builds. Gallery poses are not proof of physical stability. |
| Sandbox | Place pieces with a ghost preview, try the blueprint overlay, and see how gravity changes your design. |
| Tower challenge | Use fries only, reach the height target, and hold it for five seconds. |

Challenge levels: **Easy** uses 20 fries for 0.55 m with no wind; **Pro** uses 16 for 0.80 m with light wind; **Wild Wind** uses 14 for 1.05 m with stronger gusts. Best scores are stored locally in the browser.

<details>
<summary>Video poster</summary>

<p align="center"><a href="../assets/fry-builder-demo.mp4"><img src="../assets/fry-builder-poster.jpg" width="200" alt="Poster from the existing FriesCraft showcase video"></a></p>

The poster uses creative food imagery; it is not a screenshot of the game interface.

[Open the PDF contact sheet](../assets/fry-builder-keyframes.pdf).

</details>

## Run locally

No npm install or build step is required:

```bash
git clone https://github.com/yuzhang-zhong/mcd-fries-architect.git
cd mcd-fries-architect
python -m http.server 8080
```

Open **http://localhost:8080** in a modern WebGL-capable browser. The game loads Three.js 0.160.0 and cannon-es 0.20.0 from jsDelivr, so an internet connection is needed. It is not a fully offline build.

- Desktop: drag to orbit, scroll to zoom, click to place, `Q/E` to rotate, and `W/S` to tilt.
- Touch: drag to orbit, tap to place, and use the floating rotation/tilt controls.
- The in-game language switch supports **Chinese and English**. Other README languages are navigation pages, not additional game translations.
- Try a three-fry tent before building upward. The game's gravity, friction, and stability feedback are gameplay approximations, not engineering tools.

On the same local network, a phone can connect to the computer's LAN IP and port; availability depends on the network and firewall. If no 3D scene appears, check the browser console and whether the CDN is reachable.

Use the `中文` / `EN` controls in the upper-left panel to switch the game language.

Challenge difficulty also reduces friction. Small placement disturbances mean that a build that looks balanced may still fall. Scores remain in the current browser; results can be copied and screenshots exported for sharing.

## Controls

| Action | Desktop | Touch |
| --- | --- | --- |
| Orbit / zoom | Drag empty space / scroll | One-finger drag / pinch |
| Place a piece | Move the preview, then click | Drag the preview, then tap |
| Rotate / tilt | `Q` / `E`, then `W` / `S` | Floating ↺ ↻ ⤴ ⤵ controls |
| Adjust a gallery build | Select and drag; `Q/E/W/S/A/D`, `+/-`, `Del` | Select a piece and drag |
| Collapse the panel | — | Top-left 🍟 button |

The ghost preview indicates whether placement is possible. Center-of-mass and stability markers help inspect the state; they are not structural-engineering calculations.

## Physics

- Sandbox and challenge use cannon-es rigid-body collisions. Gravity is set to **-18 m/s²**, a gameplay parameter rather than a precise reproduction of real gravity.
- Friction decreases across the three difficulty levels: **0.60 → 0.50 → 0.42**.
- Wind pulses and placement disturbances make support area, center of mass, and building order matter.
- Three.js renders the scene, pieces, and preview. The game is contained in [`index.html`](../index.html).

## Project files

- [`index.html`](../index.html): the single-file 3D game.
- [`assets/`](../assets/): existing MP4, video poster, JPG and PDF keyframes.
- [`skills/mcd-fries-architect/SKILL.md`](../skills/mcd-fries-architect/SKILL.md): building companionship and optional MCP integration.
- [`i18n/`](./): README language entry points.
- [`MCP_INTEGRATION.md`](../MCP_INTEGRATION.md): integration requirements and boundaries.
- [`CONTEST_DECLARATION.md`](../CONTEST_DECLARATION.md): original contest declaration.

## Optional AI companion

The [companion Skill](../skills/mcd-fries-architect/SKILL.md) documents building guidance and optional nutrition, campaign, and nearby-store queries through the [McDonald's MCP server](https://github.com/M-China/mcd-mcp-server). It requires a separately configured compatible AI client. The game itself does not automatically connect to MCP, and MCP is not required to play.

WorkBuddy is one example of a compatible client. Nutrition, campaign, and store information must follow the official live results; see [MCP_INTEGRATION.md](../MCP_INTEGRATION.md) for the full boundaries.

## Inspiration and status

Inspired by the McDonald's Argentina “Jugá con la comida” triceratops tutorial and community fry-building creations, with additional original presets.

The gallery retains triceratops, 麦当龙, turtle, and hairy-crab designs, alongside original rocket, octopus, cactus, birthday-cake, snowman, crown, golden-arches M, and heart presets.

This is an independently developed **contest entry**, not an official McDonald's product, endorsement, or claim of an award. Food information, availability, and prices must be checked through official channels; outputs are not medical or nutritional advice. The original [contest declaration](../CONTEST_DECLARATION.md) is unchanged.

Other language pages: [ES](README.es.md) · [JA](README.ja.md) · [KO](README.ko.md) · [FR](README.fr.md) · [DE](README.de.md) · [PT](README.pt.md) · [RU](README.ru.md) · [AR](README.ar.md) · [HI](README.hi.md).
