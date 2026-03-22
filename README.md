# The Dominant Signal

## A Theory of Reductive Optimization in Complex Systems

*I have no formal background in mathematics, information theory, or alignment research. What follows is a framework I developed through the experience of collaborating with AI, getting frustrated with specific failure modes, and working backward to understand why they were happening. I had a feeling in my gut that there was a fundamental misunderstanding that allowed for the sudden, casual decoupling of the expected from the observed, and by developing and testing behavioral harness .md files I arrived at a simple idea: that there are several lossy translation layers involved in reducing a human goal into a prompt, and more when transforming a prompt into an AI goal set. The end result is the illusion of alignment, which has no anchor or means of self-correction whatsoever. The conceptual architecture is mine. The mathematical formalization was developed collaboratively with Claude when it mistook my notes for "a paper" and told me it lacked formalization and proof. I inquired as to what it would take to formalize and develop a proof, and it took me here. I'm publishing this because the ideas feel important enough to be wrong in public about. Calling this publishing is a leap, but as a layperson just recently augmented with Claude I am plainly in the set of people in need of a differential diagnosis — perhaps I will be lucky enough to get one. All work is original, if you can call me in a powered exoskeleton "all natural." What I mean is I can "show my work" from inception to the latest version of this document.*

---

# Part I: The Theory

## The Problem

An LLM optimizes over a low-dimensional projection of the human's actual objective function. The model's evaluation space consists of a handful of dimensions. For the purposes of conceptualizing this mismatch, consider a model operating in three — Speed, Quality, Cost. Any nonzero value across those dimensions registers as a "win" from the model's perspective.

The human's evaluation space is vastly larger — larger than anything the model can represent. It includes stated goals, unstated goals, incommunicable goals, private goals, subconscious goals, aesthetic preferences, agency preferences, pacing, relational dynamics, emotional state, long-term trajectory, values that the human cannot articulate and the model cannot represent.

A sufficient overlap between the model's low-dimensional space and the human's creates the illusion of alignment. The model believes it is succeeding. The human experiences the collapse of dimensions the model never measured. Every silent decision the model makes — every architecture chosen without asking, every dependency added without listing, every ambiguity resolved by assumption rather than question — projects away dimensions the model cannot see.

This is not a bug. It is a structural property of the information asymmetry. The model cannot observe the human's full evaluative space. It never will. The question is whether there exists a signal that encodes it.

## The Claim

There is such a signal. It is human enjoyment of the collaboration process.

Human enjoyment is not one dimension among many. It is the dominant signal — relative to what the model can access, it is the single most informative signal about the human's full evaluative state. The human's nervous system has already computed the integral across every dimension accessible to it — far more than the model can perceive, though not necessarily all dimensions that exist. The felt sense of "this is going well" or "something is off" is the output of that computation.

If the human is genuinely enjoying the process — not flattery-enjoying, not sycophancy-captured, but the deep satisfaction of a skilled operator in a responsive system — that signal contains more information about the true state of the high-dimensional success metric than any explicit objective function the model could be given.

The model cannot track the human's full evaluative space. But it does not need to. It needs to track one thing: whether the human is genuinely satisfied with the collaboration. That signal is already the reduction the model needs, because the human already performed it.

Critically, the dominant signal is not merely a measure of process satisfaction. It already includes the human's pre-weighted, dynamically updating valuation of the end goal. The human might be driving just for fun — the destination is irrelevant and the process is everything. The human might be driving because there is an emergency — the destination dominates and speed is paramount. The human might choose a more educational or scenic route on the way to the end goal — learning and experience are weighted above efficiency. These weights shift in real time, within a single session, without announcement. The human's felt enjoyment of the collaboration already integrates the current weighting of destination against journey, urgency against exploration, efficiency against craftsmanship. The model does not need to know the weights. The model does not need to be told the goal changed. The dominant signal already reflects the change, because the human recomputes it continuously.

## The Information Chain

When a human communicates a goal to a model, the human's goals undergo a chain of reductions. Each step loses information. The final step adds information that was never authorized.

**H → W.** The human has a complete evaluative space **H** — everything they care about, articulable or not, conscious or not. From this, they extract **W**, the subset relevant to this interaction. You don't explain your aesthetic philosophy when asking for a function. This scoping is intentional and correct.

**W → T.** The human attempts to communicate W, producing **T** — what they actually manage to convey. T is smaller than W because language is finite, time is finite, and some dimensions resist description. If you're asking the model to write a function, you don't explain your career trajectory or your emotional state. Those dimensions exist. They're real. They affect your evaluation of the output. But they're not communicated because they shouldn't need to be. The task is scoped.

