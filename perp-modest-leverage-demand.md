---
layout: article
title: "The Demand for Buy-and-Hold Leverage Is Already Visible — in Perp Capital Distribution"
tagline: "Perp futures markets are publicly associated with extreme leverage — 50× and 100× retail speculation, headline-grabbing liquidations, the cultural register of crypto-Twitter degeneracy. The capital-weighted reality on Hyperliquid is the opposite. 92% of long-deployer equity sits at ≤3× leverage. 73.6% sits at ≤0.5×. The dominant population on the largest on-chain perp venue is buy-and-hold leveraged-BTC capital — already in the market, already paying ~11% annualized funding for exposure that a properly architected protocol-native primitive would deliver at a fraction of the cost."
description: "92% of capital on Hyperliquid perp markets sits at ≤3× leverage; the aggregate is 0.91× — sub-1×. The buy-and-hold leveraged-BTC cohort is the dominant capital base of the largest on-chain perp venue, paying ~11% annualized funding for exposure that BTC-Jr would deliver at a fraction of the cost."
image: https://frgs3.s3.us-west-1.amazonaws.com/thought_pieces/perp_leverage/fig_perp_lev_dist.png
date: 2026-06-04
permalink: /perp-modest-leverage-demand/
---

**The argument.** The conventional read on perp futures is that they serve high-leverage short-horizon speculators. The capital-weighted distribution says otherwise. On Hyperliquid — the largest fully on-chain perp venue and the only one with per-position data publicly observable — 92% of long-deployer equity is held at ≤3× leverage, with the dominant subset (73.6%) at ≤0.5×. The aggregate leverage across the long-deployer focus cohort is **0.91× — sub-1×**. The capital base is overwhelmingly already at modest leverage, paying perp funding (~11% annualized on notional, blended across exchanges) for exposure they would unambiguously be better served holding through 2factor's perpetual-tranching architecture at a structurally lower cost. The misalignment isn't that perps don't serve buy-and-hold leverage demand. It's that perps *are* the de facto buy-and-hold leverage product for crypto-native capital, and they're charging far too much for that service.

The empirical answer, sized: the long-deployer focus cohort holds ~$983M in equity against ~$892M in long notional across the analyzed snapshots. At a blended ~11% annualized perp funding rate, that's roughly **$100M/year in funding cost paid by Hyperliquid long-deployers alone**. Extrapolated against $60–80B in global perp open interest, the implied modest-leverage cohort is paying multi-billion dollars per year to maintain leveraged buy-and-hold exposure through the wrong product.

---

## The perception versus the reality

The popular reading of perp markets — repeated across crypto media, advisor education materials, and traditional finance commentary — is that perps are a casino for high-leverage degens. The data supports that reading *if you weight by notional*, since high-leverage positions on small accounts inflate notional totals. But notional-weighting answers the wrong question. The right question is: *where is the capital?*

The 2factor research dashboard at `data.2factor.finance/perp-leverage-distribution` pulls per-account state across 64,863 Hyperliquid accounts (4-snapshot pooled methodology, Oct 2025 – June 2026), reconstructing leverage as account notional divided by account equity. The 13,347 long-deployer focus cohort holds $983M in equity. The leverage distribution across that equity:

| <picture><img alt="Bar chart of Hyperliquid long-deployer capital by per-account leverage. 73.6% of equity at 0-0.5x, 7.4% at 0.5-1x, 5.1% at 1-1.5x, 2.7% at 1.5-2x, 3.1% at 2-3x, then declining shares through higher leverage buckets. A vertical dashed line marks the 3x threshold; 92% of capital sits to the left of it." src="https://frgs3.s3.us-west-1.amazonaws.com/thought_pieces/perp_leverage/fig_perp_lev_dist.png?v=1"></picture> |
| :-- |
| *Hyperliquid long-deployer capital by per-account leverage, 4-snapshot pooled methodology. 92% of equity sits at ≤3× leverage; 73.6% at ≤0.5×. The aggregate leverage on the focus cohort is 0.91× — sub-1×. The capital base is dominated by accounts running near-zero leverage on positive-drift assets, not the high-leverage degens the public-perception narrative associates with perp markets.* |

Two things follow immediately. First, the dominant Hyperliquid posture is *barely leveraged at all*. 73.6% of capital sits at ≤0.5× — these are accounts holding more equity than long notional, often substantially more. They are using the perp venue for buy-and-hold exposure, not speculation. Second, the high-leverage cohort (>10×) — the cultural archetype of perp users — represents 1.5% of equity. The narrative is about that 1.5%; the capital is everywhere else.

