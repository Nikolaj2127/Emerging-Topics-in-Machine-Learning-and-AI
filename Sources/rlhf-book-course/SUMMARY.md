# RLHF Book Course — Summary

- **Author:** Nathan Lambert.
- **Source:** [RLHF Book Course](https://rlhfbook.com/course), accompanying *Reinforcement Learning from Human Feedback*.
- **Snapshot:** Retrieved 2026-11-12; Markdown and companion code pinned to upstream commit `0be34d8ed8a66cd0b41d4f98123987e2526d05cd`. Website slide PDFs are separately hashed snapshots.
- **Basis:** Published slide sources and selected core book chapters. Recordings are indexed for further study; this is not a video transcript or a claim to have watched every lecture.
- **Navigation:** [Material index](README.md), [lecture and recording catalog](LECTURES.md), and [source manifest](manifest.json).

## Overview

The course treats RLHF as part of the broader process of **post-training**: adapting a pretrained language model into a useful assistant, reasoner, or tool-using system. Its main message is that successful behavior depends on the combination of training objectives, feedback data, inference procedures, and engineering choices.

For this seminar, distinguish three questions: **what behavior is rewarded**, **how model parameters are updated**, and **how much computation is spent answering a new question**. Preference learning, verifiable rewards, and test-time compute address different parts of this picture and can be combined.

## 1. Instruction Tuning, Reward Models, and Selection

Supervised fine-tuning (SFT), also called instruction fine-tuning, learns from example responses. It establishes instruction-following behavior, output structure, and task conventions. Chat templates and which tokens contribute to the loss matter: a model should learn the intended assistant behavior rather than accidentally train on the wrong parts of a conversation.

Preference reward models learn from comparisons between responses. The Bradley–Terry formulation models a chosen response beating a rejected response through a sigmoid of their reward difference. The fitting objective averages **log-likelihoods** across the dataset, rather than maximizing the average raw preference probability.

The course distinguishes preference models, outcome reward models, process reward models, and generative judges. Their scores have different meanings and supervision requirements; they should not be treated as interchangeable correctness oracles.

Rejection sampling uses a scorer to select candidate responses for further training. **Best-of-N selection at inference** also generates and ranks candidates, but need not update model weights. This distinction separates data selection from inference-time reasoning strategies.

Sources: [Lecture 2](source/teach/course/lec2-chap4-5-9.md), [reward-model chapter](source/book/chapters/05-reward-models.md), and [Q&A 2 corrections](source/teach/course/qa-02.md).

## 2. Policy Gradients: PPO, RLOO, and GRPO

Policy-gradient training samples responses, scores them, and changes the policy to make advantageous behavior more likely. Advantages compare an outcome with a baseline, reducing variance and helping determine which sampled actions should be reinforced.

The course develops several related algorithms:

- **REINFORCE:** Uses sampled returns to estimate a policy gradient.
- **RLOO:** Uses other responses to the same prompt to construct a leave-one-out baseline.
- **PPO:** Uses constrained updates, importance ratios, and commonly a learned critic with advantage estimation.
- **GRPO:** Uses relative rewards within a group of responses, avoiding a separate learned critic in the standard formulation.

The reference policy used to constrain drift and the older policy that generated a rollout serve different purposes. Implementation details—including normalization, clipping, response masks, numerical precision, and loss aggregation—can change the effective objective. Asynchronous rollouts improve throughput but introduce stale-policy data and additional correction requirements.

Sources: [Lecture 3](source/teach/course/lec3-chap6-p1.md), [Lecture 4](source/teach/course/lec4-chap6-p2.md), and [policy-gradient chapter](source/book/chapters/06-policy-gradients.md).

## 3. Verifiable Rewards and Reasoning Models

**Reinforcement learning with verifiable rewards (RLVR)** replaces or supplements a learned preference score with an explicit checker. Examples include extracting a mathematical answer or executing generated code against tests. A verifier can accept multiple valid solutions; it need not compare every response with one canonical solution string.

The optimization algorithms can remain broadly similar to RLHF. The major change is the feedback signal and the tasks on which it is available. Modern recipes mix correctness, preferences, format constraints, language consistency, and other objectives rather than following a rigid RLHF-versus-RLVR division.

Long reasoning traces can become useful when training rewards successful solutions and the base model can already generate informative attempts. Training data difficulty, curriculum, maximum response length, and rollout throughput all affect this process. Distillation provides another route: a student can learn from a stronger reasoning model's outputs through SFT.

The course leaves open whether particular improvements represent discovery of new capabilities or more reliable use of capabilities already supported by pretraining. Do not resolve that debate merely from the presence of longer outputs.

Sources: [Lecture 5](source/teach/course/lec5-chap7.md) and [reasoning chapter](source/book/chapters/07-reasoning.md).

## 4. Direct Preference Optimization

**Direct Preference Optimization (DPO)** turns a KL-regularized preference-learning objective into a contrastive loss over chosen and rejected responses relative to a reference policy. Standard offline DPO does not require training a separate reward model or generating fresh rollouts inside each optimization step.

Its practical attraction is a simpler training loop. Its limitations include the coverage and quality of the preference dataset and possible displacement of probability mass: improving a chosen-versus-rejected margin does not guarantee that the chosen response's absolute probability increases.

The course contrasts offline preference optimization with online RL's ability to obtain fresh samples. This is a comparison of data collection and optimization procedures, not a universal rule that one method is always better. Preference labels may also come from AI judges rather than humans.

Sources: [Lecture 6](source/teach/course/lec6-chap8-dpo.md) and [direct-alignment chapter](source/book/chapters/08-direct-alignment.md).

## 5. Inference-Time Computation

Training changes model parameters; inference-time scaling spends additional computation while answering a new prompt. Examples include longer reasoning traces, independent candidate generation, majority voting, and verifier-based selection. Their value depends on the policy's capabilities and the reliability of selection.

Keep the evaluation metrics distinct:

- **Pass@1:** Success probability of one sampled response.
- **Pass@k:** Whether at least one of several candidates succeeds; this measures coverage and assumes correctness can be assessed for evaluation.
- **Consensus or selected-answer accuracy:** Success of the answer actually chosen from a candidate set.

A large pass@k gap identifies possible selection headroom, but does not supply a deployable selector. Compare approaches under explicit token, FLOPs, latency, or financial budgets rather than treating these quantities as equivalent.

Sources: [Lecture 5](source/teach/course/lec5-chap7.md) and [Lecture 12](source/teach/course/lec12-chap16-evals.md). For the seminar's detailed analysis of adaptive inference allocation, use the separate [Snell et al. summary](../scaling-test-time-compute/SUMMARY.md).

## 6. Synthetic Data, Preferences, and Regularization

Synthetic demonstrations, AI preference labels, and teacher distillation can reduce dependence on expensive human demonstrations. They still require choices about coverage, filtering, judging, and whose behavior constitutes a good target. On-policy distillation trains on student-generated contexts and uses teacher feedback there, addressing a distribution mismatch in offline imitation.

Human preferences are themselves context-dependent. Annotation instructions, presentation order, response length, and evaluator background influence collected data. Optimizing a single learned score therefore compresses a more complicated goal.

Regularization constrains harmful or unstable changes. The course distinguishes an explicit reference-policy KL penalty from broader properties of the optimization procedure. Some RLVR recipes omit that penalty; this does not make every possible regularization mechanism irrelevant. KL divergence is asymmetric and is not a distance metric.

Sources: [Lecture 7](source/teach/course/lec7-chap12-synthetic-data.md), [Lecture 8](source/teach/course/lec8-chap10-11-preferences.md), [Lecture 10](source/teach/course/lec10-chap15-regularization.md), and [Q&A 2](source/teach/course/qa-02.md).

## 7. Failure Modes, Tools, and Evaluation

Reward over-optimization occurs when improving the training proxy stops improving the intended outcome. Verbal confidence, verbosity, or agreement may be rewarded without equivalent gains in correctness. Verifiable checks reduce some ambiguities but still depend on the completeness of the checking procedure.

Tool use extends the system beyond model weights: an orchestrator executes calls and returns observations. Agent evaluations consequently depend on the harness, tool definitions, environment, timeouts, sampling, and budget. Character training additionally shapes conversational style and dispositions. These topics provide context, but should not displace the seminar's core comparison of learning and inference mechanisms.

Sources: [Lecture 9](source/teach/course/lec9-chap14-appb-overoptimization.md), [Lecture 11](source/teach/course/lec11-chap13-tools.md), [Lecture 12](source/teach/course/lec12-chap16-evals.md), and [Lecture 13](source/teach/course/lec13-chap17-character.md).

## Seminar Synthesis and Critical Questions

| Mechanism | What changes? | Main condition for useful reasoning improvements |
| --- | --- | --- |
| Preference learning | Parameters or response selection are guided by comparative judgments | Judgments must reward the intended quality rather than superficial proxies |
| RLVR | Parameters are optimized using explicit verification feedback | Tasks must provide informative attempts and trustworthy checks |
| Additional inference compute | More tokens, candidates, revisions, or search are used for a new question | The policy and selector must turn the added budget into better answers |

**Interpretation for the seminar:** Lambert supplies the methodological vocabulary; [DeepSeek-R1](../deepseek-r1/SUMMARY.md) provides a concrete training pipeline; [Snell et al.](../scaling-test-time-compute/SUMMARY.md) investigate how to allocate inference compute. Together they motivate asking which component improves single-sample reasoning, which improves candidate coverage or selection, and what each improvement costs.

Evaluate claims against primary experiments. The course is an evolving educational synthesis, not a controlled experiment isolating every intervention. In particular, distinguish correctness from preference, training reward from held-out performance, and expanded output length from evidence of more reliable reasoning.

For a focused first pass, prioritize Lectures **2, 3, 5, 6, 9, 10, and 12**, using Lecture 0 for prerequisites, Lecture 4 for implementation questions, and Q&A 2 for corrections.

## Attribution and Reuse

This summary adapts Nathan Lambert's course and book explanations, with additional seminar commentary clearly identified above. It is not an official Lambert document. It is released under [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/), consistent with the included book-chapter license. Upstream lecture sources, code, and book chapters retain their respective licenses; see the [material index](README.md).
