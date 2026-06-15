# Tolerancing and GD&T

No part is made exactly to its nominal dimension. **Tolerancing** specifies the allowable variation so that parts fit and function while remaining manufacturable. It is where design meets the factory.

## Limits and Fits

A **tolerance** is the permissible range of a dimension. Mating parts are designed for a **fit**:

| Fit | Behavior |
|---|---|
| Clearance | always assembles with gap (sliding) |
| Interference | always press-fit (no slip) |
| Transition | may be either |

Standard fit systems (ISO hole-basis/shaft-basis) tabulate tolerances by size and grade (IT grades).

## Tolerance Stack-Up

When several toleranced dimensions add along a chain, their variations accumulate:
- **Worst-case:** sum the tolerances — guarantees fit but is conservative.
- **Statistical (RSS):** \\(T_{\text{total}} = \sqrt{\sum T_i^2}\\) — realistic when variations are independent and random.

Stack-up analysis prevents the surprise of in-spec parts that won't assemble.

## Geometric Dimensioning and Tolerancing (GD&T)

Plain ± tolerances cannot capture form and orientation. **GD&T** (ASME Y14.5) adds geometric controls relative to **datums**:

| Category | Controls |
|---|---|
| Form | flatness, straightness, circularity |
| Orientation | parallelism, perpendicularity, angularity |
| Location | position, concentricity |
| Runout | circular/total runout |

A **feature control frame** ties a tolerance to datums, and **maximum material condition (MMC)** allows bonus tolerance — communicating function precisely and unambiguously to manufacturing and inspection.

## Why It Matters

Good tolerancing balances **function** (tight enough to work) against **cost** (loose enough to make cheaply). Over-tolerancing wastes money; under-tolerancing causes assembly failures and field returns.

## See Also

- [Machine Elements](machine-elements.md)
- [Mechanical Properties](../../app/materials-science/properties.md)
- [Statistical Modeling](../../cs/data/modeling.md) — stack-up statistics.
