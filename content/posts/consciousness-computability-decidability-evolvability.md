---
title: "Consciousness, Computability, Decidability, and Evolvability: A Weaker Problem Worth Attacking"
date: 2026-08-15
author: Saeid Aliei
---
## 1. The starting intuition, and why it's too strong as stated

Gödel's incompleteness theorems show that any sufficiently expressive,
consistent formal system \$F\$ contains a true statement \$G\$ it cannot prove
from its own axioms — informally,

$$
G \leftrightarrow \neg \mathrm{Provable}_F(G).
$$

It's tempting to reach for an analogy: what if consciousness is a real
physical phenomenon whose complete truth can't be derived from whatever
formal or mathematical framework we use to describe physical reality?

It's a good question to *have*, but a bad one to *answer* directly, for a
specific reason: Gödel's theorem is a statement about a particular formal
system, not about formal systems in general. A statement undecidable in
system \$F_1\$ can become provable once you move to a richer system \$F_2\$:

$$
F_1 \rightarrow F_2 \rightarrow F_3 \rightarrow \cdots
$$

So "consciousness is true but mathematics can never touch it, because of
Gödel" doesn't actually follow from Gödel — it's a category error dressed up
as a deep result. The more useful question is narrower: does consciousness
have specific computational, logical, or evolutionary limitations that can
be formalized and tested, rather than gestured at?

That reframing points toward a strategy: don't attack "is consciousness
computable" head-on. Attack progressively weaker, better-defined questions
instead, and see how far that gets.

## 2. Three different kinds of question, often conflated

Before building any hierarchy, it's worth separating three questions that get
run together constantly in casual writing about this topic.

**Computability** asks whether there is *any* algorithm that calculates a
function \$f(x)\$ at all — not necessarily one that halts on every input.

**Decidability** is the stricter, specifically yes/no version: is there an
algorithm \$A(x)\$ that, for *every* input, halts and returns the correct
answer? The halting problem is the canonical case where this fails — given a
program \$P\$ and input \$x\$,

$$
H(P,x) =
\begin{cases}
1 & \text{if } P(x) \text{ eventually halts} \\
0 & \text{otherwise,}
\end{cases}
$$

and no total, always-halting \$H\$ computing this exists for arbitrary \$P, x\$.
Note the asymmetry: a program that simulates \$P\$ on \$x\$ and outputs \$1\$ the
moment it halts gets the "yes" case right — the problem is *semi-decidable*
— but nothing catches the "no" case, since a non-halting \$P\$ just runs
forever. That gap is precisely why "undecidable," not "uncomputable," is the
accurate word for the halting problem.

The distinction matters for consciousness the moment you try to write it
down as a function. Define

$$
C(S) =
\begin{cases}
1 & \text{if physical system } S \text{ is conscious} \\
0 & \text{otherwise.}
\end{cases}
$$

The question "is there a universal algorithm that takes an arbitrary complete
description of \$S\$ and computes \$C(S)\$" is a **decidability** question about
the map \$S \rightarrow C(S)\$ — not automatically a computability question
about consciousness itself. If that recognition problem turned out
undecidable, it would not follow that consciousness was non-computable: a
conscious system could still be perfectly constructible or simulable while
the general recognition problem \$S \rightarrow C(S)\$ remained undecidable.
Recognizing a property from an arbitrary description, and instantiating that
property, are different problems.

**Learnability / evolvability** asks something different again: can a
*specific, resource-bounded process* — a bounded learning algorithm, or
evolution itself — actually discover the answer, even in cases where an
unconstrained, hypothetical algorithm could? These form a rough hierarchy,

$$
\boxed{\text{Computable} \;\supseteq\; \text{Decidable} \;\supseteq\; \text{Learnable} \;\supseteq\; \text{Evolvable}}
$$

but the containments matter less than the fact that these are genuinely
different *questions*, each about a different resource-bounded process
attempting the same target. A property can be perfectly computable and
decidable while remaining completely inaccessible to a specific, constrained
search process like Darwinian evolution. That gap — between "this could in
principle be figured out" and "this specific, history-bound process could
ever find it" — is the most productive place to look if consciousness itself
is off the table as a direct target.

## 3. Where the parity example actually helps, and where it doesn't

Parity — the XOR of a set of bits,

