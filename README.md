<p align="center">
  <a href="i18n/README.en.md">English</a> · <strong>简体中文</strong> ·
  <a href="i18n/README.es.md">ES</a> · <a href="i18n/README.ja.md">JA</a> ·
  <a href="i18n/README.ko.md">KO</a> · <a href="i18n/README.fr.md">FR</a> ·
  <a href="i18n/README.de.md">DE</a> · <a href="i18n/README.pt.md">PT</a> ·
  <a href="i18n/README.ru.md">RU</a> · <a href="i18n/README.ar.md">AR</a> ·
  <a href="i18n/README.hi.md">HI</a>
</p>

<h1 align="center">薯条建筑师 · FriesCraft</h1>

<p align="center"><strong>一根薯条会倒。三根，也许能搭出第一座塔。</strong><br>有重力、会滑落、会坍塌的 3D 休闲搭建游戏。</p>

<p align="center">
  <a href="assets/fry-builder-demo.mp4">看演示</a> ·
  <a href="#开始搭建">本地开玩</a> ·
  <a href="#先玩哪一种">三种玩法</a> ·
  <a href="MCP_INTEGRATION.md">可选 MCP 联动</a>
</p>

<p align="center">
  <a href="assets/fry-builder-demo.mp4"><img src="assets/fry-builder-poster.jpg" width="280" alt="FriesCraft 已有展示视频的食物造型海报，点击查看视频"></a>
</p>

<p align="center"><sub>已有展示视频的封面，包含创意食物视觉，不是游戏界面截图。<a href="assets/fry-builder-demo.mp4">打开 MP4 演示</a></sub></p>

把薯条当梁柱、鸡块当底座，先摆出一个造型，再看看它能不能站稳。FriesCraft 用 **Three.js + cannon-es** 做成一个无需构建的单文件网页游戏，支持桌面和触屏操作，应用内可切换中文 / English。

> 独立开发的麦当劳程序员节创意开发大赛参赛作品，**不是麦当劳官方产品，参赛不代表获奖或官方背书**。无需连接 MCP 即可玩游戏；加载 3D 库需要网络。

## 先玩哪一种

| 模式 | 适合怎么开始 | 你会看到什么 |
| --- | --- | --- |
| **灵感图鉴** | 先选一个造型，看看怎样组合 | 12 种预设，可选中积木微调；图鉴用于展示与编辑造型 |
| **自由搭建** | 用幽灵预览放下第一根薯条 | 刚体重力、碰撞、稳定度反馈；可开蓝图虚影照着搭 |
| **高塔挑战** | 只用薯条，冲过目标高度 | 有限预算、三档难度；达到高度并稳住 5 秒才获胜 |

**第一次玩：**先试三根薯条撑成“帐篷”，再加上层结构。单根竖着放容易倒，把重心压低通常比一味堆高更有用。图鉴造型不等于已经通过物理稳定性验证，想试重力请进入自由搭建或挑战模式。

![FriesCraft 现有展示视频的六帧图集，包含创意食物视觉与游戏画面](assets/fry-builder-keyframes.jpg)

[查看 PDF 图集](assets/fry-builder-keyframes.pdf)

### 高塔挑战

| 难度 | 薯条预算 | 目标高度 | 环境 |
| --- | ---: | ---: | --- |
| 新手 | 20 根 | 0.55 m | 无风 |
| 老手 | 16 根 | 0.80 m | 轻风扰动 |
| 妖风 | 14 根 | 1.05 m | 更强的随机风力 |

三档都需要达标后**稳住 5 秒**。难度提升还会降低摩擦；放置时的轻微扰动，让“看起来稳”不一定真的稳。最好成绩保存在当前浏览器本地，可复制战绩或导出截图分享。

## 开始搭建

推荐使用本地 HTTP 服务，不需要 npm 安装或构建：

```bash
git clone https://github.com/yuzhang-zhong/mcd-fries-architect.git
cd mcd-fries-architect
python -m http.server 8080
```

浏览器打开 **http://localhost:8080**。电脑与手机在同一局域网时，手机可访问电脑的局域网 IP 和同一端口；是否可达取决于网络与防火墙设置。

- 游戏通过 jsDelivr 加载 Three.js 0.160.0 与 cannon-es 0.20.0，**不是完全离线版**。
- 需要支持 WebGL 的现代浏览器。若打开后没有 3D 场景，先检查浏览器控制台与 CDN 是否可达。
- 左上面板的 `中文` / `EN` 按钮切换游戏语言。其他语言 README 是导航入口，不代表游戏已有对应翻译。

## 操作速查

| 操作 | 桌面端 | 手机端 |
| --- | --- | --- |
| 旋转视角 / 缩放 | 拖动空白处 / 滚轮 | 单指拖动 / 双指捏合 |
| 放置积木 | 移动鼠标预览，单击放置 | 拖动预览，轻点放置 |
| 调整方向 | `Q` / `E` 旋转，`W` / `S` 倾倒 | 悬浮按钮 ↺ ↻ ⤴ ⤵ |
| 图鉴微调 | 点选并拖动；`Q/E/W/S/A/D`、`+/-`、`Del` | 点选积木拖动 |
| 收起面板 | — | 左上角 🍟 按钮 |

幽灵预览会提示能否放置，重心标记与稳定度帮助观察状态，但不是工程结构安全计算。

## 物理手感从哪里来

- 自由搭建与挑战使用 cannon-es 刚体碰撞，游戏重力设为 **-18 m/s²**，是玩法参数，不是现实重力的精确复刻。
- 摩擦系数随挑战难度从 **0.60 → 0.50 → 0.42** 变化。
- 风力脉冲与放置扰动让重心、支撑面积和搭建顺序都影响结果。
- Three.js 负责场景、积木和预览渲染；游戏本体集中在 [`index.html`](index.html)。

## 可选：让 AI 陪你搭

[`skill/SKILL.md`](skill/SKILL.md) 面向支持 Skill、并连接了[麦当劳 MCP](https://github.com/M-China/mcd-mcp-server) 的 AI 客户端，例如 WorkBuddy。它提供搭建陪玩指引，以及营养查询、活动日历和附近门店查询的联动说明。

**游戏本体不会因为打开网页就自动连接 MCP。** 这些能力需要客户端单独配置；营养、活动与门店信息以官方实时返回为准。完整边界见 [MCP_INTEGRATION.md](MCP_INTEGRATION.md)。

## 项目地图

```text
mcd-fries-architect/
├── index.html                 # 单文件 3D 游戏
├── assets/                    # 已有 MP4、视频海报、JPG / PDF 关键帧
├── skill/SKILL.md             # 搭建陪玩与可选 MCP 联动
├── i18n/                      # 多语言 README 入口
├── MCP_INTEGRATION.md
└── CONTEST_DECLARATION.md      # 原有参赛声明
```

## 创意来源与声明

项目灵感来自麦当劳阿根廷“Jugá con la comida”三角龙教程，以及“麦当龙”等食物搭建二创。图鉴保留三角龙、麦当龙、乌龟、大闸蟹等造型，并包含项目原创的火箭、章鱼、仙人掌、生日蛋糕、雪人、皇冠、金拱门 M 与爱心预设。

本项目由参赛者独立开发，与品牌官方产品或背书无关。餐品信息、价格及供应状态以官方渠道实时结果为准；项目输出不构成医疗、营养或其他专业建议。[参赛声明原文](CONTEST_DECLARATION.md)保留不变。
