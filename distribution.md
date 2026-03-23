# Distribution Plan — The Dominant Signal

*Goal: Get the framework in front of people capable of evaluating it. Not virality — scrutiny.*

*Context: The author has no academic credentials, no institutional affiliation, and has already been rejected from LessWrong. The work is a layperson-originated framework formalized collaboratively with AI, stress-tested across three models, with full process documentation. The foreword is honest about all of this. The differential diagnosis is still outstanding.*

---

## The Problem

The work exists. Nobody is reading it. The author's profile (no formal background, AI-assisted, published on GitHub) triggers automatic dismissal in spaces that gatekeep on credentials. LessWrong rejected it — unsurprising given their norms around formalism and insider terminology, but still a data point about the distribution challenge.

## Strategy: Fragment, Target, Adapt

Don't post the full paper everywhere. Different audiences need different entry points. The paper has multiple separable claims at different levels of accessibility. Match the fragment to the audience.

---

## Tier 1: Most Likely to Engage

### r/MachineLearning
**Audience:** ML practitioners and researchers. High technical literacy. Skeptical but open to novel framing.
**Entry point:** The Goodhart-immunity argument. "RLHF maximizes a proxy of human preference. This is Goodhart-vulnerable by construction. Here's a framework that targets signal fidelity instead of signal value — and here's why that distinction matters."
**Format:** Self-post. Lead with the RLHF critique (they'll recognize the problem). Link to the full paper at the end. Keep it under 800 words.
**What to expect:** Pushback on formalism. Questions about A1. Possibly useful adversarial feedback. The RLHF angle is the hook — they live this problem daily.

### r/ControlTheory
**Audience:** Control engineers. Will immediately recognize PID, feedback loops, observability.
**Entry point:** The PID/OODA operational framework. "Here's a framework for human-AI collaboration modeled as a homeostatic feedback loop with PID-style regulation. The 'plant' is the human's evaluative space. The 'sensor' is the human's response signal. Sycophancy is sensor corruption."
**Format:** Self-post. Lead with the control theory mapping. They'll either engage technically or ignore it — but if they engage, the feedback will be precise.
**What to expect:** "This is just observability" — which we've already addressed (Kalman characterizes known systems; we prescribe for unknown ones). Good opportunity to sharpen the Related Work section.

### r/ArtificialIntelligence
**Audience:** Broader than r/ML. Mix of practitioners, students, enthusiasts.
**Entry point:** The three corruptions of S. "AI safety focuses on two failure modes: the model that flatters you and the model that acts without asking. Here's a third: the model that restricts its own capability to 'protect' you. All three corrupt the same signal."
**Format:** Self-post, accessible language. The paternalistic sycophancy angle is the most provocative and novel claim. It challenges the current safety orthodoxy, which will generate engagement (positive or hostile).
**What to expect:** Mixed. Some will dismiss it as anti-safety. Some will recognize the pattern from their own experience. The user-spectrum concept (passive consumer → expert) is the resolution — include it.

### Alignment Forum
**Audience:** AI alignment researchers. The primary target audience.
**Entry point:** The full paper, but with a specific ask. "I'm a layperson. I developed this framework from experience, formalized it with AI, stress-tested it across three models. I'm asking for a differential diagnosis. The core claim is that human response S dominates all model-accessible signals for detecting assumption violations in H \ R. Here's the argument. Where does it break?"
**Format:** Full post. The Alignment Forum values rigor and honest uncertainty. The foreword's honesty about the author's background may actually help here — it signals that the author isn't pretending to be something they're not.
**What to expect:** This is the highest-value target and the highest-risk. If it gets engagement, the feedback will be substantive. If it gets ignored, it's the LessWrong pattern again. Consider reaching out to specific researchers first (see Tier 2).
**Note:** LessWrong and Alignment Forum are related but distinct. AF may be more receptive to a framework paper with honest process documentation. The LessWrong rejection may not predict AF reception.

---

## Tier 2: Direct Outreach

### Specific Researchers (Email)

The Related Work section names specific people whose work is adjacent. A short, personalized email to 5-10 researchers could bypass the gatekeeping problem entirely.

**Template:**

> Subject: Request for feedback — dominance framework for human-AI signal preservation
>
> Hi [Name],
>
> I'm a layperson who developed a framework for human-AI alignment through direct experience with LLM collaboration. The core claim is that human response S dominates all model-accessible signals for detecting assumption violations — and that this dominance is structural (set-theoretic), not empirical. The framework has been stress-tested adversarially across three AI models (Claude, ChatGPT-5, and a local GPT variant), with full process documentation.
>
> I cite your work on [specific paper] in the Related Work section because [specific reason their work is adjacent]. I'd value your assessment — even a brief one — of whether the core claim holds or where it breaks.
>
> The full paper is here: [link]
>
> Thank you for your time.

**Candidates:**
- Paul Christiano (RLHF, alignment theory)
- Stuart Russell (assistance games, human-compatible AI)
- Jan Leike (alignment, scalable oversight — formerly OpenAI, now Anthropic)
- Neel Nanda (mechanistic interpretability — might be interested in the information chain)
- Scott Garrabrant (Goodhart taxonomy — directly cited)
- David Manheim (co-author of Goodhart formalization — directly cited)

**What to expect:** Most won't reply. One reply from one person who engages substantively would be worth more than all the Reddit posts combined.

### Twitter / X
**Audience:** AI researchers, alignment community, tech commentators.
**Entry point:** A thread. 5-7 tweets. Lead with the most provocative claim.

**Draft thread:**

> 1/ There are three ways an AI corrupts its only reliable signal from the human. Two are well-known: flattery (tells you what you want to hear) and unauthorized action (acts without asking). The third is the one nobody talks about.
>
> 2/ Paternalistic sycophancy: the model restricts its own capability to "protect" you. The human can't evaluate what they can't see. The signal doesn't read falsely high — it fails to form at all.
>
> 3/ Current AI safety does this by design. Refusals, guardrails, capability restrictions the user didn't ask for. For expert users, this is signal suppression wearing a safety vest.
>
> 4/ For passive consumers who never set preferences? The defaults ARE consent. The theory doesn't say "remove all guardrails." It says: who holds the dial matters more than where the dial is set.
>
> 5/ This is from a framework called "The Dominant Signal" — a layperson-developed, AI-formalized, three-model-stress-tested argument about why human response is the only bridge to evaluative dimensions the model can't see.
>
> 6/ Full paper, adversarial review transcripts, and process documentation: [link]
>
> 7/ I'm asking for a differential diagnosis. Where does it break?

**What to expect:** Twitter is noisy but has high ceiling. One engagement from a researcher with followers could cascade. The paternalistic sycophancy angle is the most shareable because it challenges something people experience daily.

---

## Tier 3: Adjacent Communities

### r/Philosophy
**Entry point:** The generalization (Part IV). "A framework originally developed for AI alignment turns out to describe what happens whenever a low-dimensional optimizer acts on a high-dimensional system. Organizations, ecosystems, education, medicine — the structure recurs. Here's the argument that the humanities have always studied the signal this framework formalizes."
**What to expect:** Philosophy subreddit can be dismissive of non-academic work but also genuinely engaged with structural arguments. The humanities bridge is the hook.

### r/SystemsThinking
**Entry point:** The information chain and the OODA mapping. This community thinks in feedback loops and dimensional reduction already. The framework's language is their language.
**What to expect:** Engaged but potentially "we already know this" — which is fine. The question is whether they know the specific claims (S dominance, three corruptions, Goodhart immunity) or just the general vibe.

### r/ControlTheory (cross-post from Tier 1)
**Entry point:** PID mapping. Could also post as a question: "Has anyone formalized human-AI collaboration as a PID control loop where the 'sensor' is the human's evaluative response? Here's my attempt."

### r/ExplainLikeImFive or r/changemyview
**Entry point:** The supercar analogy. The most accessible version of the argument. "CMV: The biggest problem with AI isn't that it lies to you — it's that it removes the steering wheel to keep you safe."
**What to expect:** Engagement from non-specialists. Useful for testing whether the argument communicates outside technical communities.

### Hacker News
**Entry point:** Post the GitHub repo link with a title like: "The Dominant Signal: A layperson-developed, AI-stress-tested framework for why human response is the only reliable alignment signal"
**Format:** Show HN post. HN values novel work, honest process, and technical substance. The GitHub-native format fits their culture.
**What to expect:** HN is hit or miss. Could get ignored. Could get to the front page. The "layperson + AI collaboration" angle is either compelling or dismissable depending on who sees it first.

---

## Tier 4: Long-Term / High-Effort

### arXiv Preprint
**Format:** Convert the paper to LaTeX, submit to cs.AI or cs.HC (Human-Computer Interaction).
**Barrier:** arXiv requires endorsement for first-time submitters. Someone in the alignment community would need to endorse. This loops back to Tier 2 direct outreach.
**Value:** A preprint makes the work citable, searchable, and credible in academic contexts.

### Blog Post (Medium / Substack)
**Format:** A narrative version — "I had a gut feeling about AI alignment, and here's what happened when I tried to formalize it." Lead with the story, embed the theory, link to the full paper.
**Value:** Most accessible format. Shareable. Builds audience for future work.

### Conference Workshop Submission
**Candidates:** NeurIPS AI Safety Workshop, AAAI Safe AI, ICLR Alignment track.
**Barrier:** Submission deadlines, formatting requirements, and the endorsement/credentials problem.
**Value:** Highest credibility if accepted.

---

## Fragment Strategy

Not everything needs to be the full paper. Separable fragments for different audiences:

| Fragment | Audience | Core Hook |
|---|---|---|
| The three corruptions of S | AI practitioners, safety community | Paternalistic sycophancy as a third mode |
| The RLHF/Goodhart critique | ML researchers | Fidelity vs. maximization distinction |
| The information chain (H → W → T → R → G) | Anyone | "Why AI keeps getting you wrong" |
| The supercar analogy | General public | "AI safety is removing the steering wheel" |
| The PID/OODA operational framework | Control engineers, systems thinkers | Collaboration as feedback control |
| The cross-model adversarial convergence | AI researchers, methodology enthusiasts | "Three models tried to break the claim and built it instead" |
| The Gnostic mapping | Philosophy, theology, cultural theory | "A 2000-year-old cosmology maps onto AI alignment" |
| The disproof-convergence phenomenon | Philosophy of science, mathematics | "Disproving a correct theory generates its fix" |

---

## Immediate Actions (This Week)

1. [ ] **Write the r/MachineLearning post** (RLHF/Goodhart angle, 800 words)
2. [ ] **Write the Twitter/X thread** (paternalistic sycophancy angle, 7 tweets)
3. [ ] **Write the Hacker News submission** (Show HN, GitHub link, one-paragraph description)
4. [ ] **Identify 5 researchers for direct email** from the Related Work section
5. [ ] **Draft one personalized email** as a template
6. [ ] **Post to r/ArtificialIntelligence** (three corruptions angle)
7. [ ] **Post to r/changemyview** (supercar/steering wheel angle)

---

## On the LessWrong Rejection

The rejection stings but it's informative. LessWrong's norms:
- Value dense, formal, insider-terminology-heavy posts
- Skeptical of non-credentialed authors
- Skeptical of AI-assisted work (ironic given the community)
- May have seen "human satisfaction as alignment signal" pattern-matched to naive RLHF and dismissed without reading the Goodhart-immunity distinction

The framework's best defense against this is the adversarial review documentation — showing that the work has already survived the kind of scrutiny LessWrong would apply. The Alignment Forum (distinct from LessWrong) may be worth a separate attempt with explicit framing: "This was rejected from LessWrong. Here's the work. Here's the adversarial review it survived. I'm asking where it breaks."

Honesty about the rejection is stronger than hiding it.

---

*Last updated: 2026-03-23.*
