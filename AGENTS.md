# Repository Guidelines

## Seminar Context & Scope

This repository supports a literature review, written seminar paper, and oral presentation for Emerging Topics in Machine Learning and AI.

- **Area 2:** Model Learning, Adaptation and Reasoning.
- **Topic 6:** Reasoning Models, RLHF and Test-Time Compute.
- **Research question:** How do preference learning, verifiable rewards and additional inference-time computation improve reasoning?
- **Supervisor (Betreuer):** Kaiwei Lei.

Bachelor’s or Master’s level remains unspecified. Confirm assignment-specific requirements before assuming a scope, length, or format.

## Starting Literature

The supplied starting references are:

1. Lambert (2025–2026), [RLHF Book Course](https://rlhfbook.com/course).
2. DeepSeek-AI (2025), [DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning](https://arxiv.org/abs/2501.12948).
3. Snell et al. (2024), [Scaling LLM Test-Time Compute Optimally Can Be More Effective than Scaling Model Parameters](https://arxiv.org/abs/2408.03314).

## Project Structure & Organization

Use the following layout; introduce additional directories only as needed:

- `Sources/`: downloaded paper sources, version metadata, and per-paper summaries; preserve originals under each paper's `source/` directory.
- `paper/`: paper source.
- `presentation/`: slides and speaker notes.
- `literature/`: additional reading notes and the seminar bibliography.
- `assets/`: attributed figures and diagrams.
- `src/`, `notebooks/`, `tests/`: optional experiments and tests.

Use descriptive filenames such as `literature/author-year-short-title.md`. Keep generated outputs separate from editable sources.

## Research & Writing Standards

Prioritize original papers. Verify bibliographic details, versions, and claims before citing them. Attribute numerical results and adapted figures. Distinguish reported findings from interpretation; never invent references or results.

Compare preference learning, verifiable rewards, and inference-time computation while distinguishing training from inference. Assess assumptions, evaluation settings, compute costs, limitations, and open problems. Keep terminology and citations consistent across paper and slides.

## Development & Validation Commands

No build toolchain or test framework is configured. Use `git status --short` to inspect changes, `git diff` to review tracked edits, and `git diff --check` for whitespace errors.

Document adopted build, execution, and test commands in `README.md`. Check citations, figure attribution, paper–slide consistency, and rendered layout. For experiments, record dependencies, seeds, and evaluation settings.

## Commit & Pull Request Guidelines

No commit conventions exist yet. Use focused, imperative subjects, such as `Compare verifiable rewards and preference learning`. Pull requests should explain changes, sources, and validation; include previews for visual changes.

## Repository Hygiene

Exclude secrets, private material, local environments, and large generated artifacts. Check redistribution permissions for publications and datasets.
