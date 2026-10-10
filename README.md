| [EN](./i18n/README.en.md) | [中文](./README.md) | [ES](./i18n/README.es.md) | [JA](./i18n/README.ja.md) | [KO](./i18n/README.ko.md) | [FR](./i18n/README.fr.md) | [DE](./i18n/README.de.md) | [PT](./i18n/README.pt.md) | [RU](./i18n/README.ru.md) | [AR](./i18n/README.ar.md) | [HI](./i18n/README.hi.md) |

# 薯条建筑师 FriesCraft 🍟🗼

> 真·物理重力的麦当劳薯条 3D 搭建游戏 —— 薯条会倒、会滑、会塌。电脑手机都能玩。

📹 **演示视频**（真重力、会塌的那种）—— 点海报直接播放：

<a href="./assets/fry-builder-demo.mp4"><img src="assets/fry-builder-poster.jpg" width="300" alt="FriesCraft 演示视频首帧"></a>

🖼️ **关键帧速览**（完整收藏版：[PDF 图集](./assets/fry-builder-keyframes.pdf)）：

<img src="assets/fry-builder-keyframes.jpg" width="720" alt="FriesCraft 关键帧图集">

> 视频直链：[fry-builder-demo.mp4](./assets/fry-builder-demo.mp4)

## 🌐 多语言 / Languages

- 应用内已支持 **中文 / English** 切换（左上角面板右上方 `中文` / `EN` 按钮）。
- README 当前主文为中文，下方附英文速览，内容与应用玩法保持同步。

## English Overview

**FriesCraft** is a 3D fry-building game with real rigid-body physics (three.js + cannon-es): pieces can tip, slide, and collapse under gravity.

### Core Modes
- **Gallery**: browse 12 preset builds (official triceratops, viral fry dragon, turtle, crab, rocket, heart, etc.).
- **Sandbox**: free placement with ghost preview, blueprint overlay, stability feedback, and share/screenshot tools.
- **Challenge**: fry-only tower mode with 3 levels (Easy / Pro / Wild Wind), height goals, and a 5-second stability win condition.

### Controls
- Desktop: drag to orbit, wheel to zoom, click to place, `Q/E/W/S` rotate & tilt.
- Mobile: touch drag/orbit + floating direction pad (`↺ ↻ ⤴ ⤵`).

### Quick Start
```bash
start index.html           # Windows
open index.html            # macOS
python -m http.server 8080 # local server for phone testing
```

## 这是什么

2026 年全网爆火的"麦当龙"玩法：把麦乐鸡当身体、薯条当四肢和尾巴，拼出各种造型。**薯条建筑师**把它做成了带真实物理引擎（cannon-es）的 3D 搭建游戏：

- 🖐️ **自由搭建**：真实重力 + 幽灵预览轻点放置，实时显示塔高和稳定度；可开**蓝图模式**（半透明虚影）照着 12 种造型拼
- 🧭 **搭建辅助**：重心投影点实时变色（绿稳/橙晃/红危）、突破里程碑播报、幽灵红绿提示（预算耗尽变红）
- 🗼 **高塔挑战（核心玩法）**：限定薯条搭塔，达标并稳住 5 秒获胜，胜利彩带庆祝。三档难度：
  - 新手：20 根薯条 / 0.55m / 无风
  - 老手：16 根薯条 / 0.80m / 轻风扰动
  - 妖风：14 根薯条 / 1.05m / 随机强风突袭 💨
- 📖 **灵感图鉴**：12 种造型一键上桌——麦当劳阿根廷**官方三角龙配方**（2 鸡块 + 14 薯条）、网红麦当龙、小乌龟、大闸蟹，以及原创的火箭、章鱼、仙人掌、生日蛋糕、雪人、皇冠、金拱门 M、爱心
- 📱 **手机友好**：触屏拖拽转视角、轻点放置、悬浮方向键调角度、面板可收起，竖屏也能玩
- 📣 **社交裂变**：战绩一键复制分享，截图导出晒图；最好成绩本地存档

