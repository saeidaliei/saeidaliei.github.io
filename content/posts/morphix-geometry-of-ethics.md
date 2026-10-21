---
title: "Morphix: Can Ethics Have a Geometry?"
date: 2026-10-21
author: Saeid
---

There is a simple question that sounds too vague to be mathematical: when the
same moral judgment is expressed in many different ways, what stays the same?

One culture phrases it one way. A philosophical tradition phrases it another. A
vignette, a legal clause, and a proverb can carry the same verdict in different
clothes. Philosophy has mostly handled this with more words. This essay is about
what happens when you try to handle it with structure instead.

Not because ethics reduces to mathematics. 
Not because a model that finds a stable pattern has found what is *right*.
And not because borrowed formalism counts as insight by itself.

The claim is more basic:

> **A concept is what survives a change of domain. A value is the parameter that
> is allowed to vary.**

This is the idea behind Morphix, a research project inside
[Visprax](https://saeidaliei.github.io/posts/visprax-unsafeai-announcement/). It
points the representation-learning machinery we have been building,
transformational representation learning (TRL), whose core move is to learn
representations that stay invariant under transformations across domains, at
philosophical concepts instead of its original targets.

Before anything else, the status. Morphix is an early research prototype.
Everything reported below was run on synthetic data with known ground truth. Two
real datasets have been identified. One of the central hypotheses failed. 
That failure is, I think, the most instructive result so far, so it gets 
its own section rather than a footnote.

## Where this started

The obvious first attempts at giving ethics mathematical structure both stall,
and they stall in instructive places.

The first is game theory. Norms can be modeled as equilibria of repeated
interaction: fairness, promise-keeping, and reciprocity survive because
deviating from them does not pay once everyone else is following them[^1]. This
has real machinery behind it. The trouble is the same theorem that makes it
work. The folk theorem says that in a repeated game almost any outcome can be
sustained as an equilibrium if players are patient enough, and that includes
terrible ones. A stable caste system is an equilibrium. A stable protection
racket is an equilibrium. Nothing in the apparatus says which equilibrium a
society lands in, or which one it should. That job falls to equilibrium
selection, and that is exactly where the contestable philosophical judgment
hides. The mathematics does not retire the disagreement. It relocates it.

The second is geometry. Concepts as regions of a space with real dimensions is a
serious program, and it works nicely for colour, where "red" is a literal
region[^2]. For justice, harm, or autonomy you have to say what the dimensions
are, and what nearness licenses you to infer. A word-embedding space gives you a
distance for free, but that distance tracks co-occurrence in text, not logical
or normative proximity. Two positions can use nearly the same words and be
incompatible. Unless you can say what the open sets *are*, "a topological space
of ideas" is a metaphor wearing mathematics' clothes.

What both attempts were missing is an invariant. A space is empty until you say
what is held fixed. This is an old lesson. Klein's Erlangen program reorganized
geometry around it: a geometry is the study of whatever stays unchanged under a
chosen group of transformations, and different geometries are just different
choices of group[^3].

So choose the group first. Let \$G\$ be the transformations that carry one
domain's expression of a judgment to another's: a different culture's framing, a
different tradition's vocabulary, a different surface style. A concept is then a
representation \$f\$ with

$$
f(g\cdot x)=f(x)\qquad\text{for all } g\in G
$$

In practice the strict version is too much to ask, so we use a soft one: a
representation from which an adversary, trained to guess the domain, cannot do
better than chance, while the judgment itself stays predictable[^4].

That is a much smaller claim than "the true nature of fairness." It is closer
to: *the part of fairness-talk that is not an artifact of who is talking.* A
smaller claim has the advantage that it can be tested.

## The first experiment: does the mechanism work at all?

The simplest test has known ground truth. Generate a judgment label shared
across four domains, and let each domain add its own nuisance signal to the
observed features. Train an encoder to predict the judgment while a domain
adversary tries to recover which domain each example came from, with the encoder
rewarded for defeating it.

On the raw input, a classifier recovers the domain 80% of the time (chance is
25%). On the learned representation it recovers the domain 20% of the time,
while the judgment is predicted with accuracy 1.00. With no adversarial
pressure, domain recovery sits at about 50%, so the adversary is doing real
work. The result also survives a nonlinear probe: a nearest-neighbour classifier
recovers the domain 23% of the time from the trained encoder and 46% from an
encoder trained without the adversary.

One success at one setting proves little, so there is a second check with a
different failure mode. Classical canonical correlation analysis is a 1936
technique with no neural network and nothing adversarial in it[^5]. It can find
the shared direction across two domains by pairing examples that carry the same
judgment. If two unrelated methods land on the same signal, that is evidence it
is not an artifact of either. They agree with a correlation of 0.986.

Then the part I find most reassuring. I swept how strong the shared signal is
relative to the domain-specific noise. Agreement stays at 0.97 or above whenever
the signal is at least half as strong as the nuisance. When the signal is one
eighth as strong, agreement falls to 0.26. A metric that collapses when the
problem has no real shared structure to find is a metric that is measuring
something.

Hold on to the phrase "with known ground truth." There is a catch in how that
world was built, and section 5 is where it comes due.

## A space of ethical positions

The founding question was whether philosophical positions can form a space. Here
is one real instance, built from standard pieces.

Take a society with \$n\$ positions and an allocation of utilities
\$x=(x_1,\dots,x_n)\$ across them. Call an evaluation rule *impartial* if it
does not depend on which position carries which label, which is to say it is
invariant under permuting the positions. That is the veil of ignorance stated as
a symmetry.

Two serious theories satisfy it exactly. Harsanyi argued that an impartial
observer maximizing expected utility behind the veil ranks allocations by their
average[^6]. Rawls argued that behind a thick veil probabilities are
unavailable, and the rational response is to rank allocations by their worst-off
position[^7]. Both rules are invariant under relabeling. Both are equally
licensed by the veil. And they disagree: an allocation with a high average and
one badly-off position is preferred by the first and rejected by the second.

So the symmetry narrows the field enormously, but it does not pick a winner. The
tie is broken by something that is not group theory at all: whether you
aggregate over the position you might occupy by expected value or by worst case.

Here is the part that surprised me. These are not two unrelated theories. They
are two points on a single continuous line. For positive utilities, define

$$
M_p(x)=\Big(\tfrac{1}{n}\sum_{i=1}^{n}x_i^{\,p}\Big)^{1/p}
$$

with the limiting cases \$M_0\$ the geometric mean, \$M_{-\infty}=\min_i x_i\$
and \$M_{+\infty}=\max_i x_i\$. Every \$M_p\$ is permutation invariant, so the
whole family is impartial. And the power mean inequality orders it:

$$
p_1 < p_2\;\Longrightarrow\;M_{p_1}(x)\le M_{p_2}(x)
$$ 

Three named positions sit on this line:

- \$p=-\infty\$ is Rawls's maximin.
- \$p=0\$ is the geometric mean, the quantity whose maximization defines Nash's
  bargaining solution, which maximizes the product of utilities relative to a
  disagreement point[^8].
- \$p=1\$ is Harsanyi's average.

This is also, under another name, the welfare function economists use to measure
inequality aversion: Atkinson's family, with \$p=1-\varepsilon\$ for inequality
aversion \$\varepsilon\$[^9]. Nothing here is a new theorem. What is new is
having the pieces in one place, as an object that can be computed with.

And it can. Take two allocations, \$(100,100,100,1)\$ and \$(40,40,40,25)\$. The
utilitarian prefers the first, with mean 75.25 against 36.25. The maximin
theorist prefers the second, with a floor of 25 against 1. The preference flips
at exactly one value of the exponent, \$p^*\approx 0.063\$, which lands almost
on the Nash point. "Rawls and Harsanyi disagree" becomes a number: a precise
place on a line where one stance gives way to the other.

Now the limit, stated plainly so it is not oversold. This line is a map of one
neighbourhood: symmetric, utility-aggregating rules. A deontological theory with
hard side-constraints is not a point on it. It is not shown to be near anything
here, because it is not the kind of object \$M_p\$ describes. This is a rigorous
instance of "positions form a space," not a topology of all of ethics.

## Inferring values

If \$p\$ is where positions are allowed to differ, the natural inverse problem
is to recover it from behaviour. Suppose an agent chooses between allocations
\$A\$ and \$B\$ noisily:

$$
P(\text{choose } A)=\sigma\Big(\beta\,\big[\log M_p(A)-\log M_p(B)\big]\Big)
$$

where \$\beta\$ is a noise parameter. Given choices, \$p\$ can be estimated by
maximum likelihood, with a likelihood-ratio interval around it.

The interesting finding is about which questions are worth asking. A pair where
one allocation dominates the other, in the sense that its sorted utilities are
larger everywhere, is a bad question: every impartial rule gives the same
verdict, so the answer carries no information about \$p\$. The most informative
pairs are those whose crossover sits near the current estimate. The Fisher
information of one query makes this exact:

$$
I(p)=P(1-P)\,\big(\beta\,\partial_p\Delta\big)^2,
\qquad \Delta=\log M_p(A)-\log M_p(B)
$$

Choosing queries to maximize it, rather than at random, helped substantially.
For an inequality-averse agent with \$p=-2\$, the error after 80 random queries
was 2.47. With adaptive queries it was 0.36. For an agent with \$p=1\$ the
figures were 0.33 and 0.15. Across budgets and agents the adaptive design was
between roughly two and seven times more accurate, and the gap narrows as the
budget grows. The 95% intervals covered the truth between 93% and 100% of the
time.

Two honest limits showed up. Strongly inequality-averse agents are intrinsically
hard to pin down, because \$M_p\$ saturates toward the minimum as \$p\$ falls,
and very negative exponents become behaviourally similar. And people need not be
power-mean aggregators at all. A diagnostic that measures how much worse the
best power-mean fit is than the true generating process reads about zero for a
true power-mean agent and 0.15 nats per choice for a sufficientarian, an agent
who simply counts how many positions clear a threshold. So the model family can
tell when it is the wrong shape, at least in that case.

A fitted \$p\$ is a compact description of revealed choices under a stated
model. It is not a discovery of what anyone ought to value. I will come back to
that.

## Where it failed

The two halves suggested a division of labour. Facts, meaning how well off each
position actually is, should be domain-invariant, so they should be learned as
an invariant representation. Values, meaning \$p\$, should be fitted on top of
that, separately per domain. The testable claim: an invariant factual encoder
should make value inference transfer better to a domain it has never seen.

I tested it leave-one-domain-out. Train a decoder of factual quantities on three
domains, then on the fourth, unseen domain, fit its value parameter from
observed choices using the decoded facts, and compare the error against an
oracle that sees the true facts.

The hypothesis was not supported. The invariant encoder was worse than the same
architecture with no adversary: parameter error 0.38 against 0.24, with the
oracle at 0.14, and worse decoding of the facts themselves.

The explanation is a known tension. When domains face different mixes of
allocations, the domain label carries real information about the facts, so a
representation forced to hide the domain throws away signal. Zhao and coauthors
prove a general version of this: when the marginal label distributions differ
across domains, there is a fundamental tradeoff between learning an invariant
representation and keeping the error small on both[^10]. Their result suggests
two things to look for. The penalty should cost nothing when domains face the
same mix, and cost more as they diverge. Both held:

| domains differ by | plain | marginal | conditional |
|------------------:|------:|---------:|------------:|
| none              |  0.30 |     0.31 |           - |
| small             |  0.26 |     0.48 |        0.30 |
| moderate          |  0.29 |     0.98 |        0.41 |
| large             |  1.15 |     1.22 |        1.64 |

These are mean errors in the recovered \$p\$ on the held-out domain. "Marginal"
is the standard adversary. "Conditional" lets the adversary also see the target,
so only domain information beyond what the facts explain is penalized, which is
the fix the theory suggests. It repairs most of the damage at moderate shift. It
still never beats plain training, and at the extreme setting even the plain
decoder fails, because a linear model extrapolating to a very different domain
just fails.

I should be honest about how much weight these numbers bear. Cells average
sixteen held-out evaluations, no confidence intervals were computed, and the
same nominal setting gave 0.38 in one set of seeds and 0.98 in another. The
direction was consistent. The magnitudes are not stable.

Two consequences matter more than the numbers.

First, the definition in section 1 needs a qualifier. *Marginal* invariance is
the wrong target when domains differ in what they face. The defensible target is
invariance *given the facts*, and even that earned nothing here.

Second, and this is the one that stings, the successes in section 2 were
obtained in a world where the label is balanced across domains by construction.
That is precisely the regime where marginal invariance is free. Those results
stand, but only for that regime, and any real dataset that gives each domain its
own pool of scenarios should be expected to behave differently.

The core idea is not refuted. The experiment was linear, small, Gaussian, and it
lacked the one case where invariance ought to help: a genuinely harmful shortcut
with no difference in scenario mix. That experiment has not been run. But the
specific claim that invariance improves downstream value inference is, as of
today, unsupported, and I would rather say so than let it sit in the repository
looking like a result.

## The operator-algebra question

The framework behind Morphix lives in the same neighbourhood as the argument in
[Cognition as Non-Commutative
Geometry](https://saeidaliei.github.io/posts/ncg-cognition/), so it is natural
to ask whether TRL's operators form an algebra of a particular type. The
vocabulary of von Neumann algebras, types I, II and III, is not decoration in
physics. Chandrasekaran, Longo, Penington and Witten show that the algebra of
observables for a static patch of de Sitter space, dressed to an observer's
worldline, is of type II\$_1\$[^11].

For Morphix's operators the answer is plain, and it is not glamorous. They are
finite matrices. Every von Neumann algebra acting on a finite-dimensional space
is a finite direct sum of full matrix algebras, which makes it type I. That is a
structure theorem, not a conjecture, and training the operators differently
cannot change it. Calling the current construction type II or III would be
false, not merely unproven.

What would make the question real is an infinite limit. Take matrix algebras of
doubling size, embedded by \$a\mapsto \mathrm{diag}(a,a)\$. These embeddings
preserve the normalized trace,

$$
\mathrm{tr}_{2n}\big(\mathrm{diag}(a,a)\big)=\mathrm{tr}_{n}(a)
$$

which I checked numerically, and the limit of the tower is the hyperfinite
II\$_1\$ factor.

I deliberately did not build such a tower for the trained operators. Every
construction I could write down was trace-preserving by definition, and so could
not fail. A tower that cannot fail proves nothing. The honest state of the claim
is: trivially type I today, with a concrete route to anything more interesting
that has not yet been designed in a way that could go wrong.

## What Morphix does and does not claim

It does **not** claim:

- that a stable, cross-domain-invariant representation of a concept is
  *correct*, *good*, or what anyone *should* do.
- that people are power-mean aggregators, or that a fitted \$p\$ is someone's
  true ethics.
- that the power-mean line covers ethics. It covers one family of symmetric,
  utility-aggregating rules.
- that invariance training improves downstream value inference. The one test of
  that came back negative.
- that TRL's operators have a nontrivial von Neumann type.

It **does** claim:

> **The question "what survives a change of domain?" can be asked in a form that
> is computable, falsifiable, and capable of failing.**

And the gap between *invariant* and *good* stays exactly where it always was. If
a representation of fairness turns out stable across many framings, that is
evidence the concept tracks something shared rather than something parochial,
which has the same shape as the convergence arguments for moral realism. It is
not a proof that the shared thing is right. Getting from "stable" to "binding"
needs a further premise, and that premise is as contestable as ever. Morphix
supplies the first half of that sentence, and leaves the bridge to be argued,
openly, by whoever wants to cross it.

## What comes next

The next steps, in order of how much each would teach.

**Run the case that should favour invariance.** A world with a genuinely harmful
domain-specific shortcut and no difference in scenario mix. If invariance cannot
help there, the idea is in real trouble. If it can, the failure in section 5 is
a statement about regimes, not about the idea.

**Move to real data.** Two candidates are ready, with loaders written. The Moral
Machine experiment collected 40 million trolley-style decisions from 233
countries and territories[^12]. Its structure is the useful one: the scenario
factors are held fixed and only the respondent's country varies, so domain and
content are cleanly separated. The ETHICS benchmark is organized by normative
theory, which is closer to the original question[^13]. But each category has its
own pool of scenarios, so domain and content vary together. An encoder invariant
across those categories cannot be credited with finding a content-invariant
representation, and given section 5, that kind of dataset is exactly where label
shift should be expected. The paper describes a separate collection procedure
for each of the five tasks, and its annotators were English speakers from the
United States, Canada and Great Britain, so the benchmark spans theories rather
than cultures. That distinction is now a permanent note: matched-content
cross-domain moral data appears to be rare, and what a result is allowed to
claim depends on which kind you have.

**Join the halves properly.** Section 5 joined them and found the join works
mechanically. Making it work *because of* invariance, rather than in spite of
it, is the open problem.

Underneath all of it is a plain observation. Looking for the mathematical
structure of ethics did not dissolve the philosophy. It sharpened it. Every
formalization hit the same wall at a different place: equilibrium selection, the
free exponent between Harsanyi and Rawls, the extra premise between *stable* and
*good*. I do not read that as a failure of the method. It is a map of where the
philosophy actually lives, drawn precisely enough that you can point at it.

## References

[^1]: Brian Skyrms, *Evolution of the Social Contract*, Cambridge University
    Press, 1996. See also Ken Binmore, *Game Theory and the Social Contract*,
    MIT Press, 1994 and 1998.

[^2]: Peter Gärdenfors, *Conceptual Spaces: The Geometry of Thought*, MIT Press,
    2000.

[^3]: Felix Klein, *Vergleichende Betrachtungen über neuere geometrische
    Forschungen* (the Erlangen program), 1872.

[^4]: Yaroslav Ganin and Victor Lempitsky, Unsupervised Domain Adaptation by
    Backpropagation, ICML 2015, https://arxiv.org/abs/1409.7495.

[^5]: Harold Hotelling, Relations Between Two Sets of Variates, *Biometrika*
    28(3/4), 1936, pp. 321-377.

[^6]: John C. Harsanyi, Cardinal Welfare, Individualistic Ethics, and
    Interpersonal Comparisons of Utility, *Journal of Political Economy* 63(4),
    1955, pp. 309-321.

[^7]: John Rawls, *A Theory of Justice*, Harvard University Press, 1971.

[^8]: John F. Nash, The Bargaining Problem, *Econometrica* 18(2), 1950, pp.
    155-162.

[^9]: Anthony B. Atkinson, On the Measurement of Inequality, *Journal of
    Economic Theory* 2(3), 1970, pp. 244-263.

[^10]: Han Zhao, Remi Tachet des Combes, Kun Zhang and Geoffrey Gordon, On
    Learning Invariant Representations for Domain Adaptation, ICML 2019,
    https://proceedings.mlr.press/v97/zhao19a.html.

[^11]: Venkatesa Chandrasekaran, Roberto Longo, Geoff Penington and Edward
    Witten, An Algebra of Observables for de Sitter Space, *Journal of High
    Energy Physics* 2023(2), 82, https://arxiv.org/abs/2206.10780.

[^12]: Edmond Awad, Sohan Dsouza, Richard Kim, Jonathan Schulz, Joseph Henrich,
    Azim Shariff, Jean-Francois Bonnefon and Iyad Rahwan, The Moral Machine
    Experiment, *Nature* 563, 2018, pp. 59-64,
    https://doi.org/10.1038/s41586-018-0637-6.

[^13]: Dan Hendrycks, Collin Burns, Steven Basart, Andrew Critch, Jerry Li, Dawn
    Song and Jacob Steinhardt, Aligning AI With Shared Human Values, ICLR 2021,
    https://arxiv.org/abs/2008.02275.

