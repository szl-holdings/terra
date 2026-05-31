# terra

[![License](https://img.shields.io/badge/license-Proprietary-28251D?style=flat-square)](./LICENSE)
[![Series-A Engineering](https://img.shields.io/badge/Series--A-Engineering-28251D?style=flat-square)](https://github.com/szl-holdings)
[![Doctrine v7](https://img.shields.io/badge/Doctrine-v7-7c5cff?style=flat-square)](https://github.com/szl-holdings/.github/blob/main/doctrine/DOCTRINE_V7.md)
[![Security Policy](https://img.shields.io/badge/security-policy-1B474D?style=flat-square)](./SECURITY.md)

Real estate intelligence platform — AI-assisted deal-pipeline scoring, portfolio analytics, and underwriting workflows with governed decision trails.

---

## Overview

**terra** is the real estate intelligence component of the SZL Holdings governed AI platform. It provides AI-assisted underwriting, deal-pipeline scoring, and portfolio analytics for commercial and residential real estate operations, with every consequential decision executed through Covenant Policy and backed by a cryptographic audit trail.

### Key capabilities

| Feature | Description |
|---|---|
| Deal pipeline scoring | AI-scored deal flow with Λ-axis governance on every rating |
| Portfolio analytics | Live portfolio metrics with governed signal processing |
| AI-assisted underwriting | Document analysis, comparable extraction, risk scoring |
| Proof-chain delivery | Cryptographic receipt for every underwriting decision |
| Human gates | No AI recommendation executed without human confirmation |

## Architecture

```
Deal intake → Data enrichment → AI scoring (Λ-governed) → Human approval gate → Receipt emission
```

terra integrates with the SZL Holdings Ouroboros runtime for Λ-axis governance scoring and the `uds-mesh` observability layer for full span telemetry on every decision.

## Installation

> **Note:** terra is proprietary software. Contact [partners@szlholdings.com](mailto:partners@szlholdings.com) to discuss access.

```bash
# Internal: via pnpm workspace (platform monorepo)
pnpm --filter @szl/terra install
pnpm --filter @szl/terra build
```

## Usage

```typescript
import { TerraDeal } from '@szl/terra';

const deal = await TerraDeal.score({
  property: propertyData,
  comparables: [...],
  policy: CovenantPolicy.underwriting(),
});

const report = await deal.underwrite(); // Requires human gate
```

## Security and Governance

All scoring and underwriting outputs are governed by Covenant Policy. No AI-generated valuation or recommendation is binding without human confirmation and a proof receipt. Security disclosures: [security@szlholdings.com](mailto:security@szlholdings.com).

## How to Cite

```bibtex
@software{lutar_terra_2026,
  author    = {Lutar, Stephen P.},
  title     = {terra — Real estate intelligence for governed AI workflows},
  year      = {2026},
  publisher = {SZL Holdings},
  url       = {https://github.com/szl-holdings/terra}
}
```

See [CITATION.cff](./CITATION.cff) for machine-readable citation metadata.

## Contributing

See [CONTRIBUTING.md](./CONTRIBUTING.md). Proprietary software; contributions by invitation only. All commits require DCO sign-off (`git commit -s`).

## License

Proprietary — SZL Holdings, LLC. See [LICENSE](./LICENSE) for terms.

## Related repositories in the SZL substrate

| Repo | Role |
|---|---|
| [platform](https://github.com/szl-holdings/platform) | Monorepo substrate |
| [ouroboros](https://github.com/szl-holdings/ouroboros) | Runtime + Lutar formulas |
| [uds-mesh](https://github.com/szl-holdings/uds-mesh) | Observability spans |
| [ouroboros-thesis](https://github.com/szl-holdings/ouroboros-thesis) | Formal research paper |