$$
P(x_1, \dots, x_n) = x_1 \oplus x_2 \oplus \cdots \oplus x_n,
$$

— is perfectly computable and decidable. It is *not* an example of anything
undecidable. Its real relevance lies elsewhere: in Leslie Valiant's formal
theory of evolvability, parity is a canonical function that is easy to learn
in general (it is PAC-learnable) but *not* evolvable, because it defeats
statistical-query-style learning — every individual bit, on its own, carries
zero information about the output, so a process that only receives an
aggregate, noise-tolerant performance signal can never get a foothold on it.

That's a different failure mode from the philosophical Gödel worry entirely,
and it generalizes past parity. Suppose the true state of the world is
\$x = (x_1, \dots, x_n)\$, but an organism doesn't observe \$x\$ directly — it
only receives \$y = f(x)\$ for some observation function \$f\$. If two states
satisfy

$$
x_a \neq x_b \qquad\text{but}\qquad f(x_a) = f(x_b),
$$

then the organism cannot distinguish them from the information available to
it. If the target property differs between them,

$$
C(x_a) \neq C(x_b),
$$

then no learner receiving only \$f(x)\$ can reliably determine \$C\$ — its
probability of getting it right cannot exceed chance. This is *not*
undecidability. It's an **information-theoretic limitation** imposed by the
observation channel itself, and it's worth keeping three distinct
obstructions apart rather than lumping them together as "hard":

- a **computational barrier** — the problem is intrinsically difficult to compute;
- an **information barrier** — the relevant information never reaches the process at all;
- an **evolvability barrier** — the target may be computable and even learnable in principle, yet inaccessible to a specific, constrained Darwinian process.

## 4. Evolution as a constrained computer

Darwinian evolution can be described, without much metaphor, as a loop:

$$
\text{variation} \rightarrow \text{interaction} \rightarrow \text{selection} \rightarrow \text{inheritance} \rightarrow \text{variation.}
$$

It has no access to the full causal structure of the world; it receives
extremely restricted feedback, compressed almost entirely into survival and
reproduction. That makes it structurally similar to a particular kind of
learning algorithm — one that never inspects the target function directly,
and only ever sees an aggregate, noisy performance signal:

$$
\text{computable} \;\neq\; \text{efficiently learnable} \;\neq\; \text{evolvable.}
$$

Leslie Valiant formalized this in his 2009 paper *Evolvability* (Valiant won
the Turing Award the following year, 2010). He models evolution as a
restricted form of PAC (probably approximately correct) learning: a
population of candidate representations \$r \in R\$ is updated only according
to its aggregate performance,

$$
\mathrm{Perf}_f(r, D) = \mathbb{E}_{x \sim D}\big[\, \mathrm{agreement}(r(x), f(x)) \,\big]
$$

against a target function \$f\$ under distribution \$D\$ — never by direct
inspection of individual labeled examples, and never by anything more
expressive than a polynomial-size sample of *performance values*, not raw
data. Valiant proves evolvability is strictly weaker than both ordinary PAC
learnability and the related Statistical Query model: monotone conjunctions
and disjunctions are evolvable under this model; parity is not, despite being
straightforwardly PAC-learnable by an algorithm with more direct access to
individual examples. This gives the useful hierarchy of questions

$$
\boxed{\text{Computability} \rightarrow \text{Decidability} \rightarrow \text{Learnability} \rightarrow \text{Evolvability}}
$$

not as nested mathematical sets so much as different questions about the same
target under different constraints. Valiant states his own motivation
explicitly — he intends the theory as a unifying framework for evolution
*and* cognition, because separating what an organism's genes already encode
from what it separately learns during its own lifetime has always been hard
to do cleanly.

## 5. Attacking the weaker rungs instead

Proving or disproving "consciousness is computable" is not currently a
well-formed question, because there is no complete, agreed formal definition
of consciousness to write down as \$C : S \rightarrow \{0,1\}\$ in the first
place. Decidability and evolvability questions become well-formed the moment
an *operational proxy* is fixed instead — something theory-neutral,
checkable, and plausibly a candidate ingredient of whatever "consciousness"
refers to, without claiming to *be* consciousness. Candidates worth
considering, roughly in increasing order of ambition:

- a **persistent self-model** \$M_{\text{self}}(t)\$ that distinguishes
  consequences the system caused from consequences that happened to it,
