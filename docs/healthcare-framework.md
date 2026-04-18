# Healthcare Framework
## Bridge Document

Healthcare in this framework has two distinct policy layers:

1. `Basic care`
2. `Earned healthcare continuity insurance`

Those layers are related, but they solve different policy problems and should be read separately.

They also do **not** replace Medi-Cal. Medi-Cal remains the primary federal-state public insurance program for Californians who already qualify for it. The purpose of this framework is to add a universal baseline below the current patchwork and a work-earned continuity layer above that floor without making the entire architecture depend on a wholesale rewrite of Medi-Cal eligibility.

In the California version of the framework, that continuity layer is positioned first as a bridge model: an earned, time-limited major-medical backstop for periods when ordinary coverage fails.

> Basic care is universal. Medi-Cal stays primary where it already applies. Earned healthcare continuity insurance protects the household when ordinary coverage fails and neither Medi-Cal nor adequate private coverage fills the gap.

The operating hierarchy should be stated just as plainly:

1. `Basic care` first
2. `Medi-Cal` where eligible
3. adequate private coverage where active
4. the bridge only when ordinary coverage fails

## Basic Care

The universal healthcare baseline is defined in:

- [Basic Care Framework](basic-care-framework.md)

That document explains:

- what basic care includes
- what sits outside the basic-care package
- pregnancy and family inclusion
- basic-care financing and administration
- provider participation, pricing, fraud controls, and quality safeguards

## Earned Healthcare Continuity Insurance

The broader work-earned continuity layer beyond basics is defined in:

- [Earned Healthcare Continuity Insurance Framework](earned-healthcare-continuity-insurance-framework.md)

That document explains:

- how earned healthcare continuity insurance differs from basic care
- why it should be framed as a work-earned major-medical bridge
- the household-month bridge bank
- the current California bridge-bank math: `0.008` months per taxed hour, `150` credited hours per month, and a `12.0` month cap
- voluntary, involuntary, and cliff-driven transition use cases
- the objective tests for when private coverage is or is not adequate
- the anti-bureaucracy rules for automatic accrual, activation, and renewal
- work incentives and high-income draw suspension
- emergency and higher-acuity payment protection
- the handoff to Medi-Cal, private insurance, and the marketplace
- the boundary between covered advanced care and excluded experimental care
- family-unit bridge coverage
- financing and unresolved design questions

## Reading Order

For healthcare, the clean reading order is:

1. [Core README](../README.md)
2. [Basic Care Framework](basic-care-framework.md)
3. [Earned Healthcare Continuity Insurance Framework](earned-healthcare-continuity-insurance-framework.md)

The federal and California framework documents then summarize those two layers at the jurisdictional level, while treating Medi-Cal as the public backbone California has to build around.
