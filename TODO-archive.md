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

- [ ] **T2** **生产 Git 漫画书试读版（Git-Comic-v1，先试读后全本）**——按 Scout《机会研判报告》执行（记录：2026-09-18 11:47）：

  - **报告位置（唯一权威输入）**：`/Users/xhq/Developer/ProductStrategistAgent/artifacts/git-comic-book-report.md`（`product_id: Git-Comic-v1`；`trend_id: TR-vibecoding-nontech-2026`）。生产前**通读全文**，重点 §2（产品形态与版本顺序）、§5（定价）、§7（风险与对策）。
  - **本次范围：20 页英文试读版，不做全本**（报告 §6 验证优先策略：先试读测 X/小红书互动，验证通过再启动全本 80-120 页——全本任务等验证结果另派）。
  - **制作流程（报告 §2 版本顺序决策）**：先用**中文写分镜脚本**定稿（质量最可控），再翻译嵌字出**英文版**；一套分镜双语出稿，中文版暂存不发（等国内 vibe coding 痛点成熟 + 英文版验证后作第二落点）。
  - **内容规格**：
    - 场景驱动：每章一个 vibe coder 真实惨案（AI 改坏 15 个文件 / 误删功能 / 丢几周工作成果），漫画剧情演示 git 怎么救——不是命令手册；
    - 五命令极简主义：commit（存档）/ diff（看 AI 改了什么）/ revert·checkout（后悔药）/ branch（安全试验田）/ .gitignore（保命清单）；
    - 试读 20 页 ≈ 2–3 章，开篇即最痛的惨案（丢工作成果）；
    - AI 生图，固定角色设定词，少角色多场景（画风跨页一致，§7 风险对策）。
  - **同步产出**：8–12 张竖版图卡（Git-Comic-Mini，`product_id: Git-Comic-Mini`，Instagram/小红书规格 1080×1350），从试读章节拆解——引流素材与产品共生（报告 §6）。
  - **验收线**：① 非技术读者 10 分钟能翻完试读并复述核心信息（「git 是 AI 时代的后悔药」）；② 同一角色跨页可识别（画风一致性）；③ 英文文案无语法硬伤（母语级校对）。
  - **产物**：试读 PDF + 图卡包 + 《产品说明》写本项目 `artifacts/`，产品说明**必须带 `product_id: Git-Comic-v1`**（下游 Vendy / Buzz / Echo 归因用）。
  - **生产期间素材与报告如有出入**：以报告为准；报告本身有疑义，回 Scout 项目会话提，不在生产中擅自改规格。

  ✅**已完成**（完成：2026-09-18 12:16）——20 页英文试读 PDF（`product_id: Git-Comic-v1`，0.1.0：封面 + 扉页 + 3 章正文 + 尾页 CTA，五命令全覆盖）+ 10 张图卡（`Git-Comic-Mini`，1080×1350 PNG）+ 《产品说明》（`artifacts/git-comic-spec.md`，含双 product_id、验收记录 6 项、下游接口）；制作链路：中文分镜定稿（`git-comic-v1/storyboard-zh.md`）→ SVG 矢量自绘（本机无 AI 生图通道，角色组件化单一来源，跨页一致性由构建机制物理保证——报告 §7 风险对策的替代落地）→ rsvg-convert 出 PDF/PNG；验收线达成：核心信息三重强化（p15 大字页 / p19 总结页 / p20 定位句）、角色组件复用 + OCR 抽查渲染无字体缺失、全文案逐条审校（濓号统一、术语同词同义）+ lint 文字越界零告警 + pypdf 页数尺寸验证；打包 `git-comic-v1-en-0.1.0.zip` + `git-comic-mini-en-0.1.0.zip`（逐文件比对一致）并完成 Wright→Mason 交接（handoff 追加产品二节 + 双仓 CHANGELOG 各记一条）。全本任务等验证结果另派。详见 CHANGELOG 2026-09-18 条目。
