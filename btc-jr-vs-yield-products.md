---
layout: article
title: "Moderate Leverage Outperforms Every BTC Yield Product — Here's Why the Gap Persists"
tagline: "If the goal is to accumulate more Bitcoin without deploying more capital, modest leverage is an extremely simple and obvious answer. The 10-year thought experiment makes the case in one chart."
description: "A 10-year thought experiment showing why moderate (1.33×) leverage on Bitcoin outperforms every available BTC yield product, why the gap is structural, and what changed."
image: https://frgs3.s3.us-west-1.amazonaws.com/thought_pieces/btc_jr_vs_yield_products/fig_yield_headline.png
date: 2026-05-30
permalink: /btc-jr-vs-yield-products/
---

## The simple, obvious claim — and the thought experiment

If you hold Bitcoin and your goal is to accumulate more of it without deploying more capital, **modest leverage is an extremely simple and obvious answer**. More performant than yield, mathematically straightforward under reasonable assumptions, and consistent with what portfolio theory has said about positive-drift assets for over half a century.

Run the thought experiment. Imagine you had held 1.33× leverage on Bitcoin for the last 10 years — instead of holding spot only, instead of chasing yield through lending platforms, instead of using covered call vaults or basis trade structures or any of the other yield-adjacent strategies that have promised to compound your Bitcoin position.

| <picture><source media="(prefers-color-scheme: light)" srcset="https://frgs3.s3.us-west-1.amazonaws.com/thought_pieces/btc_jr_vs_yield_products/fig_yield_headline.png?v=7"><img alt="10-year comparison of moderate (1.33×) leverage against representative BTC yield products, BTC-denominated" src="https://frgs3.s3.us-west-1.amazonaws.com/thought_pieces/btc_jr_vs_yield_products/fig_yield_headline.png?v=7"></picture> |
| :-- |
| *BTC-denominated, 2015-12 to 2025-12. The leverage line is the thought-experiment ideal (no friction); the lending line is 2% APY. Covered-call and convert-and-return categories underperform structurally and are discussed in prose rather than charted.* |

The result isn't subtle. Modest leverage compounds far more favorably than yield products for positive-drift assets like Bitcoin. Lending-based yields run a percent or two of BTC per year; covered-call and convert-and-return structures often forfeit BTC in BTC-denominated terms during bull cycles. Over the 10-year window, the gap is multiple turns of starting capital — *substantially* more Bitcoin per dollar, not marginally more.

The interesting questions the thought experiment raises:

1. **Why haven't people been doing this?**
2. **Why are BTC yields so low** that yield products haven't been a credible alternative to holding spot?
3. **What changed**, such that modest leverage on Bitcoin is now actually deliverable in practice?

---

## Why BTC yields are so low

The BTC yield landscape divides into three architectural categories. Each has structural trade-offs that limit what it can deliver — and the trade-offs explain why the yields you see across the market are what they are.

### Borrowing-based products

These work by lending BTC out and earning interest from borrowers. The category is well-known and includes major DeFi platforms, institutional lending desks, and the centralized lending platforms that dominated pre-2022 CeFi. Yields across the category run from near-zero to about 3% APY. This is the largest category by AUM and the most representative of "what BTC yield actually is."

The yields are low because of the structural problem behind the architecture. **Almost nobody wants to borrow Bitcoin long-term.** To borrow BTC for years means taking a multi-year short position against an asset with positive long-run drift — a structurally bad trade where your debt grows even when you're right about short-term direction. Short-term borrowers exist (traders shorting for days or weeks), but they generate modest yield because the trades are short-duration and the supply of BTC available to lend is enormous relative to demand.

The result: the demand side of the BTC borrow market is structurally thin. Supply massively exceeds demand. Rates stay low. No yield platform, however well-implemented, gets around this — the constraint is on the borrowing side, not the lending side.

### Convert-and-return products

These work by accepting BTC, converting it to USD or USD-equivalent, deploying the USD in yield-bearing strategies, and converting back to BTC over time. Sometimes called "synthetic BTC yield." Headline yields can look attractive — sometimes 5–10% — but the mechanism contains an undisclosed directional bet: it only delivers "more BTC" if the USD-denominated strategy outperforms BTC-denominated returns over the holding period.

Under any realistic high-CAGR BTC environment, that bet loses sustainably. At ~30%-annualized BTC returns, a USD yield strategy needs to earn 30%+ just to break even on the BTC-denominated outcome. They don't. This category structurally bets against BTC's positive drift, which is the opposite of what most BTC holders are trying to do.[^1]

### Exotic / regime-dependent products

