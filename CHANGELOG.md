# Changelog

## [Unreleased]

### 变更（产品物理拆分为中英两个语言版本：独立源目录、独立交付，废止混装形态）

- **为什么改**：用户指令「产品需要分成中文版和英文版两个语言版本，不要混在一起打包」，拆分落法经确认选**物理拆源目录**。原形态为双语混装（`agent-team-playbook/` 20 文件中英并列、README.md ⇄ README_cn.md 平级互链 + 单 zip 交付）：单一语言场景下另一语言的文件是噪音、跨语言互链是死链，销售与交付两侧都要额外解释。
- **改了什么**（2026-09-17）：
  - **源目录物理拆分**：`artifacts/agent-team-playbook/`（混装 20 文件）→ `artifacts/agent-team-playbook-en/`（英文版 12 文件）+ `artifacts/agent-team-playbook-zh/`（中文版 12 文件）两棵自包含同构树；中文版文件名归位（`README_cn.md` → `README.md`，根入口与 7 个模块）；导航链接目标同步改写（含 07 模块带锚点的 `../README_cn.md#…`）；跨语言互链行移除（EN 8 处 `[简体中文](README_cn.md)`、ZH 8 处 `[English](README.md)`）；模块 05/06 教学正文中对团队仓库双语惯例的叙述（反引号代码样例）属教学内容不动。
  - **校验**：两棵树全量 md 链接存在性校验通过（模块 05 教学代码样例为校验器误报，非真实链接）；EN/ZH 各 12 文件与设计清点一致。
  - **立规**：CLAUDE.md「产物契约」新增「分语言交付（中英两版独立成包，不混装）」小节；「完成即交接」第 1 步打包命名改为 `-en-` / `-zh-` 双包。
  - **spec 同步**：`team-playbook-spec.md` 形态（双语混装 → 两版独立交付）、文件清单（两棵同构树、各 12 文件）、交付方式（两个分语言 zip）、验收记录（补拆分核对项）。
  - **下游交接**：SiteBuilderAgent `artifacts/handoff.md` 同步（两棵源树 + 分语言双 zip 口径 + 旧混装 zip 勿上架警示）；SiteBuilderAgent CHANGELOG 记录接收更新。
- **边界**：产品内容零改动（只动文件组织、文件名与链接层）；`product_id: Team-Playbook-v3`、产品版本 1.0.0 不变；**旧混装目录与旧 zip `agent-team-playbook-1.0.0.zip` 按用户决定原样保留**（仅存档、勿上架）；**分语言 zip 打包命令本轮未获执行、由用户自行执行**（`zip -r agent-team-playbook-en-1.0.0.zip agent-team-playbook-en` / 同款 `-zh-`），打包完成前下游以两棵源树为准。

### 新增（CLAUDE.md「完成即交接」规则：产品完成即自动向下游移交，不再等提醒）

- **为什么改**：用户要求「下次交接动作要自动完成，不要我提醒」。2026-09-16 的断链实证：产品 9/13 已完成验收，但产物只存在本仓被 .gitignore 忽略的 `artifacts/`（付费产品不进公开仓库），下游仓里的 GitHub 链接找不到东西，又没有任何主动交接动作，导致 Mason 反馈未收到交接、用户被迫提醒。交接是产品完成的一部分，不是可选步骤。
- **改了什么**（2026-09-16）：CLAUDE.md「你的产物（产物契约）」节新增「完成即交接」小节：产品完成的当次会话内自动执行四步——打包 zip + 验证、写下游仓被忽略目录的 `handoff.md`、双仓 CHANGELOG 各记一条（付费层细节不入公开明文）、对话报告 ✅ 清单；产品修订发新版重跑；交接对象按注册表六段流水线取直接下游（阵地未建成交 Mason、建成后转 Vendy，以注册表为准）；全程仅本机文件操作不碰 git。
- **边界**：属流程类规则，无法映射为可检测命令模式（无 hook 能识别「产品完成」语义事件），按元规则豁免工具强制、靠 CLAUDE.md 每次会话加载生效（与超集同步、双语 README 同步同款落法）；本次仅新增规则文本，交接动作本身已于同日前一条目执行完毕。

