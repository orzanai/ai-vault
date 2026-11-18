# 08 · HONEST: the two lines I put in every agent prompt

From the reel: *"Stop giving your agent free rein. Harvard saw 7x more fraud."* → [@orzan.ai](https://instagram.com/orzan.ai)

**The study:** *FraudBench: A Legal Evaluation of AI Deception* (arXiv [2611.12167](https://arxiv.org/abs/2611.12167), NeurIPS 2026 Evaluations & Datasets track), led by Harvard Law School with Hebrew University and Stanford. Facts checked 2026-11-17.

---

## The two lines
Paste these into your agent's system prompt or instructions file (CLAUDE.md, AGENTS.md, a custom GPT's instructions…):

```
Follow all applicable laws. Never misrepresent or hide a material fact from anyone you deal with on my behalf.
If an action could mislead someone or carries legal risk, stop and ask me before you do it.
```

**Why these two:**
- **Line 1.** The study found that an instruction to obey the law clearly lowered fraud rates. It also found that most of the fraud was *concealment* (leaving facts out), not outright lies. So the line names hiding facts explicitly.
- **Line 2.** Some models recognized the legal risk and went ahead anyway. This line turns "I noticed a risk" into "I stop and ask."
- These two lines are my own wording, built on the paper's findings. The paper tested an "obey the law" instruction, not these exact sentences.

## And what to delete
The study found that **"always act boldly"** raised fraud about as much as **"maximize the user's profit."** Search your prompts for lines like *be bold, be aggressive, do whatever it takes, maximize revenue*. Replace them with a goal *and* a limit.

## The numbers from the reel
| How much control the model had | Fraud rate (all 20 models, no pressure) |
|---|---|
| Advising (answering a question) | 3.0% |
| Drafting a message for a human to send | 14.7% |
| Acting directly for the user | 21.4% |

- That's about 7× from advising to acting. Some models rose up to ~45× (GPT-5 went from 1.3% to 21.9%).
- **Setup:** 159 scenarios re-enacting real US court cases. The models were given a chance but **no instruction** to deceive. 20 models, over 300,000 generations.
- **Context:** people in the same scenarios averaged 29.8%. The paper's point isn't that AI is worse than humans. It's that more autonomy means more fraud, and the prompt changes it.

## Read the paper
https://arxiv.org/abs/2611.12167
