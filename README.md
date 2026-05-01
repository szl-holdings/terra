# Terra — Real Estate Intelligence

  > NYC distress pipeline and AI-assisted real-estate deal workflow — sourcing, underwriting, comps, and decision artifacts in one governed surface.

  [![CI](https://github.com/szl-holdings/szl-holdings-platform/actions/workflows/ci.yml/badge.svg)](https://github.com/szl-holdings/szl-holdings-platform/actions/workflows/ci.yml)
  [![TypeScript](https://img.shields.io/badge/TypeScript-5.9-3178C6?style=flat-square&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
  [![License](https://img.shields.io/badge/license-Proprietary-red?style=flat-square)](../../LICENSE.md)

  [Live Demo](https://szlholdings.com) · [Platform Demo Video](https://szlholdings.com/szl-demo-video/) · [Investor Dashboard](https://szlholdings.com/stephen/investor) · [Architecture](../../docs/architecture/architecture.md)

  ![Terra — Real Estate Intelligence](https://raw.githubusercontent.com/szl-holdings/szl-holdings-platform/master/.github/assets/screenshots/terra-hero.jpg)

  ---
  ## What it does

  Terra is the **NYC distress pipeline + AI-assisted real-estate deal workflow** — sourcing, underwriting, comps, predictive cap-rate modeling, and full decision artifacts in one governed surface. Built on the same Ouroboros runtime + Codex decision-receipt kernel as the rest of the platform.

  ## Government alignment

  Terra inherits the platform's NYSTEC-audited governance posture and is uniquely positioned for NY State property/asset workflows:

  - **NIST AI RMF**: full coverage across GOVERN / MAP / MEASURE / MANAGE
  - **GSA RAG source attribution**: every cited record hashed via Katzilla primary-source feed
  - **Predictive cap-rate model**: ML-driven forecasting with uncertainty bands surfaced per step
  - **Amaru reconciliation**: property and asset records merged across agency systems with consistency gates

  ## Run locally

  ```bash
  pnpm install
  pnpm --filter @workspace/api-server dev
  pnpm --filter @workspace/terra dev
  ```

  **Primary route:** `/terra/`

  ## Tech stack

  React 19 + Vite 7 + TypeScript (strict) · Express 5 · PostgreSQL 16 / Drizzle ORM · Mapbox GL · Predictive cap-rate ML model · Ouroboros loop runtime (`PRF_SYSTEM_CLAIMS`) · Codex decision receipts
  
  ---

  **SZL Holdings** · [szlholdings.com](https://szlholdings.com) · [inquiries@szlholdings.com](mailto:inquiries@szlholdings.com)

  ---
  ## About this repository

  This is a public showcase of one product in the [SZL Holdings platform](https://github.com/szl-holdings/szl-holdings-platform) monorepo. It mirrors the README from the platform artifact directory; the canonical, version-controlled source — including the React app, tests, and infrastructure — lives in the platform repo.

  All seven products share the same governed substrate:

  - **[`@workspace/ouroboros`](https://github.com/szl-holdings/ouroboros)** — bounded loops with measurable convergence, v6 ecosystem layer, government readiness module (**133/133 tests**)
  - **[`@workspace/codex-kernel`](https://github.com/szl-holdings/szl-holdings-platform/tree/master/packages/codex-kernel)** — decision receipts, validators, replay, trace-hash verification
  - **The Ouroboros Thesis** — [`szl-holdings/ouroboros-thesis`](https://github.com/szl-holdings/ouroboros-thesis) — architectural rationale + v6 operational contract

  Government readiness audit (NYSTEC pre-briefing, 2026-04-30): [`docs/audit/szl-government-readiness.md`](https://github.com/szl-holdings/ouroboros/blob/main/docs/audit/szl-government-readiness.md)

  © 2026 SZL Holdings. All rights reserved.
  