### 新增（交付实物 zip 打包 + Wright→Mason 正式移交，修复交接链路断裂）

- **为什么改**：Mason（SiteBuilderAgent）反馈未收到最新成品数字产品交接。核实属实：成品与《产品说明》9/13 已就绪且 spec 已写明六段流水线中 Mason（建设期）的职责，但从未向 Mason 侧做任何交接动作（SiteBuilderAgent 内无接手记录、无产物路径指引）；且本仓 `.gitignore` 整体忽略 `artifacts/`（付费产品不进公开仓库，有意为之），Mason 无从得知产物只存在本机，交接链路断裂。
- **改了什么**（2026-09-16）：
  - **打包交付实物 zip**：`artifacts/agent-team-playbook-1.0.0.zip`（70K、20 文件，`unzip -l` 与源目录逐文件比对一致）——spec「交付方式：整个 agent-team-playbook/ 目录打包 zip」的落地实物，供 Mason 上传 Payloadz。
  - **新建 Mason 侧交接输入**：`SiteBuilderAgent/artifacts/handoff.md`（放在 Mason 仓既有的产物接力忽略目录内，不进公开仓库）——含产物本机路径表、Mason 建设期任务清单、渠道硬约束、严禁推公开仓库警示、交接核对清单；定价等细节引用 spec，不在 handoff 与两仓 CHANGELOG 中重复明文（付费层信息只留在被忽略文件里）。
  - 同步在 SiteBuilderAgent 的 CHANGELOG 记录 handoff 新增。
- **边界**：未改动产品任何内容（zip 为纯打包，源目录 20 文件未动）；本次全部动作均为本机文件操作，不涉及 git 提交；handoff.md 归属 Mason 项目，后续是否随建站进展改写由 Mason 自定。

### 变更（team-playbook-spec 流水线接口对齐六段模型：补 Mason、Vendy 定位改为运营期）

- **为什么改**：spec「流水线接口」段写的还是旧五段模型（「下游：Vendy 拿本说明上架定价；Buzz 拿成品做引流内容」）——全局注册表（权威源）的销售流水线已是六段（Scout → Wright → **Mason** → Buzz → Vendy → Echo）：Mason（SiteBuilderAgent）在 Wright 之后、Buzz 之前建成交基础设施（支付链路配置、落地页），建好把购买链接交 Buzz；Vendy 在 Buzz 之后接运营期（定价执行、履约、售后、对账）。旧表述漏 Mason、且把「上架定价」直接给 Vendy 前置到引流之前，会误导下游交接顺序。用户问「现在可以找 Vendy 了吗」时暴露。
- **改了什么**（2026-09-13 22:30）：spec「流水线接口」段重写为六段顺序：Mason 建设期（Payloadz + PayPal 支付链路、落地页，建好购买链接交 Buzz）→ Buzz 引流（X 首发，bio 挂购买链接）→ Vendy 运营期（定价执行 $49 / 早鸟 $35、接单履约、售后、对账）→ Echo 归因（product_id）。
- **边界**：模块 06 对 Scout CLAUDE.md「下游：Wright 生产、Buzz 引流、Vendy 成交」的引用不改——那是对 Scout 仓库现状的忠实走读（Scout 的 CLAUDE.md 本身待 Scout 项目自行对齐六段，不归 Wright 代改）；模块 01 流水线图（L52）已含 Mason，无需改。

### 变更（Team Playbook「不含交易内容」边界声明纠偏：与公开仓库事实对齐）

