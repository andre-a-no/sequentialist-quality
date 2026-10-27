# Changelog

## sequentialist-quality 0.1.0 — unreleased

First version, on sequentialist-core 0.1.0 and sequential-analysis 0.4.
Developed in the repository that is now
[sequentialist-core](https://github.com/andre-a-no/sequentialist-core);
moved here with its history.

- Plans `quality.plan/1` by attributes, nonconformities and variables (known
  sigma, one limit); sequential plans designed with
  `design.kiefer_weiss_plan` (truncated, both risks met, smallest average or
  maximum number of items) and single sampling plans with curtailment; the
  designed boundaries and operating characteristic stored in the plan.
- Operating characteristic and average sample number at any quality,
  exact for attributes and nonconformities; checked against the binomial and
  Poisson formulas of single sampling and by simulation of the executed plans.
- Schemes `quality.scheme/1`: lots inspected item by item with `PlanTest`;
  switching between normal, tightened and reduced inspection; discontinuation
  and resumption; rework and resubmission; dispositions and concessions with
  actor and reason; a CUSUM watch on the supplier; every decision in the audit
  log; inspection records of lots and reports of schemes.
- `sequentialist quality design | oc | check | schema | protocol | report`.
