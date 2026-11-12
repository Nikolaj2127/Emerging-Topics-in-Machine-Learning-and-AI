# Course

A full course accompanying the book with added resources and other lectures I've given.


The slide decks are built by me with the help of the latest frontier models, in my Markdown-based slide tool, [Colloquium](https://github.com/natolambert/colloquium). PRs are welcome. Please extend, modify, and use these slides for your courses if you are an educator.

### Welcome to the Course

Introduction and overview of what you'll learn

[Watch](https://www.youtube.com/watch?v=jQPiH-KB4B0&list=PLL1tdVxB1CpVpEtMHxwuR4uI4Lxjw00_y)

This course is roughly aimed at early AI PhD or master's students, but it is designed to be accessible to anyone willing to put in the work.

You do **not** need prior reinforcement learning or language modeling background to start. A motivated learner who studies hard — leaning on today's top LLMs as a tutor to unpack unfamiliar math, code, and jargon — can follow the entire course. I encourage you to go down rabbit holes, skip or reorder videos, and chase what excites you.

If you prefer the traditional coursework path, the usual background is the basics of language modeling / NLP plus basic machine learning (e.g. an intro to AI course and an intro to ML course).

[Additional learning material](https://rlhfbook.com/course#extra-resources)

### Lecture 0: The ML Foundations of LLM Post-Training

A refresher on the ML prerequisites of post-training — language modeling, KL, cross-entropy, & other math — to acclimate to the series

[Watch](https://www.youtube.com/watch?v=MMDNaeIFVy8&list=PLL1tdVxB1CpVpEtMHxwuR4uI4Lxjw00_y&index=2)· [PDF](https://rlhfbook.com/teach/course/lec0-prereq-review/slides.pdf)· [Slides](https://rlhfbook.com/teach/course/lec0-prereq-review/)· [Source](https://github.com/natolambert/rlhf-book/blob/main/teach/course/lec0-prereq-review.md?plain=1)

### Lecture 1: Overview

Chapters 1-3 · Foundations of RLHF and post-training

[Watch](https://www.youtube.com/watch?v=o6l6tJQgUg4&list=PLL1tdVxB1CpVpEtMHxwuR4uI4Lxjw00_y&index=2)· [PDF](https://rlhfbook.com/teach/course/lec1-chap1-3/slides.pdf)· [Slides](https://rlhfbook.com/teach/course/lec1-chap1-3/)· [Source](https://github.com/natolambert/rlhf-book/blob/main/teach/course/lec1-chap1-3.md?plain=1)

### Lecture 2: IFT, Reward Models, & Rejection Sampling

Chapters 4, 5, 9 · Start of the core optimization methods section

[Watch](https://www.youtube.com/watch?v=4gIwiSPmQkU&list=PLL1tdVxB1CpVpEtMHxwuR4uI4Lxjw00_y&index=3)· [PDF](https://rlhfbook.com/teach/course/lec2-chap4-5-9/slides.pdf)· [Slides](https://rlhfbook.com/teach/course/lec2-chap4-5-9/)· [Source](https://github.com/natolambert/rlhf-book/blob/main/teach/course/lec2-chap4-5-9.md?plain=1)

### Lecture 3: RL Motivation & Math

Chapter 6, Part 1 · Policy gradients math, intuitions, and theory

[Watch](https://www.youtube.com/watch?v=K_Sj_-1BUMM&list=PLL1tdVxB1CpVpEtMHxwuR4uI4Lxjw00_y&index=4)· [PDF](https://rlhfbook.com/teach/course/lec3-chap6-p1/slides.pdf)· [Slides](https://rlhfbook.com/teach/course/lec3-chap6-p1/)· [Source](https://github.com/natolambert/rlhf-book/blob/main/teach/course/lec3-chap6-p1.md?plain=1)

### Lecture 4: RL Implementation & Practice

Chapter 6, Part 2 · Code, loss aggregation, async training, and practical engineering

[Watch](https://www.youtube.com/watch?v=i-AIMpZHgeg&list=PLL1tdVxB1CpVpEtMHxwuR4uI4Lxjw00_y&index=5)· [PDF](https://rlhfbook.com/teach/course/lec4-chap6-p2/slides.pdf)· [Slides](https://rlhfbook.com/teach/course/lec4-chap6-p2/)· [Source](https://github.com/natolambert/rlhf-book/blob/main/teach/course/lec4-chap6-p2.md?plain=1)

### Q&A 1: Reader questions, lec. 1-4

Show questions

[Watch](https://www.youtube.com/watch?v=x-MqKBzoxkI&list=PLL1tdVxB1CpVpEtMHxwuR4uI4Lxjw00_y&index=6)· [PDF](https://rlhfbook.com/teach/course/qa-01/slides.pdf)· [Slides](https://rlhfbook.com/teach/course/qa-01/)· [Source](https://github.com/natolambert/rlhf-book/blob/main/teach/course/qa-01.md?plain=1)

- [What prerequisites should a learner cover before this course?](https://rlhfbook.com/teach/course/qa-01/#3) [(0:38)](https://www.youtube.com/watch?v=x-MqKBzoxkI&t=38s)
- [For synthetic SFT data, is one teacher model better than many?](https://rlhfbook.com/teach/course/qa-01/#6) [(2:05)](https://www.youtube.com/watch?v=x-MqKBzoxkI&t=125s)
- [Is there a unified benchmark across pairwise RMs, ORMs, PRMs, and generative RMs?](https://rlhfbook.com/teach/course/qa-01/#11) [(5:13)](https://www.youtube.com/watch?v=x-MqKBzoxkI&t=313s)
- [Why choose token-level rewards over sequence-level rewards?](https://rlhfbook.com/teach/course/qa-01/#13) [(6:24)](https://www.youtube.com/watch?v=x-MqKBzoxkI&t=384s)
- [Is GAE the only way to compute the advantage in PPO?](https://rlhfbook.com/teach/course/qa-01/#16) [(7:59)](https://www.youtube.com/watch?v=x-MqKBzoxkI&t=479s)
- [What is the shape of the importance ratio ρ?](https://rlhfbook.com/teach/course/qa-01/#18) [(9:15)](https://www.youtube.com/watch?v=x-MqKBzoxkI&t=555s)
- [Why does PPO use `torch.max` for both policy and value losses?](https://rlhfbook.com/teach/course/qa-01/#21) [(11:20)](https://www.youtube.com/watch?v=x-MqKBzoxkI&t=680s)
- [How should data-annotation companies stay valuable as synthetic data gets simpler?](https://rlhfbook.com/teach/course/qa-01/#24) [(13:11)](https://www.youtube.com/watch?v=x-MqKBzoxkI&t=791s)

### Lecture 5: The Rise of Reasoning Models

Chapter 7 · RLVR, inference-time scaling, and the 2025 reasoning model wave

[Watch](https://www.youtube.com/watch?v=o4AB5xHIDdM&list=PLL1tdVxB1CpVpEtMHxwuR4uI4Lxjw00_y&index=7)· [PDF](https://rlhfbook.com/teach/course/lec5-chap7/slides.pdf)· [Slides](https://rlhfbook.com/teach/course/lec5-chap7/)· [Source](https://github.com/natolambert/rlhf-book/blob/main/teach/course/lec5-chap7.md?plain=1)

### Lecture 6: Direct Preference Optimization

Chapter 8 · Deriving DPO step by step, plus variants and practice

[Watch](https://www.youtube.com/watch?v=6g6b4gvO-y0&list=PLL1tdVxB1CpVpEtMHxwuR4uI4Lxjw00_y&index=8)· [PDF](https://rlhfbook.com/teach/course/lec6-chap8-dpo/slides.pdf)· [Slides](https://rlhfbook.com/teach/course/lec6-chap8-dpo/)· [Source](https://github.com/natolambert/rlhf-book/blob/main/teach/course/lec6-chap8-dpo.md?plain=1)

### Conversation 1: Frontier post-training recipes in 2026 (w/ Finbarr Timbers)

[Watch](https://www.youtube.com/watch?v=sbXEPxIazqY&list=PLL1tdVxB1CpVpEtMHxwuR4uI4Lxjw00_y&index=9)· [PDF](https://rlhfbook.com/teach/course/conversation-01/slides.pdf)· [Slides](https://rlhfbook.com/teach/course/conversation-01/)· [Source](https://github.com/natolambert/rlhf-book/blob/main/teach/course/conversation-01.md?plain=1)

### Lecture 7: Synthetic Data and Modern Post-training Methods

Chapter 12 · On-policy distillation, AI feedback, Constitutional AI, and rubrics

[Watch](https://www.youtube.com/watch?v=6nyJ8y8ghsE&list=PLL1tdVxB1CpVpEtMHxwuR4uI4Lxjw00_y&index=10)· [PDF](https://rlhfbook.com/teach/course/lec7-chap12-synthetic-data/slides.pdf)· [Slides](https://rlhfbook.com/teach/course/lec7-chap12-synthetic-data/)· [Source](https://github.com/natolambert/rlhf-book/blob/main/teach/course/lec7-chap12-synthetic-data.md?plain=1)

### Q&A 2: Reader questions, lec. 5-7

Show questions

[Watch](https://www.youtube.com/watch?v=gB-bYUECpzE&list=PLL1tdVxB1CpVpEtMHxwuR4uI4Lxjw00_y&index=11)· [PDF](https://rlhfbook.com/teach/course/qa-02/slides.pdf)· [Slides](https://rlhfbook.com/teach/course/qa-02/)· [Source](https://github.com/natolambert/rlhf-book/blob/main/teach/course/qa-02.md?plain=1)

- [Correction: the KD-as-RL-advantage slide (Lecture 7)](https://rlhfbook.com/teach/course/qa-02/#3) [(0:32)](https://www.youtube.com/watch?v=gB-bYUECpzE&t=32s)
- [Correction: KL divergence is not a “distance” (Lecture 0)](https://rlhfbook.com/teach/course/qa-02/#6) [(1:40)](https://www.youtube.com/watch?v=gB-bYUECpzE&t=100s)
- [Correction: the Bradley-Terry loss derivation (Lecture 2 / Ch 5)](https://rlhfbook.com/teach/course/qa-02/#9) [(4:27)](https://www.youtube.com/watch?v=gB-bYUECpzE&t=267s)
- [Can we get programming & math assignments?](https://rlhfbook.com/teach/course/qa-02/#13) [(6:14)](https://www.youtube.com/watch?v=gB-bYUECpzE&t=374s)
- [Notation gotchas in Chapter 6: reward indexing, scalar placement, trajectory expectations](https://rlhfbook.com/teach/course/qa-02/#17) [(8:14)](https://www.youtube.com/watch?v=gB-bYUECpzE&t=494s)
- [Why switch between ∇J(θ) and J(θ) across algorithms?](https://rlhfbook.com/teach/course/qa-02/#21) [(12:00)](https://www.youtube.com/watch?v=gB-bYUECpzE&t=720s)

### Lecture 8: On "Preferences" and Preference Data

Chapters 10 & 11 · Where the idea of quantifying preference came from and opaque data practices

[Watch](https://www.youtube.com/watch?v=Y2tv5vuaxFs&list=PLL1tdVxB1CpVpEtMHxwuR4uI4Lxjw00_y&index=13)· [PDF](https://rlhfbook.com/teach/course/lec8-chap10-11-preferences/slides.pdf)· [Slides](https://rlhfbook.com/teach/course/lec8-chap10-11-preferences/)· [Source](https://github.com/natolambert/rlhf-book/blob/main/teach/course/lec8-chap10-11-preferences.md?plain=1)

### Lecture 9: Over-Optimization and RLHF's Bad Reputation

Chapter 14 & Appendix B · Goodhart's law, reward hacking, sycophancy, and style

[Watch](https://www.youtube.com/watch?v=y04JhXpiI4s&list=PLL1tdVxB1CpVpEtMHxwuR4uI4Lxjw00_y)· [PDF](https://rlhfbook.com/teach/course/lec9-chap14-appb-overoptimization/slides.pdf)· [Slides](https://rlhfbook.com/teach/course/lec9-chap14-appb-overoptimization/)· [Source](https://github.com/natolambert/rlhf-book/blob/main/teach/course/lec9-chap14-appb-overoptimization.md?plain=1)

### Lecture 10: Regularization in RL, Why RL Generalizes, and Why SFT Forgets

Chapter 15 · The KL penalty, implicit regularization, and why RL forgets less

[Watch](https://www.youtube.com/watch?v=IwpYxANrpUs&list=PLL1tdVxB1CpVpEtMHxwuR4uI4Lxjw00_y&index=15)· [PDF](https://rlhfbook.com/teach/course/lec10-chap15-regularization/slides.pdf)· [Slides](https://rlhfbook.com/teach/course/lec10-chap15-regularization/)· [Source](https://github.com/natolambert/rlhf-book/blob/main/teach/course/lec10-chap15-regularization.md?plain=1)

### Conversation 2: From academic research to frontier practice (w/ Scott Geng)

We discuss what it takes to land a well-grounded academic result into a near-frontier model. Scott and I worked together on DPO for Olmo 3, and how building models is much more than the idea, it's making it fit in a more complex puzzle.

[Watch](https://www.youtube.com/watch?v=rhA7pLVt4E0&list=PLL1tdVxB1CpVpEtMHxwuR4uI4Lxjw00_y&index=16)· [PDF](https://rlhfbook.com/teach/assets/from-research-to-practice.pdf)

### Lecture 11: Tool Use, Function Calling and The Road to Agents

Chapter 13 · Why models need tools, MCP and harnesses, and tool-use RL

[Watch](https://www.youtube.com/watch?v=GMry2DzC304&list=PLL1tdVxB1CpVpEtMHxwuR4uI4Lxjw00_y&index=17)· [PDF](https://rlhfbook.com/teach/course/lec11-chap13-tools/slides.pdf)· [Slides](https://rlhfbook.com/teach/course/lec11-chap13-tools/)· [Source](https://github.com/natolambert/rlhf-book/blob/main/teach/course/lec11-chap13-tools.md?plain=1)

### Q&A 3: Reader questions, lec. 8-11

Show questions

[Watch](https://www.youtube.com/watch?v=6StK9ttLNbQ&list=PLL1tdVxB1CpVpEtMHxwuR4uI4Lxjw00_y&index=18)· [PDF](https://rlhfbook.com/teach/course/qa-03/slides.pdf)· [Slides](https://rlhfbook.com/teach/course/qa-03/)· [Source](https://github.com/natolambert/rlhf-book/blob/main/teach/course/qa-03.md?plain=1)

- [Q1: Should capabilities be trained separately, then merged?](https://rlhfbook.com/teach/course/qa-03/#2) [(0:13)](https://www.youtube.com/watch?v=6StK9ttLNbQ&t=13s)
- [Q2: Why does RLVR often omit the KL penalty?](https://rlhfbook.com/teach/course/qa-03/#7) [(4:14)](https://www.youtube.com/watch?v=6StK9ttLNbQ&t=254s)
- [Q3: How does the ~1M SFT prompt budget scale with model size?](https://rlhfbook.com/teach/course/qa-03/#9) [(5:58)](https://www.youtube.com/watch?v=6StK9ttLNbQ&t=358s)
- [Q4: Is RL just regularized SFT?](https://rlhfbook.com/teach/course/qa-03/#10) [(8:11)](https://www.youtube.com/watch?v=6StK9ttLNbQ&t=491s)
- [Q5: When should in-house traces be trained into the weights vs. handled with ICL?](https://rlhfbook.com/teach/course/qa-03/#12) [(11:01)](https://www.youtube.com/watch?v=6StK9ttLNbQ&t=661s)
- [Q6: Can continued pretraining on a distillation-only dataset make a model worse?](https://rlhfbook.com/teach/course/qa-03/#13) [(12:44)](https://www.youtube.com/watch?v=6StK9ttLNbQ&t=764s)

### Lecture 12: The Evolution of Frontier Model Evaluation

Chapter 16 · The eras of evaluation, agentic evals, and trusting the numbers

[Watch](https://www.youtube.com/watch?v=dFafQmClYq4&list=PLL1tdVxB1CpVpEtMHxwuR4uI4Lxjw00_y&index=19)· [PDF](https://rlhfbook.com/teach/course/lec12-chap16-evals/slides.pdf)· [Slides](https://rlhfbook.com/teach/course/lec12-chap16-evals/)· [Source](https://github.com/natolambert/rlhf-book/blob/main/teach/course/lec12-chap16-evals.md?plain=1)

### Lecture 13: An Introduction to Character Training

Chapter 17 · Constitutions, model specs, model personalities, and open questions

[Watch](https://www.youtube.com/watch?v=xECWRYBxq1E&list=PLL1tdVxB1CpVpEtMHxwuR4uI4Lxjw00_y&index=20)· [PDF](https://rlhfbook.com/teach/course/lec13-chap17-character/slides.pdf)· [Slides](https://rlhfbook.com/teach/course/lec13-chap17-character/)· [Source](https://github.com/natolambert/rlhf-book/blob/main/teach/course/lec13-chap17-character.md?plain=1)

### Bonus 1: What's With the Shoggoths?

Bonus talk · The meme that explained post-training.

[Watch](https://www.youtube.com/watch?v=3xaaGxSjGN4&list=PLL1tdVxB1CpVpEtMHxwuR4uI4Lxjw00_y&index=21)· [PDF](https://rlhfbook.com/teach/extras/01-shoggoths/slides.pdf)· [Slides](https://rlhfbook.com/teach/extras/01-shoggoths/)· [Source](https://github.com/natolambert/rlhf-book/blob/main/teach/extras/01-shoggoths.md?plain=1)

* * *

## Additional Lectures from Nathan

Other lectures I've given closely related to the book content. The newest ones are beginning to include material not covered in the course. I hope to keep this up to date over the next few years!

### RL Systems, Score Centering, and Modern RL

Cornell CS 4789 guest lecture · Nov 2026 · Chapter 6 · Async RL, training-inference mismatch, and score centering

[PDF](https://rlhfbook.com/teach/Cornell-CS4789-2026/slides.pdf)· [Slides](https://rlhfbook.com/teach/Cornell-CS4789-2026/)· [Source](https://github.com/natolambert/rlhf-book/blob/main/teach/Cornell-CS4789-2026/talk.md?plain=1)

### An Introduction to Reinforcement Learning from Human Feedback and Post-training

SALA 2026 invited talk, Quito · Mar 2026 · A self-contained introduction: classical RL vs. RLHF vs. RLVR

[PDF](https://rlhfbook.com/teach/SALA-2026/slides.pdf)· [Slides](https://rlhfbook.com/teach/SALA-2026/)· [Source](https://github.com/natolambert/rlhf-book/blob/main/teach/SALA-2026/talk.md?plain=1)

* * *

## More talks from Nathan

Various presentations over my last few years working in post-training, grouped by corresponding chapter. These are talks I gave while building the book, and may be more research-oriented, but serve as great additional context to the course.

#### Chapter 1 · Introduction

- [Aligning Open Language Models (Stanford CS25)](https://www.youtube.com/watch?v=AdLgPmcrXwQ) Apr 2024

#### Chapter 3 · Training Overview

- [How Language Model Post-Training Is Done Today](https://www.youtube.com/watch?v=6yIMb0K-aS4) Jan 2025
- [How We Built a Leading Reasoning Model (Olmo 3)](https://www.youtube.com/watch?v=uaZ3yRdYg8A) Dec 2025

#### Chapter 6 · Reinforcement Learning

- [GRPO's New Variants and Implementation Secrets](https://www.youtube.com/watch?v=amrJDwMUFNs) Mar 2025

#### Chapter 10 · The Nature of Preferences

- [15 Minute History of Reinforcement Learning and Human Feedback](https://www.youtube.com/watch?v=Mu_-FWIuhDA) Dec 2023

#### Chapter 7 · Reasoning & Inference-Time Scaling

- [An Unexpected Reinforcement Learning Renaissance](https://www.youtube.com/watch?v=YXTYbr3hiFU) Feb 2025
- [Early Stages of the Reinforcement Learning Era of Language Models](https://www.youtube.com/watch?v=J1APR8Bo9dE) Mar 2025
- [Experimenting with Reinforcement Learning with Verifiable Rewards (RLVR)](https://www.youtube.com/watch?v=zYeIqzULzr0) Apr 2025

#### Chapter 8 · Direct-Alignment Algorithms

- [DPO Debate: Is RL Needed for RLHF?](https://www.youtube.com/watch?v=YJMCSVLRUNs) Dec 2023
- [Life After DPO (Stanford CS224N)](https://www.youtube.com/watch?v=dnF463_Ar9I) May 2024
- [An Update on DPO vs PPO for LLM Alignment](https://www.youtube.com/watch?v=rDF7eFPeVto) Jul 2024

* * *

## Extra Resources

Outside material that I've personally used for going deeper on reinforcement learning and language models. The books in particular are wonderful complements.

[BookReinforcement Learning: An IntroductionSutton & Barto · The foundational RL textbook](https://link.amazon/B04P7GB2e) [BookBuild a Large Language Model (From Scratch)Sebastian Raschka](https://amzn.to/4ef1DWP) [BookBuild a Reasoning Model (From Scratch)Sebastian Raschka](https://amzn.to/4x14Kcu) [CourseCS285: Deep Reinforcement Learning (2023)UC Berkeley · Sergey Levine](https://www.youtube.com/watch?v=SupFHGbytvA&list=PL_iWQOsE6TfVYGEGiAOMaOzzv41Jfm_Ps&index=1) [CourseIntroduction to Reinforcement Learning (2015)DeepMind / UCL · David Silver](https://www.youtube.com/watch?v=2pWv7GOvuf0&list=PLzuuYNsE1EZAXYR4FJ75jcJseBmo4KQ9-)

#### Citation

If you found this useful for your research, please cite it!

For the web and arXiv version:

```
@misc{lambert2025reinforcementlearninghumanfeedback,
  title = {Reinforcement Learning from Human Feedback},
  author = {Nathan Lambert},
  year = {2025},
  eprint = {2504.12501},
  archivePrefix = {arXiv},
  primaryClass = {cs.LG},
  url = {https://arxiv.org/abs/2504.12501}
}
```

For the Manning edition:

```
@book{lambert2026reinforcement,
  author = {Nathan Lambert},
  title = {Reinforcement Learning from Human Feedback: Alignment and post-training of {LLMs}},
  year = {2026},
  publisher = {Manning Publications},
  isbn = {9781633434301},
  url = {https://www.manning.com/books/reinforcement-learning-from-human-feedback}
}
```