## 难度从哪来（物理设计）

- 真实重力场（-18 m/s²）+ 刚体碰撞，单根薯条立不住，三脚"帐篷"结构才稳
- 难度越高摩擦越低（0.6 → 0.42），薯条更滑
- 老手/妖风档随机风力脉冲，搭高塔要考虑重心和抗风
- 放置瞬间带轻微"手抖"扰动，还原真实手感

## 目标用户

- 爱玩"麦当龙"的麦门信徒、亲子家庭、聚会玩家
- 喜欢《堆塔》《叠叠乐》类物理小游戏的休闲玩家
- 内容创作者：战绩分享 + 截图天然是 UGC 素材

## 快速开始

无需构建，浏览器直接打开（手机电脑均可）：

```bash
start index.html           # Windows
open index.html            # macOS
python -m http.server 8080 # 或起本地服务，手机扫码/同网段访问
```

## 操作说明

| 操作 | 桌面端 | 手机端 |
|---|---|---|
| 旋转视角 / 缩放 | 拖动空白处 / 滚轮 | 单指拖动 / 双指捏合 |
| 放置积木 | 移动鼠标出现幽灵预览，单击放置 | 拖动出现预览，轻点放置 |
| 调整方向 | `Q`/`E` 旋转、`W`/`S` 倾倒 | 右下角悬浮按钮 ↺↻⤴⤵ |
| 图鉴微调 | 点选积木拖动，`Q/E/W/S/A/D`，`+/-` 调长短，`Del` 删除 | 点选积木拖动 |
| 面板收起 | — | 左上角 🍟 按钮 |

## 与麦当劳 MCP 的联动（可选）

画板本身零依赖可玩。配套 Skill（`skill/SKILL.md`）面向接了[麦当劳 MCP](https://github.com/M-China/mcd-mcp-server) 的 AI 客户端（如 WorkBuddy），提供：营养热量查询（`list-nutrition-foods`，游戏内热量已用其校准）、活动日历安利（`campaign-calendar`）、以及"玩完去线下门店拼真薯条"的到店查询（`query-nearby-stores`）。详见 [MCP_INTEGRATION.md](./MCP_INTEGRATION.md)。

## 项目结构

```
mcd-fries-architect/
├── index.html              # 游戏本体（three.js + cannon-es 单文件应用）
├── assets/
│   ├── fry-builder-demo.mp4      # 演示视频（44.5s）
│   ├── fry-builder-poster.jpg    # 视频首帧海报（README 预览用）
│   ├── fry-builder-keyframes.jpg # 关键帧横幅图集（README 内嵌）
│   └── fry-builder-keyframes.pdf # 关键帧图集收藏版（6 帧）
├── skill/
│   └── SKILL.md            # WorkBuddy Skill：搭建陪玩 + MCP 联动指南
├── README.md               # 本文件
├── MCP_INTEGRATION.md      # 麦当劳 MCP 集成说明
└── CONTEST_DECLARATION.md  # 参赛声明（官方文件，未改动）
```

## 创意来源

- 麦当劳阿根廷官方"Jugá con la comida"三角龙教程（2 麦乐鸡 + 14 薯条）
- 抖音/小红书"麦当龙挑战赛"UGC 二创（麦当龙、大闸蟹、乌龟等）
- 本项目原创预设：金拱门 M、薯条爱心、薯条火箭、薯条章鱼、仙人掌盆栽、生日蜡烛蛋糕、麦乐鸡雪人、麦门皇冠

## 声明

本项目为麦当劳程序员节创意开发大赛参赛作品，由参赛者独立开发，非麦当劳官方产品。餐品信息、价格及供应状态以麦当劳官方渠道实时结果为准。详见 [CONTEST_DECLARATION.md](./CONTEST_DECLARATION.md)。
