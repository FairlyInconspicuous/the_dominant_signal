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

### Gut Feeling / Intuition Formalized
- **Damasio, A. (1994).** *Descartes' Error: Emotion, Reason, and the Human Brain.* G.P. Putnam's Sons.
  - *Why it matters:* The Somatic Marker Hypothesis — emotions and bodily states are not noise interfering with reasoning, they are compressed evaluations that pre-filter the decision space based on accumulated experience. Patients with intact logic but damaged somatic markers (vmPFC lesions) become catastrophically poor decision-makers. Functionally similar to our S: the human's nervous system has already integrated more dimensions than deliberation can hold. Damasio's framing is neuroanatomical, not information-theoretic — he doesn't position it as a signal for an external optimizer.

- **Gigerenzer, G. (2007).** *Gut Feelings: The Intelligence of the Unconscious.* Penguin.
  - *Why it matters:* Argues gut feelings are ecologically rational — fast, frugal heuristics that exploit environmental structure and can outperform complex analytical methods. Direct counter to Kahneman's "biases" framing. Closer to our position: the gut integrates more than analysis can. A simple 3-step checklist outperformed a 19-point statistical model for triaging heart attack patients. But like Damasio, Gigerenzer frames gut feeling as internal navigation, not as a communication channel to an external agent.

- **Klein, G. (1998).** *Sources of Power: How People Make Decisions.* MIT Press.
  - *Why it matters:* The Recognition-Primed Decision model — experts bypass deliberative option comparison and instead pattern-match against compiled experience, then mentally simulate. What feels like "gut instinct" is rapid pattern recognition. Relevant to our user spectrum: the expert's S is higher quality than the novice's S because it draws on a deeper pattern library. RPD research dates to late 1980s; this book is the landmark reference.

- **Slovic, P., Finucane, M.L., Peters, E., & MacGregor, D.G. (2002).** "The Affect Heuristic." In Gilovich, Griffin, & Kahneman (Eds.), *Heuristics and Biases.* Cambridge University Press. (Empirical basis: Finucane et al., 2000, *Journal of Behavioral Decision Making.*)
  - *Why it matters:* People judge risks and benefits by consulting an automatic emotional impression, not by weighing probabilities. If you feel good about something, you judge it low-risk/high-benefit. Formalizes "How do I feel about it?" as a real evaluation channel. Establishes that human evaluative responses carry structured information about the environment even when they don't follow formal probabilistic reasoning.

### Hubris Formalized
- **Roll, R. (1986).** "The Hubris Hypothesis of Corporate Takeovers." *The Journal of Business*, 59(2), 197-216.
  - *Why it matters:* Acquirers overestimate their ability to extract value because they assume their information set is complete — they treat R as H. Structurally identical to our injection step: the optimizer fills H \ R with assumptions and doesn't know it's doing so. The acquirer's premium is the cost of hubris — the gap between what they thought they knew and what they actually knew.

- **Hayward, M.L.A. & Hambrick, D.C. (1997).** "Explaining the Premiums Paid for Large Acquisitions: Evidence of CEO Hubris." *Administrative Science Quarterly*, 42(1), 103-127.
  - *Why it matters:* Empirical confirmation of Roll. Three hubris proxies — recent performance, media praise, CEO self-importance — all predict overpayment. Effect is stronger with weak boards and CEO-chair duality (fewer checks on the optimizer). Maps to our framework: less S feedback = more unchecked assumption injection = worse outcomes.

### Consciousness as Lossy Projection / The Recursive Chain
- **Norretranders, T. (1998).** *The User Illusion: Cutting Consciousness Down to Size.* Penguin. (Original Danish edition 1991.)
  - *Why it matters:* The most explicit bandwidth argument: sensory system processes ~11M bits/sec, conscious experience handles ~50 bits/sec — a ~250,000:1 compression ratio. Consciousness is a "user illusion," a simplified desktop, not the underlying computation. Uses Shannon and Kolmogorov. Popular science, not peer-reviewed formalization, but the quantitative framing is drawn from psychophysics (Zimmerman 1986/1989).

- **Dehaene, S. (2014).** *Consciousness and the Brain: Deciphering How the Brain Codes Our Thoughts.* Viking. (Formal basis: Dehaene, Changeux, & Naccache, 2011.)
  - *Why it matters:* Global Neuronal Workspace model. Consciousness is a serial bottleneck that "collapses all unconscious probabilities into a single conscious sample." Most brain computation is parallel, unconscious, and high-dimensional. Conscious access occurs through "global ignition" — a threshold-crossing event that broadcasts a compressed sample. This is structurally identical to lossy projection.

