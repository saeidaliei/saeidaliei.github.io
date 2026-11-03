---
title: "Evolution is a Computer"
date: 2026-11-03
---

Evolution is a distributed, resource-bounded computer. Its state is a
population of heritable representations interacting with a developmental
system and an environment. Variation generates candidate states;
development expresses them as phenotypes; selection changes their
frequencies; inheritance carries the resulting distribution forward.

The computational claim is precise but limited. Evolution does not
calculate an explicitly specified answer, and natural selection is not
an algorithmic agent. Rather, the evolutionary process has the essential
structure of computation: a state, a set of admissible transitions, an
evaluation signal, and a mechanism for retaining the outcomes of those
transitions.

## 1. The computational structure

The relevant state is not an organism in isolation. It is a population
of heritable variants together with the developmental and environmental
conditions under which they are expressed. A schematic transition is

$$
P_t \xrightarrow{\text{variation}} V_t
\xrightarrow{\text{development}} \Phi_t
\xrightarrow{\text{selection}} P_{t+1},
$$

where \$P_t\$ is the inherited population state, \$V_t\$ is the set of
variants generated from it, and \$\Phi_t\$ is the resulting collection
of phenotypes and their interactions with the environment. Selection
changes the frequencies of heritable variants; inheritance carries that
changed distribution into the next generation.

This decomposition identifies four computational roles:

- **Representation:** heritable structures constrain the mechanisms an
  organism can develop.
- **Variation:** mutation and recombination generate candidate changes.
- **Evaluation:** environmental conditions determine the consequences
  of expressed mechanisms.
- **State retention:** differential reproduction changes the inherited
  population from which subsequent variants arise.

The genome is therefore not a complete description of the phenotype,
nor is development a passive decoding operation. Development mediates
between inherited structure and expressed mechanism. Any adequate model
must specify that mapping, at least at the level relevant to the target
behavior.

## 2. Evolvability as constrained learning

Valiant's theory of evolvability gives this computational structure a
formal learning-theoretic interpretation.[^1] The object being acquired
is a function. Let \$X_n\$ be a set of environmental conditions, represented
by \$n\$ variables. An ideal function
\$f : X_n \rightarrow \{-1,+1\}\$ specifies the response that would be
beneficial under each condition. A candidate mechanism is represented
by a hypothesis
\$r : X_n \rightarrow \{-1,+1\}\$.

The environment is represented by a probability distribution \$D_n\$
over \$X_n\$. Valiant defines the performance of \$r\$ relative to \$f\$ as

$$
\mathrm{Perf}_f(r,D_n)
= \sum_{x \in X_n} f(x)r(x)D_n(x).
$$

This is correlation, not a universal measure of biological fitness.
It equals \$1\$ when the functions agree on every condition with nonzero
probability, and \$-1\$ when they are perfectly anticorrelated. It is a
formal proxy for the accumulated benefit of a mechanism across the
conditions it encounters.

Four constraints govern the evolutionary learner:

1. **Target class:** the ideal functions belong to a class \$C\$.
2. **Representation:** candidate mechanisms belong to a class \$R\$.
3. **Variation:** from a current representation \$r\$, only members of a
   prescribed neighborhood \$N(r,\epsilon)\$ can be considered.
4. **Evaluation:** candidate mechanisms are compared using a finite
   sample of experiences drawn from \$D_n\$.

The neighborhood has polynomial size in \$n\$ and \$1/\epsilon\$, and its
members must be generated with non-negligible probability. The sample
size and number of generations are also polynomially bounded. In each
step, the mutator selects a candidate whose empirical performance
exceeds that of the current representation by a specified tolerance.
If no such beneficial candidate is available, it may select a neutral
candidate whose performance is not worse by more than that tolerance.

The essential restriction is informational: the update depends on the
aggregate performance of a candidate, not on the descriptions of the
individual examples that produced that performance. The evolutionary
process does not inspect an experience and infer which particular input
feature caused success or failure. It receives a coarse signal about
how well the mechanism performed over the sampled conditions.

A class \$C\$ is evolvable, in this framework, when there are suitable
representations, mutation neighborhoods, sample bounds, and an update
rule such that, for every target \$f \in C\$ and every initial
representation \$r_0\$, the process reaches performance greater than
\$1-\epsilon\$ within polynomially many generations, with probability
greater than \$1-\epsilon\$. Evolvability is thus a property not merely
of a target function, but of the relation among the target class, its
representation, the allowed variations, the environmental distribution,
and the available resources.

## 3. Evolvability is stricter than learnability

The distinction between learning and evolvability is substantive.
A general learner may use the content of individual labeled examples
when choosing its next hypothesis. Valiant's evolutionary learner is
more restricted: it can use only aggregate performance estimates and
must move through a polynomially bounded neighborhood at each step.

