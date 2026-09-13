# Changelog

## [Unreleased]

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
