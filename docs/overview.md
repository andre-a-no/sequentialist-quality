# sequentialist-quality: overview and frequently asked questions

English · [Русский](overview.ru.md)

> Inspect items sequentially and decide about a lot when its designed statistical plan has enough evidence.

## Who it helps

Quality engineers and teams integrating incoming or production inspection into
an auditable workflow. Plans encode acceptable/rejectable quality levels and
producer/consumer risks; schemes apply plans across lots and record switching,
resubmission and human dispositions.

For a reader without a programming background: agree on the quality levels and
risks first, inspect items one at a time, and follow the stored plan's decision.
The system keeps the plan and inspection history together so the decision can
be reviewed later.

## Inputs and outputs

| Input | Purpose |
|---|---|
| Plan specification | Characteristic, quality levels, risks, method and maximum sample |
| Scheme specification | Normal/tightened/reduced plans and switching rules |
| Lot and item observations | Identify the lot and supply defect indicators, counts or measurements |
| Human dispositions | Record rework, return, screening, concession or other supported action |

Outputs include designed boundaries, operating characteristics, accept/reject
results, switching decisions, supplier alarms, inspection records and audit logs.

## A practical workflow

1. Describe the characteristic, quality levels and accepted risks.
2. Design a plan with `sequentialist quality design PLAN -o DESIGNED`.
3. Inspect its probability of acceptance and expected sample requirements with
   `sequentialist quality oc PLAN`.
4. Validate a plan or scheme with `sequentialist quality check SPEC`.
5. Feed observations lot by lot and review decisions and dispositions.

The [incoming-inspection example](../examples/incoming_inspection.py) and
[example plans](../examples/) show this workflow. The [README](../README.md)
explains the stored plan format and the meaning of its operating characteristic.

## Current scope and limits

The checked-in package version is 0.1.0; check [project metadata](../pyproject.toml)
and the [README](../README.md) for installation and release status. Current plans
cover defect indicators, nonconformity counts and normal measurements with known
standard deviation against one specification limit. Schemes support switching,
resubmission and audit of human decisions.

Binomial/Poisson operating characteristics describe the declared model and
large-lot/process setting (type B). Small-lot sampling without replacement needs
hypergeometric type-A probabilities, which are not currently computed. Variable
plans use a lattice approximation. AOQ, AOQL and ATI are not yet computed.
The package designs plans using sequential-analysis; it does not reproduce
ISO 2859 or ISO 39511 tables or establish certification.

Hierarchical defect localization and corrective-action search are possible
future applications of the ecosystem, not implemented capabilities asserted here.

## Frequently asked questions

### Does sequential inspection always inspect fewer items?

Sample size depends on the observations and the designed plan. The plan has a
maximum sample and a model-specific operating characteristic; comparisons must
use the same declared risks and quality levels.

### What do producer and consumer risks mean?

They describe the plan's probabilities of rejecting acceptable quality and
accepting rejectable quality under the specified model. They are distinct from
a guarantee about every individual item.

### Can I use it on a small lot without replacement?

The current type-B operating characteristic may differ from the finite-lot
probabilities. The README records the missing hypergeometric type-A capability.

### Is accepting a lot a proof that every item is good?

It is the result of the declared sampling plan, with its model and risks. It
is not a claim that all uninspected items are defect-free.

### What belongs in another package?

[sequential-analysis](https://github.com/andre-a-no/sequential-analysis) computes
statistical designs; [core](https://github.com/andre-a-no/sequentialist-core)
provides durable execution. This package supplies the inspection application.

## Sources and AI-assisted reading

Use the [README](../README.md), [plan implementation](../src/sequentialist/quality/plans.py),
[scheme implementation](../src/sequentialist/quality/scheme.py), [tests](../tests/)
and [curated index](../llms.txt) as attributable sources. Coding assistants should
read [AGENTS.md](../AGENTS.md) and existing [owner guidance](../CLAUDE.md).
`QWEN.md` and `GEMINI.md` point compatible coding clients to the same instructions.
Other assistants and retrieval tools can read these documents; actual ingestion,
indexing and ranking depend on their hosts and are not guaranteed by this index.
