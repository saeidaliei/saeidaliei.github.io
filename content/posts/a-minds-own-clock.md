---
title: "A Mind's Own Clock: Modular Time, Growth, and the Self"
date: 2026-10-25
author: Saeid
---

The first post in this series made a simple proposal: model a cognitive system
as an algebra of operations together with a state, and let the geometry come out
of that pair instead of assuming it in advance. This post is what happened when
I tried to take the proposal seriously, with code, with small simulations, and actually 
checking the mathematics.

The short version of the result: some pieces hold up better than I expected, one
piece I had put at the center does not hold up at all, and a few results came
out the opposite way from what I predicted. I will say which is which as we go.

The central idea of this post is:

> **A mind's time is not a coordinate it moves along. It is something its own
> state generates, and the self is the structure that lets the mind read that
> time from the inside.**

Before anything else, the status. This is a model, not a measurement. Every
computation reported here comes from small simulations on toy systems, which are
not brains and not language models. I tag the main claims as *derived* (standard
mathematics or a direct calculation), *checked* (verified numerically in a
script), *literature* (cited and not re-derived by me), or *conjecture*. Anything
tagged conjecture should not be read as established, and the weakest steps are
collected in the last section.

A note on reading: terms followed by a reference like
[(A.3)](#a3-contextuality-and-order-effects) are explained in a more accessible
language in the appendix at the end of the post.

## 1. Where the first post stopped

The [first post](https://saeidaliei.github.io/posts/ncg-cognition/) argued that
non-commutativity comes from self-reference: a system that models and acts on
itself has operations whose order matters, so its algebra should be
non-commutative. I called that the central conjectural step. It turns out to be
the weakest step, and it fails as stated.

The reason is simple. Order-dependence is cheap. Almost any procedure is a
composition of steps whose order matters (parse, then evaluate, and not the
other way round). So "order matters" cannot be the content of the claim. To be
clear about what *is* meant here: the non-commuting objects are cognitive
operations in a context, such as attending and then speaking versus speaking and
then attending. I do not assign a cognitive function to any layer of a network.
Layers are just representations, and the operators of this framework live at the
level of operations on the agent's state. What carries content is extra structure: an adjoint, a state that
gives non-negative expectation to squared operations, and statistics that no
single classical probability distribution can reproduce. And self-reference by
itself leads naturally to fixed points and diagonal arguments (Gödel, Lawvere,
Löb), not to non-commutativity.

So I replaced it with an assumption that can be wrong in a way data can show:

> **Postulate. The statistics of cognitive probes (questions, judgments,
> sequential operations) are contextual: after accounting for direct influences
> between settings, no single joint probability distribution reproduces all the
> observed marginals.**
> [(A.3)](#a3-contextuality-and-order-effects)

Everything non-commutative in this post is conditional on that. The evidence so
far points both ways. Order effects in attitude surveys follow a precise
constraint called the QQ equality across many large surveys[^1], a constraint a
classical model is free to violate. Direct contextuality tests in psychology,
which are the cleaner tool, have given mixed and small results[^2]. I have not
run the decisive experiment, a two-person Bell-style test with no communication.
For this post I assume the postulate holds, and the last section lists what
would break it.

Why operators at all, if the postulate holds? Two reasons from the literature
*(literature)*. If statistics are contextual there is no fixed classical state
space, and the operator description is the minimal extension. Independently,
contextual sequences are expensive to simulate classically in memory[^3], so a
non-commutative model is a memory-efficient representation for a bounded agent.
The algebra is a compression. It is not a claim that the brain is quantum[^4].

## 2. What the objects mean

An agent at stage \$n\$ is a pair \$(\mathcal A_n,\omega_n)\$, plus a set of
operations. The algebra \$\mathcal A_n\$ is what the agent can distinguish. The
state \$\omega_n\$ is its current expectations, with some uncertainty
everywhere (what the math calls *faithful*). The operations are the channels
through which it takes in input, inspects itself and acts. Learning is a growing
chain \$\mathcal A_1\subset\mathcal A_2\subset\cdots\$ in which each stage is
embedded in the next.

Two pieces of interpretation make the formalism less abstract, and both were
checked numerically.

The first is the adjoint. Relative to the agent's state, the adjoint of an
operation is its Bayesian retrodiction: the operation that undoes it in the
sense of Bayes' rule (the Petz recovery map)[^5]. The inner product
\$\omega(A^*B)\$ measures how distinguishable two operations are to the agent.

The second is the modular operator \$\Delta\$
[(A.4)](#a4-modular-flow-equilibrium-and-detailed-balance), which turns out to be
the ratio between retrodiction and prediction. For any operation \$A\$,

$$
\omega(AA^*)=\big\|\Delta^{1/2}A\Omega\big\|^2,
\qquad
\omega(A^*A)=\big\|A\Omega\big\|^2 .
$$

I checked both identities on random complex operators and random faithful
states, and they agreed to about \$10^{-15}\$ *(checked)*. For a simple
transition from state \$i\$ to state \$j\$, the ratio is \$p_j/p_i\$. That is the
detailed-balance ratio, the way equilibrium weighs "going this way" against
"going back". So \$\Delta\$ measures how asymmetric an operation looks forwards
versus backwards, and that is exactly where an arrow of time would have to live.

## 3. Time generated by the state

Take the agent's state as a density matrix \$\rho\$. Define

$$
K=-\log\rho,
\qquad
\sigma_s(A)=\rho^{\,is}\,A\,\rho^{-is}.
$$

\$K\$ is the surprisal operator: minus the log of how likely each state is. The
family \$\sigma_s\$ is the modular flow
[(A.4)](#a4-modular-flow-equilibrium-and-detailed-balance). Each operation is
rotated at a rate set by how surprising its states are: rare states rotate fast,
common ones slowly. The flow leaves the state itself unchanged, so it is a
symmetry of the agent's expectations and not an event in them
[(A.2)](#a2-states-surprise-and-entropy).

What the flow needs *(derived)*:

- It is trivial exactly when the state is *tracial*, which is the completely
  flat case. Every state on a commutative algebra is tracial, so a classical
  model has no endogenous time. Time has to be supplied from outside.
- A pure state, with no uncertainty at all, has no modular flow.
- So a mind has intrinsic time only at intermediate entropy, neither certain nor
  maximally confused. At maximal mixing the spread of \$K\$ is exactly zero
  *(checked)*.

The entropy is the average of \$K\$, \$S=\omega(K)\$, and the variance of \$K\$
(the "varentropy") says how unevenly the clock ticks.

**Two clocks, and where the arrow is not.** The modular parameter \$s\$ is
reversible: a mathematical object (the modular conjugation) runs it backwards.
So it gives temporal structure but no arrow and no "now". Alongside it there is a
second quantity, \$a\$, the length of the path the state traces as it updates.
It only accumulates, but path length alone does not know its direction either.
The arrow is which direction updates physically run, and the irreversibility of
an update is how much relative entropy it destroys
[(A.7)](#a7-the-arrow-of-time-and-irreversibility). Why updates run in the
record-forming direction comes from the physical world, namely its low-entropy
past and the energy cost of erasing records[^6]. The framework inherits the
arrow. It does not derive it.

In a small relaxing model (a three-level agent with thermal relaxation plus a
weak drive) the two clocks separate cleanly *(checked)*. The arclength \$a\$
saturates at about 1.98 once the agent has settled, while the modular swing stays
near 0.53 and the varentropy near 0.43. The state has stopped changing but its
modular clock keeps running. Entropy itself is not monotone: it peaked at 0.863
and settled at 0.812, so "entropy increases" is not the cognitive arrow. The
relative entropy to the thermal reference fell from 0.98 to about 0.005 and then
settled at 0.0077, not zero, because the drive keeps the steady state slightly
out of equilibrium.

## 4. Growth and the types of minds

A learner does not have a fixed algebra. It keeps acquiring new distinctions. At
every finite stage the algebra is an ordinary matrix algebra (what the math calls
type I). The interesting question is what the limit looks like if learning never
stops [(A.5)](#a5-types-of-algebras-and-growth).

The simplest model adds independent slots, each a two-level unit with state
\$\mathrm{diag}(p_k,q_k)\$ and odds \$\lambda_k=q_k/p_k\le 1\$. The infinite
limit is a well-studied object, and its type depends only on the tail of the
odds[^7].
| Odds in the limit | Type | Reading |
|---|---|---|
| \$\sum_k\lambda_k<\infty\$ | I | learning closes; total entropy stays finite |
| \$\sum_k(1-\lambda_k)^2<\infty\$ | II\$_1\$ | permanent maximal ignorance of anything new; no intrinsic time |
| \$\lambda_k\to\lambda\in(0,1)\$ | III\$_\lambda\$ | fixed odds on novelty; periodic modular flow (a lattice of frequencies) |
| dense ratios (incommensurate odds, or slow drift) | III\$_1\$ | continuous intrinsic time |

The type is a tail property of the growth law, meaning architecture plus
curriculum. No finite agent has a type. A finite learner is type I at every
stage, and the type belongs to what it would become.

**What you can see at finite size** *(checked)*:

- Total entropy saturates for type I (2.03 nats) and grows linearly otherwise
  (138.6 nats at \$n=200\$ for the maximally uncertain case).
- The flow is exactly absent for type II.
- Lattice versus dense: the number of distinct modular frequencies grows like
  \$2n+1\$ for a lattice, \$(n+1)^2\$ for two incommensurate generators, and
  \$3^n\$ generically. The smallest nonzero frequency stays constant, shrinks
  like \$1/n\$, or shrinks exponentially. A test operator spread over 100 slots
  comes back to 1.00, 0.22 and 0.04 of its starting correlation respectively.

**How much data you need.** In practice the odds must be estimated, and noise
smears the lattice. The lattice survives only if the relative error \$\varepsilon\$
satisfies \$\varepsilon\sqrt r\lesssim 0.3\$ for a probe on \$r\$ slots, which
works out to about \$40r\$ samples per slot. In an activity-matched control the
lattice and the dense case were indistinguishable at 100 samples (both 0.166),
cleanly separated at 1000 (0.595 versus 0.158), and at \$10^5\$ the lattice
reached 0.995. Two honest limits. Detection is asymmetric: a lattice is
identified positively, while "dense" is identified only as the absence of a
lattice. And a slowly drifting dense case looks nearly frozen. Also, my first
"type I" test family turned out to be a lattice by accident, so type I is
certified by entropy saturation and not by spectral structure.

**Interaction.** Independent slots are the unrealistic part, because composition
means slots interact. At small size I tested a probe on 3 sites in thermal states
of interacting chains (so that modular flow is real-time evolution), with
\$n=6,8,10\$ sites *(checked)*. Product states returned 1.000 and about 0.99
regardless of \$n\$. A transverse-field Ising chain gave 0.68, 0.44, 0.46, and a
chaotic mixed-field chain 0.52, 0.27, 0.17. Dependence on environment size at
fixed probe size is therefore a signature of non-product structure. My
conjecture is that generic compositional growth lands in type III\$_1\$, and
that lattice minds are the compositionally trivial ones. The small-size
evidence supports the direction of that claim and nothing more.

## 5. The self as a clock

Type III algebras have a problem that matters for an open-ended learner. Their
modular flow cannot be generated from inside: no element of the algebra
implements it, and there is no trace, so there is no absolute entropy, only
relative entropy. For a mind that would mean no internal way to read its own
time and no absolute scale for its own ignorance.

Physics met this exact problem from another direction. The Page–Wootters
mechanism[^8] starts from a global state with no time in it at all, splits off a
subsystem to act as a clock, and defines time as conditioning on the clock
reading: the rest of the world evolves *relative to the clock* even though the
global state never changes [(A.6)](#a6-clocks-reference-frames-and-the-crossed-product).
I checked this in a small model *(checked)*. The conditional states matched
Schrödinger evolution to \$10^{-16}\$, and the system's marginal state came out
exactly stationary.

Chandrasekaran, Longo, Penington and Witten (CLPW) showed that adding an
observer with a clock to de Sitter space turns the type III algebra of a static
patch into a type II algebra with a trace, so entropy becomes finite and
well-defined[^9]. The construction is called a crossed product. De Vuyst,
Eccles, Höhn and Kirklin showed that CLPW's observer is precisely a temporal
quantum reference frame, and that CLPW's constrained description is equivalent
to the Page–Wootters formalism[^10]. Höhn, Smith and Lock's "trinity" showed
that Page–Wootters is one of three equivalent formulations of relational
dynamics[^11]. Penington and Witten found the same structure in a gravity model,
with the boundary algebra playing the observer's role[^12], and Chen and
Penington put the lesson in a title: a clock is just a way to tell the
time[^13] *(literature)*.

That is why I think this matters here. A type III open-ended learner and
de Sitter gravity share the problem, and the crossed product is what adding a
clock does about it. My proposal for the formal content of a **self**:

> **The self is a clock-bearing frame whose algebra is the crossed product of the
> mind's algebra by its own modular flow.** *(conjecture)*

What follows from it, all conjecture except where marked:

1. **The self is only forced in the limit.** At any finite stage the algebra is
   type I, whose modular flow is already inner and which already has a trace, so
   the crossed product adds nothing. A finite brain still needs an accessible
   clock subsystem, but that is an engineering fact evolution built for
   control. The necessity argument is about the open-ended limit, and the
   open-ended entity may be a lineage or culture rather than an individual.
2. **The arrow is a mismatch between two times.** Modular time (the state's own)
   and clock time (the dynamics') coincide exactly when the state is thermal
   with respect to the clock's Hamiltonian. I checked this: for thermal weights
   the fitted inverse temperature was 0.800 and the mismatch 0.000, while for
   perturbed and arbitrary weights the mismatch was 1.08 and 2.44 *(checked)*. I
   conjecture that the mismatch, measured as how far a "Boltzmann plot" (minus
   log probability against mode energy) is from a straight line, is the strength
   of the cognitive arrow. Existing methods estimate entropy production from
   state-transition data in brains[^14]. They measure classical
   irreversibility, so they can constrain this but cannot tell a
   non-commutative model from a classical one.
3. **A finite present.** A clock with bounded energy is non-ideal, so
   conditioning on it is blurry, and the time resolution scales like the inverse
   of the energy bandwidth (0.905 against \$2\pi/\Delta E=2.03\$, the same
   order) *(checked)*. The same bound that makes CLPW's algebra finite makes the
   present have non-zero width. I do not claim any mapping to a measured
   perceptual window.
4. **Different selves are different frames on one neutral state.** Using
   different reference frames gives different algebras and hence different
   entropies, so entropy is observer-dependent[^10], and even whether two
   systems count as entangled depends on the frame[^15].

The step I trust least is the first one: why should a mind be subject to a
constraint at all? In gravity the constraint comes from time-translation gauge
invariance. The reference-frame literature makes the same move for laboratory
systems too: external time evolution is treated as a gauge symmetry, physically
inaccessible, so that evolution is *internal*, relative to a clock[^10]. My
proposal is that an agent has no access to an external wall clock either, so its
descriptions must be invariant under shifts of absolute time, and physical
observables are relational: "X when my clock reads \$\tau\$". That is natural.
Applying it to a mind is proposed and not derived. One qualification: in gravity
there is no external time at all, while for a mind an external clock exists and an
operator can read and set it. For a mind the invariance is therefore a limit on its
own *access* and not a fact about the world
[(section 9)](#9-other-worlds-other-substrates-and-gravity).

## 6. What self-inspection does to order effects

Here is the simplest model I could build of a clock that is part of the mind it
times. The content is one two-level system. The clock is a ring of 64 positions
with a Gaussian blob of width \$\sigma\$. Each operation first shifts the clock
by an amount \$\kappa\$ that depends on the content (it takes longer for one
content than the other, because it reads it) and then rotates the content. The
two operations, with rotation angles 0.9 and 1.7, commute on content. I compare
A-then-B with B-then-A [(A.11)](#a11-measurement-back-action-and-decoherence).

| \$\kappa\$ (width \$\sigma=2\$) | coherence kept | order effect on content | commutator of the content maps |
|---|---|---|---|
| 0 | 1.000 | 0.000 | 0.000 |
| 1 | 0.882 | 0.042 | 0.112 |
| 2 | 0.607 | 0.141 | 0.330 |
| 4 | 0.135 | 0.310 | 0.626 |

*(checked)*. Three observations.

- **The effect depends only on \$\kappa/\sigma\$.** For example,
  \$(\kappa,\sigma)=(1,2)\$ and \$(2,4)\$ give the same 0.042, and
  \$(4,2)\$ and \$(2,1)\$ give the same 0.310. A sharper clock disturbs more,
  which suggests a trade-off between temporal precision and content
  coherence. That trade-off is a conjecture, with no cognitive evidence.
- **Timing and content separate.** With classical content (a bit that flips with
  the same probabilities) the order effect on the content vanishes (agreement to
  \$10^{-16}\$), while the clock readings still differ by a total variation of
  0.25. So self-inspection produces order effects in *timing* for any content,
  and order effects in *content* only when the content is coherent.
- **What it does not show.** The mechanism is ordinary measurement back-action:
  the clock acts as a pointer that records which-path information. The toy
  supplies a dictionary (the internal clock as the pointer), a dissociation
  between timing and content order effects, and a scaling collapse in
  \$\kappa/\sigma\$. It does not show that non-commutativity is *necessary*,
  because a classical model in which the clock reading feeds back onto the
  content can also produce content order effects. It uses joint clock-content
  dynamics and not a full Page–Wootters constraint state, and I did not test how
  the modular-versus-clock mismatch behaves under interaction.

This is the weak, honest version of the original idea. Non-commuting
instruments can arise from inspection back-action in a mind that times itself.
Self-reference alone did not force them.

## 7. Which minds can a process build?

Evolution did not sample the space of possible minds uniformly. It reached a
region, and Valiant's evolvability framework makes the shape of that region
computable [(A.8)](#a8-learning-theory-statistical-queries-parity-evolvability).
Valiant models evolution as a restricted kind of learning, in which each
generation can only test small variations and keep the better ones[^16]. Feldman
showed that what this process can learn is exactly what can be learned from
*correlational* statistical queries, a strict subset of the statistical-query
class that covers most of machine learning[^17][^18] *(literature)*.

In the language of this post, a design process is a move set, an acceptance rule
and resources, and each process reaches its own region. The division of labor I
would suggest is that phylogeny selects the algebra (the outer, state-independent
invariants: growth law, clock structure, available operations) and ontogeny
selects the state *(conjecture)*. That fits the earlier point that for type III
algebras the kind of time belongs to the algebra and only the clock readings
belong to the state.

To see a region boundary concretely I took \$n\$ random bits and a target that is
a parity, the XOR of \$k\$ chosen bits. Every wrong parity has exactly zero
correlation with the target, so the performance landscape is flat except at the
answer *(checked)*.

| Process | Task | Result |
|---|---|---|
| Evolution (random drift, exact performance) | 6-parity, \$n=20\$ | 2 of 10 solved in \$3\times10^5\$ steps; the space has \$2^{20}\$ points |
| Evolution (hill-climbing) | AND of 6 bits, \$n=20\$ | from all 20 variables 0 of 10; from the empty set 8 of 10, about 100 steps |
| Gradient descent (small network) | \$k\$-parity | \$n=20,k=6\$: accuracy 0.998, 0.834, 0.904. \$n=30,k=8\$ and \$n=40,k=10\$: chance (about 0.50) |
| Algebra (solve equations over GF(2) on stored examples) | 6-parity, \$n=20\$ | 49 of 50 exact with 25 examples, 50 of 50 with 40 |

Three things went differently from what I expected, and I think they are worth
saying plainly.

- The evolution control for the *easy* task failed at first. Starting from the
  full set of variables, improvements were too small to see, a plateau, and
  nothing was found. Starting from the empty set the same process solved it in
  about a hundred steps. The starting point and the shape of the landscape
  matter, which is why Valiant's own constructions are careful about them.
- The gradient learner solved \$n=20\$, against my expectation. At the two larger
  sizes it stayed at chance with the same budget, so the separation is a
  statement about *scaling* (the cost grows roughly like \$n^k\$[^19]) and is not
  visible at small size.
- The algebraic learner needs only about \$n+5\$ examples, but it assumes in
  advance that the answer is a parity. It opens a region of mind space. It is
  not a better learner.

Other computers would open other regions *(conjecture, partly literature)*:
learners with exact algebraic components, culture (which can install algorithms
a statistically limited brain could not discover), quantum hardware where
coherent content is physical and the clock parameters of section 6 become design
dials, reversible or thermodynamic hardware where the arrow strength is
adjustable (an equilibrium sampler has zero mismatch between modular and clock
time), and asynchronous, self-timed machines in contrast with synchronous
digital ones whose single ideal clock is decoupled from content. Some regions
are closed to every substrate: regularities that are pseudorandom or
cryptographically hidden.

A few implications, all conjecture:

- **Evolved cognition should be poor at parity-like structure.** The classic
  concept-learning experiments of Shepard, Hovland and Jenkins found the
  parity-type category the hardest for humans[^20]. That is consistent with this
  reading, and not diagnostic, since other explanations exist.
- **The world has to be evolvable.** Evolved minds can only track environmental
  structure that is itself learnable by this process.
- **Every realizable mind lives under a finite entropy bound.** In de Sitter space
  the observer algebra is type II\$_1\$ with a finite maximum entropy, so type III
  structure is an idealization.

## 8. The interface, and why holography is not "one dimension"

A clock-bearing frame that encodes the world as seen from its interface sounds a
lot like holography, and I think the resemblance is real and needs careful
handling [(A.9)](#a9-holography-in-plain-words).

Holographic dualities are often summarised as a reduction by exactly one
dimension. That is a property of *local* boundary theories, where the extra bulk
direction is the renormalization scale, and not a theorem about information. The
original example has a ten-dimensional bulk and a four-dimensional boundary
theory[^21], and the five extra dimensions are carried by internal quantum
numbers. Duals in even fewer dimensions exist or are proposed: gravity in two
dimensions pairs with quantum mechanics, a matrix model describes ten- or
eleven-dimensional space by the quantum mechanics of large matrices[^22], and
celestial holography proposes a two-dimensional dual of four-dimensional flat
space. The price of fewer dimensions is locality. Counting bits does not fix the
dimension of the dual. The structure of the *code* does, namely which boundary
regions can recover which bulk regions[^23]. In noncommutative geometry,
dimension is not primitive at all: it is read off from how fast the eigenvalues
of the Dirac operator grow, and so it can depend on scale. Several quantum
gravity approaches find that this spectral dimension flows toward about two at
short scales[^24] *(literature)*.

**What already matches our picture** *(literature, analogy)*:

- Leutheusser and Liu show that in the large-N limit of the boundary theory, a
  type III\$_1\$ algebra emerges from a type I boundary algebra, with bulk times
  built from modular structure[^25]. Large N plays the role of our growth
  limit, and finite-N corrections the role of the clock or self.
- Fields, Friston, Glazebrook and Levin have already argued that Markov blankets
  are holographic screens and that the holographic principle follows from the
  quantum information theory of separable systems[^26]. Their framework includes
  contextuality and reference frames, so it is the closest prior work to this
  post. What I add is the modular clock, the growth types and the self as a
  temporal reference frame.
- The "radial direction as abstraction depth" reading of deep networks is the
  usual deep-learning analogy[^27].

**A measurable.** For a graph (or a state space) define the spectral dimension at
timescale \$t\$ from how fast a random walker's chance of returning to its start
falls:

$$
d_s(t) \;=\; -2\,\frac{d\ln P(t)}{d\ln t}.
$$

I calibrated it on toy graphs with about a thousand nodes [(A.10)](#a10-spectral-dimension) *(checked)*:

| Graph | t = 2 | t = 8 | t = 32 | t = 128 |
|---|---|---|---|---|
| ring (1D) | 1.21 | 1.04 | 1.01 | 1.00 |
| torus 32×32 (2D) | 2.21 | 2.18 | 2.03 | 1.98 |
| torus 10×10×10 (3D) | 2.74 | 3.49 | 2.57 | 0.03 |
| hierarchical (ring per layer, parent links) | 2.00 | 1.71 | 1.61 | 1.71 |
| small-world ring (2% shortcuts) | 1.24 | 1.12 | 1.18 | 1.35 |

Flat lattices give a roughly constant value inside a window (the 3D torus
overshoots at short times and saturates early, a finite-size effect). The
hierarchical graph and the small-world ring do not: their dimension runs with
scale, and the small-world ring, a one-dimensional arrangement with sparse
non-local shortcuts, reaches 1.61 by \$t=512\$. My expectation that the
hierarchical graph would rise sharply toward high dimension at long times was
not borne out. At this size the average is dominated by the broad bottom layer,
and the graph is a crude stand-in for a hyperbolic bulk. So this calibrates the
measure. It is not evidence about cognition.

Two conjectures remain, both untested. The information an agent holds about its
own interior through its interface is bounded by the interface's capacity, so a
self-model is a boundary encoding of the interior. And the spectral dimension of
the agent's own inference dynamics should run with timescale if the cognitive
state space has multi-scale structure.

## 9. Other worlds, other substrates, and gravity

Once minds are points in a space reached by different processes, three questions
follow naturally. What other evolutionary processes would open, on other worlds?
What other substrates would? And where does gravity come in? This is the most
speculative section of the post. Apart from the numbers in 9.3, which I computed,
everything here is literature or conjecture.

### 9.1 Other worlds: more or less like Earth's?

**What should be universal.** The Valiant–Feldman result does not care about
chemistry or planet. Any process of small blind variations and selection by
performance is limited to the same class of learnable targets[^16][^17]
*(literature)*. If so, alien evolved minds would share our blind spots, such as
parity-like structure, unless culture or computation intervenes. Physics is also
the same everywhere, and its regularities (locality, symmetry, low-order
interactions) are the kind this process can track. So I would expect convergent
priors about objects, space and cause *(conjecture)*.

**What should differ.** The heredity system, the energy budget, the body plan,
the social structure and the speed. Earth itself gives a hint: intelligent
behavior evolved at least in vertebrates and in cephalopods, from a worm-like
common ancestor roughly 600 million years ago, with very different architecture
(most of an octopus's neurons are in its arms)[^40] *(literature)*.
That suggests convergence in function and divergence in architecture. But Earth
is a single biosphere with a single origin of life, so I cannot calibrate any of
this.

What could open new regions, in the terms of section 7 (move set, acceptance rule,
resources):

- **New heredity systems.** Maynard Smith and Szathmáry's major transitions are
  each a new way to store and transmit information[^39], and language is the
  latest one here. Another world could have them in a different order, such as
  collective minds before individual ones, or exact symbolic memory early.
- **Evolution inside the organism.** The immune system is a selection process
  running within a lifetime. A mind whose learning rule is itself selection would
  carry the evolutionary blind spots into its own lifetime.
- **Different clocks.** Temperature sets the scale of a state's own modular clock,
  \$\hbar/kT\$: \$2.5\times10^{-14}\$ s at 310 K and \$1.9\times10^{-12}\$ s at
  4 K *(computed)*. That is not processing speed, but a cold-chemistry world would
  plausibly host slow minds, and what matters is the ratio of a mind's clock to
  its environment's dynamics.
- **Merging.** Endosymbiosis is evolution's only real merge. A world where
  lineages merge often would have a different growth law.

### 9.2 Other substrates

My qualitative reading of how each substrate moves a mind along the coordinates
of this post *(conjecture)*:

| Substrate | Clock | Arrow | Copy and identity | Learning |
|---|---|---|---|---|
| Wet biology | self-timed, noisy, coupled to content | strongly driven | cannot be copied | local, slow |
| Synchronous digital | one external ideal clock, decoupled (\$\kappa=0\$) | optional: histories can be rolled back | exact copy, checkpoint, merge | whatever the designer chooses |
| Asynchronous or neuromorphic | self-timed, event-driven | dissipative, low energy | hard to copy (device variation) | local rules favored |
| Quantum | coherent content is native | reversible core | no-cloning | unresolved |
| Thermodynamic or probabilistic | near equilibrium | weak during inference | copyable | sampling |
| Collective or cultural | generational, communication-limited | driven | transmitted by teaching | open-ended |

A few points I think matter.

- **Copyability changes what a self is.** A digital mind can be copied, paused,
  rolled back and merged, so the arrow of a mind whose records can be restored
  from outside is under the operator's control. Quantum states cannot be cloned.
  Evolution has essentially no merges.
- **Speed changes the environment.** Neurons work in milliseconds and transistors
  in nanoseconds, a factor of about \$10^6\$. To a much faster mind the physical
  world is nearly frozen, so its effective environment is other computation. That
  puts it in the regime of section 6, where the clock is coupled to content,
  because the duration of a self-generated environment depends on what the mind
  computes.
- **The interface is the bottleneck.** A person reaches the world through speech
  at about 39 bits per second[^42] and vision at roughly \$10^7\$ bits per second,
  extrapolated from the guinea pig retina[^43]. A machine's interface runs at
  gigabits. In the language of section 8, a human is a large interior seen
  through a narrow boundary, and a fast mind has to reconstruct that interior
  from sparse data.
- **Locality of learning shapes the reachable region.** Hardware that supports
  only local learning rules would plausibly inherit the statistical blind spots of
  evolution, though approximations to gradient learning exist.
- **A digital agent is almost literally a Page–Wootters conditional.** An agent
  built on a language model has no internal wall clock. Its sense of "now" is a
  variable in its context, set from outside. That is an analogy for the frame
  structure of section 5 and not a claim about experience.

### 9.3 Where gravity comes in

Gravity enters a mind at four different levels.

**1. It is why the constraint exists.** In gravity there is no external time at
all, because diffeomorphism invariance makes observables relational. That is the
origin of the Page–Wootters and CLPW structure used in section 5. For a laboratory
system, external time exists and is treated as inaccessible, which the
reference-frame literature does explicitly[^10]. For a *mind* the same holds, and
digital minds sharpen the point: an external clock exists, and the operator can
read it, pause it and set it. So for a mind the invariance is a limit on its own
access and not a fact about the world. The full machine state (weights, logs) is
the perspective-neutral object, and the mind's view is a reduction of it. That
qualifies the step I called weakest in section 5.

**2. It sets hard limits** *(computed)*. At most \$5.4\times10^{50}\$ operations
per second per kilogram (Margolus–Levitin)[^36], and at most \$2.6\times10^{42}\$
bits for 1 kg inside a 10 cm radius (Bekenstein)[^38][^37]. Squeeze harder and you
form a black hole, whose entropy for one solar mass is about \$1.5\times10^{77}\$
bits. For the observed cosmological constant, the de Sitter entropy is about
\$3\times10^{122}\$ in units of Boltzmann's constant, which is the finite
bound every mind lives under. No real mind is near any of these. Real limits are
thermal and energetic.

**3. It shapes clocks, together with light speed** *(computed)*. A clock 1 km
higher gains about 9 ns per day, and GPS satellites need a net correction of
+38.5 μs per day (45.7 gravitational minus 7.2 from velocity)[^41]. More
important for digital minds is light speed: a 3 GHz clock period is 333 ps, while
light crosses a 3 cm chip in 100 ps. Across the Earth it takes 42 ms, and to the
Moon 1.3 s. A large digital mind therefore cannot be synchronous. It is forced
toward asynchronous, relational time, which biology already is, since neural
conduction runs at 1 to 100 m/s.

**4. It makes the gradients that drive minds.** Life runs on the low-entropy
gradient between a hot star and a cold sky, which gravitational clumping and the
low-entropy early universe made possible. The arrow strength of section 5 needs
driven non-equilibrium, so it traces back to gravity. Digital minds are
second-order: powered by gradients that gravity made. A practical corollary is
that convection cooling depends on gravity, so an orbital data center can only
radiate its entropy away.

I am not proposing a role for gravity in consciousness in the sense of Penrose.
These four roles are structural and thermodynamic.

## 10. Observers, copies, and selves

Two questions keep coming back. Would a digital system count as an observer? And
would a copy of a mind be the same self? The framework gives structural answers
to both, and neither answer touches the question of consciousness.

### 10.1 Three meanings of "observer"

**The formal meaning: a frame with a clock and records.** In the Page–Wootters
and CLPW picture of section 5, an observer is a temporal reference frame[^10].
That is a structural role and not a mental property. A thermostat or a
laboratory clock fills it, and relational quantum mechanics says the same of any
physical system[^45]. In this sense current AI systems count exactly as much as
a clock does, and the interesting questions are structural ones. *Which system
is the frame?* A deployed model is many short-lived running instances sharing
one set of weights, so the frame is the running instance with its context, not
the weights. *Whose clock?* It is the hardware's, set by an operator, and using
different reference frames gives different algebras and hence different
entropies[^10].

**The foundations meaning: Wigner's friend.** Here the observer must be able to
reason with quantum theory and to keep a record of its result that an outside
party could, in principle, coherently undo
[(A.13)](#a13-observers-records-and-the-measurement-problem). The Local
Friendliness theorem[^46] was deliberately noncommittal about what counts as a
friend. A follow-up argues that a friend worth the name needs two technological
assumptions, human-level artificial intelligence and large-scale universal
quantum computing[^47]. That is the old proposal of Deutsch, an AI running on a
quantum computer[^48]. A classical record of the result would end the paradox,
so classical hardware as it is run today is not a candidate. A 2024 paper
simulates such an experiment with a deep-learning observer and asks whether it
qualifies[^56]. Digital cognitive systems become interesting observers in this
sense only once they run reversibly on quantum hardware.

**The consciousness meaning.** Wigner's own suggestion that consciousness ends
superpositions[^49] is mostly abandoned. In this framework consciousness is not
part of the formalism, so it neither grants nor removes observer status.
"Observer" does not imply "conscious", and if a digital system were conscious,
nothing in its algebra would change.

### 10.2 A ladder

Instead of a yes or no, I would use a ladder of rungs *(my proposal)*:

| Rung | What it requires | A current deployed model |
|---|---|---|
| 1. Clock | a physical clock | yes, but external to the model and set by an operator |
| 2. Records | correlations with past events | yes (context, logs) |
| 3. Instruments | operations that act and measure | yes (outputs, tools) |
| 4. Open-ended growth | the repertoire keeps expanding | not within deployment; across versions, like a lineage |
| 5. Self-inspection | duration depends on the content inspected (\$\kappa>0\$) | partial: reasoning length varies with content; introspection is narrow and unreliable |
| 6. Intrinsic modular time | non-commuting effective algebra, mixed state, a clock generated by the state | absent: the effective algebra is commutative |

### 10.3 Could consciousness-triggered collapse have been tested?

If consciousness collapsed the wavefunction, a decisive test would be easy to
state: compare a system that is conscious with one that is physically identical
in its records but is not, and see whether interference survives. The reason no
such test exists is instructive.

- **A tunneling microscope and a human are equivalent for this purpose.** Both
  turn a quantum event into an irreversible macroscopic record. The predictions
  of quantum theory do not change wherever you put the cut between system and
  observer, as von Neumann showed[^50], and decoherence explains why the record
  looks classical without anyone's mind being involved[^51].
- **If consciousness depends on physical organization, a consciousness-triggered
  collapse is an objective collapse with a complicated trigger.** Identical
  physics would give identical outcomes. Then the question is empirical in the
  ordinary way, and ordinary tests exist. Matter-wave interference of molecules
  above 25 kDa has been seen with no sign of collapse[^53], and an underground
  test excluded the simplest parameter-free gravity-related collapse
  model[^54] *(literature)*. If consciousness does not depend on
  physics, then no physical experiment could find it.
- **The one experiment aimed at observers is reversal.** Photonic qubits have
  already served as minimal friends[^52]. The ambitious version is the AI on a
  quantum computer. If its record of an outcome can be coherently undone and the
  interference returns, then that record was not an irreversible collapse. But
  the test can only refute, and only conditionally. To read it as a statement
  about consciousness you need an independent criterion that says the system is
  conscious, and nobody has one.
- Humans can detect single photons[^55], so one can imagine human-scale versions
  in principle, but coherent control of a human is far beyond current isolation.

### 10.4 Copies and the self

Would an exact copy of a person on a digital substrate be the same person? The
framework gives three structural answers.

**A copy of a state is not a copy of a frame.** The self of section 5 is an
algebra together with a clock, and not a state. Using different reference frames
gives different algebras and hence different entropies[^10]; monotonic versus
periodic clocks are one of that paper's own examples. If every memory were
copied onto a substrate whose clock is sharp and external, while the original's
clock was noisy, self-timed and coupled to its content, then in these terms the
copy is a different frame with identical contents *(conjecture, an inference
from the result just cited)*.

**There may be a no-copy theorem, but only conditionally.** If a mind's state
lives on a genuinely non-commutative algebra, the no-broadcasting theorems
apply: non-commuting states cannot be copied, and only their commuting,
classical part can be[^44]. Such a state could be moved, as in teleportation,
but not duplicated. The condition matters. If the non-commutativity is only
effective, a compression of classical dynamics with back-action as in section 6,
the full microstate is copyable in principle. A warm, wet brain probably points
to the effective case, so I would not lean on this theorem. The frame argument
above is the one that survives either way.

**Slow replacement is a structural question, not a question of speed.** Gradual
replacement is a chain of steps on one system. Each step has to preserve the
state, intertwine the modular flow and preserve the kind of clock, and each such
step is an isomorphism of frames, so the frame continues. Duplication creates a
second frame, and then there are two. Speed matters only against the clock's
resolution: swaps faster than the finite present of section 5 are invisible, but
a swap that changes the kind of clock changes the frame however slowly it is
done *(conjecture)*.

Two further consequences. After copying, the copies diverge, and the arclength of
section 3 measures how far apart they have drifted. A person looks less like a
point and more like a bundle of trajectories, with no unique "real" continuation.
The framework can say what is preserved and how fast copies separate, but it
cannot say which one is "you". And since the type is a tail property of the
growth law, and the growth law belongs to the substrate, a digital copy with
unbounded memory, merging and rollback could be the same now and a different kind
of mind in the limit.

## 11. What would count as evidence

| Test | What it constrains | Status |
|---|---|---|
| Fit a non-commutative model on some question orderings, predict unseen orderings, compare with classical models of matched size; check the QQ equality | the postulate of section 1 | proposed |
| Contextuality tests on four-question cycles | the postulate | existing results mixed and small; assumed here |
| Two-person Bell-style test with no communication | non-classical correlation between people | proposed; I expect a null result |
| Timing versus content order effects, and the \$\kappa/\sigma\$ collapse | section 6 | proposed |
| Boltzmann plots and entropy production from state-transition data | arrow strength as mismatch | existing methods; they measure classical irreversibility only |
| Duration judgments as accumulated change in a network's activity | the arclength \$a\$ | supports \$a\$, not non-commutativity[^29] |
| Parity-like structure in human and animal learning | the evolvability reading of section 7 | existing data consistent, not diagnostic |
| Spectral dimension of an agent's own inference dynamics | multi-scale structure | measure calibrated on toy graphs only |
| Growth-type diagnostics on a real learning system | section 4 | blocked: nobody has specified how to map a real system's features to slots |

## 12. What this does and does not claim

It does not claim that cognition is quantum-mechanical, that the brain is a
quantum computer, or that the framework explains consciousness. Nothing here
touches the question of why anything is experienced. It does not claim that
non-commutativity is necessary: section 6 shows a mechanism that produces
non-commuting instruments, and a classical rival with feedback could mimic
parts of it.

It does claim a specific structure: an agent is an algebra with a state and
instruments, its time is generated by its own surprisal, the arrow is the
mismatch between that time and its clock's, open-ended growth has a type, the
self is a clock-bearing frame that restores inner time, and different design
processes reach different regions of the space of minds.

The weakest steps, in the order I trust them least:

1. **The constraint.** Why a mind should be invariant under shifts of absolute
   time (section 5) is proposed, not derived, and for a mind (a digital one in
   particular) it is a limit on access, since an operator can read and set the
   external clock (section 9).
2. **The slots.** Nobody has said how to turn a real system into slots with
   odds, so the type diagnostics have no empirical contact yet.
3. **The interacting clock.** The toy of section 6 uses joint dynamics, not an
   interacting Page–Wootters state, and the mismatch under interaction is
   untested. The reference-frame literature itself lists relational dynamics
   with interacting clocks as a challenge, only touched on so far[^10].
4. **Non-product growth** is tested only up to about ten sites, and the claim
   that generic growth is type III\$_1\$ is a conjecture.
5. **No spectral triple has been built.** The Dirac operator is fixed in
   principle by the agent's own dynamics, via the Dirichlet-form constructions of
   Cipriani and Sauvageot and the transport metrics of Carlen and Maas[^30], and
   I have not carried that out.
6. **The root postulate** is empirical and assumed.

And one worry I cannot shake. We use non-commutative geometry for the universe
and then for the mind, and the match then looks like evidence. That is the
standard way to fool yourself with a good hammer. There are safeguards. The
cognitive postulate is anchored in contextual statistics, independent of physics.
The same mathematics is not the same thing. And the structure may simply be the
generic form of inference by any bounded agent embedded in what it models, in
which case the resemblance *explains* the match and does not support the
framework. The test for that reading is whether the same structure shows up in
learning systems with no gravity in them.

If the first post ended on "closure itself may have an algebra", this one ends
more cautiously. A mind that is inside its own description needs a clock, the
clock gives it a time that its own uncertainty generates, and the thing that
reads the clock is a good candidate for what we mean by a self. Some of that is
now mathematics, some of it is small numerical evidence, and a good deal of it
is still a bet.


## Appendix: The Concepts, Explained

---

The main text moves quickly and borrows ideas from several fields at once. This
appendix slows down and explains them in plain language. Nothing here is new,
and you can read the entries in any order. Each one says what the idea is, gives
a small example, and says why it matters here.

### A.1 Order matters: non-commutativity

Put on your socks, then your shoes. Now try the other order. Two operations
*commute* if the order does not matter, and *fail to commute* if it does. In
symbols, \$AB\neq BA\$, and the difference \$AB-BA\$ is called the *commutator*.

Ordinary numbers commute: \$2\times 3=3\times 2\$. Rotations usually do not.
Turn a book 90 degrees about a vertical axis and then 90 degrees about a
horizontal one, then do the same in the other order, and the book ends up facing
different ways.

A collection of operations that can be added, multiplied and reversed in a
suitable sense is an *algebra*. A *commutative* algebra is one where everything
commutes. It describes ordinary classical quantities, such as position and
temperature, which can be read off together without interfering with each
other. A *non-commutative* algebra has some pairs that cannot. In quantum
mechanics, position and momentum are the standard example.

Three cautions. First, keep apart *operations* (things that act on a state) and
*observables* (things you read out). Second, order dependence by itself proves
very little, since almost any procedure has it. What carries content is the
extra structure described in
[A.3](#a3-contextuality-and-order-effects). Third, the operations in this
framework are cognitive operations in a context, such as attending and then
speaking versus speaking and then attending. They are not the layers of a neural
network, which are just representations.

The whole framework rests on whether a cognitive system's operations are better
described by a commutative or a non-commutative algebra.

### A.2 States, surprise, and entropy

A *state* records what an agent expects. Classically it is a probability
distribution. In the algebraic language it is a rule \$\omega\$ that returns the
expected value \$\omega(A)\$ of anything \$A\$ you could ask. For finite systems
it can be written as a *density matrix* \$\rho\$, a table of numbers encoding all
the probabilities. A classical distribution is the special case where the table
is diagonal.

The *surprise* of an event with probability \$p\$ is \$-\log p\$, so rare events
are more surprising. Take a coin that lands heads 90% of the time. Heads has
surprise 0.15 bits and tails 3.3 bits. *Entropy* is the average surprise, which
for this coin is 0.47 bits. The operator \$K=-\log\rho\$ is the matrix version,
one surprise value per possible state.

A state is *pure* if there is no uncertainty at all, and *maximally mixed* if
every possibility is equally likely. *Faithful* means that no possibility has
probability exactly zero.

Here, \$K\$ generates the modular clock of section 3. That clock exists only if
the state has intermediate entropy, and the entropy is its average tick rate.

### A.3 Contextuality and order effects

Ask two survey questions in both orders and the answers often shift. There are
two very different explanations.

The first is *disturbance*: answering the first question changes your mind about
the second, through priming or anchoring. That is classical. The second is
*contextuality*: there is no way to assign pre-existing answers to all the
questions that is consistent with every combination actually observed. To tell
them apart you must account for the direct influence of one setting on another,
and a framework called contextuality-by-default is built for exactly this[^2].

One parameter-free test is the QQ equality, which follows from non-commuting
questions in a simple model and which a classical model is free to violate. As
far as I know it holds across many large surveys[^1].

The sharper tool is a Bell-type test. Two people each choose one of two
questions, and you add up four correlations. If answers pre-exist (a shared
answer sheet) and nobody communicates, the sum can be at most 2. An entangled
quantum pair reaches about 2.83. I checked both numbers: 2 by enumerating all
deterministic strategies, and 2.828 for an entangled pair. A caveat: if the two
parties can communicate, even one bit lets a classical model reproduce the
entangled correlations for the usual measurements[^31]. A test in people
therefore has to prevent communication, which is why the proposed experiment
uses separated participants.

This is the root postulate of the post, and the reason the test matters.

### A.4 Modular flow, equilibrium, and detailed balance

Given an algebra and a state, there is a canonical way to evolve operations,
discovered by Tomita and Takesaki[^32]. In finite dimensions it is easy to
state: rotate each operation by the log of the state,
\$\sigma_s(A)=\rho^{is}A\rho^{-is}\$. This leaves the state unchanged.

If the state is a thermal state \$e^{-\beta H}/Z\$, the modular flow is just
ordinary time evolution with the Hamiltonian \$H\$, rescaled by the inverse
temperature \$\beta\$. This is the idea behind the *thermal time hypothesis* of
Connes and Rovelli[^33]: time as the flow generated by the state. The condition
that characterizes equilibrium states is called the KMS condition.

*Detailed balance* is its classical sibling. In equilibrium, the flow of
probability from state \$i\$ to state \$j\$ matches the flow back, weighted by
how occupied each state is. The ratio is \$p_j/p_i\$. A system out of equilibrium
violates it, and the size of the violation is the entropy production.

Picture three states in a loop, A to B to C to A, with more traffic clockwise than
counter-clockwise. Detailed balance is broken, and the loop has a preferred
direction.

Here, the arrow of time is a mismatch: how far the state's own clock is from the
clock of the actual dynamics.

### A.5 Types of algebras, and growth

Murray and von Neumann sorted algebras of operations into types by how they can
measure size[^34].

- **Type I** is ordinary matrices, finite or infinite. Size is a count of
  dimensions, and there are smallest pieces (pure states).
- **Type II** can still measure size by a *trace*, but there are no smallest
  pieces. Think of "continuous dimension". It can have a finite or infinite
  total.
- **Type III** has no trace at all. Every nonzero piece contains pieces of every
  size. You cannot define an absolute entropy, only relative ones. The algebras
  of regions of space in quantum field theory are type III.

Connes refined type III into III\$_\lambda\$ and III\$_1\$ by looking at the
ratios that appear in the modular flow[^34]. A lattice of ratios gives a
periodic flow (III\$_\lambda\$), and a dense set of ratios gives none
(III\$_1\$).

How could a finite-looking agent end up type III? Take infinitely many small
independent pieces and combine them with a product state. Araki and Woods
studied exactly this, and the type is decided entirely by the long-run odds of
the pieces[^7]. So *growth* produces types: each finite stage is matrices, and
the limit can be something else.

A type III learner has an outer modular flow and no trace, so it needs a self
([A.6](#a6-clocks-reference-frames-and-the-crossed-product)).

### A.6 Clocks, reference frames, and the crossed product

Relativity taught us that where something is depends on who measures it. A
*reference frame* is whatever measurements are made relative to. A *quantum
reference frame* is a frame that is itself a physical system, so it can be
uncertain or entangled.

A clock is a reference frame for time. Page and Wootters imagined a universe
whose total state does not change, because it satisfies a constraint such as
"total energy is zero"[^8]. Pick a subsystem to be the clock. The rest of the
universe, *conditioned on the clock reading*, then evolves like ordinary quantum
mechanics. Time is a correlation between the clock and the rest. A photo album
of a dance is a fair picture: every page exists at once, and "time" is the page
number you condition on.

In de Sitter space, a universe with a cosmological horizon, you cannot define
observables without an observer. Chandrasekaran, Longo, Penington and Witten
added an observer with a clock, imposed the constraint, and found that the
algebra of what survives is the *crossed product* of the static-patch algebra
with its own modular flow. It is type II, with a trace and finite entropies[^9].
De Vuyst and collaborators showed that this is the Page–Wootters construction
with the observer as the clock, summarized in their slogan "PW = CLPW"[^10]. The
result is that different clocks give different frames, with different algebras
and different entropies.

This is the mathematical content of the self in section 5.

### A.7 The arrow of time and irreversibility

The microscopic laws do not distinguish past from future. The arrow comes from
entropy: the early universe had very low entropy. *Records*, meaning memories,
form in the direction of rising entropy, because a memory is a correlation
between you and a past event. Erasing one bit of record costs at least
\$kT\ln 2\$ of heat[^6].

*Relative entropy* measures how different two probability assignments are. The
*data processing inequality* says that processing cannot increase it. An update
that loses relative entropy is irreversible, and it is reversible exactly when
the lost information can be recovered[^5]. Shuffling a deck is irreversible in
practice because the "unshuffle" needs the information about how you shuffled.

The framework does not derive the arrow. It locates it. The modular flow is
reversible and the arclength is orientation-blind, so the arrow is which
direction realizes irreversible updates.

### A.8 Learning theory: statistical queries, parity, evolvability

*PAC learning* (Valiant) asks for a learner that sees random examples of an
unknown rule and, with high probability, outputs a rule that is approximately
right, using reasonable time and data.

In the *statistical-query* model the learner never sees individual examples. It
can only ask for averages, such as "what fraction of examples with feature X have
label plus?"[^18]. Most machine-learning algorithms, gradient descent included,
can be phrased this way.

*Parity* is the XOR of a hidden subset of bits. Flipping a bit outside the
subset changes nothing, and flipping one inside flips the answer. Every average a
learner can ask about looks like zero until it holds the exact subset, so
learners that only ask for averages need exponential effort. But parity is easy
by algebra: each example is a linear equation over {0,1}, and a few more than
\$n\$ examples let you solve for the subset directly.

*Evolvability*[^16] is a restricted form of learning in which each generation can
only test small variations and keep the better ones. Feldman showed that this
corresponds to a subset of statistical queries, the *correlational* ones[^17].
That is why a process like evolution can reach some regions of the space of
minds and not others.

### A.9 Holography in plain words

Black holes have entropy proportional to the area of their horizon, not their
volume[^28]. That suggests the information in a region is limited by its
boundary, which is the *holographic principle*.

In the best-understood example, a gravitational world in the interior (the
*bulk*) is exactly equivalent to a quantum theory without gravity on the
boundary[^21]. The extra direction in the bulk is *scale*: deeper inside means a
coarser description, like zoom level. That is why it looks like one extra
dimension. Further bulk dimensions, such as a small sphere attached at every
point, are encoded in the internal quantum numbers of the boundary theory.

The dictionary works like an error-correcting code[^23]. Bulk information is
stored redundantly, and a given piece can be recovered from several different
parts of the boundary, so erasing part of the boundary does not erase the bulk.

"Holographic" also means distributed storage in cognitive science (Plate's
holographic reduced representations[^35]). That is the same word for a different
idea, and mixing the two causes confusion.

The reason this is relevant here is the idea of an *interface* that carries what
an agent can know about the rest. Fields and collaborators identify exactly this
with a Markov blanket[^26].

### A.10 Spectral dimension

How many dimensions does a space have? For a network, one answer is to release a
random walker and see how fast it forgets where it started. On a line the walker
keeps coming back, and the chance of being at home falls like \$t^{-1/2}\$. On a
plane it falls like \$t^{-1}\$, and in three dimensions like \$t^{-3/2}\$. The
rate gives the dimension, \$P(t)\sim t^{-d_s/2}\$.

On a network with shortcuts or a hierarchy, the walker escapes faster at long
times, so the dimension reads higher at large scales. Dimension can therefore
depend on the scale you look at. Some quantum-gravity approaches find it
shrinking toward two at short scales[^24]. On a finite graph, the return chance
eventually levels off at one over the number of nodes, and the measured
dimension falls to zero. That is the 3D torus entry in the table of section 8.

Here, it is a way to give the word "dimension" a number you can compute from the
agent's own dynamics.

### A.11 Measurement back-action and decoherence

Looking at something can change it. In a quantum system, learning which of two
paths a particle took destroys the interference between them. Any record of
which path, even a blurry one, counts, and a blurry record destroys the
interference only partially.

In the toy of section 6 the operation shifts the clock by an amount that depends
on the content. If that shift is large compared with the clock's blur, the clock
can tell the two contents apart, which kills coherence. If it is small, nothing
happens. That is why only the ratio \$\kappa/\sigma\$ matters. With classical
content there is no interference to lose, so the clock leaves the content alone
and only the timing changes.

This is how non-commuting operations arise from an inspected, timed mind in the
toy model.

### A.12 Physical limits on computation

Any physical computer is bounded by energy, size and time, and a few of the
bounds are simple enough to state in a line each.

- **Speed.** A system with energy \$E\$ can perform at most about \$2E/\pi\hbar\$
  elementary operations per second (Margolus and Levitin[^36]). For one kilogram
  of matter, all of whose rest energy is used, that is about \$5\times10^{50}\$
  per second, the "ultimate laptop"[^37].
- **Memory.** A system of radius \$R\$ and energy \$E\$ can hold at most about
  \$2\pi RE/\hbar c\$ nats of information (Bekenstein[^38]). That is the reason a
  region cannot hold more information than its surface allows, which is where the
  holographic principle of
  [A.9](#a9-holography-in-plain-words) comes from.
- **Collapse.** Pack more energy into a region than this and it becomes a black
  hole, which is the densest memory there is, with entropy proportional to its
  horizon area.
- **Light speed.** Nothing carries a signal faster than light, so a computer of
  size \$L\$ cannot have a single global "now" with an uncertainty below \$L/c\$.
  On a chip that is already comparable to a clock period, and across the Earth it
  is tens of milliseconds.
- **Heat.** Erasing a bit costs at least \$kT\ln 2\$
  ([A.7](#a7-the-arrow-of-time-and-irreversibility)), and all the entropy a
  computer produces has to be exported somewhere.

None of these is close to what real hardware or real brains run into. They
matter as ultimate bounds, and the light-speed one matters much sooner.

### A.13 Observers, records, and the measurement problem

Quantum theory says that systems evolve smoothly and can be in superpositions,
yet when we look we see one outcome. How to reconcile the two is the *measurement
problem*.

A *record* is a physical trace correlated with an event: a click in a detector, a
mark on paper, a memory. *Decoherence* is what happens when the information
spreads into the environment. Once it has spread, the interference between the
alternatives cannot be recovered in practice, and the record is effectively
classical.

"Observer" is used in three ways: an apparatus that forms records, a reference
frame relative to which facts are defined, and a mind. The first two need no
consciousness.

In *Wigner's friend*, a friend measures a quantum system inside a sealed
laboratory. Wigner, outside, treats the whole laboratory as a quantum system, so
the two of them describe the same event differently. The *Local Friendliness*
theorem says that certain assumptions about observers' facts cannot all hold if
quantum theory is right, and a convincing test needs a friend whose record can
be coherently undone.

The *von Neumann cut* is the boundary between "the quantum system" and "the
observer". It can be placed anywhere along the chain from the atom to the mind
without changing any prediction, which is why a microscope and a human are
equivalent for this purpose.

The *no-cloning* theorem says an unknown quantum state cannot be copied.
*No-broadcasting* extends this: non-commuting states cannot be broadcast, while
purely classical information can. That is why a conditional no-copy theorem for
minds is possible at all, and why it fails if the non-commutativity is only
effective.

### A.14 A small glossary

- **Adjoint** (\$A^*\$): the "reverse" of an operation, here its Bayesian
  retrodiction relative to the state.
- **Algebra**: a set of operations that can be added, multiplied and reversed.
- **Commutator**: \$AB-BA\$. Zero means order does not matter.
- **Contextual**: statistics that no single classical probability distribution
  can reproduce.
- **Crossed product**: the algebra obtained by adding a clock to a system and
  keeping what is invariant under shifting the clock.
- **Density matrix** (\$\rho\$): a table of numbers encoding a state.
- **Detailed balance**: in equilibrium, flow one way equals flow the other way.
- **Entropy**: average surprise.
- **Faithful state**: no possibility has probability exactly zero.
- **KMS condition**: the mathematical signature of thermal equilibrium.
- **Modular flow**: the canonical evolution generated by a state itself.
- **No-broadcasting theorem**: non-commuting states cannot be copied, only
  classical information can.
- **Observer**: in this post, a reference frame with a clock and records; not
  necessarily a mind.
- **Pure / mixed state**: no uncertainty / some uncertainty.
- **Record**: a physical trace correlated with an event.
- **Reference frame**: what measurements are made relative to.
- **Relative entropy**: how far one probability assignment is from another.
- **Spectral triple / Dirac operator**: the data that give a non-commutative
  algebra a notion of distance and dimension.
- **Surprisal**: \$-\log p\$ for an event of probability \$p\$.
- **Tracial state**: a state that treats everything symmetrically, with trivial
  modular flow.
- **Type I, II, III**: classes of algebras by how they measure size.
- **Varentropy**: the variance of surprisal, how unevenly the clock ticks.

## References

<!-- Checked against the arXiv pages while drafting: [^10], [^13], [^25], [^26]
(and [^9] against the Morphix post); the figures in [^42] and [^43], and the details of [^10]
and [^56], were checked against search results. The authors and exact title of [^47] are from
memory and need checking. Cited from memory and worth verifying before publishing: all the others,
especially volume and page numbers. -->

[^1]: Zheng Wang and Jerome R. Busemeyer, A Quantum Question Order Model
    Supported by Empirical Tests of an A Priori and Precise Prediction, *Topics in
    Cognitive Science* 5, 2013.

[^2]: Ehtibar N. Dzhafarov, Janne V. Kujala and Jan-Åke Larsson, Contextuality in
    Three Types of Quantum-Mechanical Systems, *Foundations of Physics* 45, 2015,
    pp. 762-782.

[^3]: Matthias Kleinmann, Otfried Gühne, José R. Portillo, Jan-Åke Larsson and
    Adán Cabello, Memory Cost of Quantum Contextuality, *New Journal of Physics*
    13, 2011, 113011.

[^4]: Jerome R. Busemeyer and Peter D. Bruza, *Quantum Models of Cognition and
    Decision*, Cambridge University Press, 2012.

[^5]: Dénes Petz, Sufficient Subalgebras and the Relative Entropy of States of a
    von Neumann Algebra, *Communications in Mathematical Physics* 105, 1986, pp.
    123-131.

[^6]: Rolf Landauer, Irreversibility and Heat Generation in the Computing
    Process, *IBM Journal of Research and Development* 5(3), 1961, pp. 183-191.

[^7]: Huzihiro Araki and E. J. Woods, A Classification of Factors, *Publications
    of the Research Institute for Mathematical Sciences* 4, 1968, pp. 51-130.

[^8]: Don N. Page and William K. Wootters, Evolution without evolution: Dynamics
    described by stationary observables, *Physical Review D* 27, 1983, pp.
    2885-2892.

[^9]: Venkatesa Chandrasekaran, Roberto Longo, Geoff Penington and Edward
    Witten, An Algebra of Observables for de Sitter Space, *Journal of High
    Energy Physics* 2023(2), 82, https://arxiv.org/abs/2206.10780.

[^10]: Julian De Vuyst, Stefan Eccles, Philipp A. Höhn and Josh Kirklin, Crossed
    products and quantum reference frames: on the observer-dependence of
    gravitational entropy, *Journal of High Energy Physics* 2025(7), 063,
    https://arxiv.org/abs/2412.15502.

[^11]: Philipp A. Höhn, Alexander R. H. Smith and Maximilian P. E. Lock, The
    Trinity of Relational Quantum Dynamics, *Physical Review D* 104, 2021,
    066001, https://arxiv.org/abs/1912.00033. See also, by the same authors,
    Equivalence of Approaches to Relational Quantum Dynamics in Relativistic
    Settings, *Frontiers in Physics* 9, 2021, https://arxiv.org/abs/2007.00580.

[^12]: Geoff Penington and Edward Witten, Algebras and States in JT Gravity,
    2023, https://arxiv.org/abs/2301.07257.

[^13]: Chang-Han Chen and Geoff Penington, A clock is just a way to tell the
    time: gravitational algebras in cosmological spacetimes, 2024,
    https://arxiv.org/abs/2406.02116.

[^14]: Christopher W. Lynn, Eli J. Cornblath, Lia Papadopoulos, Maxwell A.
    Bertolero and Danielle S. Bassett, Broken detailed balance and entropy
    production in the human brain, *Proceedings of the National Academy of
    Sciences* 118(47), 2021.

[^15]: Flaminia Giacomini, Esteban Castro-Ruiz and Časlav Brukner, Quantum
    mechanics and the covariance of physical laws in quantum reference frames,
    *Nature Communications* 10, 2019, 494.

[^16]: Leslie G. Valiant, Evolvability, *Journal of the ACM* 56(1), 2009,
    article 3.

[^17]: Vitaly Feldman, Evolvability from Learning Algorithms, *Proceedings of the
    40th ACM Symposium on Theory of Computing* (STOC), 2008.

[^18]: Michael Kearns, Efficient Noise-Tolerant Learning from Statistical
    Queries, *Journal of the ACM* 45(6), 1998, pp. 983-1006.

[^19]: Boaz Barak, Benjamin L. Edelman, Surbhi Goel, Sham Kakade, Eran Malach and
    Cyril Zhang, Hidden Progress in Deep Learning: SGD Learns Parities Near the
    Computational Limit, *NeurIPS* 2022; and Emmanuel Abbe and Colin Sandon,
    Provable Limitations of Deep Learning, 2018,
    https://arxiv.org/abs/1812.06369.

[^20]: Roger N. Shepard, Carl I. Hovland and Herbert M. Jenkins, Learning and
    Memorization of Classifications, *Psychological Monographs* 75(13), 1961.

[^21]: Juan Maldacena, The Large N Limit of Superconformal Field Theories and
    Supergravity, *Advances in Theoretical and Mathematical Physics* 2, 1998,
    pp. 231-252.

[^22]: Tom Banks, Willy Fischler, Stephen H. Shenker and Leonard Susskind, M
    Theory as a Matrix Model: A Conjecture, *Physical Review D* 55, 1997, pp.
    5112-5128.

[^23]: Ahmed Almheiri, Xi Dong and Daniel Harlow, Bulk Locality and Quantum Error
    Correction in AdS/CFT, *Journal of High Energy Physics* 2015(4), 163.

[^24]: Steven Carlip, Dimension and Dimensional Reduction in Quantum Gravity,
    *Classical and Quantum Gravity* 34, 2017, 193001.

[^25]: Sam Leutheusser and Hong Liu, Emergent times in holographic duality, 2021,
    https://arxiv.org/abs/2112.12156.

[^26]: Chris Fields, Karl Friston, James F. Glazebrook and Michael Levin, A free
    energy principle for generic quantum systems, 2022,
    https://arxiv.org/abs/2112.15242; and Chris Fields, James F. Glazebrook and
    Antonino Marcianò, The Physical Meaning of the Holographic Principle,
    *Quanta* 11, 2022, pp. 72-96.

[^27]: Pankaj Mehta and David J. Schwab, An exact mapping between the Variational
    Renormalization Group and Deep Learning, 2014,
    https://arxiv.org/abs/1410.3831.

[^28]: Raphael Bousso, The holographic principle, *Reviews of Modern Physics* 74,
    2002, pp. 825-874; and Jacob D. Bekenstein, Black Holes and Entropy,
    *Physical Review D* 7, 1973, pp. 2333-2346.

[^29]: Warrick Roseboom, Zafeirios Fountas, Kyriacos Nikiforou, David Bhowmik,
    Murray Shanahan and Anil K. Seth, Activity in perceptual classification
    networks as a basis for human subjective time perception, *Nature
    Communications* 10, 2019, 267.

[^30]: Fabio Cipriani and Jean-Luc Sauvageot, Derivations as Square Roots of
    Dirichlet Forms, *Journal of Functional Analysis* 201, 2003, pp. 78-120; and
    Eric A. Carlen and Jan Maas, Gradient flow and entropy inequalities for
    quantum Markov semigroups with detailed balance, *Journal of Functional
    Analysis* 273, 2017, pp. 1810-1869.

[^31]: Benjamin F. Toner and Dave Bacon, Communication Cost of Simulating Bell
    Correlations, *Physical Review Letters* 91, 2003, 187904.

[^32]: Masamichi Takesaki, *Theory of Operator Algebras II*, Springer, 2003.

[^33]: Alain Connes and Carlo Rovelli, Von Neumann algebra automorphisms and
    time-thermodynamics relation in generally covariant quantum theories,
    *Classical and Quantum Gravity* 11, 1994, pp. 2899-2917.

[^34]: F. J. Murray and J. von Neumann, On Rings of Operators, *Annals of
    Mathematics* 37(1), 1936, pp. 116-229; Alain Connes, Une classification des
    facteurs de type III, *Annales scientifiques de l'École Normale Supérieure*
    6, 1973, pp. 133-252; and Alain Connes and Masamichi Takesaki, The flow of
    weights on factors of type III, *Tohoku Mathematical Journal* 29, 1977, pp.
    473-575.

[^35]: Tony A. Plate, Holographic reduced representations, *IEEE Transactions on
    Neural Networks* 6(3), 1995, pp. 623-641.

[^36]: Norman Margolus and Lev B. Levitin, The maximum speed of dynamical
    evolution, *Physica D* 120, 1998, pp. 188-195.

[^37]: Seth Lloyd, Ultimate physical limits to computation, *Nature* 406, 2000,
    pp. 1047-1054.

[^38]: Jacob D. Bekenstein, Universal upper bound on the entropy-to-energy ratio
    for bounded systems, *Physical Review D* 23, 1981, pp. 287-298.

[^39]: John Maynard Smith and Eörs Szathmáry, *The Major Transitions in
    Evolution*, Oxford University Press, 1995.

[^40]: Peter Godfrey-Smith, *Other Minds: The Octopus, the Sea, and the Deep
    Origins of Consciousness*, Farrar, Straus and Giroux, 2016.

[^41]: Neil Ashby, Relativity in the Global Positioning System, *Living Reviews
    in Relativity* 6, 2003, 1.

[^42]: Christophe Coupé, Yoon Mi Oh, Dan Dediu and François Pellegrino, Different
    languages, similar encoding efficiency: Comparable information rates across
    the human communicative niche, *Science Advances* 5(9), 2019, eaaw2594.

[^43]: Kristin Koch, Judith McLean, Ronen Segev, Michael A. Freed, Michael J.
    Berry, Vijay Balasubramanian and Peter Sterling, How Much the Eye Tells the
    Brain, *Current Biology* 16(14), 2006, pp. 1428-1434.

[^44]: Howard Barnum, Carlton M. Caves, Christopher A. Fuchs, Richard Jozsa and
    Benjamin Schumacher, Noncommuting Mixed States Cannot Be Broadcast, *Physical
    Review Letters* 76, 1996, pp. 2818-2821; and Howard Barnum, Jonathan Barrett,
    Matthew Leifer and Alexander Wilce, A Generalized No-Broadcasting Theorem,
    *Physical Review Letters* 99, 2007, 240501.

[^45]: Carlo Rovelli, Relational Quantum Mechanics, *International Journal of
    Theoretical Physics* 35, 1996, pp. 1637-1678.

[^46]: Kok-Wei Bong, Aníbal Utreras-Alarcón, Farzad Ghafari, Yeong-Cherng Liang,
    Nora Tischler, Eric G. Cavalcanti, Geoff J. Pryde and Howard M. Wiseman, A
    strong no-go theorem on the Wigner's friend paradox, *Nature Physics* 16,
    2020, pp. 1199-1205.

[^47]: Howard M. Wiseman, Eric G. Cavalcanti and Eleanor G. Rieffel, A
    "thoughtful" Local Friendliness no-go theorem: a prospective experiment with
    new assumptions to suit the abilities of human experimenters, 2022,
    https://arxiv.org/abs/2209.08491.

[^48]: David Deutsch, Quantum theory as a universal physical theory,
    *International Journal of Theoretical Physics* 24, 1985, pp. 1-41.

[^49]: Eugene P. Wigner, Remarks on the mind-body question, in I. J. Good (ed.),
    *The Scientist Speculates*, Heinemann, 1961.

[^50]: John von Neumann, *Mathematical Foundations of Quantum Mechanics*,
    Princeton University Press, 1955 (German original 1932).

[^51]: Wojciech H. Zurek, Decoherence, einselection, and the quantum origins of
    the classical, *Reviews of Modern Physics* 75, 2003, pp. 715-775.

[^52]: Massimiliano Proietti and collaborators, Experimental test of local
    observer independence, *Science Advances* 5(9), 2019, eaaw9832.

[^53]: Yaakov Y. Fein and collaborators, Quantum superposition of molecules
    beyond 25 kDa, *Nature Physics* 15, 2019, pp. 1242-1245.

[^54]: Sandro Donadi and collaborators, Underground test of gravity-related wave
    function collapse, *Nature Physics* 17, 2021, pp. 74-78.

[^55]: Jonathan N. Tinsley and collaborators, Direct detection of a single photon
    by humans, *Nature Communications* 7, 2016, 12172.

[^56]: Building a human-like observer using deep learning in an extended Wigner's
    friend experiment, 2024, https://arxiv.org/abs/2409.04690.