Valiant shows that evolvability implies learnability, including
learnability in the statistical-query framework. The converse does not
hold. A target may be efficiently learnable while remaining inaccessible
to the restricted evolutionary process.

Parity provides the central example. For binary inputs, a parity
function returns the parity of a selected subset of variables:

$$
f_S(x_1,\ldots,x_n)
= \bigoplus_{i \in S} x_i.
$$

Parity functions are computationally simple and can be efficiently
learned from labeled examples. Yet under the uniform distribution,
the class of parity functions is not evolvable in Valiant's model, for
any representation. The obstruction follows from the fact that parity
is not efficiently learnable through statistical queries. In contrast,
monotone conjunctions and disjunctions are evolvable under the uniform
distribution with their natural representations.[^1]

The result is a separation between what can be computed, what can be
learned with informative access to examples, and what can be acquired
through restricted selection. It is not a claim that biological
organisms cannot contain parity-like circuits. It is a theorem about
what a specified evolutionary process can acquire under specified
information and resource constraints.

## 4. Evolvable target pursuit

A single evolutionary stage has a fixed target function, representation
class, mutation neighborhood, and environmental distribution. Biological
evolution is not plausibly limited to one such stage. The target of
selection can change, and the products of earlier evolution can alter
the conditions under which later mechanisms become accessible.

Valiant proposes *evolvable target pursuit* as a model of this larger
process. Evolution consists of successive stages, each pursuing a target
that is evolvable given the environment and the mechanisms produced by
previous stages. The outcome of one stage supplies the starting
representation for the next. The process need not make a direct jump
to a complex target; earlier stages can make later targets evolvable.

This is not equivalent to saying that evolution follows a plan or
optimizes a fixed global objective. Each stage is defined relative to
its own target and environmental distribution. The sequence of targets
is not specified in advance. Valiant's proposal is that the interaction
between prior evolutionary outcomes and changing opportunities can
produce a succession of locally accessible targets.[^1]

The framework also exposes a limitation of the formal model. Within a
stage, the representation class and mutation neighborhood are specified
in advance. In biological evolution, the developmental architecture
and the structure of variation can themselves change. Earlier evolution
can therefore alter not only which candidate performs better, but also
which candidates can be generated and expressed at all. A full account
of this process requires models in which the effective representation
and transition structure are themselves subject to evolution.

## 5. Scope of the computational claim

The computational description does not imply that evolution has an
explicit objective function, a global evaluator, or a representation of
its future products. Fitness is local to an environment and depends on
the distribution of conditions encountered. A trait can be beneficial
under one distribution and harmful under another. Reproductive success
is not equivalent to progress toward intelligence, complexity, welfare,
or any other external standard.

Nor does evolution necessarily increase complexity. Selection can
preserve, elaborate, simplify, or eliminate mechanisms. The direction
of change depends on the current population and its environment; there
is no general destination encoded in the process.

The model is therefore not a claim that organisms are digital computers
or that genomes are conventional programs. It is a claim about the
computational organization of evolutionary change. Heritable states
are transformed through constrained variation; expressed mechanisms
are evaluated under environmental conditions; and reproductive
outcomes determine which states persist. The process is computational
without being deliberative.

## 6. Consequences for cognition

The distinction among computability, learnability, and evolvability is
particularly important for cognitive mechanisms. A capacity may be
computable in principle, and an individual learner may be able to acquire
it from sufficiently informative data, without the capacity being
reachable by a particular evolutionary process. The relevant question
is not whether a cognitive function is useful once present, but whether
there is an accessible sequence of representations and variations by
which selection could produce it.

This suggests analyzing cognitive capacities separately rather than
treating intelligence or consciousness as a single evolutionary target.
For a proposed capacity, one must specify the function to be acquired,
the representation available to the organism, the environmental
distribution, the permitted variations, and the information supplied
by selection. Only then does the question of evolvability become
well-defined.[^2]

## Conclusion

Evolution can be understood as computation because it transforms
heritable states through constrained transitions, evaluates their
expressed consequences, and retains the outcomes across generations.
Valiant's framework makes one part of this claim mathematically
precise: it characterizes the function classes that can be acquired
when variation is local, resources are polynomially bounded, and
selection has access only to aggregate performance.

The central explanatory problem is therefore reachability. A mechanism's
existence, computability, or usefulness does not establish that it is
evolvable. The relevant unit of explanation is the sequence of
representations and transitions through which it can be reached.

## References

[^1]: Leslie G. Valiant, "Evolvability," *Journal of the ACM*, 56(1),
    Article 3, 2009. https://doi.org/10.1145/1462153.1462156

[^2]: Saeid Aliei, "Consciousness, Computability, Decidability, and
    Evolvability: A Weaker Problem Worth Attacking," 2026.
    /posts/consciousness-computability-decidability-evolvability/
