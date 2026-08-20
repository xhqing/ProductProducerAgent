# Changelog

## [Unreleased]

### 新增（TODO.md 初始化 + 首个流水线任务：生产 Fleet Playbook）

- **为什么改**：Scout《机会研判报告》v3.1（`product_id: Fleet-Playbook-v3`）已定稿，流水线接力进入生产环节；经用户与 Scout 会话确认，交接方式为把生产任务直接写入本项目 TODO.md（而非仅在报告里附交接清单），Wright 会话开工时读 TODO 即获得完整生产指令——报告绝对路径、素材源清单（三个仓库路径与各自用途）、验收线、product_id 归因要求一次到位。
- **改了什么**：新建项目根 `TODO.md`（绿色紧急度「流水线任务」分节，含 Fleet Playbook 生产任务全文：报告位置 / 产品形态 / 素材源含路径 / 完成标准 / 产物与 product_id 要求 / 规格冲突处理原则）与 `TODO-archive.md`（归档空初始化）。素材源指定：ProductStrategistAgent（角色化 CLAUDE.md 五段式 + rules 踩坑沉淀样板）、DayTradingAgent（多 skill 组织主教材，交易内容禁入红线）、CapabilityManagerAgent（全局 ↔ 镜像同步补充案例）。

### 变更（Visitors 徽章更名 Visits/day (14d)：alt 文本与 xhqing 集中统计新 label 对齐）

- **为什么改**：用户要求（2026-08-17）访问量徽章名需表达「最近半月日均访问量」口径——xhqing 集中统计侧的 badge JSON label 已从 `Visitors` 改为 `Visits/day (14d)`（`Visits/day` 是 shields.io 表达日均的惯例写法、`(14d)` 标注 14 天滚动窗口），各仓 README 的徽章 alt 文本同步对齐，避免 alt 与徽章实际显示文字脱节。
- **改了什么**：README 徽章区 `alt="Visitors"` → `alt="Visits/day (14d)"`，仅改 alt 文本，endpoint URL、数据源、徽章口径均不变（口径改动记 xhqing 仓库 CHANGELOG，本仓只改 alt）。

### 变更（Visitors 徽章 alt 文本首字母大写：README 访问量徽章命名统一）

- **为什么改**：用户指令（2026-08-16）「Visitors 徽章全局统一，首字母大写」——配合全局 `~/.claude/CLAUDE.md`「徽章英文首字母必须大写」新规，集中统计上线时挂的访问量徽章 `alt="visitors"` 为小写存量，与 badge JSON label（`Visits/day`）及大写规范不一致，本次一次收口。
- **改了什么**：README（EN/CN）徽章区 visitors 徽章 `alt="visitors"` → `alt="Visitors"`，仅改 alt 显示文本，endpoint URL 与数据源不变。

### 新增（README 访问量徽章——舰队集中式访问统计）

- **为什么改**：全舰队上线集中式「真去重」访问统计（图片徽章方案无法去重，走官方 Traffic API 路线）：统计集中部署在 xhqing 仓库（`scripts/update_traffic.py` + 每日 GitHub Action），各 fleet 仓库只需在 README 挂徽章、零运行负担。
- **改了什么**：README（EN/CN）徽章区新增 visitors 徽章（shields.io endpoint 指向 `xhqing/xhqing` 仓库 `traffic/badges/<repo>.json`，由每日采集的官方 Traffic API 数据更新）。徽章数字含义：按日去重访客的累计（GitHub 只提供每日 uniques，跨天不去重），自 2026-08-16 起累计。