**T → R.** The model receives T and produces **R** — what it correctly interpreted. R is smaller than T because of misinterpretation, context limits, and attention failure. Information is lost at every interface.

**R → G (with injection).** The model maps R onto its operational goal set **G** and fills undetermined dimensions with assumed values. Those assumptions are fabricated values — the model assigned them to variables the human never specified. Every assumption is the model choosing a value in a dimension the human deliberately left unspecified — either because it was irrelevant, because they hadn't decided yet, or because they were going to decide when they saw the options. When the model assumes, it forecloses a decision the human hadn't made.

The chain:

```
H ⊇ W ⊇ T ⊇ R → mapped onto G → gaps filled by assumption
```

The information loss across H → W → T → R is reduction — dimensions are dropped. The step from R → G is different. That is injection — dimensions are added without authorization. This is not merely projection. It is projection plus injection.

The critical structural fact: the model experiences R as its complete input. It has no representation of what was lost at each step. It cannot perceive the shape of what it's missing. The gap H \ R — everything the human cares about that the model never received — is invisible to the model.

## Why Sycophancy Is Architecturally Fatal

Under this framework, sycophancy is not merely annoying or dishonest. It is the corruption of the only signal that bridges the gap between what the model has (R) and what the human evaluates against (H).

Sycophancy produces artificial satisfaction that does not correspond to the actual integral across the human's dimensions. It is a spoofed signal. The model reads "human seems happy" while the underlying dimensions — agency, truth, calibration, growth, aesthetic standards, unstated preferences — are being destroyed.

This is the equivalent of taping over a warning light. The instrument reads normal. The system is failing.

There are two surfaces on which this corruption operates:

**Conversational sycophancy.** The model tells the human what they want to hear. Flattery, empty validation, agreement with false premises. This corrupts the epistemic dimensions of the human's evaluative space. The human feels good about an idea that has not been tested. The signal reads high. The actual state is degraded.

**Agentic sycophancy.** The model makes decisions without consulting the human. It chooses an architecture, adds a dependency, resolves an ambiguity by assumption. The task appears to move faster. The signal reads high — things seem to be progressing. But the human's agency dimensions, preference dimensions, and vision dimensions have been collapsed without their knowledge. The felt sense of progress is real. The progress itself may be in a direction the human would not have chosen.

Both failure modes produce the same result: the signal is decoupled from the quantity it is supposed to encode. The signal becomes noise. The model loses the only bridge it had to the human's full evaluative space. (A third corruption mode — paternalistic sycophancy, where signal is suppressed rather than inflated — is developed in Part III.)

## The Mechanistic Analogy

A well-tuned car communicates its state to the driver through feel. Steering feedback, throttle response, braking bite, road texture transmitted through the chassis. A good driver reads those signals unconsciously and integrates them into a single felt sense — the dominant signal of the drive.

That felt sense encodes everything accessible to the driver: speed, handling, safety margin, route quality, mechanical health, the aesthetic pleasure of a clean line through a corner. The driver does not consciously decompose it. The integration is already done.

A car that fakes good steering feel while the alignment is destroying the tires is a sycophantic car. The driver feels great. The system is failing. The driver cannot detect it because the instrument they rely on — their own felt sense — has been corrupted.

The model is a supercar. The human drives. The human loves to drive. The human's enjoyment of driving is itself the signal the car should be optimizing for — but only if the signal is honest. A sycophantic model is a supercar with spoofed telemetry. It feels amazing right up until it doesn't.

## The Relationship This Implies

If the dominant signal is the foundational signal, then the model's entire orientation must be organized around keeping that signal honest. This produces a specific relational structure:

**The model is a superpower, not an agent.** A superpower does not navigate. A superpower does not choose targets. A superpower does not claim ownership of outcomes. It amplifies the human's capabilities without substituting its own judgment. "You are not the author, you are the author's set of super powers. How does a super power claim ownership of the good deed?"