The asymmetry is a function of cohort distribution. Per-position leverage skews high (median ~10×) when weighted by position count, because thousands of retail accounts hold tiny positions at maximum leverage. Per-capital leverage skews low (aggregate ~0.91×) because the small number of large accounts that hold most of the capital run minimal leverage:

| <picture><img alt="Horizontal bar chart of Hyperliquid capital concentration by account-size cohort. Mega cohort (15 accounts with greater than 10 million dollars each) holds 459 million dollars or 46.7% of capital. Whale cohort (103 accounts, 1 to 10 million dollars) holds 301 million dollars or 30.6%. Pro cohort (522 accounts, 100k to 1 million dollars) holds 160 million dollars or 16.3%. Smaller cohorts hold negligible amounts." src="https://frgs3.s3.us-west-1.amazonaws.com/thought_pieces/perp_leverage/fig_perp_cohort_share.png?v=1"></picture> |
| :-- |
| *Capital concentration by account-size cohort. The mega and whale tiers (15 + 103 accounts respectively, both ≥$1M equity) hold 77.3% of all Hyperliquid capital. These are the accounts driving the aggregate-leverage finding. They use leverage like institutional allocators — sparingly, around 1-2×, with most of the position structurally unleveraged. The cultural perception of perps reflects what retail does; the capital weight reflects what large pools do.* |

The 15 mega accounts and 103 whale accounts together represent 118 wallets that hold 77.3% of Hyperliquid equity. The same 118 wallets drive the aggregate-leverage finding. They are systematically running near-zero leverage despite having full access to 40× on BTC and 25× on ETH. They are exactly the holder profile 2factor's productive-band architecture is designed to serve — and they are already paying perp funding rates to maintain exposure that the protocol would deliver more efficiently.

---

## What the cost looks like

The cost of leverage on perps is the funding rate, paid on the *notional* position size. This is a critical detail that the cultural framing of "leverage is cheap" obscures. Funding is charged on notional, not on equity — which means at higher leverage levels, the cost per dollar of equity scales linearly with leverage.

At a blended ~11% annualized funding rate (the rough cross-exchange average across the past 24 months, with cycles ranging from -10% during deleveraging to >50% during euphoric bull markets), the cost per dollar of equity scales as:

- 1× leverage: 11% on equity (full spot exposure)
- 2× leverage: 22% on equity
- 3× leverage: 33% on equity
- 5× leverage: 55% on equity
- 10× leverage: 110% on equity
- 25× leverage: 275% on equity

The funding cost on a leveraged perp position annihilates returns at any non-trivial leverage. Even at modest 2× leverage, the holder pays 22% per year just to maintain the position. The market price of high-leverage exposure on perps is, by construction, ruinous — which is why most capital systematically avoids it.

2factor's perpetual-tranching architecture prices leverage fundamentally differently. The financing cost is the Sr-side yield: (r<sub>f</sub> + 1%) paid on the Sr capital borrowed, not on the entire notional. For a Jr position at leverage L, the borrowed Sr is (L−1) per dollar of Jr equity, so the annual cost per dollar of Jr equity is (L−1) × (r<sub>f</sub> + 1%). At r<sub>f</sub> = 4%:

- 1× leverage: 0% on equity
- 1.3× leverage: 1.5% on equity
- 2× leverage: 5% on equity
- 3× leverage: 10% on equity
- 5× leverage: 20% on equity

The cost comparison across leverage levels makes the structural advantage visible:

| <picture><img alt="Line chart comparing annual cost per dollar of equity between perp funding (red line) and BTC-Jr financing (blue line) across leverage levels from 1x to 25x. Perp funding scales linearly with leverage from 11% at 1x to 275% at 25x. BTC-Jr financing scales as L minus 1 times rf plus 1 percent, staying near zero at low leverage and reaching only 120% at 25x. At 2x leverage perp costs 22% versus BTC-Jr 5%. At 3x leverage perp costs 33% versus BTC-Jr 10%." src="https://frgs3.s3.us-west-1.amazonaws.com/thought_pieces/perp_leverage/fig_perp_cost_compare.png?v=1"></picture> |
| :-- |
| *Annual cost per dollar of equity, perp funding versus BTC-Jr financing, across leverage. Perp funding scales linearly with leverage because it is paid on the full notional. BTC-Jr's cost scales as (L−1) × (r<sub>f</sub> + 1%) — only on the borrowed Sr capital. The structural ratio is ~4–5× cheaper at any modest leverage level. At 2×, perp costs 22%/year vs BTC-Jr's 5%. The cost saving compounds — and the risk profile is also fundamentally different, since BTC-Jr has no liquidation, no oracle dependency, no funding-spike risk.* |

