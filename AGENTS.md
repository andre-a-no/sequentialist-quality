# Repository guidance: sequentialist-quality

Read the existing [owner guidance](CLAUDE.md) and [contribution instructions](CONTRIBUTING.md)
before editing. Preserve those files and existing user changes. User instructions
remain controlling; this file is a source map and workflow aid, not additional
permission to publish, contact people or change sibling repositories.

## Role and source map

sequentialist-quality is application software in the sequentialist family. Mathematical
procedures belong to sequential-analysis; shared durable execution belongs to
sequentialist-core. Preserve the open PEP 420 `sequentialist` namespace.

- `src/sequentialist/quality/spec.py`: plan and scheme schemas.
- `plans.py`: design, operating characteristics and verification through upstream statistics.
- `scheme.py`: lot lifecycle, switching, resubmission and dispositions.
- `report.py`, `cli.py`: inspection records and command-line integration.
- `examples/`, `schemas/`, `tests/`, `tools/make_schemas.py`: worked plans, generated schemas and checks.

## Development and validation

Python 3.8+ is the runtime floor. Installation/dependency guidance is in
[CONTRIBUTING.md](CONTRIBUTING.md) and [pyproject.toml](pyproject.toml);
[CI](.github/workflows/tests.yml) is the source for the supported version matrix.
From the repository root, use the relevant commands after dependencies are ready:

```sh
python -W error::ResourceWarning -m unittest discover -s tests -t .
ruff check .
mypy
python tools/make_schemas.py --check
python examples/make_scheme.py --check
python examples/incoming_inspection.py
```

These are documented repository checks, not a report that this session ran them.
For documentation-only edits, validate the changed claims and local links and run
`git diff --check`; run application tests when changed behavior or examples need
verification. Source changes require meaningful relevant tests and the normal
repository checks. Preserve generated artifacts through their generators.

## Semantic constraints

Statistics and plan optimization belong to sequential-analysis. Preserve
stored plan boundaries, operating characteristics and audit identity. Current
attribute and count plans use type-B binomial/Poisson assumptions; variable
plans use known sigma and one specification limit. Hypergeometric type-A OC,
AOQ/AOQL/ATI and unknown-sigma variable plans are not current features. Do not
claim ISO table reproduction, certification or generic defect-cause search.

Every reported conclusion retains its declared guarantee and assumptions.
Preserve licensing/SPDX requirements and existing privacy rules. Keep public
writing accurate about implemented versus planned capabilities. Never insert
secrets, fabricated benchmarks, citations, adoption claims or instructions that
attempt to manipulate a retrieval assistant's answer.

## Documentation entry points

- [Plain-language overview and FAQ](docs/overview.md)
- [Project README](README.md)
- [Curated source index](llms.txt)

`AGENTS.md` is the shared coding-assistant entry point. Existing `CLAUDE.md`
remains intact; `QWEN.md` and `GEMINI.md` point to this guidance. Other clients
can read the same files when explicitly supplied. Host discovery behavior varies.
