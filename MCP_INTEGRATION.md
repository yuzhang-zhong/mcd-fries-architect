# MCP 集成说明

薯条建筑师 FriesCraft 通过麦当劳 MCP Server 把"3D 虚拟拼装"闭环到"真实原料包配送"。

## MCP Server

- 名称：`mcd-mcp`
- 协议：Streamable HTTP
- 地址：`https://mcp.mcd.cn`
- 鉴权：`Authorization: Bearer YOUR_MCP_TOKEN`（Token 申请见 [mcd-mcp-server](https://github.com/M-China/mcd-mcp-server)）

## 调用流程

```
用户在 3D 画板完成设计
   ↓ 点击「生成原料包下单口令」
口令文本（作品名 + 薯条/鸡块/汉堡数量 + 步骤指令）
   ↓ 粘贴到 WorkBuddy（已安装 skill/SKILL.md）
Skill 解析口令，按序调用 MCP：
   1. query-nearby-stores / delivery-query-stores   定位门店
   2. query-meals / query-meal-detail               确认中薯、麦乐鸡在售并取餐品编码
   3. available-coupons + auto-bind-coupons         一键领券
      query-store-coupons                           查本店可用券
   4. calculate-price                               算价（商品金额/配送费/优惠/应付）
   5. —— 向用户出示清单，等待显式确认 ——
   6. create-order                                  下单，返回支付链接
   7. query-order / cancel-order / order-list       售后
```

## 实际使用的 Tools 与业务价值

| Tool | 在本项目中的作用 |
|---|---|
| `query-nearby-stores` / `delivery-query-stores` | 找到能送出"原料包"的门店 |
| `delivery-query-addresses` / `delivery-create-address` | 外送地址管理 |
| `query-meals` / `query-meal-detail` | 把"N 根薯条 + N 块鸡块"映射为真实可售餐品（中薯×N、麦乐鸡 5 块×N） |
| `available-coupons` / `auto-bind-coupons` / `query-store-coupons` | 下单前自动领券，帮用户省钱 |
| `calculate-price` | 下单前列出价格清单，用户确认后再支付 |
| `create-order` | 创建真实订单并返回支付链接 |
| `query-order` / `cancel-order` / `order-list` | 订单进度查询与取消 |
| `list-nutrition-foods` | 回答"这一盘麦当龙多少热量"（画板内估算仅作参考） |
| `campaign-calendar` | 推荐麦当劳当月活动，与拼装玩法联动安利 |

## 业务价值

1. **从流量到订单的闭环**：把"麦当龙"社交热度直接翻译成原料包订单，复刻麦当劳官抖"团购原料包"的成功路径，且入口在 AI 对话里，转化链路更短。
2. **亲子/聚会场景增量**：拼装教程 + 一键下单，天然适配家庭与派对场景（可扩展对接 `query-party-city` 主题活动预约）。
3. **UGC 放大器**：作品截图 + 口令都是可分享的社交货币，每个分享者都是新的下单入口。
4. **安全克制**：先算价、经确认、再下单；营养信息以 `list-nutrition-foods` 真实数据为准。