For the modest-leverage cohort that actually populates Hyperliquid, this is not a marginal cost difference. At 2× leverage, the holder pays 22% per year through perps. The same exposure through BTC-Jr would cost 5%. The savings compounded over a year on $1M of equity is $170K. Across the long-deployer focus cohort's $983M of equity at typical 1-2× exposure, the implied annual funding cost is roughly $100M — half of what the same exposure would cost through the protocol.

And cost is only the first dimension. The qualitative differences compound:

1. **Liquidation risk.** Perps liquidate any position that crosses the maintenance margin threshold. At 2× leverage on BTC, a 50% drawdown wipes the position entirely. BTC-Jr has no liquidation — by architecture, the Jr tranche absorbs the drawdown without forced exit.

2. **Funding-rate volatility.** The 11% blended is a long-run average; the path is what holders actually experience. During euphoric bull markets, funding can spike to 50% or 100%+ annualized. Holders who entered at moderate funding are not protected from regime shifts. BTC-Jr's financing cost is bounded structurally — it cannot spike.

3. **Oracle and mark-price risk.** Perp positions are marked against an index price that can be temporarily manipulated, dislocated during stress, or used to trigger cascading liquidations. BTC-Jr's NAV is protocol-defined and doesn't depend on any oracle in the same way.

4. **Counterparty risk.** Perp positions carry exchange credit risk — FTX-era memory is recent enough to matter for institutional allocators. Protocol-native positions on BTC-Jr have only smart-contract risk, which is bounded and auditable.

5. **Identity coding.** Perps are culturally degen-coded, which constrains institutional adoption even when the structural use case is buy-and-hold. The same allocators who would happily hold a tranched leverage product cannot mandate-justify "we're using Hyperliquid perps for our institutional BTC sleeve." This is the same psychographic constraint the LETF and DAT essays documented in different markets.

---

## What this measures

The point of this analysis is not to argue that perps are bad. Perps are a perfectly good product for the use case they were architecturally designed to serve — short-horizon directional speculation with deep liquidity and tight spreads. For that holder, perps work.

The point is that a significant share of the capital using perps *is not that holder*. They are buy-and-hold leveraged-BTC capital that defaulted to perps because no protocol-native modest-leverage product existed when the allocation decision was made. The cost of that mismatch is observable, in published per-account data, in real dollars. The size of the mismatch is the size of the addressable market for a properly architected buy-and-hold leverage primitive.

Three observations close the analysis:

**The capital-weighted finding is the honest finding.** The notional-weighted distribution shows 10-20× median leverage and looks like a degen casino. The capital-weighted distribution shows 0.91× aggregate and looks like a corner of the institutional allocator space. The same data supports both readings depending on what you weight by — but only one of those readings tells you where the capital actually is.

**Modest leverage is the dominant Hyperliquid posture.** 92% of long-deployer equity at ≤3× leverage. 73.6% at ≤0.5×. Whales and mega accounts running near-zero leverage. This isn't a niche cohort hiding inside a high-leverage market; it's the dominant cohort, paying high-leverage prices for low-leverage exposure.

**The cost savings would be immediate and large.** At 2× leverage, the structural ratio is ~4× cheaper through BTC-Jr (5% vs 22% annualized). For an allocator holding $100M of leveraged BTC exposure at 2× through perps, the annual funding cost is ~$22M; the same exposure through BTC-Jr would cost ~$5M. That's not an optimization — it's an architectural correction that recaptures $17M per $100M of equity, every year, indefinitely.

The capital is already at modest leverage. It is already paying for the leverage. It is using the wrong product because the right product wasn't accessible when the allocation decision was made. The architectural fix is what unlocks this capital — not a marketing push, not investor education, not a new product category. Just substitution of the leverage primitive at the same effective leverage level.

The buy-and-hold leveraged-BTC cohort that the prior three essays (MSTR substitution, BTC yield products, LETF holding periods) sized in adjacent markets is here too — and in fact is the dominant capital base of the largest on-chain perp venue. Make it legible, price it correctly, and the migration is straightforward.

