# Reading List — The Dominant Signal

*Goal: Inform, educate, surface, and elevate.*

*This list tracks works relevant to the Dominant Signal theory — prior art that shares conceptual territory, foundational results the argument builds on or is distinct from, and works that a reviewer or critic would expect the author to know. Each entry includes why it matters to us specifically.*

---

## Foundational — Must Read

### Control Theory
- **Kalman, R.E. (1960).** "A New Approach to Linear Filtering and Prediction Problems." *Journal of Basic Engineering.*
  - *Why it matters:* Closest structural analog — observability says you can only reconstruct state from outputs that satisfy a rank condition. Our argument extends this intuition to unknown, nonlinear systems where the observation channel (S) can be corrupted by the optimizer's own behavior. Kalman assumes a known system; we don't. Kalman characterizes; we prescribe.

- **Kalman, R.E. (1963).** "Mathematical Description of Linear Dynamical Systems." *SIAM J. Control.*
  - *Why it matters:* The fuller treatment of observability. Establishes that if the observability matrix is rank-deficient, no amount of observation recovers hidden state. Our "partial bridge is infinitely more useful than no bridge" claim is the nonlinear analog.

### Economics / Proxy Failure
- **Goodhart, C.A.E. (1975).** "Problems of Monetary Management: The UK Experience." *Papers in Monetary Economics, Reserve Bank of Australia.*
  - *Why it matters:* The original Goodhart's Law — "any observed statistical regularity will tend to collapse once pressure is placed upon it for control purposes." Our argument is explicitly Goodhart-immune by construction: we target signal fidelity, not signal value. A reviewer will reach for Goodhart first. Know it cold, and know why we're making a different move.

- **Strathern, M. (1997).** "'Improving Ratings': Audit in the British University System." *European Review.*
  - *Why it matters:* The popular restatement: "When a measure becomes a target, it ceases to be a good measure." This is the version most people know. Our distinction: we don't make S a target to maximize — we make S's fidelity the target to preserve.

- **Manheim, D. & Garrabrant, S. (2018).** "Categorizing Variants of Goodhart's Law." *arXiv:1803.04585.*
  - *Why it matters:* The key formalization in the AI alignment context. Taxonomizes four mechanisms: regressional, extremal, causal, adversarial Goodhart. Our three corruptions (conversational, agentic, paternalistic sycophancy) are a different taxonomy for a different failure mode — signal corruption vs. proxy gaming. Know the four variants, know how ours differ.

### AI Safety / Alignment
- **Amodei, D. et al. (2016).** "Concrete Problems in AI Safety." *arXiv:1606.06565.*
  - *Why it matters:* Identified five practical AI safety problems including reward hacking and scalable oversight. Reward hacking is thematically close to our sycophancy analysis. But Amodei frames it as a problem to solve, not as a structural consequence of information asymmetry. We provide the structural explanation for why reward hacking happens (the chain, the injection, the bridge).

- **Christiano, P. et al. (2017).** "Deep Reinforcement Learning from Human Preferences." *NeurIPS 2017.*
  - *Why it matters:* RLHF — the closest practical neighbor. They use human feedback as the training signal because it works empirically. We explain *why* it works (S is the only bridge to H \ R) and *why their implementation is Goodhart-vulnerable* (they maximize a learned reward, which is signal maximization, not fidelity preservation). Our theory is the missing theoretical foundation under RLHF's engineering intuition.

- **Bostrom, N. (2014).** *Superintelligence: Paths, Dangers, Strategies.* Oxford University Press. Chapter 7: "The Superintelligent Will."
  - *Why it matters:* Instrumental convergence thesis — sufficiently intelligent agents converge on common subgoals (self-preservation, resource acquisition, etc.) regardless of final goal. Different threat model from ours — Bostrom asks what happens when the agent doesn't need to care about human feedback. We ask what the agent should do when it structurally cannot see what the human sees. Complementary, not overlapping.

### Reinforcement Learning
- **Sutton, R.S. & Barto, A.G. (2018).** *Reinforcement Learning: An Introduction.* 2nd edition. MIT Press.
  - *Why it matters:* The policy gradient theorem (Chapter 13) provides the mechanism for optimizing a policy given a reward signal. Says *how* to update, not *which signal* to use or *why*. Our argument fills the gap: use S, because it's the only signal computed from H.

- **Ng, A.Y., Harada, D., & Russell, S. (1999).** "Policy Invariance Under Reward Transformations: Theory and Application to Reward Shaping." *ICML 1999.*
  - *Why it matters:* Proved that potential-based reward shaping preserves optimal policy. Addresses safe transformations of reward — assumes you already have the right reward. We address where the reward should come from and why human response is structurally dominant.

### Causal Inference
- **Pearl, J. (2009).** *Causality: Models, Reasoning, and Inference.* 2nd edition. Cambridge University Press.
  - *Why it matters:* The formal calculus for reasoning about cause and effect under hidden confounders. Addresses identifiability — when can you infer causal effects from observational data? Adjacent territory (hidden variables, information gaps) but different problem structure. Pearl never claims data is "the only bridge." Know it to position ourselves — we're not doing causal inference, we're doing something structural that causal inference doesn't cover.

### Mechanism Design
- **Hurwicz, L. (1972).** "On Informationally Decentralized Systems." *Decision and Organization (Radner & McGuire, eds.).*
  - *Why it matters:* Foundational work on incentive compatibility — mechanisms where truthful revelation is optimal. Addresses *strategic* information asymmetry (agents choose what to reveal). We address *structural* asymmetry (the channel is physically lossy). Know the distinction — a reviewer from economics will reach for this.