This is the heterogeneous category of higher-yield products that depend on specific market conditions persisting: covered call vaults that cap your upside, basis trade structures that depend on positive funding, leveraged yield farming with WBTC collateral, and various staking-adjacent and subsidy-phase products. Yields can run 5–15% in favorable regimes.

The structural problem is that the regimes these strategies require don't persist across full market cycles. Positive funding rates reverse. Covered calls cap upside in the rallies that drive most of BTC's long-run returns.[^2] Yield farming positions blow up in volatility events. Subsidy periods compress as protocols scale.

There's also an accessibility issue worth naming: many of the higher-yield strategies in this category — particularly the basis trade structures, sophisticated delta-neutral vaults, and various dual-position approaches — are only practically reachable through hedge funds or specialized DeFi products that most pragmatic BTC holders can't easily access. Even when the strategies happen to be working, the people asking "how do I get more BTC over time?" aren't typically the people who can capture them.

### The pattern

Each of the three architectures trades away something else to deliver the yield it produces. Borrowing-based products are capped by structural thin demand. Convert-and-return products bet against BTC's drift. Exotic products require trading away upside, simplicity, or regime independence.

This is why BTC yields look the way they do across the market. It's not bad implementation — it's the mathematical output of structurally constrained architectures. To produce a different output, you need a different architecture.

The on-chain record confirms it. Two of the most prominent live BTC yield protocols — Aave V3 WBTC lending and Ribbon V2's flagship BTC covered-call vault — have delivered roughly zero or negative BTC-denominated return across the period both have been operational, despite Bitcoin's significant USD appreciation over the same window.

| <picture><source media="(prefers-color-scheme: light)" srcset="https://frgs3.s3.us-west-1.amazonaws.com/thought_pieces/btc_jr_vs_yield_products/fig_empirical_btc_yield.png?v=7"><img alt="Live on-chain BTC-denominated NAVs of Aave V3 WBTC lending and Ribbon V2 BTC Theta Vault vs spot BTC baseline, fetched from Ethereum archive RPC" src="https://frgs3.s3.us-west-1.amazonaws.com/thought_pieces/btc_jr_vs_yield_products/fig_empirical_btc_yield.png?v=7"></picture> |
| :-- |
| *On-chain NAVs of two live BTC yield products vs spot BTC, BTC-denominated, Feb 2023 → Nov 2025. **Ribbon V2 BTC Theta Vault: 0.955 BTC** (−1.65%/yr) — visible step-down losses where weekly bull moves breached the covered-call strike. **Aave V3 WBTC lending: 1.003 BTC** (+0.11%/yr). Fetched directly from Ethereum archive RPC: `pricePerShare()` on the Ribbon vault and `getReserveNormalizedIncome(WBTC)` on the Aave V3 Pool.* |

---

## Why modest leverage hasn't been practical

The thought experiment showed that modest leverage on Bitcoin would have substantially outperformed any of these yield categories. So why hasn't anyone been doing it?

Portfolio theory hasn't been the obstacle. Kelly (1956), Merton (1969), Samuelson (1969), and Ayres-Nalebuff (2013) have made the case for moderate leverage on positive-drift assets for over half a century. The obstacle has been the available instruments. The existing leverage products — LETFs, perpetual futures, margin loans — were built for short-duration trading, not for buy-and-hold use, and each imposes structural costs that disqualify it from the use case modest BTC leverage requires:

- **Leveraged ETFs** rebalance daily, and the resulting path-dependent decay compounds against the holder over multi-month and multi-year horizons. They aren't built for buy-and-hold; they aren't deceptive about that, but it means they can't deliver the long-term compounding outcome the thought experiment shows.
- **Perpetual futures** charge funding costs that accumulate against the position. Held over years, the cumulative funding drag erases the leverage benefit.
- **Margin loans** can't passively hold a leverage target at all. A margin position's leverage ratio is set by current equity and current debt, so without rebalancing it drifts asymmetrically against the holder: drawdowns push the ratio *up* (more leverage, exactly when less is wanted), while rallies pull it *down* (less leverage, exactly when constant exposure is wanted). Maintaining any target across Bitcoin's volatility means continuous rebalancing — taxable events and active management throughout, the opposite of passive accumulation. Liquidation risk sits on top of all that: a single severe drawdown can force exit at the worst possible price.


These instruments serve their intended use cases — short-duration trading, hedging, speculation — and aren't badly designed for those uses. They're just not the right tool for "moderate leverage on a buy-and-hold position for years." That tool hasn't existed as a practical option.

This is why the simple, obvious answer has stayed unreachable. The math has been clear, and pragmatic BTC holders have correctly avoided the products that exist, because those products would have produced worse outcomes than just holding spot. Until now, "modest leverage on BTC" has been the right answer to the wrong instrument.