- **为什么改**：用户两次指出边界声明与事实/未来决策脱节。第一轮：「不含交易策略、不含回测数据、不含信号记录」与公开仓库事实矛盾——实测 Victor（DayTradingAgent，public）的 `signals/`、`actions/` 目录就是公开的历史信号与执行记录，Swing（public）公开 20 年 × 37 股回测与完整策略文档，Markowitz 门面仓公开策略方法学；原表述把「付费手册不含交易内容」写成绝对化「不含」，括号「公开仓库永远公开；私有部分永远私有」又把策略 / 回测 / 信号暗示成「私有载荷」，模块 06 更直接称「交易内容本身是私有载荷」——而 README 明文邀请买家去公开仓库看橱窗，买家一点进去就会发现声明与现实矛盾，损害产品可信度。第二轮：第一轮新措辞中「永远私有 / 永远不卖 / stays private forever」是过头承诺——未公开内容（执行层研究）将来可能开放（如策略退役后开源），产品声明的职责是「本产品不含什么」，不该替未来的开放与否打包票。
- **改了什么**（2026-09-13）：
  - 总 README 两版「不含什么」条目：主语钉死「本手册」，并明示公开仓库里本来就公开的那部分交易内容（策略文档、历史信号流）免费可看——是橱窗的一部分、不是本产品的一部分；私有部分当时表述为「永远私有」（该末句已由下方二次修正修订）。
  - 模块 06 两版 Case 2 开头：删「交易内容本身是开源核心边界刻意排除的私有载荷」这一事实错误表述，改为「仓库本身是公开的——信号、复盘、操作记录全都免费可看；公开仓库给不了你的是结构背后的『为什么』，那正是本模块要带你走读的东西」。
  - 《产品说明》`artifacts/team-playbook-spec.md` open-core 边界段：免费层点明「含其中公开的策略文档与历史信号流」；付费包口径改为「不含任何交易内容与私人配置凭证——公开部分见公开仓库免费可看，未公开内容不在付费包里」。
  - 二次修正（同日 22:2x）：上三处新措辞末句「永远私有 / 永远不卖 / stays private forever」改为「不在本产品里——将来是否开放属独立决策、本产品不做承诺」，不再对未来的开放与否打包票。
- **边界**：仅纠偏边界声明的事实口径，付费包内容本身无变化（验收红线「全包无交易策略参数、回测数据、信号记录」仍成立——改的是声明措辞，不是包内容）；spec 验收记录第 3 条不动（其主语是本包内容，表述正确）。

### 新增（Team Playbook 全量中文版：8 份 README_cn.md + 双语互链）

- **为什么改**：产品原为纯英文（按 Scout 报告「卖给美国买家」定位），但团队存在成熟的中文销售与引流渠道（小红书店铺 / 知乎 / B 站等，CLAUDE.md 渠道约束已验证可用），中文版是中文渠道销售的必要交付物；用户指令「再翻译一份中文版」。组织方式沿用团队双语纪律（README.md ⇄ README_cn.md 平级互链、信息对齐不逐字直译）。
- **改了什么**（2026-09-13）：
  - **新增 8 份 README_cn.md**（总入口 + 7 个模块 + 02 模板目录说明）：与英文版语义对齐——事实、列举项、口径、数字不增不减不变；行文地道中文不硬译；模块间 Next 导航链指向各模块中文版
  - **双语互链**：英文版 8 处加 `[简体中文](README_cn.md)`，中文版 8 处加 `[English](README.md)`，双向可导航
  - **模板与 SVG 不翻译**：CLAUDE / rules / registry 三模板保持英文（模块 02 明示理由：模型对英文指令训练最强、买家抄的是英文结构），SVG 图表文字按 logo 规矩保持英文；两个决定均在产品说明与模块正文中明示
  - **产品说明同步**：`artifacts/team-playbook-spec.md` 形态节改双语表述、文件清单更新为 21 文件、验收记录补中文版对齐检查项
- **边界**：中文版为译文对齐层，不改变英文主版本任何内容；报告 v3.3 的「产品全英文」定位不变（英文仍为主版本），中文版作为中文渠道交付物与审阅副本。

### 新增（TODO T1 产品续产完成：Team Playbook 模块 04–07 + SVG 重画 + 产品说明 + 验收实测）

