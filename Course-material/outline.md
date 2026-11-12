# Paper Outline (draft v2, due Fri 13 Nov 2026, 23:59)

Topic 6: Reasoning Models, RLHF and Test-Time Compute. Mentor: Kaiwei Lei.
Format: IEEE LaTeX template, 6 to 8 pages. Method: structured literature analysis.

## Working title

What Is Rewarded, What Is Updated, What Is Spent: Three Routes to Better LLM Reasoning

## Research question

The assigned topic is broad, so we narrow it with one lens from Lambert's course: separate **what behavior is rewarded**, **how parameters are updated**, and **how much compute is spent on a new question**. Preference learning, verifiable rewards and test-time compute act on different parts of this picture.

**RQ:** How do preference learning, verifiable rewards and additional inference-time compute each improve LLM reasoning, and do they raise single-sample accuracy or the chance of selecting a correct answer from many candidates, at what cost?

**Sub-questions**

1. **Mechanism.** What does each route reward or select, how does it change the model or its outputs (policy update versus more inference), and what signal does it need (human or AI preference labels, a checkable answer, a learned verifier)?
2. **Evidence.** What gains do the core sources report, measured how (pass@1, pass@k, selected-answer accuracy) and under which budget, and how comparable are these numbers?
3. **Limits.** Where does each route fail or depend on assumptions (reward over-optimization, verifier errors, difficulty-estimation cost, tasks without checkable answers), and what does this imply for combining them?

**Working hypothesis (to test, not assume):** the routes are complementary. Training with preferences and verifiable rewards shapes a policy that can use long reasoning, and inference-time allocation decides how much of that capability to spend on each question. Whether training adds new capability or makes existing capability more reliable is an open question that we report and do not settle.

## Scope

- In scope: RLHF pipeline (SFT, reward models, policy optimization), policy-gradient methods as used for reasoning (PPO, RLOO, GRPO), DPO as the offline alternative, RLVR, distillation of reasoning traces as a comparison point, best-of-N, PRM-guided search, sequential revisions, compute accounting, over-optimization.
- Out of scope: tool use and agents, character training, multimodal reasoning, hardware and serving cost, full derivations of the algorithms.
- Caveat to state in the paper: the core sources use different models and benchmarks (mostly competition math), and Lambert's course is an educational synthesis, not a controlled experiment. We compare reported findings and run no experiments. Claims about specific methods must cite the primary paper.

## Structure and page budget (8 pages)

| # | Section | Pages | Content |
| --- | --- | --- | --- |
| 0 | Abstract | 0.2 | About 150 words: question, method, headline finding |
| 1 | Introduction | 1.0 | Motivation (reasoning models, growing training and inference cost), RQ, sub-questions, contribution, structure |
| 2 | Background and related work | 1.5 | RLHF pipeline and reward models, policy gradients (PPO, GRPO), DPO, RLVR, chain of thought, test-time compute; framework and vocabulary from Lambert, each concept anchored in its primary paper |
| 3 | Methodology | 0.8 | Search strategy, selection criteria, comparison criteria and metrics below |
| 4 | Three routes | 2.2 | 4.1 Preference learning (reward models, PPO, DPO, AI feedback). 4.2 Verifiable rewards (R1-Zero, R1 pipeline, distillation). 4.3 Inference-time compute (verifiers, search, revisions, difficulty-dependent allocation) |
| 5 | Comparison and discussion | 1.6 | Comparison table, sub-questions 2 and 3, combined pipelines, when to use which, gaps |
| 6 | Conclusion and future work | 0.4 | Answer to the RQ, open problems |
| | Bibliography | | IEEE style, every reference checked against the source |

## Comparison criteria (Section 3, used as a table in Section 5)

| Criterion | Preference learning (RLHF, DPO) | Verifiable rewards (DeepSeek-R1) | Inference-time compute (Snell et al.) |
| --- | --- | --- | --- |
| What is rewarded or selected | Comparative judgments of responses | Checked correctness, plus format and language rewards | Verifier or consensus choice among candidates |
| Parameters change? | Yes | Yes | No (verifier and revision models are trained beforehand) |
| Signal needed | Human or AI preference labels, reward model | Rule-based checker (answers, code tests) | Learned PRM and ORM, trained revision model |
| Main metric | Preference win rate and general evaluations | Pass@1 on math and code benchmarks | Selected-answer accuracy under a generation budget |
| Reported gain | Per Lambert: instruction following and alignment, not reasoning alone | AIME 2024 pass@1 from 15.6% to 77.9% (R1-Zero, reported) | Up to 4x fewer generations than best-of-N in the revision setting (reported) |
| Main failure mode | Reward over-optimization, optimizing a compressed proxy of human goals | Model-based reward hacking, language mixing, overthinking | Verifier exploitation, revisions that break correct answers |
| Hidden costs | Preference data, reward model, rollouts | RL training compute, data curation | Difficulty estimation (2,048 samples per question, excluded from the efficiency analysis) |
| Evidence scope | Broad assistant behavior | Math, code, general benchmarks | One model family, MATH benchmark |

All numbers come from the authors' summaries in `Sources/` and must be re-checked against the papers and course material before they go into the draft. The final R1 pipeline combines SFT, reasoning RL and preference alignment, so its total gain cannot be assigned to one route.

**Metric discipline:** keep pass@1 (one sample), pass@k (coverage, any candidate correct) and selected-answer accuracy apart. Compare routes under an explicit budget (tokens, FLOPs, latency), not by treating these as equal.

## Golden thread

Motivation: reasoning models improve through training and through inference, at different cost. Background: the RLHF toolbox, RLVR and test-time compute. Related work and gap: the three sources are well known, but compared on one lens (what is rewarded, updated and spent) and one set of metrics they are rarely put side by side. Question: the RQ above. Method: structured literature analysis with fixed criteria. Results: the comparison table. Conclusion: which route improves single-sample accuracy, which improves selection, and what each costs. Future work: unified compute accounting across training and inference, and reasoning without checkable answers.

## Sources

Core:
- Lambert, RLHF Book Course (2025 to 2026), local snapshot `Sources/rlhf-book-course/` (upstream commit 0be34d8). Use `CITATION.bib` there for the citation. Cited so far: reward-model chapter, policy-gradient chapter, reasoning chapter, direct-alignment chapter, and the over-optimization lecture, all via the summary only.
- DeepSeek-AI (2025), arXiv:2501.12948v2.
- Snell et al. (2024), arXiv:2408.03314v1.

Local summaries: `Sources/rlhf-book-course/SUMMARY.md`, `Sources/deepseek-r1/SUMMARY.md`, `Sources/scaling-test-time-compute/SUMMARY.md`.

To find and verify (not yet checked, do not cite until confirmed): primary papers for PPO, RLHF from human preferences, Bradley-Terry reward modeling, GRPO, DPO, a process-reward-model paper, and one or two recent follow-ups on test-time scaling. Lambert's `refs.bib` in the course folder is a place to look for exact entries.

## Open points for the mentor

- Is a comparison of reported findings enough as the method, or does the mentor expect a small experiment?
- Is the three-routes framing acceptable, and is the weight on preference learning right?
- Bachelor scope: confirm 6 to 8 pages and the group arrangement with Nicolas.

## Open points for us

- Who writes which section (suggestion: one of us takes 2, 4.1 and 4.2, the other 4.3, 5 and 6).
- AI use disclosure line for the IEEE rule.
- First reading pass of the course: Lectures 2, 3, 5, 6, 9, 10 and 12, as the summary suggests.