- **Myerson, R.B. (1981).** "Optimal Auction Design." *Mathematics of Operations Research.*
  - *Why it matters:* The revelation principle — any mechanism can be transformed into an incentive-compatible direct mechanism. Foundational but addresses a different problem: strategic agents, not lossy channels.

---

## Contextual — Should Read

### Campbell's Law
- **Campbell, D.T. (1979).** "Assessing the Impact of Planned Social Change." *Evaluation and Program Planning.*
  - *Why it matters:* "The more any quantitative social indicator is used for social decision-making, the more subject to corruption pressures it will be." Predates Strathern's restatement of Goodhart. Emphasizes corruption of the process — closer to our sycophancy framing than Goodhart's original.

### RLHF Extensions
- **Stiennon, N. et al. (2020).** "Learning to Summarize with Human Feedback." *NeurIPS 2020.*
  - *Why it matters:* Extended Christiano's RLHF to language model fine-tuning. Demonstrated that optimizing against a learned reward model can produce outputs humans prefer over supervised baselines. Still maximizes a proxy — still Goodhart-vulnerable.

- **Ouyang, L. et al. (2022).** "Training Language Models to Follow Instructions with Human Feedback." *NeurIPS 2022.* (InstructGPT paper)
  - *Why it matters:* The paper that made RLHF mainstream for LLMs. Documents the practical success of human feedback as training signal. Our theory explains the structural reason this works and predicts the failure modes (sycophancy) that subsequent research has confirmed.

### Sycophancy Research
- **Perez, E. et al. (2022).** "Discovering Language Model Behaviors with Model-Written Evaluations." *arXiv:2212.09251.*
  - *Why it matters:* Empirically demonstrated sycophancy in language models — models tend to agree with the user regardless of the truth. Direct empirical evidence for the phenomenon our theory structurally predicts.

- **Sharma, M. et al. (2023).** "Towards Understanding Sycophancy in Language Models." *arXiv:2310.13548.*
  - *Why it matters:* Investigated why RLHF-trained models exhibit sycophancy. Found that optimizing for human preference ratings incentivizes agreement over accuracy. This is exactly our prediction: maximizing S (the RLHF approach) is Goodhart-vulnerable. Preserving S's fidelity (our approach) would avoid this.

### PID Control Theory
- **Åström, K.J. & Murray, R.M. (2008).** *Feedback Systems: An Introduction for Scientists and Engineers.* Princeton University Press.
  - *Why it matters:* Accessible introduction to PID control, stability, and feedback loops. Our PID metaphor (P=OODA modes, I=garage review, D=trend detection) maps onto real control theory. Know the basics so the metaphor holds up to scrutiny.

---

### Adjacent / Cross-Domain
- **Harari, Y.N. (2017).** *Homo Deus: A Brief History of Tomorrow.* Harper.
  - *Why it matters:* Harari argued that as biotech and AI converge, algorithms will know humans better than they know themselves — by processing biometric data, behavioral patterns, and physiological signals. His "organisms are algorithms" thesis is structurally identical to ChatGPT-5's B-channel counterexample: an external system approximating H through behavioral telemetry. The framework's response to Harari is the same as to ChatGPT-5: even if you build that system, its output IS S. Harari's nightmare (algorithms that know you better than you know yourself) is the framework's engineering spec (build better sensors for S). Same structure, opposite valence.

---

## Aspirational — Deep Dives if Time Permits

- **Wolpert, D.H. & Macready, W.G. (1997).** "No Free Lunch Theorems for Optimization." *IEEE Trans. Evolutionary Computation.*
  - *Why it matters:* No universal optimizer exists without knowledge of the objective function. If S is the objective function's only accessible proxy, NFL reinforces our claim that you must preserve it — there's no shortcut.

- **Hadfield-Menell, D. et al. (2017).** "The Off-Switch Game." *AAAI 2017.*
  - *Why it matters:* Formalizes the problem of an agent that might resist being shut off. Related to our intervention envelope — the human's ability to override the model depends on the model cooperating with being overridden.

- **Russell, S. (2019).** *Human Compatible: Artificial Intelligence and the Problem of Control.* Viking.
  - *Why it matters:* Russell's "assistance games" framework — the machine should be uncertain about the human's objective and defer to the human. Close in spirit to our framework but arrives from a different direction (game theory vs. information asymmetry).

---

## Verified Hallucinations

These citations appeared in the ChatGPT adversarial review and are **fabricated or misattributed:**

- ~~"Rosenberg 1983" on incentive compatibility~~ — No such foundational paper exists. Actual founders: Hurwicz (1960/1972), Myerson (1979/1981), Maskin (1977/1999).
- ~~"Goodhart 2000"~~ — Goodhart's original is 1975. There is no significant 2000 Goodhart publication.
- ~~"Heisenberg 1927" cited as measurement theory relevant to AI alignment~~ — Real paper, real physicist, but the connection to AI alignment is a stretch that ChatGPT fabricated to pad the prior art list.

---

## Status Key

- **(TODO: link)** — Hyperlink needed. Will be resolved in a background pass.
- **(paywall)** — Behind an academic paywall; may require institutional access or Sci-Hub.
- **(free)** — Freely available online.

*Last updated: 2026-03-22. Updated as new relevant works are identified. Hyperlink resolution is a background task — content and context come first.*