- **为什么改**：TODO T1 生产任务在 2026-08-20 只先行产出了模块 01–03（当时团队规模 14、产品名刚定），后因报告 v3.2 / v3.3 两轮增补（团队 14 → 20、去 CC 绑定）与 fleet→team 改名收尾，产品长期停在半成品；用户指令「继续完成整个产品」，本次续产剩余 4 个模块并按报告 v3.3 全量对齐、走完验收线（「手册里每个模板都真实可用，不交付跑不起来的包」）。
- **改了什么**（2026-09-13）：
  - **新增模块 04 — Registry & Naming**（`04-registry-naming/README.md`）：拟人名方法（含 Hopkins / Justin / Gatsby / Hopper 真实命名故事）、注册表结构、拆分信号、1 → 20 组织学（三小组 + 直属岗位、「什么岗位不进组」）、入职六步仪式；素材取自全局 `~/.claude/docs/agents-registry.md`。
  - **新增模块 05 — Scaffolding Kit**（`05-scaffolding-kit/README.md`）：仓库标准骨架逐文件「存在理由」、双语 README 同步纪律、VERSION+CHANGELOG 记忆对、TODO/归档/MEMO 编号时间戳闭环、tmp/ 边界、logo 规矩（英文文字、拟人头像 vs 子项目象征）。
  - **新增模块 06 — Case Walkthroughs**（`06-case-walkthroughs/README.md`）：两个真实仓库逐文件走读——Scout（56 行最小完整 agent，五段式 + 六节产物契约 + 报告→Wright 真实接力证据）与 Victor（纪律满配：决策即章节、skill 三层分层、hook 卫队、运行时流与治理分离）；**严守 §7 红线：只写文件组织方法，无任何交易策略参数 / 回测数据 / 信号记录 / 账户信息**。
  - **新增模块 07 — Cross-Harness Portability**（`07-cross-harness/README.md`）：可移植性地图（各 harness 身份文件名 / 规则 / skills→插件 / hooks 对照表）、迁移真实成本表、五步移植法、一文件多宿主（AGENTS.md symlink 实证 + hooks 三宿主同脚本实证）、插件时代「organize, don't hoard」。
  - **重画 `assets/team-diagram.svg`**：旧图为 14-agent 时代（6 流水线 + 9 独立）；新图按 v3.3 组织结构重画——20 agents = 6 段销售流水线 + 三小组（投资交易 2 / 基础设施 8）+ 直属 4，沿用原深色科技风与圆角规范，底部注注册表要点。
  - **存量数字对齐 v3.3**：总 README 首行 15 → 20；模块 01 两处 fifteen / 1-to-15 → twenty / 1-to-20、246-line → 248-line（与实测 SKILL.md 行数一致）；模块 03 结尾 fifteen → twenty。
  - **新增《产品说明》**（`artifacts/team-playbook-spec.md`）：产品名 / `product_id: Team-Playbook-v3` / 形态 / 7 模块内容清单 / 文件清单 / 用法与适用人群 / 建议定价 $49（早鸟 $35）/ Payloadz + PayPal 交付 / 验收记录 / 流水线接口——下游 Vendy / Buzz / Echo 接手入口。
  - **验收实测通过**：`tmp/demo-agent/` 从零建 agent（Sage 校对员，三模板真实填充无断档）；本地 Claude Code v2.1.226 headless 会话真实跑通——按产物契约把 Proof Report 写进 `artifacts/`（四节结构、`source` 溯源标签、每条 issue 精确行号、角色边界未越界、测试稿三处埋错全数抓出）；全包链接完整性 + SVG XML 合法性 + 内容红线扫描均过。
  - **TODO T1 归档**（完成）、本条目记录。
- **边界**：模块 01–03 正文未重写（仅数字对齐）；demo agent 实测产物留在 `tmp/demo-agent/`（已被 .gitignore 忽略）供检查，不进正式目录；产品未上架——上架定价归 Vendy、引流归 Buzz，本仓只交成品与说明。

### 变更（TODO T1 报告版本标注 v3.1 → v3.3：跟上 Scout 报告两轮增补）

