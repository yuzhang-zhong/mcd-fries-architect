# FriesCraft

**One fry falls over. Three might become your first tower.**

A 3D building game where fries and nuggets become structures that can tip, slide, and collapse. Built with Three.js and cannon-es as a single HTML application, with desktop and touch controls.

[简体中文 / full documentation](../README.md) · [Watch the demo](../assets/fry-builder-demo.mp4) · [Optional MCP integration](../MCP_INTEGRATION.md)

[![Poster from the existing FriesCraft showcase video](../assets/fry-builder-poster.jpg)](../assets/fry-builder-demo.mp4)

The showcase mixes creative food imagery with a game segment. Its poster is not a screenshot of the game interface.

## Pick a mode

| Mode | What to try |
| --- | --- |
| Gallery | Explore and edit 12 preset builds. Gallery poses are not proof of physical stability. |
| Sandbox | Place pieces with a ghost preview, try the blueprint overlay, and see how gravity changes your design. |
| Tower challenge | Use fries only, reach the height target, and hold it for five seconds. |

Challenge levels: **Easy** uses 20 fries for 0.55 m with no wind; **Pro** uses 16 for 0.80 m with light wind; **Wild Wind** uses 14 for 1.05 m with stronger gusts. Best scores are stored locally in the browser.

![Keyframes from the existing showcase video](../assets/fry-builder-keyframes.jpg)

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

## Optional AI companion

The [companion Skill](../skill/SKILL.md) documents building guidance and optional nutrition, campaign, and nearby-store queries through the [McDonald's MCP server](https://github.com/M-China/mcd-mcp-server). It requires a separately configured compatible AI client. The game itself does not automatically connect to MCP, and MCP is not required to play.

## Inspiration and status

Inspired by the McDonald's Argentina “Jugá con la comida” triceratops tutorial and community fry-building creations, with additional original presets.

This is an independently developed **contest entry**, not an official McDonald's product, endorsement, or claim of an award. Food information, availability, and prices must be checked through official channels; outputs are not medical or nutritional advice. The original [contest declaration](../CONTEST_DECLARATION.md) is unchanged.

Other language pages: [ES](README.es.md) · [JA](README.ja.md) · [KO](README.ko.md) · [FR](README.fr.md) · [DE](README.de.md) · [PT](README.pt.md) · [RU](README.ru.md) · [AR](README.ar.md) · [HI](README.hi.md).
