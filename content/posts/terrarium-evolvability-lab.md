---
title: "Terrarium: A Lab for the Evolvability of Cognitive Proxies"
date: 2026-08-15
author: Saeid
---
This is a companion piece to
[Consciousness, Computability, Decidability, and Evolvability](/posts/consciousness-computability-decidability-evolvability.md).
That piece argued for attacking weaker, well-formed questions about
consciousness-adjacent proxies instead of the metaphysical question directly,
and singled out evolvability as the more empirically checkable of the two
tracks, since a negative evolvability result can be tested against biology in
a way a negative decidability result cannot. This piece works through what
that actually looks like as a formal object, and what a controllable
synthetic world buys you when trying to study it.

## 1. Formalizing an evolutionary process

An evolutionary process is more than "mutation plus selection." A useful
abstraction, when development is represented explicitly, is a tuple

$$
E = (G, M, D, O, F, P)
$$

where

- \$G\$ is the genome / representation space,
- \$M\$ is the set of mutation operators,
- \$D\$ is the developmental process mapping genome to phenotype,
- \$O\$ is the observation / information channel available to the organism,
- \$F\$ is the fitness function,
- \$P\$ is the population dynamics and selection rule.

A single generation can be written as a chain of transformations:

$$
G_t \xrightarrow{M} G_t' \xrightarrow{D} A_t \xrightarrow{\text{environment}} o_t \xrightarrow{F} \text{fitness} \xrightarrow{P} G_{t+1}.
$$

The critical point sits in the middle of that chain. The organism does not
receive the full environmental state \$s_t\$; it receives only

$$
o_t = O(s_t).
$$

So the evolutionary information channel, stripped down to its essence, is

$$
\boxed{\; s_t \;\rightarrow\; O(s_t) \;\rightarrow\; \text{selection.} \;}
$$

Everything about what evolution can or cannot discover under a given process
\$E\$ is a statement about what survives this one arrow.

## 2. Where impossibility actually enters

The companion piece introduced the general form of this argument: if two
world states satisfy \$O(s_a) = O(s_b)\$ while a target property differs,
\$C(s_a) \neq C(s_b)\$, then no process reading only \$O\$ can distinguish them,
and its probability of correctly telling them apart cannot exceed chance.
Restated for an evolutionary process specifically, this becomes a genuine
impossibility result rather than a metaphor: the problem is not that
evolution "cannot search enough," it is that:

$$
\text{the relevant information never reaches the evolutionary process at all.}
$$

That reframing is what makes a non-evolvability theorem tractable in a way a
non-computability theorem about consciousness is not. You are no longer
asking about an unconstrained hypothetical algorithm; you are asking a
question with a precise input restriction built in from the start.

## 3. A concrete experimental setup

Start with simple organisms possessing sensors, memory, actuators, energy,
reproduction, and mutation, placed in a partially observable environment with
genuinely hidden variables. The organism observes \$o_t = O(s_t)\$ rather than
the full state \$s_t\$, and some environmental consequences are made to depend
on a hidden variable associated with the organism's *own* internal state.
This gives the population an evolutionary incentive to model itself, without
that behavior being written into the organism's design by hand.

The important design choice is what does *not* happen: nobody programs "build
a self-model" directly. Instead, the environment is constructed so that
self-modeling has causal utility, and evolution is left to determine whether
an architecture capable of exploiting that utility actually emerges under a
given \$E\$.

## 4. Systematically varying the evolutionary information channel

A single environment tells you one data point. The more useful object is a
*family* of environments that differ only in how much of the true state
reaches the organism, so that evolutionary accessibility can be mapped as a
function of information rather than asserted from a single run.

- **World A — rich information.** \$O(s) \approx s\$: near-complete access to the true state.
- **World B — sensory information.** The organism receives only local, egocentric observations of the environment, not global state.
- **World C — aggregate fitness.** The organism receives only a highly compressed success/failure signal.
- **World D — noisy aggregate fitness.** \$o = \bar f(A) + \epsilon\$: the same compressed signal, corrupted by noise.
- **World E — delayed fitness.** \$o_t = f(A_{t-k})\$: consequences are attributed to the organism only after a lag.
- **World F — deceptive fitness.** Locally advantageous changes can reduce long-run fitness — a Goodhart-style trap built directly into the environment.

The question this family is built to answer is

$$
\boxed{\text{which cognitive capabilities remain evolvable as available information decreases?}}
$$

and the answer is a curve or a surface, not a single yes/no.

## 5. Structural plasticity as an axis of its own

Development matters as much as information. Instead of evolution directly
specifying a fixed architecture, \$G \rightarrow \text{fixed network}\$, the
genome can instead specify developmental rules that produce a plastic
architecture, \$G \rightarrow \text{developmental rules} \rightarrow \text{plastic architecture}\$

Three regimes are worth distinguishing explicitly:

- **Fixed architecture.** \$A_{t+1} \approx A_t\$ — the network's structure does not change within a lifetime.
- **Functional plasticity.** Weights change dynamically, \$w_{ij}(t+1) = F\big(w_{ij}(t), x_t\big)\$, but the topology is fixed.
- **Structural plasticity.** The topology itself changes, \$G^{\text{brain}}_t \rightarrow G^{\text{brain}}_{t+1}\$: connections can appear, disappear, split, merge, or change role.

This produces a real, checkable conjecture rather than an assertion:

$$
\boxed{\text{does structural plasticity expand the class of functions evolvable by Darwinian processes?}}
$$