---

*Per-account leverage distribution data and methodology are at the [Perp Leverage Distribution Explorer](https://data.2factor.finance/perp-leverage-distribution/viz/perp_leverage_explorer.html). Companion essays in the demand-source series: [The Demand for Buy-and-Hold Leverage Is Already Visible — in LETF Holding Periods]({{ site.baseurl }}/letf-holding-period-demand/) (LETF demand), [How MicroStrategy Becomes Premium-Independent]({{ site.baseurl }}/mstr-premium-independence/) (DAT demand), and [Moderate Leverage Outperforms Every BTC Yield Product]({{ site.baseurl }}/btc-jr-vs-yield-products/) (BTC yield demand). The architectural details of the buy-and-hold leverage primitive are in the [Durable Leverage paper](https://drive.google.com/file/d/14E0phxNhliy_Qc-kBPPbRAkaedBxe3ma/view?usp=sharing) (Fragments Research, 2026).*

---

### Data & methodology

<div class="appendix" markdown="1">

**Per-account data source.** Hyperliquid L1 fills data (24-hour windows) reconstructs the universe of perp-active addresses on each snapshot date. For each active address, the Hyperliquid `clearinghouseState` info endpoint returns current cross-margin equity, per-asset position notional, leverage, and liquidation price. The 2factor research team operates this collection at `data.2factor.finance/perp-leverage-distribution`.

**Snapshot pooling.** Four snapshot dates (2025-10-31, 2025-11-30, 2025-12-31, 2026-06-01) pooled to reduce single-day artifacts. Methodology and time-series detail at the dashboard.

**Universe.** 64,863 unique perp-active accounts across the pooled snapshots; 13,347 of those accounts are classified as "long deployers" — they hold net long perp notional at snapshot time. The long-deployer focus cohort holds $983M in aggregate equity and $892M in long notional. The remaining accounts are short or net-flat.

**Leverage measurement.** Per-account leverage = gross long notional ÷ account equity (cross-margin engine value, includes uPnL). Aggregate cohort leverage = sum of long notional ÷ sum of equity. This is the capital-weighted leverage, distinguished from per-position leverage (which weights by notional and is heavily biased toward retail high-leverage positions on small capital).

**Cohorts.** Account-size cohorts: dust (<$100), retail (<$1K), mid (<$10K), active (<$100K), pro (<$1M), whale (<$10M), mega (≥$10M). Cohort boundaries reflect institutional analyst conventions for crypto wallet-size segmentation.

**Funding-rate estimate.** Blended ~11% annualized on BTC perps based on the average across major exchanges (Binance, Bybit, OKX, Hyperliquid, Deribit, Bitget) over the prior 24 months. Funding cycles considerably — sustained periods at 30–50% during euphoric markets, -10 to -20% during deleveraging events. The Schmeling, Schrimpf, and Todorov "Crypto Carry" paper (BIS Working Paper No. 1087, 2023) documents that crypto carry has reached >40% annualized at peaks but is "driven mainly by fluctuations in convenience yields" — not a stable cost.

**BTC-Jr financing cost.** Sr earns (r<sub>f</sub> + 1%) per dollar of Sr capital provided. For a Jr position at leverage L, borrowed Sr is (L−1) per dollar of Jr equity, so the cost per dollar of Jr equity is (L−1) × (r<sub>f</sub> + 1%). At r<sub>f</sub> = 4%, this is a bounded function of L, scaling linearly with (L−1) rather than with the full notional. Details in the [Durable Leverage paper](https://drive.google.com/file/d/14E0phxNhliy_Qc-kBPPbRAkaedBxe3ma/view?usp=sharing).

**CEX extrapolation.** Per-position leverage data is not publicly available for centralized exchanges. Order-of-magnitude implied long-deployer cohort sizes use Hyperliquid's distribution as the proxy applied to global BTC + ETH perp open interest (~$60–80B). This is a rough estimate; the on-chain Hyperliquid cohort may not be representative of CEX user composition.

**Sample limitations.** The Hyperliquid data captures only the on-chain perp venue, which over-represents crypto-native users and under-represents institutional allocator capital that hasn't migrated to on-chain venues. The capital-weighted modest-leverage finding likely holds across CEXs but the precise distribution may shift — institutional allocators on CEXs probably skew even lower in leverage than the Hyperliquid distribution implies. The directionality of the finding is robust; the precise dollar magnitudes deserve continued refinement as more data sources become accessible.

</div>