---

## What's new

Modest leverage on a positive-drift asset has always been growth-maximizing under reasonable assumptions. Portfolio theory has been clear about this for over half a century. Had you somehow held 1.33× leverage on Bitcoin from its earliest days, the thought experiment's outcome would be even larger than the 10-year version.

The constraint has been financing drag — and the related fact that no existing product even offers the Kelly-optimal ratio in deliverable form. The theoretical answer points to L ≈ 1.33 for Bitcoin. Existing products are offered at 2× (LETFs) or used at 2–3× (perps, margin), where the same equation hands them long-run growth at zero or below once realistic financing costs are applied. The growth-maximizing point exists in theory; it has not been operationally available in any product.

The question that follows: **how can financing drag be reduced?**

**The insight of 2factor finance:** existing leverage products fund their cost of leverage from a structurally expensive market. Funding rates on perpetuals, swap costs embedded in LETF construction, and margin loan rates all reflect, in different forms, the answer to one implicit question:

> *"How much would I have to pay you to hold a short position when you otherwise wouldn't?"*

That's an expensive question. Shorts get paid to hold positions against positive-drift assets — positions that lose money in expectation. Whatever financing cost gets priced off this question inherits its structural expense.

The cost of leverage doesn't have to be sourced from short demand. It can be sourced from yield-seeking capital instead. The implicit question becomes:

> *"How much would I have to pay you to hold a stable position when you otherwise wouldn't?"*

That market is structurally much cheaper. The prevailing risk-free rate plus a thin protocol-risk spread is enough. The spread between these two costs — the cost of paying shorts versus the cost of paying yield-seekers — is the structural savings that funds capital-efficient moderate leverage.

| <picture><source media="(prefers-color-scheme: light)" srcset="https://frgs3.s3.us-west-1.amazonaws.com/thought_pieces/btc_jr_vs_yield_products/fig_yield_cost_spread.png?v=7"><img alt="Annualized cost of leverage at 1.33× exposure: BTC perp funding (30d avg) vs BTC-Jr's stable-yield-anchored cost; structural spread averages ~9 percentage points since mid-2021" src="https://frgs3.s3.us-west-1.amazonaws.com/thought_pieces/btc_jr_vs_yield_products/fig_yield_cost_spread.png?v=7"></picture> |
| :-- |
| *Annualized cost of leverage at 1.33× exposure, mid-2021 to 2025. Perp funding averages 10.7% (with regime spikes); BTC-Jr averages 1.5%. The ~9-point gap is the structural savings tranching unlocks.* |


The architectural simplification: the entire apparatus of synthetic structures that today's leverage products use to extract leverage from short demand can be replaced by simple volatility tranching. A protocol takes the underlying asset and splits its volatility into a senior tranche (which pays yield-seekers their stable return) and a junior tranche (which absorbs the volatility and receives leveraged exposure). The construction is straightforward; the complex derivative mechanics that today's leverage products require to extract value from a structurally expensive market become unnecessary because the underlying mechanism is structurally cheap.

**The equation doesn't change. The economics do.**

Kelly's L\* is a property of the asset's drift and volatility, not of the leverage product — so the growth-maximizing allocation hasn't moved. What's moved is the financing drag. Leverage anchored to stable-yield demand instead of short demand carries a substantially lower cost of capital, and the same Kelly-optimal allocation now delivers positive compounding in practice instead of being eaten by drag.

| <picture><source media="(prefers-color-scheme: light)" srcset="https://frgs3.s3.us-west-1.amazonaws.com/thought_pieces/btc_jr_vs_yield_products/fig_three_regimes_133x.png?v=7"><img alt="Wealth trajectories of $1 over the 10-year window under four scenarios: spot BTC, ideal 1.33× (vol drag only), traditional 1.33× (LETF financing), and 2factor 1.33× (tranching-sourced financing)" src="https://frgs3.s3.us-west-1.amazonaws.com/thought_pieces/btc_jr_vs_yield_products/fig_three_regimes_133x.png?v=7"></picture> |
| :-- |
| *Same 1.33× target, same Bitcoin path, three financing architectures. 2factor tracks the ideal closely (financing cost (rf + 1%)/3 per Jr equity); traditional LETF financing surrenders most of the leverage benefit ((rf + 18%)/3, BITX-implied).* |


