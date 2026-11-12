# DeepSeek-R1 — Paper Summary

- **Authors:** DeepSeek-AI.
- **Paper:** *DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning* (2025).
- **Version summarized:** [arXiv:2501.12948v2](https://arxiv.org/abs/2501.12948v2), from the supplied source archive.
- **Local entry point:** [sn-article.tex](source/sn-article.tex); supplementary material: [appendix.tex](source/appendix.tex).
- **Status:** Reading summary and critical commentary; results below are reported by the authors, not independently reproduced.

## Central Question and Contribution

Can reinforcement learning improve an already pretrained language model's reasoning without first supplying supervised reasoning demonstrations?

The paper presents **DeepSeek-R1-Zero**, which applies RL directly to DeepSeek-V3-Base, and **DeepSeek-R1**, which combines supervised fine-tuning (SFT), reasoning-oriented RL, and preference-oriented alignment. It also demonstrates that reasoning trajectories from a stronger teacher can improve smaller models through supervised distillation.

“Pure RL” refers to R1-Zero's post-training procedure. It does not mean learning language or reasoning from scratch without pretraining, prompts, or answer supervision.

## Method

### R1-Zero: Learning from Verifiable Outcomes

The authors use **Group Relative Policy Optimization (GRPO)**. For each question, the policy samples multiple responses. Each response's reward is normalized relative to the group's mean and standard deviation to obtain its advantage. A clipped policy objective and reference-policy KL term constrain updates. GRPO avoids training a separate critic model, reducing that component of RL overhead.

The rewards combine correctness checks and formatting requirements. Mathematical answers can be checked against known solutions; generated programs can be evaluated with test cases. The training prompt asks for a reasoning segment followed by an answer, but does not supply detailed reasoning demonstrations. Learned neural reward models are avoided for R1-Zero's reasoning reward because of reward-hacking concerns.

During training, the authors observe longer responses, verification, reconsideration, and exploration of alternative approaches. They interpret these patterns as reasoning behaviors encouraged by outcome-based RL.

### R1: Combining Reasoning and Alignment

R1 uses a multistage pipeline:

1. **Cold-start SFT:** Thousands of curated reasoning examples improve readability and provide an initial policy.
2. **Reasoning RL:** Verifiable rewards improve reasoning; a language-consistency reward addresses language mixing.
3. **Rejection sampling and SFT:** Correct, filtered trajectories contribute approximately 600,000 reasoning examples, combined with approximately 200,000 non-reasoning examples.
4. **Further RL:** Reasoning rewards are combined with rewards for helpfulness and safety on general tasks.

The preference component should not be described simply as direct human ranking of every response. In this version, the helpfulness reward model uses preference pairs judged by DeepSeek-V3; the pipeline also includes human annotation and verification. Helpfulness is evaluated on the final answer, while safety evaluation considers the full response.

### Distillation

Smaller Qwen- and Llama-based models are fine-tuned on approximately 800,000 teacher-generated examples. These distilled models receive SFT without an additional RL stage in the reported experiments.

## Main Reported Results

| Evaluation | Reported result | Source location |
| --- | --- | --- |
| R1-Zero on AIME 2024 | Pass@1 rises from 15.6% to 77.9% during RL; self-consistency raises accuracy to 86.7% | Main text, “Incentivize Reasoning Capability in LLMs” |
| Final R1 on AIME 2024 | 79.8% pass@1 | Main text, developmental-stage table (`tab:stage_r1`) |
| Final R1 on MATH-500 | 97.3% pass@1 | Same developmental-stage table |
| Distilled Qwen-32B versus Qwen2.5-32B-Zero | 72.6% versus 47.0% AIME 2024 pass@1 | [Distillation comparison table](source/tables/distill_vs_rl.tex) |

The evaluation appendix estimates pass@1 by averaging correctness over repeated stochastic samples. This estimates single-sample success; it is distinct from majority-vote selection or pass@k, where any successful candidate can count. Do not compare these metrics as though they used the same inference budget.

The developmental-stage results show that reasoning improvements and preference alignment are separate objectives: reasoning RL improves reasoning benchmarks, while later general-purpose training particularly improves instruction-following and preference-oriented evaluations.

## Limitations and Critical Assessment

**Reported limitations:** R1-Zero has readability and language-mixing problems. R1 still exhibits overthinking, prompt sensitivity, and limitations in structured output, tool use, and software engineering. Model-based rewards can be exploited; the appendix gives an example in which reward increases while Codeforces performance declines. The authors also acknowledge that n-gram decontamination cannot exclude paraphrased benchmark leakage.

**Seminar interpretation:** The results support the usefulness of verifiable rewards on the tested domains. They do not establish that outcome rewards guarantee correct intermediate reasoning or transfer equally well to subjective tasks. Reflective wording and longer chains are observations, not proof that every intermediate statement faithfully explains the model's computation. The final R1 pipeline combines several interventions, so its total improvement cannot be assigned to preference learning alone.

The distillation comparison favors teacher supervision in this experimental setting; it does not establish that distillation universally outperforms RL at every model size or compute budget.

## Relevance to the Seminar Question

This paper connects **training incentives** to a model's ability to use longer inference-time reasoning. It separates verifiable task rewards from broader preference alignment, while showing that both can appear in one practical pipeline.

A useful comparison with [Snell et al.](../scaling-test-time-compute/SUMMARY.md) is the distinction between learning a stronger reasoning policy during training and choosing how to spend compute on a particular question during inference.

## Reading Map

- [Main text](source/sn-article.tex): “DeepSeek-R1-Zero,” “Reward Design,” “DeepSeek-R1,” “Model-based Rewards,” and “Conclusion, Limitation, and Future Work.”
- [Appendix](source/appendix.tex): “Data Recipe,” “Reward Hacking,” “Experiment Setup,” “An Analysis on CoT Length,” and “Distillation v.s. Reinforcement Learning.”
- [Distilled-model results](source/tables/distill_eval.tex): benchmark and metric details for the smaller models.