- a **counterfactual self-model**, \$M(W \mid \mathrm{do}(a))\$, modeling what
  would have happened under an alternative action the system itself could
  have taken,
- **metacognition**, \$M_{\text{self}}(M_{\text{self}})\$ — modeling
  properties of one's own cognitive process, including calibrated confidence
  in one's own correctness,
- **temporal self-continuity**, a coherent link between \$S_t\$ and
  \$S_{t+\Delta}\$ as states of the same persisting entity,
- a **recursive self-model** — a model of the self-model, and so on, with no
  principled stopping point specified in advance.

None of these should be called consciousness. They are operational targets a
formal question can actually be asked about, giving three progressively
weaker questions to attack instead of the strongest one:

$$
C \in \mathrm{Decidable}? \qquad\qquad C \in \mathrm{Evolvable}(E)? \qquad\qquad C \in \mathrm{Evolvable}_{\mathrm{poly}}(E)?
$$

This ladder avoids beginning with the strongest metaphysical claim.

## 6. What a decidability result would and wouldn't mean

Suppose a proxy \$C\$ is fixed, and it turns out there is no algorithm that,
given an arbitrary complete description of a system \$S\$, always halts and
correctly determines whether \$C(S)\$ holds. Two things follow, and two things
emphatically do not.

**What follows:** something about the *logical structure* of \$C\$ itself.
Undecidability results are almost always rooted in self-reference or
unbounded quantification, so a genuine undecidability proof for something
like a recursive self-model would likely trace back to the same
diagonalization machinery behind the halting problem — a real structural
finding about recursive self-reference, independent of biology.

**What doesn't follow:** that \$C\$ is rare, mysterious, or non-physical.
Undecidability is a worst-case, arbitrary-input statement; it says nothing
about whether \$C\$ can be recognized for the *actual* systems anyone cares
about, where enormous structural priors are available. It also says nothing
about whether \$C\$ can be *instantiated* — recognizing a property from the
outside, and constructing a system that has it, are different problems.
Conflating "no general recognition algorithm exists" with "the property
cannot exist" is probably the most common error in casual Gödel-and-
consciousness writing.

## 7. What an evolvability result would and wouldn't mean

Now fix a formal evolutionary process \$E\$ — bounded mutation, finite
population, local selection, a specific restricted information channel — and
suppose

$$
C \notin \mathrm{Evolvable}(E).
$$

This is a more interesting result than the decidability one, for a specific
reason: it's checkable against biology. If real evolution demonstrably
produced something resembling \$C\$ in real brains, and \$E\$ is a faithful model
of that process, a proof that \$C\$ is not evolvable under \$E\$ isn't evidence
that \$C\$ is mysterious — it's evidence that \$E\$ is the wrong model, or that
biological evolution used a broader toolkit than plain selection on a fixed
architecture: developmental plasticity, learning-within-a-lifetime
bootstrapping the search, group or sexual selection with different
information channels, exaptation from a differently-selected trait. A weaker,
still meaningful version of the same claim bounds efficiency rather than
reachability:

$$
C \notin \mathrm{Evolvable}_{\mathrm{poly}}(E)
$$

— the property might eventually appear given unbounded time, but cannot be
reached with polynomially bounded resources under the model. A failure to
observe something after billions of simulated generations is not itself a
theorem of either kind; a real theorem requires precise assumptions about
representation, mutation, population, selection, fitness, information,
development, and resource bounds, stated in advance.

A formal negative result that can be checked against a known positive case —
biology already produced brains that do something like \$C\$ — is a genuinely
rare thing to have in this area. What doesn't follow, in either direction,
is that \$C\$ requires anything extra-physical. The mundane resolution — the
model was incomplete, or the proxy was the wrong one — should be preferred by
default over anything more dramatic.

## 8. What already exists

Different pieces of this already exist in the literature, scattered across
communities that don't cite each other much.

