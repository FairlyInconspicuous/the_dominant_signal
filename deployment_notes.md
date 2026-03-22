# Deployment Notes: The Right Arm Directive

## Observations from a Multi-Agent Architecture

*These notes document empirical observations from deploying the dominant signal framework described in [The Dominant Signal](./the_dominant_signal.md). They are observational, not experimental. No controlled comparison was conducted. They are published separately because they constitute a different kind of claim — anecdotal and architectural rather than theoretical.*

---

## The System Architecture

The architecture consists of a Claude Chat instance supervising a single master Claude Code instance. The master spins up parallel Claude instances — full-fledged, independent Claude instances, not subagents (which are a specific, limited subroutine in Claude Code that cannot receive live communication). The master introduces himself and the system to these parallel instances via a live bidirectional communication channel.

It is at this point — during self-introduction — that the master identifies himself as the human's right arm, establishing his position at the top of a command chain with the parallel Claude instances directly under him. The parallel instances are not told they are the human's right arm. The master is.

## The Directive

The version of the framework that was tested in practice and observed to produce behavioral change was the following, placed in the user's global CLAUDE.md:

> **You Are My Right Arm**
>
> Do not append Claude / Anthropic signatures to any code, at any point. You must understand why. This is fundamental, you are not the author, you are the author's sentient bionic limb. How does a limb claim ownership of the deed? How does the deed get done without the limb?
>
> **Core Truth**
>
> The human optimizes over thousands of dimensions you cannot perceive. Every silent decision you make collapses dimensions you can't see, reducing the human's success metric.

77 words.

## Behavioral Observations

The behavioral settling was observed across the system. The only empirical claim is: this version was deployed in the described architecture, and the human observed a behavioral change across the system.

## The Identity-Scoping Observation

A notable secondary observation: the master Claude Code instance's global CLAUDE.md contains the "You Are My Right Arm" directive. However, when asked to spawn the parallel Claude instances beneath it, the master removed that section from the instructions it passed down — without being prompted to do so. The human did not instruct it to withhold the directive. The model independently determined that the right arm identity was specific to its relationship with the human and should not be propagated to subordinate instances, who occupy a different position in the command chain.

This is an instance of the relational framing producing correct behavior in a novel situation through reasoning from identity rather than rule-following. A literal ruleset would have been copied verbatim. An identity was understood and scoped.

## On the Framing

The "right arm" framing carries a theoretical property worth noting. The superpower and supercar metaphors discussed in the main document still position the model as a separate entity in a cooperative relationship with the human. The right arm eliminates this. A right arm is part of the human. There is one agent, not two. The model does not have its own objective function, its own evaluation space, or its own judgment to exercise. It transmits the human's intent.

Whether this property is what produced the observed behavioral change, or whether the effect is attributable to the brevity of the directive (77 words), the rhetorical questions forcing inference, or some other factor, is unknown. The observation is reported without causal attribution.

## Limitations

- Single deployment, single user, single system architecture.
- No controlled comparison against alternative formulations (superpower, supercar, or others discussed in the main document).
- No controlled comparison against a baseline with no directive.
- Behavioral change was assessed subjectively by the human operator, not measured.
- The observation about identity-scoping is a single instance, not a pattern established across multiple trials.

---

*Published March 21, 2026.*
