# Terra — Real-Estate and Land Intelligence Agent

Terra is the Ouroboros real-estate intelligence agent, responsible for property-graph construction, deed-chain verification, parcel and zoning lookups, and market-signal synthesis across managed land assets.

## Role in the ecosystem

Terra occupies the land-layer of the Ouroboros agent stack. Where other agents reason about contracts, fleet state, or guest journeys, Terra holds the authoritative view of physical property: who owns what parcel, under what zoning regime, with what deed history, and at what current market valuation. It feeds structured property records into downstream agents and integrates directly with property-management workflows operated under Bingle Properties and Mule Properties. Terra is the canonical source for any decision that touches real assets — lease renewals, acquisition diligence, encumbrance checks, or portfolio rebalancing. It writes deed-chain receipts to the shared ledger so that counsel and trust-deposit agents can reference the same immutable record.

## Capabilities

- **Property-graph construction**: builds and maintains a directed graph of parcel relationships — ownership chains, easements, liens, and adjacency.
- **Deed-chain verification**: traverses recorded instruments to confirm clean title and flag breaks or competing claims.
- **Parcel and zoning lookups**: resolves parcel identifiers (APN, lot-block, legal description) against county assessor and zoning authority data.
- **Market-signal synthesis**: aggregates comparable-sales, listing velocity, and cap-rate feeds to produce a single market-signal envelope per property.
- **Property-management integration**: exposes structured feeds consumed by Bingle Properties and Mule Properties workflow adapters.
- **Receipt emission**: writes tamper-evident deed-chain receipts to the Ouroboros shared ledger for cross-agent auditability.

## Inputs / Outputs / Receipts

**Inputs**: parcel identifiers, address strings, county assessor exports, MLS/listing feeds, owner-of-record queries, zoning-change notifications.

**Outputs**: property-graph snapshots (JSON-LD), market-signal envelopes (structured key-value with confidence intervals), zoning-status summaries, deed-chain traversal reports.

**Receipts**: each deed-chain verification run emits a signed receipt — timestamp, parcel ID, chain hash, agent version — stored in the Ouroboros ledger. These receipts are immutable once written and serve as audit anchors for title disputes or compliance reviews.

## Lambda invariant boundary

Terra operates inside the Ouroboros lambda (Λ) invariant, which constrains every agent to act only within the scope of its declared capability surface and to emit receipts for every state-changing operation. For Terra, the Λ boundary means the agent never records a property-graph mutation without a corresponding signed receipt, and it never extends its authority beyond the land-intelligence surface — Terra cannot initiate financial transactions, sign contracts, or issue legal opinions. When data sources conflict (assessor record versus deed instrument versus MLS listing), Terra surfaces the conflict in its output envelope rather than silently resolving it, preserving the invariant that downstream agents always see the full epistemic state.

The boundary also governs data freshness: Terra must declare the staleness of every data source it incorporates. Any envelope produced from data older than the declared refresh window is flagged as provisional, preventing downstream agents from treating aged assessor data as current title state.

## Current state

Alpha. Core property-graph schema and deed-chain receipt format are defined. Parcel lookup and market-signal adapters are under active development. Integration with Bingle Properties and Mule Properties workflows is pending end-to-end testing. The receipt ledger interface is stable.

## References

- Ouroboros runtime: <https://github.com/szl-holdings/ouroboros>
- Ouroboros thesis: <https://github.com/szl-holdings/ouroboros-thesis>
- SZL Trust: <https://github.com/szl-holdings/szl-trust>

## Maintainer

Stephen P. Lutar Jr. \<stephen@szlholdings.com\>, ORCID 0009-0001-0110-4173