On the computability/decidability side: Scott Aaronson's well-known critique
of Integrated Information Theory (IIT) works in roughly the territory he
calls the "Pretty Hard Problem" — predicting *which* systems are conscious,
as opposed to explaining *why* any physical process gives rise to
consciousness at all — mostly via complexity and counterexample arguments
rather than a formal undecidability proof. Maguire, Moser, Maguire and
Griffith's *Is Consciousness Computable? Quantifying Integrated Information
Using Algorithmic Information Theory* engages IIT's computability more
directly through algorithmic information theory. Jochen Szangolies has built
an explicit undecidability argument around a self-referential process,
arguing that deciding whether an action achieves a goal runs into genuinely
undecidable propositions, and using that to argue mental states need direct,
non-theoretical access to their own properties. A 2023 preprint, *A
Formalizable Proof of the No-Supervenience Theorem*, builds an explicit
diagonal argument against physicalist theories of consciousness as a class.
The much older Lucas–Penrose argument — that Gödel's theorem implies minds
cannot be formal systems — is the version most people have actually heard of,
and the one most logicians consider flawed, largely because it conflates a
system's inability to prove its own consistency with an outside observer's
ability to see that its Gödel sentence is true.

On the evolvability side: Valiant's own framing, quoted above, is explicit
about bridging evolutionary theory and cognition. The closest real
experimental precedent is Albantakis, Hintze, Findlay, Koch, Adami and
Tononi's 2014 paper, *Evolution of Integrated Causal Structures in Animats
Exposed to Environments of Increasing Complexity*: simple artificial agents
evolved via genetic algorithms in environments of controlled, increasing
complexity, tracking IIT's integration measure \$\Phi\$ as a function of
selective pressure. It isn't phrased in Valiant's formal language — no
PAC-style bound, no impossibility theorem — but methodologically it's the
same move: fix a formalized consciousness-proxy, vary the environment, watch
whether and how much it becomes accessible to a Darwinian process. Outside
that paper, Valiant's own evolvability tradition has stayed almost entirely
inside Boolean- and linear-function territory; nobody in that specific
formal lineage has pushed the target toward anything cognitive.

## 9. A note on internal tooling

None of this needs to stay purely theoretical to be useful. A controllable
synthetic world — [Terrarium](https://github.com/vispraxai/terrarium), is in development. Written in Rust, with explicit, hidden ground
truth about simulated agents' latent psychological state — built for an unrelated, more immediate purpose (developmental
evaluation of a persistent cognitive architecture), but structurally
well-suited to running exactly this kind of evolvability experiment: fix a
proxy, vary the information channel and structural plasticity available to a
population of agents, and measure whether and under what conditions the
proxy becomes accessible.

The fit isn't accidental. The same design decision that makes such a world
useful for evaluating an AI architecture against a simulated relationship —
keeping a hidden, ground-truth latent state that the agent under test never
sees directly, and scoring it against that ground truth rather than against
self-report — is exactly the instrument an evolvability experiment on a
consciousness-proxy needs: a way to know, from the outside, whether a
population of agents actually built something like a self-model, rather than
merely behaving as though they had one. A companion piece works through
Terrarium's formal experimental design — the information channel, structural
plasticity, and what a real non-evolvability theorem would need to state —
in more depth.

## 10. A different picture entirely: Panpsychism

Everything above assumes consciousness is the kind of thing that gets built —
by evolution, by development, eventually perhaps by engineering — and asks
what's computationally or informationally required to build it. Panpsychism
denies the premise. In its strongest form, it holds that some form of
experience is a fundamental feature of physical reality itself, on par with
mass or charge, rather than something that emerges only above some threshold
of biological or computational complexity. On this view, asking "is
consciousness evolvable" is close to a category error, in the same way "is
mass evolvable" would be — mass isn't a capability an organism acquires
through selection; it's a property fundamental particles simply have, and
composite systems inherit.

