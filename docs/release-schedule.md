# Release Schedule

This document defines the release schedule for Microsoft 365 Agents Toolkit products.

## CY26 Q1

| Products | Release Type | Version | Cut Bits Date | Status | Branch | preid | series |
|----------|--------------|---------|---------------|--------|--------|-------|--------|
| VSC  | Prerelease   | 6.5.6 | 2026-01-2 |  | release/6.5 | preview | CY260128 |
| VSC  | Prerelease   | 6.5.7 | 2026-02-04 |  | release/6.5 | preview | CY260204 |

## Automation Configuration

To enable automated release branch creation and deployment, define the CD parameters directly in the schedule.
These values are authoritative (the automation does not infer them).

For rows that should be automated, include these columns in the table:
- `Branch`
- `preid`
- `series`

Products column has to be either `VSC` or `VS`.

The automation workflow will:
- Parse this schedule
- Create release branches based on the `Branch` column
- Trigger CD pipeline with the provided parameters (`preid`, `series`) and derived `vsrelease`
- Require manual approval before execution

Notes:
- `Cut Bits Date` must be in ISO format `YYYY-MM-DD` (used for automatic selection).
- `vsrelease` is derived from `Products`: `VS` => true, `VSC` => false.