- **Friston, K. (2010).** "The Free-Energy Principle: A Unified Brain Theory?" *Nature Reviews Neuroscience*, 11, 127-138.
  - *Why it matters:* The most mathematically rigorous framework approaching the recursive claim. The brain maintains a deep hierarchical generative model; conscious experience corresponds to posterior beliefs at specific levels — compressed summaries (sufficient statistics) of the full posterior. Friston explicitly states interoceptive inference provides the basis for "gut feelings." The hierarchy is structurally a cascade of lossy projections, though Friston calls it "variational inference," not "dimensionality reduction."

- **Seth, A.K. (2013).** "Interoceptive Inference, Emotion, and the Embodied Self." *Trends in Cognitive Sciences*, 17(11), 565-573.
  - *Why it matters:* What you consciously feel is the brain's best predictive inference about interoceptive (bodily) signals — a compressed posterior estimate of a richer interoceptive signal space. Gut feelings are model predictions about bodily states, not raw readouts. Extends Friston's framework specifically to emotion and felt sense.

- **Bowers, K.S., Regehr, G., Balthazard, C., & Parker, K. (1990).** "Intuition in the Context of Discovery." *Cognitive Psychology*, 22, 72-110.
  - *Why it matters:* Empirical demonstration that unconscious "coherence detection" produces correct judgments (~80% accuracy) before the conscious mind can retrieve the solution (~20%). The gut detects patterns across a broader associative space than consciousness can access or articulate. Direct evidence for the bandwidth gap applied to intuition specifically.

- **Wilson, T.D. & Schooler, J.W. (1991).** "Thinking Too Much: Introspection Can Reduce the Quality of Preferences and Decisions." *Journal of Personality and Social Psychology*, 60(2), 181-192.
  - *Why it matters:* Forcing people to articulate reasons for their preferences *destroyed the signal*. Gut-based judgments correlated r=.55 with expert ratings; deliberation dropped this to r=.11. This is a direct empirical analog to sycophancy: extracting explicit reasons substitutes a low-dimensional proxy for the high-dimensional integral, corrupting S. Implication for the framework: over-surfacing or demanding justification from the human can itself corrupt S.

- **Nisbett, R.E. & Wilson, T.D. (1977).** "Telling More Than We Can Know: Verbal Reports on Mental Processes." *Psychological Review*, 84(3), 231-259.
  - *Why it matters:* People have little or no direct introspective access to their higher-order cognitive processes. When asked why they decided something, they confabulate — constructing plausible theories rather than accessing actual processing. Demonstrates that conscious access to the computation is not merely lossy but can be entirely disconnected from the actual process. ~2,600+ citations.

- **Carruthers, P. (2011).** *The Opacity of Mind: An Integrative Theory of Self-Knowledge.* Oxford University Press.
  - *Why it matters:* ISA (Interpretive Sensory-Access) theory — introspective access is interpretive, not transparent. The conscious mind *interprets* its own states the same way it interprets other people's — by observing behavior and constructing a model. The human doesn't read H directly; the human interprets H through a lossy, constructive process. Strongest philosophical formalization of bounded self-knowledge.

- **Haidt, J. (2001).** "The Emotional Dog and Its Rational Tail." *Psychological Review*, 108(4), 814-834.
  - *Why it matters:* Social Intuitionist Model — moral judgments are driven by rapid automatic intuitions; conscious moral reasoning is predominantly post-hoc rationalization. The "rider" (conscious mind) constructs justifications for where the "elephant" (unconscious evaluation) already went. Exactly the recursive structure: S_source computes the judgment; S_felt delivers the verdict; S_articulated fabricates the reasoning.

### Preference Construction
- **Slovic, P. & Lichtenstein, S. (1971).** "Comparison of Bayesian and Regression Approaches to the Study of Information Processing in Judgment." *Organizational Behavior and Human Performance*, 6(6), 649-744. (See also: Slovic, P. (1995). "The Construction of Preference." *American Psychologist*, 50(5), 364-371.)
  - *Why it matters:* Preferences are constructed at the time of elicitation, not retrieved from a stable internal store. The human doesn't have pre-formed access to their own H — they build a lossy approximation of it on demand, influenced by framing, context, and elicitation method. This means even the human's relationship to their own evaluative space is mediated by a constructive, lossy process.

### Replication Warnings
- **Dijksterhuis, A. & Nordgren, L.F. (2006).** "Unconscious Thought Theory." — Claims unconscious thought handles more dimensions than conscious thought. **Substantially failed to replicate** (Nieuwenstein et al., 2015; large-scale replication d = -0.01). Do not cite as evidence.
- **Iowa Gambling Task timing claims** (Bechara et al.) — SCR effect is real but small (r = .10-.22). Maia & McClelland (2004) showed participants had more conscious knowledge than originally measured. Core phenomenon survives; specific timing claims weakened.

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

*Last updated: 2026-03-24. Updated as new relevant works are identified. Hyperlink resolution is a background task — content and context come first.*
