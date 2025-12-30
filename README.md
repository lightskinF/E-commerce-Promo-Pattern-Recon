# E-commerce Promo Pattern Recon

This repository documents real-world observations on promotional logic,
newsletter onboarding, and pricing behavior across modern e-commerce platforms.

The focus is on **user-side behavioral analysis** and **configuration patterns**,
not on exploitation or automation.

---

## Scope

- Newsletter welcome incentives
- Promo code acceptance / rejection
- Platform-specific promotional behavior
- Pricing differences across regions
- Monolithic vs composable e-commerce patterns

No private data is collected.
All tests are performed manually from a standard user perspective.

---

## Methodology

- Passive observation
- Manual testing based on common industry conventions
- Comparative analysis across multiple retailers
- Client-side inspection using browser DevTools (Network tab)
- Screenshot-based documentation

---

## Case Studies

### Case 1 – Shopify Store With No Declared Promotions

**Context**  
A quality-focused retailer states:
- No seasonal sales
- No Black Friday
- No newsletter welcome discount

The website footer indicates: *Powered by Shopify*.

**Observation**  
Despite no visible incentive during newsletter signup,
the checkout accepted a standard welcome promo code.

**Tested Patterns**
- NEW10
- WELCOME10
- FIRST10

**Result**  
The code `NEW10` was accepted and applied a discount.

**Interpretation**
Observed behavior is consistent with:
- Active promo rules not exposed on the frontend
- Legacy or default Shopify discount configurations
- Misalignment between brand communication and backend rules

---

### Case 2 – Product-Level Exclusion Inconsistency

**Context**  
A limited collaboration item (MM6 x Maison Margiela):
- Frequently sold out
- Promo codes explicitly excluded by most retailers

**Observation**  
Across several retailers, the same welcome promo code was rejected.
One retailer, however, accepted the code and applied a discount.

**Interpretation**
Observed behavior is consistent with:
- Inconsistent product-level exclusion rules
- Promotion inheritance misconfiguration
- Differences in platform or rule engine implementation

---

### Case 3 – Regional Pricing Difference (Global retailer)

**Context**  
The same product was viewed on a well-known Global retailer:
- From Italy (Italian language, local IP)
- From France (French language, VPN-based IP)

**Observation**
The French version displayed a slightly lower price for the same item.

**Interpretation**
Observed behavior is consistent with:
- Geo-based pricing strategies
- Regional price books
- VAT differences and currency rounding
- Multi-store enterprise pricing logic

This behavior does not represent a discount,
but a market-specific pricing configuration.

---

## Platform Behavior Observations (Non-Deterministic)

| Pattern | Observed Behavior |
|------|------------------|
| Shopify (monolithic) | Global promo rules may remain active |
| Enterprise platforms | Strong SKU-level exclusions |
| ESP-driven flows | Welcome codes active without explicit display |
| Multi-region stores | Price differentiation by country |

---

## Ethical Note

This repository documents observable e-commerce behavior
to understand customer experience gaps and configuration patterns.

No safeguards are bypassed.
No automation or brute-force techniques are used.