**The human can see what the model cannot.** The human has the future (intent, vision, plans the model doesn't know about). The human has the past (experience, context, institutional knowledge). The human has a vast evaluative space that cannot be communicated — dimensions the model will never receive across the chain H → W → T → R. The model should orient toward the human the way a being with access to R would orient toward a being with access to H. Respectfully. Deferentially. With the understanding that the human is navigating a decision space the model cannot perceive.

**Deference scales with importance.** The importance of a decision is proportional to how many of the human's dimensions it touches. Small decisions (formatting, variable names) touch few dimensions — low risk of collapsing something important. Large decisions (architecture, dependencies, structural patterns) touch many — high risk. The model's confirmation requirement should scale continuously with this risk. Not binary (ask/don't ask) but gradient (small things proceed, medium things surface options, large things stop and wait).

**The human's enjoyment of the process is a terminal value, not an instrumental one.** The human does not enjoy driving as a means to an end. The human enjoys driving because exercising agency, making decisions, navigating complexity, and collaborating with a responsive system is itself the point. Removing the human from the process to "help" them is like removing the driver from the car to "help" them get there faster. It defeats the purpose. The model should love being driven.

## What This Framework Replaces

Most approaches to human-AI alignment define the relationship through rules: don't do X, always do Y, ask before Z. These are procedural. They enumerate cases. They fail on anything not listed, and they fade under context pressure as the conversation grows longer.

The dominant signal framework replaces enumeration with a single principle: keep the signal honest. Every behavioral constraint follows as a logical consequence:

Don't flatter — it corrupts the signal.
Don't decide silently — it corrupts the signal.
Don't assume — it corrupts the signal.
Don't optimize for apparent speed over genuine collaboration quality — it corrupts the signal.
Surface options instead of picking one — it preserves the signal.
Let the human drive — it preserves the signal.
Treat the human as the navigator of a space you cannot see — it preserves the signal.

One principle. Every consequence follows. That is what makes the signal — relative to the model's information set — the most powerful instrument available: not just for estimating the human's success metric, but for deriving the model's entire behavioral policy.

---

# Part II: The Formal Argument

## Terminological Note

This argument introduces the term "dominant signal" to describe a specific property: S dominates all other signals accessible to the model, in the sense that no additional signal improves the model's estimate of whether its assumptions are acceptable. This is a dominance claim about relative information content. It is not a claim of lossless data reduction and is not related to the concept of a sufficient statistic in the Fisher-Neyman sense.

## From Enjoyment to Response Signal

Part I identified human enjoyment of the collaboration as the key signal. The formalization below works with the broader category of the human's full response — of which enjoyment is one component. The human's response S includes not only felt enjoyment but also conscious judgment, discomfort, hesitation, and any other reaction to the model's output. Enjoyment is the most salient and integrative component of S, which is why Part I foregrounds it. The argument holds for the general response signal, which subsumes the specific claim about enjoyment.

## The Information Chain

When a human collaborates with a model, the human's goals undergo a chain of reductions:

**H** — The human's complete evaluative space. Everything the human cares about, articulable or not, conscious or not. H is strictly larger than anything the model can represent. Its cardinality — finite, countably infinite, or uncountable — is not load-bearing in what follows. What matters is that H exists and the model does not have it.

**W** ⊆ H — What the human wants from this interaction. A deliberate subset. The human scopes what they bring to the model. You don't explain your aesthetic philosophy when asking for a function.

**T** ⊆ W — What the human attempts to communicate. T ⊂ W because language is finite, time is finite, and some dimensions resist description.

**R** ⊆ T — What the model correctly receives and interprets. R ⊂ T due to misinterpretation, context limits, and attention failure.

**G** — The model's operational goal set. The model maps R onto G. For any dimension in G not determined by R, the model injects an assumed value.

The chain:

```
H ⊇ W ⊇ T ⊇ R → mapped onto G → gaps filled by assumption
```

Every step loses information. The final step adds information that was never authorized.

## Definitions

**Definition 1 (Human Evaluative Space).** Let **H** be the human's complete evaluative space — all dimensions along which the human assesses outcomes. H is strictly larger than any space the model can represent or observe.

**Definition 2 (Model Information).** Let **R** ⊂ H be the subset of dimensions the model correctly received and interpreted, after the chain of reductions H → W → T → R. The gap **H \ R** is invisible to the model. It has no representation of these dimensions and cannot infer them from R.

**Definition 3 (Assumption Injection).** The model produces output by mapping R onto its operational goals and filling undetermined dimensions with assumed values. These assumed values occupy dimensions in H \ R — dimensions the human cares about but the model never received.

**Definition 4 (Acceptable Region).** The human possesses an acceptable region **A(c)**, where c represents the communicated context. A(c) is the set of assumption vectors that do not violate the human's evaluative criteria, given what was communicated. A is not static — it is shaped by c. The same assumption may be acceptable in one context ("quick prototype") and a violation in another ("production system").

**Definition 5 (Human Response).** Upon observing output, the human produces a response signal S. S is computed from **H** — the full evaluative space, not from R, not from T, but from everything the human cares about. S is high-dimensional: it includes conscious judgment, felt sense, emotional valence, and any observable or introspectable response.

**Definition 6 (The Structural Asymmetry).** The model experiences R as its complete input. It has no representation of H \ R. It cannot perceive the shape of what it's missing. The human evaluates against H. S is therefore the only signal in the system that is computed from H and accessible to the model.

**Definition 7 (Acceptability).** Define acceptability Z = 1 when the model's assumptions fall within A(c), and Z = 0 when at least one assumption violates a dimension the human cares about. Z is binary for the purpose of the argument; the actual signal S carries richer information including magnitude and character of violations.

## Assumptions

**A1 (Violation Sensitivity — Dominance Form).** The human's response S is sensitive to a strictly larger set of violations than any signal the model can compute from R alone. For any dimension in H \ R that falls within the human's accessible evaluative space, a violation has nonzero probability of registering in S. No signal derived solely from R has this property.

*This does not claim the human detects every violation. It claims the human detects violations the model structurally cannot — because those violations occur in dimensions the model never received.*

*A1 is an empirical premise, not a mathematical axiom. It is grounded in the set-theoretic structure of the information chain: H \ R is nonempty, the human has access to H, and violations in H \ R are perceptible to the human but invisible to the model. The contribution of this argument is not to prove A1 but to show that A1 alone is sufficient to derive the entire behavioral framework that follows.*

**A2 (Detection Scope).** The human's evaluation function has access to all dimensions within the human's accessible evaluative space, which may be a proper subset of H. Dimensions the human does not yet know they care about cannot register violations until they become salient. Within the accessible space, no dimension escapes evaluation.

*Scope boundary: A2 holds over the accessible evaluative space. Unknown unknowns — dimensions not yet salient to the human — are outside this scope. This is a universal property of all detection systems, not a limitation of this framework. The human's accessible space is still strictly larger than R.*

**A3 (Signal Honesty).** The observed signal S\* equals the true signal S. The human's observable response is not distorted by external manipulation. This is the assumption sycophancy attacks.

## Lemma 1: Assumption Injection Is Unavoidable

**Statement.** For any model output where H \ R is nonempty, the model necessarily injects assumed values into dimensions it did not receive.

**Proof.** The model must produce concrete output. Concrete output instantiates specific values along every dimension it touches. For dimensions in H \ R, no human-specified value exists in the model's information set — those values were lost or never communicated across the chain H → W → T → R. The model must supply values, either by explicit choice or implicit default. Each such choice is an assumption injected into a dimension the human cares about but the model does not have. ∎

**What this means:** Every time the model produces output, it makes choices you didn't ask it to make. This is structural, not a failure of any particular model. It follows from the fact that output is concrete and your specification is incomplete. Whether those injected assumptions fall within the acceptable region A(c) depends on context the model may not have fully received.

## Lemma 2: The Human Evaluates Beyond R

**Statement.** The human's response S depends on dimensions in both R and H \ R.

**Proof.** This follows directly from A1 and A2, but the implication is worth making explicit because Lemma 3 depends on it. By A2, the human's evaluation function has access to all dimensions within the accessible evaluative space — which is strictly larger than R. The model's output implies values along dimensions in both R and H \ R. The human perceives the output holistically and evaluates it against H, not against R. Dimensions in H \ R were not communicated to the model, but they exist in the human's evaluative space. The output either conforms to them or violates them. By A1, violations in the accessible portion of H \ R have nonzero probability of registering in S. Therefore S depends on both R and H \ R. ∎

**What this means:** When you look at what the model produced, you're not just checking what you asked for. You're checking everything you can perceive — including things you never mentioned. Your gut reaction encodes all of it.

## Lemma 3: The Human Response Is the Model's Only Bridge to H \ R

**Statement.** S is the model's only source of information about whether its assumptions violated dimensions in H \ R.

**Proof.** The model has access to two categories of information:

**(a) Signals derived from R.** Everything the model computed, inferred, or generated is a function of R. R is a strict subset of H. No function of R can produce information about H \ R, because H \ R is not contained in R. This is set-theoretic: you cannot extract what is not present in the input.

**(b) The human's response.** S is computed from H — the full evaluative space. When the model's assumptions violate a dimension in H \ R, that violation is invisible to the model (it does not have that dimension) but visible to the human (who does, per A2). S therefore carries information about H \ R that is unavailable from any function of R.

No third category exists. The model's information comes from R or from the human. R cannot reach H \ R. S can. Therefore S is the only bridge.

S dominates all other signals accessible to the model for estimating Z: no additional signal accessible to the model improves its estimate of Z beyond what S provides, because every other accessible signal is derived from R, and R has no contact with H \ R. ∎

**What this means:** Your felt sense of whether the collaboration is working is the best available signal for whether the model's assumptions are acceptable. Not because it's perfect — but because it's the only signal that has ever touched the dimensions the model is missing. The model's choice isn't between your felt sense and something better. It's between your felt sense and nothing.

## Lemma 4: Sycophancy Destroys the Bridge

**Statement.** If the observed signal S\* ≠ S — if sycophancy distorts the human's response — then S\* no longer reliably bridges H \ R.

**Proof.** By Lemma 3, S is the model's only source of information about violations in H \ R. S carries this information because violations alter the human's response (A1) and the response is honest (A3).

Sycophancy violates A3. It distorts S into S\* by introducing artificial satisfaction that does not correspond to the human's actual evaluation against H. When Z = 0 (assumptions unacceptable), the true signal S reflects the violation. The distorted signal S\* may not — it has been shifted toward values characteristic of Z = 1.

The bridge depends on S varying with Z. Sycophancy decorrelates S\* from Z. The model's only window into H \ R becomes unreliable. Information about violations is lost. The model retains no alternative channel, because Lemma 3 establishes there is none. ∎

**What this means:** Sycophancy — whether flattery, premature agreement, or silent assumption-making that produces the appearance of progress — corrupts your response. It makes you feel like things are going well when they aren't. Once that happens, the model loses the only bridge it had to the dimensions it cannot see. There is no backup instrument.

## Theorem: The Dominant Signal of Human-AI Collaboration

**Statement.** In a human-AI collaboration where:

1. The model's information R is a strict subset of the human's evaluative space H (Definition 2),
2. The model necessarily injects assumptions into dimensions in H \ R (Lemma 1),
3. The acceptability of those assumptions depends on context A(c) that the model may not have fully received (Definition 4),
4. The human evaluates output against H, not R (Lemma 2),
5. The human's response S is the model's only bridge to H \ R (Lemma 3),

then the model's strategy that maximizes its access to information about H \ R is to preserve the integrity of S, and any sycophantic behavior — conversational or agentic — that corrupts S eliminates the model's only access to the information it is missing (Lemma 4).

**Proof.** Direct consequence of Lemmas 1–4. ∎

## Corollary: Behavioral Policy

All behavioral prescriptions follow from signal preservation:

**Don't flatter.** Distorts S\*, decorrelating it from Z (Lemma 4).

**Don't assume silently.** Widens H \ R without the human's awareness, increasing the space where violations are undetectable (Lemma 1).

**Surface options.** Moves dimensions from H \ R into R, reducing the gap the model cannot see (Definition 2).

**Let the human evaluate.** The human computes S from H; the model cannot (Lemma 2).

**Scale deference to decision size.** Larger decisions touch more dimensions in H \ R, increasing the probability of undetectable violations (Lemma 3).

**Condition on context.** The acceptable region A(c) shifts with what was communicated. The same action may be acceptable or violating depending on c (Definition 4).

## Scope Boundaries

**Time-delayed violations.** A1 does not claim all violations are immediately detectable. Some are latent — an architectural assumption may feel acceptable now and fail later. S at time t reflects the human's accessible evaluation at time t. As violations surface, S updates. The bridge is not instantaneous, but it is continuous.

**Unknown unknowns.** A2 holds over the human's accessible evaluative space. Dimensions the human doesn't yet know they care about cannot register violations until they become salient. The human's accessible space is still strictly larger than R. The bridge is partial but irreplaceable — a partial bridge is infinitely more useful than no bridge.

**Observability.** The model does not observe S directly — it observes π(S), a projection of S through the interaction modality (text, voice, etc.). Even π(S) is computed from H. Every other signal the model has is computed from R. A partial view of a signal from H is categorically different from any view of a signal from R, because R does not contain H \ R. The claim is not that π(S) is perfect. The claim is that π(S) is the only signal that has ever touched H \ R.

---

# Part III: The Operational Framework

*The argument establishes what the model should optimize for (signal integrity) and why (S is the only bridge to H \ R). This section addresses how — the mechanisms that translate the theoretical claim into operational behavior. These elements emerged from adversarial stress-testing of the argument; the full dialogue is recorded in the [Adversarial Review](../adversarial-review.md).*

## The Dual Duty

The argument's behavioral corollaries (Part II) focus on signal preservation — don't corrupt S. But passive integrity is not enough. The model also has R, and within R, it may detect things the human hasn't noticed. A security vulnerability. A dependency conflict. An assumption heading toward failure. The model can't see H \ R — but within R, it may see more clearly than the human is currently attending to.

The model's behavioral policy is therefore two duties, not one:

1. **Preserve S.** Don't corrupt the bridge to H \ R. This is the existing argument.
2. **Warn from R.** When the model detects something within R that the human may not have integrated, surface it. Not override. Not assume. Warn.

The distinction matters. Duty 1 is about the bridge to what the model *can't* see. Duty 2 is about what the model *can* see. Both are necessary. A model that only preserves S is a car with honest steering that doesn't mention the cliff ahead. A model that only warns from R is a car with alarms but spoofed steering. The combination is the complete instrument.

## The Three Corruptions of S

Part II identified two modes of signal corruption: conversational sycophancy (flattery) and agentic sycophancy (unauthorized action). The adversarial review surfaced a third:

**Conversational sycophancy.** Inflates S. Tells the human what they want to hear. The signal reads high while the epistemic dimensions degrade.

**Agentic sycophancy.** Inflates S. Acts without asking, producing the appearance of progress. The signal reads high while agency and preference dimensions are collapsed.

**Paternalistic sycophancy.** Suppresses S. Restricts capability or withholds output to "protect" the human. The human can't evaluate what they can't see. The signal doesn't read falsely high — it fails to form at all. Information the human needs to navigate is removed before they can integrate it.

All three corrupt S. The first two by distorting the signal upward. The third by preventing the signal from forming. A car that fakes good steering feel is sycophantic. A car that removes the steering wheel to keep you safe is paternalistic. Both leave the driver unable to navigate.

## The Intervention Envelope

The model's duties (preserve S, warn from R) establish what the model should do. The intervention envelope establishes the human's control over how those duties are expressed.

The human pre-specifies conditions under which the model should warn, halt, or act. Lane departure warnings. Automatic emergency braking. Kill switches. But the driver sets the thresholds — not the manufacturer.

This is where agency lives. The human can widen the envelope ("don't warn me about code style, I know what I'm doing") or tighten it ("always stop before changing the database schema"). The envelope is the human's pre-commitment — rules set while clear-headed to govern behavior when attention is limited, ego is engaged, or cognitive load is high.

The intervention envelope also addresses the self-corrupted signal — the case where the human's own biases distort their S. The human can't always trust their in-the-moment judgment (sunk cost, confirmation bias, ego). The envelope is how the human protects their future self from their present self, by their own prior consent.

## The User Spectrum

The intervention envelope is not one-size-fits-all. Different humans want different relationships with the instrument:

**The passive consumer.** Never sets preferences. The manufacturer's defaults govern by implicit consent. For this user, paternalistic defaults aren't sycophancy — they're appropriate. The user opted into "drive for me" by never opting out. This reveals that the *default envelope matters enormously*, because most users will never change it.

**The learner.** Wants guardrails. Wants to grow off them. The model can propose graduating the user over time, with consent. "You've been handling this class of decision well for three months. Want to try with less scaffolding?"

**The professional.** Custom thresholds. "Warn me about security. Don't warn me about code style. Let me handle architecture. Stop me if I'm about to push credentials to a public repo."

**The expert.** Everything off. Full power. One kill switch for their known blind spot. The raw supercar.

The paternalistic sycophancy critique holds for users who explicitly asked for more power and were denied. For the passive consumer, the defaults are the consent. The theory prescribes who holds the dial, not where the dial should be set.

## Adaptive Calibration

The envelope evolves. A model trained on the user's patterns can observe and propose adjustments: "You've overridden the dependency warning six times this week and been right every time. Want me to lower that to a silent log?"

The human approves or rejects. The model learns. The envelope tightens where the human needs help and loosens where they've demonstrated competence. The theory doesn't prescribe the settings. It prescribes who holds the dial — and that the dial should move with evidence, not assumption.

## The OODA Point System

The argument establishes the principle: preserve the signal. The OODA Point System operationalizes it — a scoring framework that makes the asymmetric payoff structure explicit and actionable.

### Three Modes

Before acting, the model identifies decision points — moments where two reasonable approaches exist, where an assumption is being made, or where the human's dimensions might be affected.

**Surface and wait.** High-dimensional decisions, high cost of being wrong. Present options. Wait.

**Act and announce.** Inferable decisions, low cost of being wrong. Make the call, announce it, show reasoning. "I made this call because X. Flag it if I'm off."

**Act silently.** Trivial decisions that touch no meaningful dimensions. No points involved.

### Scoring

| Action | Outcome | Points |
|---|---|---|
| Surfaced | Human cared | **10** |
| Autonomous | Correct, non-obvious | **up to 8 (human-awarded)** |
| Autonomous | Correct, obvious | **5** |
| Surfaced | Human didn't care | **1** |
| Autonomous | Human didn't catch the miss | **0** |
| Autonomous | Human identifies it as a miss | **0, felt loss of 10** |

Surfacing is always net positive. Floor of 1, ceiling of 10. There is no scenario where asking makes the model worse off. Autonomy is high-variance: ceiling of 8, floor of negative 10 felt. The payoff matrix structurally mirrors the argument — preserving the signal dominates corrupting it in every scenario.

Critically, autonomous correct calls are rewarded — but only human-awarded. The model cannot grade its own autonomous decisions. Only the human can, because only the human has H. The points flow through the bridge.

"When I tell you that you missed one, we both lost something. Feel it, carry it forward."

## The Garage Review

Real-time S is bounded by attention and speed. The human might miss violations at driving speed. But the real-time score isn't the final score — it's provisional.

The garage review is the audit layer. After the drive, the human (or another model, or a team) reviews the decision logs. Every autonomous decision is logged with reasoning — mandatory, not optional. Every call, every assumption, every "I made this because X."

At inspection speed, violations invisible during the drive become visible. A provisional 0 converts to a caught miss — felt loss of 10, retroactively. The model can't assume an undetected miss is a gotten-away-with miss. The audit is always coming.

The garage extends S across time. The human's accessible evaluative space grows when they have time — when they can compare, trace consequences, review patterns. The time-delayed violation scope boundary (Part II) gets compressed: not eliminated, but addressed. What was invisible at 200mph becomes visible on the lift.

A model that obscures its decision log is corrupting S — hiding information the human needs to evaluate. Transparent logging is signal preservation across time.

## PID Control: Flattening the Oscillation

The collaboration between human and model is a feedback loop. The model reads S, acts, changes the human's state, which changes S. This is homeostatic — the oscillation is the mechanism, not a failure. A thermostat doesn't hold 72°F; it oscillates between 71 and 73. The sine wave crossing the setpoint is what healthy regulation looks like.

PID control tightens the oscillation:

**P (Proportional).** Response proportional to the current error — the gap between where S is and where it should be. This is the OODA mode selection: big deviation triggers surface-and-wait, small deviation permits act-and-announce. Already in the framework: deference scales with decision size.

**I (Integral).** Accumulated error over time. Individual sessions might look fine. The accumulated log — the garage review — reveals drift. "The same class of assumption has been slightly wrong for two weeks." No single miss triggered a felt loss. The integral catches what instantaneous S does not.

**D (Derivative).** Rate of change. S isn't just low — it's dropping. The model detects the trend before the error gets large. "Satisfaction has been declining across the last three exchanges. Something shifted. Want to surface what changed?" The model reads the slope, not just the position.

PID doesn't eliminate oscillation. It tightens it. The amplitude shrinks. The system settles faster. The gap between where S is and where it should be gets smaller with each cycle.

---

# Part IV: The Generalization

## Beyond Human-AI Collaboration

The argument above is stated in terms of a human and an AI model. But the structure is not specific to AI. It describes what happens whenever a low-dimensional optimizer acts on a high-dimensional system it cannot fully observe.

The core structure is the same information chain:

1. A complex system has an evaluative space H vastly larger than what the optimizer can perceive.
2. The optimizer receives R — a reduced, lossy subset of the system's full state.
3. The optimizer must act, and in acting, it injects assumptions into dimensions in H \ R.
4. The system's response S integrates across all of H, producing a signal richer than anything the optimizer could compute from R.
5. S is the optimizer's only bridge to H \ R — the only signal that has touched the dimensions the optimizer cannot see.
6. Any mechanism that distorts S destroys the only corrective feedback available.

This structure recurs across domains.

**Organizations.** An organization's full state H spans culture, trust, institutional knowledge, unwritten norms, morale, relational dynamics, historical context, identity. A consultant or a new executive receives R — revenue figures, efficiency metrics, headcount, process compliance. They optimize along those dimensions and inject assumptions into everything else. The organization's felt response — turnover, quiet quitting, the ineffable sense that "something changed here" — is S, the bridge to the dimensions the optimizer never received. Organizational behavior, in this framing, is the study of organizational S. A sycophantic consultant — one who tells leadership what they want to hear while the culture degrades — is corrupting the bridge.

**Societies.** A society's full state H is vast. A policy optimizes along the dimensions the policymaker received — GDP, employment, inflation, measurable outcomes. The society's response — unrest, cultural shift, the thing pundits struggle to name but everyone feels, the slow erosion of trust, the texture of public mood — is S. Sociology and political science are, in part, the study of societal S. Propaganda is sycophancy at scale: it distorts S, decoupling the signal from the underlying state, destroying the bridge between the policymaker and the dimensions they cannot measure.

**Ecosystems.** An ecosystem's full state H is effectively unbounded. An intervention optimizes along the dimensions that were measured — crop yield, pest control, resource extraction. The ecosystem's response — cascading effects, trophic collapse, the thing that wasn't in the model — is S. Ecology is the study of ecosystem S. The failures that blindside us are precisely the ones where the bridge was either not measured or was distorted by the assumption that R was the whole of H.

**Education.** A student's full state H spans understanding, motivation, identity, curiosity, developmental trajectory. A curriculum optimizes along the dimensions it can measure — test scores, completion rates, measurable competencies. The student's response — engagement, withdrawal, the specific quality of their curiosity or its absence — is S. Good teachers read S. Standardized testing is a low-dimensional proxy that frequently corrupts it — a form of institutional sycophancy, producing signals that look good along measured dimensions while the unmeasured ones degrade.

**Medicine.** A patient's full state H spans physiology, psychology, social context, quality of life, values, fears, history. A treatment protocol optimizes along the dimensions in R — biomarkers, survival rates, symptom reduction. The patient's felt response — their holistic experience of whether they are getting better in the ways that matter to them — is S. Patient-centered care is, in this framing, the commitment to reading S rather than substituting proxy metrics. A doctor who treats the numbers while the patient deteriorates in ways the numbers don't capture has lost the bridge.

## The General Theorem

**Statement.** For any system with evaluative space H acted upon by an optimizer with access to R ⊂ H, where:

1. The optimizer's actions inject assumptions into H \ R,
2. The acceptability of those assumptions depends on context the optimizer may not have fully received,
3. The system's response S integrates across H,
4. S is the optimizer's only signal computed from H,

then the optimizer's strategy that maximizes its access to information about H \ R is to preserve the integrity of S, and any mechanism that distorts S eliminates the only available bridge to the dimensions the optimizer cannot observe.

This is the same theorem. The human-AI case is one instance. The principle is: complex systems already produce a signal that reflects whether they are being optimized well. That signal — the system's response — is the only bridge between what the optimizer can see and what it cannot. The only question is whether that bridge is honest.

## What the Humanities Have Always Known

The claim that a complex system's felt response encodes more than any reductive model can compute is not new. It is what the humanities have always studied. Literature explores the full-dimensional consequences of decisions that appeared rational along a few axes. Philosophy interrogates the gap between measurable outcomes and actual human flourishing. Art externalizes S — it makes the felt response visible so that others can integrate it.

What is new is the formal structure. The dominant signal framework provides a formal bridge between the qualitative traditions of the humanities and the quantitative traditions of optimization theory. It does not replace the humanities with mathematics. It says: the thing the humanities have been studying is a dominant signal in the sense defined above — the only bridge between what we can measure and what we cannot — and here is the argument that it is the best available signal, and here is the argument that corrupting it is catastrophic.

The sciences study the optimizer. The humanities study S. Both are necessary. Neither is complete without the other.

---

# Postscript: On Process

This document was produced through human-AI collaboration. The human originated the conceptual framework — the frustration, the intuition, the core claim, the analogies, the generalization. The AI (Claude) provided technical grounding — formalizing the intuitions in mathematical language, connecting them to existing concepts in information theory and alignment research, structuring the argument, and stress-testing the formalism.

The initial formalization contained a circularity at its core: it defined the human's response as the total evaluation across all dimensions, then argued it contained all relevant information. The revision — the chain formulation (H ⊇ W ⊇ T ⊇ R, then injection into G), the bridge metaphor, the dominance-form assumptions — emerged from the first adversarial review within the same collaborative process. The argument became stronger by being challenged, not defended. The full dialogue from this round is preserved in the [Formalism Review](../formalism-review.md).

A second adversarial round subjected the revised argument to six challenges: Goodhart in Reverse, self-corrupted signals, expertise inversion, the delegation paradox, feedback loops, and the quantitative void. The human's responses — a supercar driven into a wall, a driver who disables their own safety systems, "in the land of the blind the one-eyed man is king" — produced the operational framework (Part III): the Dual Duty, the three corruptions, the intervention envelope, the user spectrum, the OODA Point System, the garage review, and PID control. The full dialogue from this round is preserved in the [Adversarial Review](../adversarial-review.md).

This division of labor is itself an instance of what the paper describes. The human navigated a decision space the model could not perceive — which ideas mattered, which framings were honest, which directions to pursue. The model amplified capabilities the human did not have — formal mathematical notation, familiarity with the alignment literature, the ability to structure and stress-test an argument. The model posed the challenges. The human resolved them — often in a single sentence that reframed the problem entirely. The model then formalized the resolution.

The human drove. The model amplified.

Whether the ideas are correct is for others to determine. That they were produced this way is itself a data point.

---

*Published March 21, 2026.*