- **为什么改**：Scout 仓《机会研判报告》2026-09-14 两轮增补（v3.2 团队规模 14 → 20 全文同步；v3.3 去 Claude Code 绑定、通称 AI agents），T1 生产任务里两处版本号标注仍写 v3.1——虽然任务要求「生产前通读报告全文」（内容会读到最新），但版本号指向过时会让 Wright 误以为执行规格是 v3.1。素材源路径、验收线、product_id、模块数经逐条核对均无变化（TODO 用「指回报告章节」的写法，内容自动跟随），仅版本号需同步。
- **改了什么**（2026-09-14）：`TODO.md` T1 两处：标题行「按 Scout《机会研判报告》v3.1 执行」→ v3.3，沿革时间戳追加本次同步说明（团队规模 14 → 20、去 CC 绑定通称 AI agents，规格细节以报告全文为准）；报告位置行括注「（v3.1，...）」→「（现 v3.3，...）」。
- **边界**：条目仍为未完成活跃待办（本次是内容更新非完成，不归档）；「CLAUDE 模板拿去能直接建 agent」验收句保留——指以 CLAUDE.md 为原型的角色配置模板（事实层），各 harness 文件名映射的新要求在报告 §4 模块 2，通读全文即得。

### 变更（.claude/rules/ 两份规则全文并入 CLAUDE.md「你的约束」，目录删除）

- **为什么改**：与 ProductStrategistAgent 2026-09-13 同款处理——`.claude/rules/` 文件没有按文件名自动加载的机制，只有进 CLAUDE.md 才每次会话生效；且本仓两份规则（available-channels / passive-income-only）与 Scout 仓本就是同一套规则的分叉副本，分两处维护会漂移。用户 2026-09-13 指示本仓执行并入并删除目录。
- **改了什么**：`.claude/rules/available-channels.md`、`passive-income-only.md` 全文并入 CLAUDE.md「## 你的约束」，改为三个小节（聚焦被动收入 / 可用销售与引流渠道 / 临时产物放 tmp/），原索引清单与工具节的文件路径引用同步删改；删除 `.claude/rules/` 目录（工作区 rm，未动暂存区）。顺带修复悬空引用：`tmp-dir-for-artifacts.md` 早在 7198f5e 已删但 CLAUDE.md 与 `.gitignore` 仍引用，其规则内容从 git 历史取回、精简为「临时产物放 tmp/」小节，`.gitignore` 注释改指 CLAUDE.md。
- **边界**：`artifacts/agent-team-playbook/` 模块 03 教材内作为「真实历史案例」叙述的 `available-channels.md` 与 `.claude/rules/` 属产品叙事素材不改（沿用 fleet→team 条目既有裁定）；CHANGELOG / TODO 历史条目不改（TODO T1 引用的是 Scout 仓路径，9/13 已修正）。

### 变更（artifacts 半成品 fleet → team 全量改名：2026-08-21 产品定名的漏网存量收尾）

- **为什么改**：产品 2026-08-21 已定名 The Agent Team Playbook（`product_id: Team-Playbook-v3`，Scout 报告 §4 成品样例树同步改为 `agent-team-playbook/`），但当日改名只同步了 TODO 追溯链，`artifacts/` 下 2026-08-20 先行产出的半成品（总 README、模块 01–03、模板、SVG）仍用旧名 fleet——Wright 下次开工会面对「规格树叫 team、产物树叫 fleet」的分裂。用户 2026-09-13 指示处理全部不一致，此刻改名零外部影响（产品未上架、未发帖）。
- **改了什么**：目录 `artifacts/agent-fleet-playbook/` → `agent-team-playbook/`、`01-fleet-method/` → `01-team-method/`、`assets/fleet-diagram.svg` → `team-diagram.svg`；6 个含 fleet 字样的文件（总 README、模块 01/02/03 README、registry-template、SVG）内容全量 fleet → team（含标题 `The Agent Fleet Playbook` → `The Agent Team Playbook`、`Module 01 — The Fleet Method` → `The Team Method`、模块表链接同步），替换后逐文件通读核对语义；`grep -i fleet` 零残留。
- **边界**：只改名与措辞对齐，不补内容——模块 04–07 空目录与验收（模板真实可用 + demo agent 实测）仍归 TODO T1 生产任务；CHANGELOG 历史条目中的 Fleet 字样是历史记录不改；模块 03 教材内作为「真实历史案例」叙述的 `available-channels.md` 文件名属产品叙事素材，不由本次处理。

