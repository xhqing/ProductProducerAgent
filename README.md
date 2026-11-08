<div align="center">

<img src="assets/logo.svg" width="640" alt="Wright logo" />

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Version](https://img.shields.io/badge/Version-1.0.0-blue)
![AI Agent](https://img.shields.io/badge/Type-AI%20Agent-FF1493)

</div>

# ProductProducerAgent · Wright

> **数字产品制作人** — 把机会研判变成可售卖的成品数字产品。
>
> **Digital Product Producer** — Turns validated opportunities into finished, sellable digital products.

**拟人名 / Persona：Wright**（制造者 · 把想法做成成品）

[简体中文](README_cn.md)

---

## 职责 / What it does

照 Scout 的《机会研判报告》，产出成品数字产品（prompt 包 / 模板 / ebook / 素材包 / 小工具）+《产品说明》（含 `product_id`、建议定价、交付方式）。

Builds finished digital products (prompt packs / templates / ebooks / asset packs / small tools) plus a *Product Spec* (with `product_id`, suggested pricing, delivery) based on Scout's Opportunity Brief.

## 在流水线中的位置 / Pipeline position

① Scout 研判 → ② **Wright** 生产 → ③ Buzz 引流 → ④ Vendy 成交 → ⑤ Echo 复盘

## Built-in capabilities

Common capabilities (anysearch, find-skill, etc.) are not duplicated in this repo; they are distributed via the `claude/` mirror of [CapabilityManagerAgent](https://github.com/xhqing/CapabilityManagerAgent) — clone that repo to get all shared capabilities.

## 约束 / Constraints

只做被动收入形态（排除课程 / 服务 / 代运营）；中间产物放 `tmp/`，成品进 `artifacts/`。

Passive-income products only (no courses / services / agency work); intermediate artifacts go to `tmp/`, finished products to `artifacts/`.

## License & Attribution

- Copyright (c) 2026 xhqing <https://github.com/xhqing>. Licensed under [MIT](LICENSE.md).
- When referencing this project, please keep the copyright notice and cite the source.
- Project URL: <https://github.com/xhqing/ProductProducerAgent>