The architectural details for BTC-Jr specifically — how the funding mechanism works, how the tranches behave, how the financing cost is bounded — are in the [*Durable Leverage* paper](https://drive.google.com/file/d/14E0phxNhliy_Qc-kBPPbRAkaedBxe3ma/view?usp=sharing). BTC-Jr's cost of leverage is anchored to stable-yield demand, not to short demand. That cost spread, applied to a 1.33× leveraged position on a positive-drift asset, is what produces the outperformance the 10-year thought experiment shows.

BTC-Jr at 1.33× delivers what the thought experiment imagined. It is **sensible** — Kelly bounds say modest leverage on a positive-drift asset is growth-maximizing. It is **simple** — no hidden directional bet, no regime-dependent strategy, no upside cap. It is **scrutable** — verifiable mechanism, transparent financing cost, bounded leverage ratio. It is **reliable** — works across regimes, not just bullish ones; doesn't depend on continuing positive funding; doesn't blow up in volatility events. None of the three yield categories is all four of these. BTC-Jr is.

---

## What this means in practice

The thought experiment isn't hypothetical anymore. The 10-year backtest shows what modest leverage on Bitcoin would have produced across the available historical window. The architectural conditions to deliver it durably are now in place. Going forward, the simple obvious answer is operationally available.

| <picture><source media="(prefers-color-scheme: light)" srcset="https://frgs3.s3.us-west-1.amazonaws.com/thought_pieces/btc_jr_vs_yield_products/fig_yield_breakout.png?v=7"><img alt="Per-category breakout: each BTC yield product against BTC-Jr and spot, all BTC-denominated over the same 10-year window" src="https://frgs3.s3.us-west-1.amazonaws.com/thought_pieces/btc_jr_vs_yield_products/fig_yield_breakout.png?v=7"></picture> |
| :-- |
| *Each yield-product category against BTC-Jr and spot, BTC-denominated. Lending compounds modestly; covered-call and convert-and-return collapse far below 1 BTC over a bull decade.* |

If you've been holding Bitcoin and looking for a way to accumulate more without deploying more capital, you've been right about what you want. The reason nothing's worked is that the available instruments — yield products and existing leverage products alike — have all had structural problems that no implementation improvement could solve. That's now changing.

The pragmatic answer to "how do I get more Bitcoin over time" has been the same for as long as portfolio theory has had positive-drift assets to apply itself to. The only thing missing was an instrument that could actually deliver it without compromise. Modest leverage on Bitcoin, delivered through a construction that's sensible, simple, scrutable, and reliable, is what was missing. It's no longer missing.

---

*Specific backtest methodology and numerical results are in the [Durable Leverage paper](https://drive.google.com/file/d/14E0phxNhliy_Qc-kBPPbRAkaedBxe3ma/view?usp=sharing) (Fragments Research, 2026). A companion analysis covers the comparison between BTC-Jr and MicroStrategy / Bitcoin-treasury vehicles as the leveraged-BTC-exposure workaround that emerged outside DeFi.*

---

### References

[^1]: For analysis of how crypto cash-and-carry / basis-trade strategies derive their yield from the gap between perpetual futures and spot prices, see Schmeling, Schrimpf, and Todorov, "**Crypto Carry**," BIS Working Paper No. 1087 (2023, revised October 2025). The authors show crypto carry has reached >40% annualized at peaks but is "driven mainly by fluctuations in convenience yields" stemming from trend-chasing demand and limited arbitrage capital — i.e., the yield is compensation for risk-bearing in a structurally constrained market, not arbitrage. They also demonstrate that "a high crypto carry predicts future price crashes." Ethena's own protocol documentation describes the delta-neutral mechanism that converts BTC exposure into a USD-yield strategy via spot+short-perp construction; sUSDe annualized yields have ranged from low single digits to >30%, with funding flipping negative during stress events (Luna/3AC, FTX, October 2025 flash crash). The structural BTC-bet critique applies to any architecture that operationally converts BTC to a synthetic-USD position to capture this carry.

[^2]: The academic critique of covered-call strategies as yield enhancement is well-established. Israelov and Nielsen, "**Covered Call Strategies: One Fact and Eight Myths**," *Financial Analysts Journal*, Vol. 70, No. 6 (November/December 2014), decompose covered-call returns into equity premium + short-volatility premium + an uncompensated naive equity-reversal exposure, demonstrating that the "yield enhancement" framing misclassifies risk-transfer compensation as income. Whaley, "**Return and Risk of CBOE Buy-Write Monthly Index**," *Journal of Derivatives*, Vol. 10, No. 2 (Winter 2002), provides foundational empirical analysis of the BXM buy-write index, which has materially underperformed the S&P 500 across trending bull regimes. For a crypto-specific data point from the strategy's own designers: Ribbon Finance's own published backtest of their Theta Vault (their flagship covered-call strategy) showed a 20%-OTM weekly-call-selling strategy *underperformed spot ETH by 13.7 percentage points* during the March 2020 – March 2021 bull period, even with the strategy operating exactly as designed.