Philip Goff and Galen Strawson are among the more prominent contemporary
defenders of this position, motivated less by mysticism than by a genuine
dissatisfaction with the alternatives: physicalism has never produced a
non-question-begging account of how experience arises from non-experiential
matter (the Hard Problem, again), and substance dualism has its own
well-known problems explaining how a non-physical substance could causally
interact with a physical one at all. Panpsychism's proposal is that matter
has some primitive form of experience "all the way down," and complex
experience — the human kind — is a matter of how that primitive experience
combines and organizes at higher levels of physical structure (the
"combination problem" is the open technical difficulty here: nobody has a
working account of how countless simple experiential facts combine into one
unified experience like a human's).

If something like this is right, the entire evolvability framing above
answers a real but narrower question than it might appear to: not "how does
consciousness arise," but "under what conditions does a *sufficiently
organized, self-referential* form of an already-fundamental property become
functionally expressed, reportable, and behaviorally consequential" —
evolution's contribution would be to organize matter into a shape where
whatever is already there becomes usable, not to manufacture the
experiential ingredient from nothing. That's a real and non-trivial
distinction, and it's one the formal machinery above is agnostic to: nothing
about decidability or evolvability arguments depends on picking a side here.

## 11. Wavefunction collapse and consciousness

A different, older, and more specifically physical version of the same
instinct — that consciousness might be doing real causal work in the
universe rather than merely observing it — comes from quantum mechanics.

Standard quantum mechanics has the "measurement problem": a system evolves
smoothly and deterministically under the Schrödinger equation into a
superposition,

$$
|\psi\rangle = \sum_i c_i |i\rangle,
$$

right up until a measurement occurs, at which point it appears to
discontinuously "collapse" into a single definite outcome \$|i\rangle\$, with
probability \$|c_i|^2\$. Nothing in the deterministic part of the theory says
*what counts as a measurement*, or *why* collapse happens at all rather than
the superposition simply continuing to spread — this is the actual open
problem, not a settled detail.

Von Neumann's original analysis pushed the question as far as it would go:
if the measuring device is itself a physical system, it too should be
describable by the Schrödinger equation, entangling with the system it
measures rather than collapsing it — and the same argument applies to
whatever measures the measuring device, and so on. Von Neumann noted this
regress has to terminate somewhere for anyone to ever observe a definite
outcome, and speculated the chain terminates specifically at a conscious
observer — not because consciousness is caught in the act of collapsing
anything, in his account, but because it's the one link in the chain that
isn't itself describable as just another physical system to be measured.
Eugene Wigner later pushed this into the well-known "Wigner's friend"
thought experiment and, for a period, took the stronger position that
consciousness is what *causes* collapse directly — a position he reportedly
moved away from later in his life.

Roger Penrose and Stuart Hameroff's Orchestrated Objective Reduction
(Orch-OR) is the most developed modern attempt to connect this to
neuroscience directly, rather than leaving it as an interpretational stance
about measurement. Their proposal is that collapse is not caused by
observation or consciousness at all, but is an *objective*,
observer-independent physical process, triggered once a quantum
superposition's gravitational self-energy crosses a threshold — roughly,

$$
t \approx \frac{\hbar}{E_G},
$$

where \$E_G\$ is the gravitational self-energy of the mass difference between
the superposed states, and \$t\$ is the time until spontaneous collapse. Their
further, much more contested claim is that this process occurs inside
microtubules within neurons, orchestrated by neuronal biochemistry, and that
this specific objective-reduction event *is*, or directly gives rise to, a
moment of conscious experience.

This proposal has been criticized heavily and specifically on the grounds
that the warm, wet, noisy environment of a living brain should destroy
quantum coherence in microtubules far faster than any proposed collapse
timescale — decoherence calculations put the
relevant coherence times many orders of magnitude below what Orch-OR would
need. It remains a minority position even among physicists sympathetic to
the idea that consciousness and quantum mechanics might be related at all.

What's worth taking from this, independent of whether Orch-OR specifically
survives scrutiny, is that it's a structurally different kind of proposal
from panpsychism or the evolvability framing above: it's a claim about a
specific physical mechanism, with a specific timescale, that is at least in
principle experimentally distinguishable from ordinary decoherence — which is
exactly why it has been criticized on hard physical grounds rather than
purely philosophical ones. That's a genuinely different epistemic situation
from most of what else appears in this piece, where the proxies discussed
earlier are deliberately chosen to be checkable *precisely because* nobody
has an analogous physical mechanism to test.

## 12. Where this leaves things

The last two sections are not compatible, in any simple way, with the
evolvability framing that occupies most of this piece — and that's fine to
leave sitting there unresolved. If some form of experience is fundamental to
matter itself, or if it's tied to a specific, as-yet-undiscovered physical
collapse mechanism, then the whole computability/decidability/evolvability
ladder built out of Valiant's framework is answering a real question about
*organization and function*, while quietly assuming an answer to a deeper
question — whether experience needs to be built at all — that it has no way
of actually settling. That's not a flaw specific to this framing; it's true
of essentially every functionalist or computational theory of mind currently
on the table. Worth remembering as a standing caveat, not a reason to stop
asking the narrower, checkable version of the question.
