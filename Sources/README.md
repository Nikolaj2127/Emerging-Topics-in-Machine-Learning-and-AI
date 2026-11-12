# Seminar Sources

Local reading material for **Reasoning Models, RLHF and Test-Time Compute**, supervised by Kaiwei Lei.

| Resource | Local version | Summary | Original files |
| --- | --- | --- | --- |
| Nathan Lambert, *RLHF Book Course* (2025–2026) | Snapshot: 2026-11-12; upstream commit `0be34d8` | [Summary](rlhf-book-course/SUMMARY.md) | [Course materials and lecture catalog](rlhf-book-course/README.md) |
| DeepSeek-AI, *DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning* (2025) | arXiv:2501.12948v2 | [Summary](deepseek-r1/SUMMARY.md) | [LaTeX, figures, tables, and bibliography](deepseek-r1/source/) |
| Charlie Snell, Jaehoon Lee, Kelvin Xu, and Aviral Kumar, *Scaling LLM Test-Time Compute Optimally can be More Effective than Scaling Model Parameters* (2024) | arXiv:2408.03314v1 | [Summary](scaling-test-time-compute/SUMMARY.md) | [LaTeX, figures, and bibliography](scaling-test-time-compute/source/) |

## Organization

Each resource has an authored `SUMMARY.md` alongside a `source/` directory. The paper directories contain the complete, unchanged contents of their downloaded arXiv archives. Those archives contain document sources and supporting assets, not model implementations or training datasets. Figure PDFs inside the paper archives are individual assets, not complete paper PDFs.

The summaries describe the exact local versions. They distinguish reported findings from critical seminar discussion points and link to the relevant source files and section names. Read the papers before using the summaries as evidence in the seminar paper.

Lambert's course directory contains the published lecture sources and slide PDFs, book chapters, companion code, bibliographies, and original license texts. Its [README](rlhf-book-course/README.md) describes snapshot coverage and its [manifest](rlhf-book-course/manifest.json) records provenance and checksums. Recordings remain linked online.

## Provenance

Imported on **2026-11-12** from the supplied files in Downloads. Archive checksums allow the inputs to be identified without keeping duplicate compressed copies here.

| Source archive | SHA-256 |
| --- | --- |
| `arXiv-2501.12948v2.tar.gz` | `71b18a7e73434b7b49981e380d5d2eac54548f2359e93059dfcba8e1f05afcc3` |
| `arXiv-2408.03314v1.tar.gz` | `f179cbc6b43f09285096e8a088bdacb8b2f0af4f6e3bcaaf8c12721a0f5331f9` |

## Source Licenses

License links checked on the version-specific arXiv pages on **2026-11-12**:

| Paper | License linked by arXiv |
| --- | --- |
| [DeepSeek-R1, v2](https://arxiv.org/abs/2501.12948v2) | [arXiv non-exclusive distribution license](https://arxiv.org/licenses/nonexclusive-distrib/1.0/) |
| [Scaling LLM Test-Time Compute, v1](https://arxiv.org/abs/2408.03314v1) | [Creative Commons Attribution 4.0 International](https://creativecommons.org/licenses/by/4.0/) |

The original files were supplied by the repository owner and are preserved unchanged, with their attribution and notices. The arXiv distribution license is a grant to arXiv, not a general reuse license. No standalone paper license file was included in either archive; model-weight and template licenses should not be applied to the papers or repository as a whole.

Lambert's upstream [licensing statement](rlhf-book-course/source/README.md) assigns CC BY-NC-SA 4.0 to book chapters and MIT to the remaining material. The original texts and the summary's attribution are preserved in the [course folder](rlhf-book-course/README.md).
