<div align="center">

<img src="assets/logo.svg" width="640" alt="Wright logo" />

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)
![Version](https://img.shields.io/badge/Version-1.0.0-blue)
![AI Agent](https://img.shields.io/badge/Type-AI%20Agent-FF1493)
<img src="https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/xhqing/xhqing/main/traffic/badges/ProductProducerAgent.json" alt="Visits/day (14d)" />

</div>

# ProductProducerAgent · Wright

> **数字产品制作人** — 把机会研判变成可售卖的成品数字产品。
>
> **Digital Product Producer** — Turns validated opportunities into finished, sellable digital products.

**拟人名 / Persona：Wright**（制造者 · 把想法做成成品）

[English](README.md)

---

## 职责 / What it does

照 Scout 的《机会研判报告》，产出成品数字产品（prompt 包 / 模板 / ebook / 素材包 / 小工具）+《产品说明》（含 `product_id`、建议定价、交付方式）。

## 在流水线中的位置 / Pipeline position

① Scout 研判 → ② **Wright** 生产 → ③ Buzz 引流 → ④ Vendy 成交 → ⑤ Echo 复盘

## 内置能力 / Built-in skills

通用能力（anysearch、find-skill 等）不在本仓库放副本，统一经 [CapabilityManagerAgent](https://github.com/xhqing/CapabilityManagerAgent) 的 `claude/` 镜像分发，clone 该仓库即得全部通用能力。

## 约束 / Constraints

只做被动收入形态（排除课程 / 服务 / 代运营）；中间产物放 `tmp/`，成品进 `artifacts/`。

## 版权与署名

- 版权所有 `Copyright (c) 2026 All Contributors`，许可证为 [MIT](LICENSE.md)。
- 引用本项目时，请保留版权声明并注明来源。
- 项目地址：<https://github.com/xhqing/ProductProducerAgent>