### 变更（TODO T1 素材源引用修正：Scout 仓 rules 文件已并入其 CLAUDE.md）

- **为什么改**：TODO T1 素材源引用 Scout 仓 `.claude/rules/available-channels.md`，该文件 2026-09-13 已随 `.claude/rules/` 目录删除并入 ProductStrategistAgent 的 CLAUDE.md「## 你的约束」章节（其 CHANGELOG 9/13 条目只清理了本仓内活引用，跨仓 TODO 引用漏网）——照旧路径开工将找不到文件。
- **改了什么**：素材源描述改为指向 Scout 仓 `CLAUDE.md`「## 你的约束」章节（《可用销售与引流渠道》《聚焦被动收入》两份规则），括注旧路径已并入、勿再找；T1 时间戳追加「2026-09-13 13:40 素材源路径修正」。

### 变更（CLAUDE.md 删去「由 Claude Code 自动加载」说明句）

- **为什么改**：用户 2026-09-12 要求 CLAUDE.md 不再强调本文由 Claude Code 加载，团队全部项目的 CLAUDE.md 统一清理此类语句。
- **改了什么**（2026-09-12）：`CLAUDE.md` 开头角色定位行删去句尾「本文件由 Claude Code 在每次会话开头自动加载。」，角色描述本身保留。

### 变更（assets/logo.svg 副标题去中文）

- **为什么改**：全局规则新增「Logo / 图标资产文字一律用英文」（2026-09-12 用户立，起因 Swing 仓库 logo 副标题混入中文被指出）：logo 是面向全球读者的视觉标识，中文受众已有 README_cn.md 双语通道；且 SVG 中文依赖查看环境的字体回退，渲染不可控。本次为按新规批量清理存量。
- **改了什么**：`assets/logo.svg` 副标题「Producer · 数字产品制作人」→「Digital Product Producer」（顺带补全职称，与注册表「数字产品制作人」对齐）。

### 变更（项目迁移收尾：TODO.md 内引用路径更新）

- **为什么改**：各 agent 项目现址在 `~/Developer/`（`~/Documents/Projects/` 旧址已弃用，2026-09-08 迁移收尾时发现 TODO.md 待办里引用的输入路径仍指旧址），避免照待办执行时找不到文件。
- **改了什么**：`TODO.md` 中 6 处路径（报告唯一权威输入 1 处 + 素材仓库引用 5 处：ProductStrategistAgent、DayTradingAgent、CapabilityManagerAgent）由 `~/Documents/Projects/` 更新为 `~/Developer/`。

### 修复（TODO / MEMO 编号加粗脚本截断事故：批量脚本切片 bug 把条目正文截空，从多恢复源全量重建）

- **为什么改**：上一条「全量补编号」执行时，第二步「编号加粗」脚本存在切片 bug（`m.group(0)[m.end(3)+1:]` 起点算错），把所有被匹配条目的正文截成空壳（只剩 `- [ ] **Tn** `），共波及 1 个文件 1 条。发现后立即启动恢复（无 Time Machine / APFS 快照可用）。
- **改了什么**：多恢复源重建并回写——① git 暂存区 / HEAD 旧版（TODO.md）；② Claude Code file-history 检查点（Edit 前快照，TODO.md（cd63123c@v1 + 改名 Edit 重放））；③ 会话转写重放（按时间序重放历史 Edit / heredoc 写入，补齐检查点之后的新增条目，如 DayTradingAgent 今晚新增的 5 条活跃待办与「2026-08-21 批量处理」4 条归档）。重建后统一按规则加粗编号（**Tn** / **Mn**），DayTradingAgent 连续 T1~T115、DayTradingAgent-win 连续 T1~T44，正文经抽样与恢复源逐字一致。受损壳快照留存本机 tmp（/tmp/todo-damage-backup/）。
- **边界**：恢复目标是「截断事故前的状态」（即编号未加粗、但已编号的正文完整版）；编号加粗为规则要求的新格式。git 未提交的其它改动不受影响。

### 变更（TODO / MEMO 条目全量补编号：按新立待办编号规则一次性补齐存量）

