# TODO Archive

> 已处理条目归档。状态标记：`✅**已完成**`（完成）+ `（完成：YYYY-MM-DD HH:MM）`；`✅**已更新**`（决定变更，新决定另记 TODO.md）+ `（更新：YYYY-MM-DD HH:MM）`。保留归档供日后回溯排查，与 CHANGELOG 互补不重叠。

## 🟢 绿色紧急度

### 流水线任务（来自 Scout）

- [ ] **T1** **生产 Team Playbook（Agent Team Playbook 智能体团队作战手册）**——按 Scout《机会研判报告》v3.3 执行（记录：2026-08-20 22:43；2026-08-21 20:05 产品名 Fleet → Team、product_id 同步改；2026-09-13 13:40 素材源路径修正；2026-09-14 报告 v3.1 → v3.3——团队规模 14 → 20、去 Claude Code 绑定通称 AI agents，规格细节以报告全文为准）：

  - **报告位置（唯一权威输入）**：`/Users/xhq/Developer/ProductStrategistAgent/docs/product/hot-trend-ai-agent-money-system.md`（现 v3.3，`product_id: Team-Playbook-v3`；产品 2026-08-21 定名 The Agent Team Playbook，见报告 §0 定名说明——原拟名 Fleet Playbook 弃用）。生产前**通读全文**，重点 §4（生产规格）、§7（内容红线）、§9（追溯标签）。
  - **产品形态**：数字手册 + 模板包 + clone 即得整合包三合一，**全英文**，7 个模块（含 §4 第 7 模块 Cross-Harness Portability），文件夹结构照 §4 成品样例。
  - **素材源（可直读，含路径与用途）**：
    - `/Users/xhq/Developer/ProductStrategistAgent/`（Scout 本项目）：角色化 CLAUDE.md 五段式样板（`CLAUDE.md`——「你是谁 / 产物契约 / 工具 / 约束 / 流水线位置」）+ 真实踩坑沉淀成硬约束的案例（同文件「## 你的约束」章节——《可用销售与引流渠道》《聚焦被动收入》两份规则；原独立文件 `.claude/rules/available-channels.md` 已于 2026-09-13 并入此处，勿再找旧路径；§4 模块 3 的活教材）。
    - `/Users/xhq/Developer/DayTradingAgent/`（Victor）：最成熟的多 skill 实战仓库——案例走读（§4 模块 6）的主教材（`.claude/skills/` 多 skill 组织、`CLAUDE.md`、TODO / MEMO / CHANGELOG 项目管理文件体系）；**注意：只作为组织方法的展示素材，交易策略参数、回测数据、信号记录、账户信息一律不得进产品（§7 红线）**。
    - `/Users/xhq/Developer/CapabilityManagerAgent/`（Prometheus）：全局 ↔ 镜像同步机制素材（`claude/` 开源镜像目录组织），可作模块 1「规范沉淀三层体系」的补充案例。
  - **完成标准（验收线）**：手册里每个模板都真实可用（CLAUDE 模板拿去能直接建 agent、registry 模板能直接抄）——**不交付跑不起来的包**（v2 教训，报告 §6 第 1 条）。本地实测「从零建一个 demo agent」流程跑通后再交。
  - **产物**：成品 + 《产品说明》写本项目 `artifacts/`，产品说明**必须带 `product_id: Team-Playbook-v3`**（下游 Vendy / Buzz / Echo 归因用，见你 CLAUDE.md 产物契约）。
  - **生产期间素材与报告如有出入**：以报告为准；报告本身有疑义，回 Scout 项目会话提，不在生产中擅自改规格。

  ✅**已完成**（完成：2026-09-13 18:50）——产品全 7 模块完成并交付 `artifacts/agent-team-playbook/`（模块 01–03 为 2026-08-20 先行产出，本次续产模块 04–07、重画 20-agent SVG、全包数字对齐 v3.3）；《产品说明》交付 `artifacts/team-playbook-spec.md`（含 `product_id: Team-Playbook-v3`、建议定价 $49/早鸟 $35、Payloadz + PayPal 交付、验收记录）；验收线达成：tmp/demo-agent 从零建 agent（Sage 校对员）+ 本地 Claude Code v2.1.226 真实会话跑通产物契约（Proof Report 四节结构、source 溯源、逐条行号引用、埋错全数抓出）；内容红线扫描通过（无交易策略 / 回测 / 信号 / 账户内容）。详见 CHANGELOG 2026-09-13 条目。
