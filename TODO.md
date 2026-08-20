# TODO

> 活跃待办。已处理条目归档至 `TODO-archive.md`（看到即跳过）。每条待办附记录时间戳「（记录：YYYY-MM-DD HH:MM）」；前后矛盾的待办以最新时间戳为准。超低频备忘（无排期压力）不放本文件，放 `MEMO.md`。

## 🟢 绿色紧急度

### 流水线任务（来自 Scout）

- [ ] **生产 Fleet Playbook（Agent Fleet Playbook 智能体军团作战手册）**——按 Scout《机会研判报告》v3.1 执行（记录：2026-08-20 22:43）：

  - **报告位置（唯一权威输入）**：`/Users/xhq/Documents/Projects/ProductStrategistAgent/docs/product/hot-trend-ai-agent-money-system.md`（v3.1，`product_id: Fleet-Playbook-v3`）。生产前**通读全文**，重点 §4（生产规格）、§7（内容红线）、§9（追溯标签）。
  - **产品形态**：数字手册 + 模板包 + clone 即得整合包三合一，**全英文**，7 个模块（含 §4 第 7 模块 Cross-Harness Portability），文件夹结构照 §4 成品样例。
  - **素材源（可直读，含路径与用途）**：
    - `/Users/xhq/Documents/Projects/ProductStrategistAgent/`（Scout 本项目）：角色化 CLAUDE.md 五段式样板（`CLAUDE.md`——「你是谁 / 产物契约 / 工具 / 约束 / 流水线位置」）+ 项目专属 rules 样板（`.claude/rules/available-channels.md`——真实踩坑沉淀成硬约束的案例，§4 模块 3 的活教材）。
    - `/Users/xhq/Documents/Projects/DayTradingAgent/`（Victor）：最成熟的多 skill 实战仓库——案例走读（§4 模块 6）的主教材（`.claude/skills/` 多 skill 组织、`CLAUDE.md`、TODO / MEMO / CHANGELOG 项目管理文件体系）；**注意：只作为组织方法的展示素材，交易策略参数、回测数据、信号记录、账户信息一律不得进产品（§7 红线）**。
    - `/Users/xhq/Documents/Projects/CapabilityManagerAgent/`（Prometheus）：全局 ↔ 镜像同步机制素材（`claude/` 开源镜像目录组织），可作模块 1「规范沉淀三层体系」的补充案例。
  - **完成标准（验收线）**：手册里每个模板都真实可用（CLAUDE 模板拿去能直接建 agent、registry 模板能直接抄）——**不交付跑不起来的包**（v2 教训，报告 §6 第 1 条）。本地实测「从零建一个 demo agent」流程跑通后再交。
  - **产物**：成品 + 《产品说明》写本项目 `artifacts/`，产品说明**必须带 `product_id: Fleet-Playbook-v3`**（下游 Vendy / Buzz / Echo 归因用，见你 CLAUDE.md 产物契约）。
  - **生产期间素材与报告如有出入**：以报告为准；报告本身有疑义，回 Scout 项目会话提，不在生产中擅自改规格。