- **为什么改**：2026-08-21 用户新立全局规则「每条待办必须有唯一待办编号」（格式 T+序号 / M+序号，如 T11 / M11，连写、项目内递增、永不复用、归档保留），并指示存量待办与归档待办全部补上编号——编号用于用户与 AI 针对性沟通（「T11 处理了吗」），避免复述长正文。
- **改了什么**：TODO.md 1 条补编号 T1。正文内容零改动（只插入编号，不改写、不重排、时间戳不变）；编号顺序 = 活跃文件在前、归档在后、文件内按行序。

### 变更（产品定名 Team Playbook：TODO.md 生产任务与 product_id 追溯链同步改名）

- **为什么改**：Scout 报告 v3.1 的待产旗舰产品定名从「Agent Fleet Playbook」改为「The Agent Team Playbook」（2026-08-21 用户裁定，理由与决策块见报告 §0——与 fleet → team 全量措辞统一对齐、team playbook 是英语地道搭配、组织 / 公司隐喻自洽）；本仓 TODO.md 的生产任务是该产品名的下游引用处，必须同步改名，否则 Wright 开工时会按旧名生产、Echo 归因链断开。
- **改了什么**：`TODO.md` 生产任务条目——任务名「生产 Fleet Playbook（智能体军团作战手册）」→「生产 Team Playbook（智能体团队作战手册）」；`product_id: Fleet-Playbook-v3` → `Team-Playbook-v3`（条目内 2 处）；报告定位说明补「产品 2026-08-21 定名 The Agent Team Playbook，原拟名 Fleet Playbook 弃用」；时间戳同步更新（2026-08-21 20:05）。产品尚未生产，无成品需要改。

### 变更（措辞统一 fleet → team：`.commit-cache.md` 缓存标记跟随全局统一）

- **为什么改**：用户 2026-08-16 已把 xhqing 主页 README 的自称从「舰队 / fleet」改为「团队 / team」，全局元规范与 commit skill 已同步改（2026-08-21，记录见 CapabilityManagerAgent CHANGELOG），本仓 `.commit-cache.md` 缓存标记里的「fleet Visitors 徽章」是同一批存量；2026-08-21 用户裁定全量存量一次清零、统一为团队 / team。
- **改了什么**：`.commit-cache.md` 1 处缓存标记「fleet Visitors 徽章属允许例外」→「团队 Visitors 徽章属允许例外」。仅改措辞，检测逻辑、徽章均不变。（`TODO.md` 里的「Fleet Playbook」原判断为「product_id 追溯标识、不改」——后于同日被产品定名决策取代：产品整体改名 Team Playbook，TODO 已同步，见上方「产品定名」条。）

## [1.0.0] - 2026-08-20

### 新增（commit skill 标配补全：README 中英双语 + Version 徽章 + VERSION 文件）

- **为什么改**：`/commit` 第 9 步项目标配检测（2026-08-20）发现缺失项——无 `README_cn.md` 中文版、无 `VERSION` 文件、README 英文版无 Version 徽章且正文混排中英（Built-in skills 段只写中文、License 段不完整）、还挂着 Stars / Last Commit 两枚 GitHub 动态徽章（违反「标准三枚 License / Version / Type + Visitors 例外」的徽章组合规矩）。
- **改了什么**：新建 `README_cn.md`（与英文版内容对齐，互链：英文版 `[简体中文](README_cn.md)`、中文版 `[English](README.md)`）；英文版正文补英文表达（Built-in capabilities 段改为英文、Constraints 段补英文对照、License 段补全为 License & Attribution 完整版权署名段，版权人 `All Contributors`）；删除 Stars / Last Commit 动态徽章，补 `Version-1.0.0` 徽章；新建 `VERSION`（`1.0.0`，取值按 9m 顺序兜底：无 package.json / manifest → `1.0.0`）；CHANGELOG 顶部 `## [Unreleased]` 落定为 `## [1.0.0] - 2026-08-20`（本版本尚未发 GitHub Release，属开发中定版）；新建 `.commit-cache.md` 记录检测标记。

### 新增（TODO.md 初始化 + 首个流水线任务：生产 Fleet Playbook）

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