$$
\mathrm{Evolvable}(\mathcal{E}_{\text{fixed}}) \;\subset\; \mathrm{Evolvable}(\mathcal{E}_{\text{plastic}}) \quad ?
$$

This question is worth answering independently of anything about
consciousness — it is a genuine, self-contained question about the power of
developmental search relative to fixed-architecture search.

## 6. The evolvability landscape

For a target cognitive property \$C\$, define an evolutionary difficulty
measure \$D_E(C)\$, depending on generations, population size, mutation
constraints, information bandwidth, noise, deception, plasticity, and
developmental constraints. Varying two axes at a time — say

$$
x = \text{information bandwidth}, \qquad y = \text{structural plasticity},
$$

the measured quantity becomes \$\Pr(\text{evolve } C)\$, mapped out as a
surface rather than a point estimate. Surfaces of this kind can reveal a
critical boundary,

$$
I < I_{\mathrm{critical}}(C),
$$

below which the capability becomes effectively inaccessible regardless of
how much time is allowed to run. Finding such a boundary empirically is the
first step; explaining *why* it sits where it does — connecting it back to
something like Valiant's statistical-query argument for why parity resists
evolvability — is the step that turns an observation into an actual result.

## 7. Latent ground truth, and why it matters here

A synthetic world can contain something biological experiments structurally
cannot: latent ground truth. For a simulated agent, internal variables can be
recorded directly,

$$
Z_t = \{\text{beliefs, memory, goals, self-model, world-model, latent state}\}
$$

fully accessible to whoever is running the experiment, while remaining
entirely inaccessible to the agent's own evolutionary process. This is what
makes it possible to distinguish *behavior that merely looks like
self-modeling* from *an internal representation that actually corresponds to
the agent's own latent state* — a distinction that is close to impossible to
draw cleanly in a real organism, where the internal state is exactly the
thing you don't have direct access to.

## 8. The loop between experiment and theorem

The point of building a world like this is not to run simulations and
declare conclusions from them. The more defensible structure runs in both
directions:

$$
\boxed{\text{experiment} \rightarrow \text{conjecture} \rightarrow \text{mathematical analysis} \rightarrow \text{theorem} \rightarrow \text{new experiment}}
$$

or, starting from the other end,

$$
\boxed{\text{theorem} \rightarrow \text{prediction} \rightarrow \text{experiment.}}
$$

A simulated world of this kind supplies the experimental half; Valiant-style
theory supplies the formal notion of evolvability being tested against it.
Neither half is sufficient on its own — a simulation result without a
matching formal argument is a data point that might not generalize, and a
formal argument without empirical grounding rests entirely on how faithfully
its assumptions were chosen.

## 9. What a real non-evolvability theorem would need to say

Let \$C\$ be a formally defined cognitive capability and \$\mathcal{E}\$ a class
of evolutionary systems satisfying a stated set of assumptions: bounded
mutation radius, finite population, local selection, limited sensory
bandwidth, noisy fitness, no direct access to latent variables, specific
developmental constraints. A real theorem in this space takes one of two
forms. The weaker one bounds the probability of success:

$$
\forall E \in \mathcal{E}, \qquad \Pr[E \text{ reaches } C] \leq p.
$$

The stronger one rules it out entirely:

$$
C \notin \mathrm{Evolvable}(\mathcal{E}).
$$

Either would say: no Darwinian process satisfying these specific assumptions
can reach the target, regardless of how long it runs. Neither would say
consciousness is impossible. If biological consciousness in fact exists —
and by ordinary standards of evidence, it does — a result like this would
instead force a reconsideration of one or more of: the evolutionary model
\$\mathcal{E}\$ itself, the information actually available to biological
organisms (richer than the model assumed), the developmental process, the
target definition \$C\$, the underlying neural mechanisms, or the assumption
that consciousness arose from ordinary Darwinian evolution acting alone
rather than in combination with development, learning, or selection at other
levels.

## 10. The hierarchy this all sits inside

Put together, the research program this instrument serves can be read as a
single descending ladder:

$$
\boxed{
\begin{array}{c}
\text{Can it be computed?} \\
\downarrow \\
\text{Can it be decided?} \\
\downarrow \\
\text{Can it be learned?} \\
\downarrow \\
\text{Can evolution discover it?} \\
\downarrow \\
\text{Under what information constraints?} \\
\downarrow \\
\text{What physical architecture is required?}
\end{array}
}
$$

The point of the ladder is not to assume in advance that consciousness lies
outside computation, or outside evolution's reach — it's to progressively
constrain the space of possible explanations. Consciousness could turn out to
be computable but not efficiently evolvable; computable but undecidable to
recognize from an arbitrary system description; or something stranger than
either. Each individual result, however narrow, narrows that space by one
notch. A sensible entry point into the ladder is deliberately unglamorous:

$$
\text{linear functions} \rightarrow \text{XOR/parity} \rightarrow \text{hierarchical functions} \rightarrow \text{recursive tasks} \rightarrow \text{self-modeling tasks,}
$$

asking at each stage what specifically makes that function evolvable or not,
before the target becomes anything cognitive at all. Whether consciousness
eventually turns out to be just another difficult point on this landscape, or
sits behind a qualitatively different boundary, is exactly the kind of
question this instrument is built to make less speculative — one formal
result at a time, and by the same logic laid out in the companion piece, with
every such result read as conditional on the proxy actually mattering, not as
a verdict on consciousness itself.
