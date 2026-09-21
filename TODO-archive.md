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
  ✅**已迁移**（迁移：2026-09-19 20:51）——本条及 GitComic 全部产品内容随 GitComic 子项目建仓迁往 `/Users/xhq/Developer/GitComic`（归档与制作资产在该仓 `artifacts/`），本条留在本归档仅作指针。

## 🟡 黄色紧急度

### 漫画构建链气泡指向审计（遗留变体 + 自动检查）

- [ ] **T3** **气泡尾巴→说话人归属的系统性审计与自动校验**——0.2.1 修复了交付版（pages-art）p12/p06 的气泡指向错人，但同类问题未彻底清查（记录：2026-09-18 21:40）：
  - 0.1.0 遗留变体（`src/pages`，非交付版本）p04 的 Pixi 气泡尾 'tl' 指向空处已确认；其余页未逐一几何复核——若该变体复活使用需先全量审计；
  - 交付版 pages-art 现靠人工 VLM 抽查，建议后续在构建链加一道「气泡尾巴必须指向画面内某角色区域」的自动校验（几何规则或 VLM），新增/改版页面时防回归。
  ✅**已迁移**（迁移：2026-09-19 20:51）——本条仍为**活跃待办**，随 GitComic 子项目建仓迁往 `/Users/xhq/Developer/GitComic` 的 TODO.md 继续跟踪（编号沿用 T3），本条留在本归档仅作指针。

- [ ] **T4** 美国麻将新手 Playbook 双语生产（英文主品 + 中文版一起出，用户 2026-09-20 裁定）（记录：2026-09-20 18:10）
  - **唯一权威输入**：ProductStrategistAgent 仓 `artifacts/mahjong-us-boom-report.md`（trend_id: trend_mahjong_us_boom）。生产前先通读全文，尤其 §2 关键事实（美国主流玩法是 American Mahjong / NMJL 年度卡规则，不是中国麻将）、§6 盈利模式、§7 两条链路。
  - **范围（两个产品一起生产）**：
    1. 英文版主品（product_id: `product_am_mahjong_playbook`）：American Mahjong 新手 Playbook + 聚会主办包——英文 PDF 电子书 + 可打印速查表附赠件，定价锚 $9.99（首发券 $6.99）。内容主体：144 张牌图解 → American 规则分步教学（Charleston、Joker、怎么读年度卡）→ 新手最常犯错误 → How to Host Your First Mahjong Night（聚会主办清单：人数、零食、教学局流程）。速查表是附赠件不是主体。
    2. 中文版（product_id: `product_am_mahjong_playbook_cn`）：《美国麻将玩法入门》，面向在美华人 / 留学生（链路 2）。角度是「会打中国麻将的人学美国麻将」：对照讲差异（年度卡 vs 开放胡牌、Joker、Charleston），不是从零教麻将。
  - **合规红线（硬约束）**：NMJL 年度卡片上的具体牌型有版权，产品内一律不得复制；产品定位是「教你读懂官方卡 + 怎么打」，并引导读者去买官方卡（$14，NMJL 官网）。规则、流程、术语本身可以讲。
  - **差异化要求（避红海）**：Etsy 速查表已红海，不做「又一张 cheat sheet」；主体是「新手到主办第一场麻将局的完整路径」——这是竞品分析确认的空档。
  - **验收线**：① 英文版：非麻将背景的美国读者 30 分钟内能看懂 Charleston 流程、Joker 用法、怎么读年度卡，host 清单可直接照做办局；② 英文无语法硬伤（校对工具过一遍 + 人工抽读）；③ 中文版：已会中国麻将的读者 20 分钟内理解 American 规则与中国的差异、能上桌跟美国朋友玩；④ 速查表排版 A4 可打印；⑤ 产物文件带 trend_id / product_id 标签（下游归因用）。
  - **交付位置**：初版产物落本仓 `artifacts/mahjong/`（英文版 + 中文版分文件）；产品线成型后再议是否独立子仓（参照 GitComic 先例，由用户裁定）。
  - **不在本任务内**：候选 B（中美双规则对照手册 `product_cn_am_dual_rules`）——等本产品验证付费能力后再派；上架与引流属下游 Mason / Buzz / Vendy。

  ✅**已完成**（完成：2026-09-21 19:05）——两产品完成并交付本仓 `artifacts/mahjong/`：英文主品《The American Mahjong Playbook》22 页 PDF + 单页 A4 速查表（含 How to Host 专章：装备采购表 + 2.5 小时教学局时刻表），中文版《美国麻将玩法入门》20 页 PDF + 速查表（中美差异对照表主菜 + 中国玩家十大坑）；规则经多源交叉核实（含关键修正：弃 Joker 为合法但成死牌，非「禁止弃出」）；分语言双 zip（en/zh 各 3 文件，MD5 比对一致）；NMJL 牌型版权红线零连例，三处独立身份声明 + 引导官网购卡；T4 五条验收线全过（write-good 校对无硬伤 + 拼写筛查 + 人工抽读；像素级排版验证含封面麻将字符墨迹分布定量验证）；完成即交接：Mason 仓 handoff.md 产品三节 + 双仓 CHANGELOG 各记一条。详见本仓 CHANGELOG 2026-09-21 条目。
