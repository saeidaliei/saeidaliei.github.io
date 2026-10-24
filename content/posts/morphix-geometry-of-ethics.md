---
title: "Morphix: Can Ethics Have a Geometry?"
date: 2026-10-21
lastmod: 2026-10-24
author: Saeid
---

There is a simple question that sounds too vague to be mathematical: when the
same moral judgment is expressed in many different ways, what stays the same?

One culture phrases it one way. A philosophical tradition phrases it another. A
vignette, a legal clause, and a proverb can carry the same verdict in different
clothes. Philosophy has mostly handled this with more words. This essay is about
what happens when you try to handle it with structure instead.

Not because ethics reduces to mathematics. Not because a model that finds a stable 
pattern has found what is *right*. And not because borrowed formalism counts as insight by itself.
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
real datasets have been identified and loaders written, but neither has been
used yet, because I could not fetch them from the build environment. And one of
the central hypotheses failed. That failure is, I think, the most instructive
result so far, so it gets its own section rather than a footnote.

A note on reading: terms followed by a reference like (A.3) are
explained in a more accessible language in the appendix at the end of the post.

## 1. Where this started

The obvious first attempts at giving ethics mathematical structure both stall,
and they stall in instructive places.

The first is game theory. Norms can be modeled as equilibria of repeated interaction 
[(A.3)](#a3-game-theory-equilibria-the-folk-theorem-and-equilibrium-selection): 
fairness, promise-keeping, and reciprocity survive
because deviating from them does not pay once everyone else is following
them[^1]. This has real machinery behind it. The trouble is the same theorem
that makes it work. The folk theorem 
[(A.3)](#a3-game-theory-equilibria-the-folk-theorem-and-equilibrium-selection) 
says that in a repeated game
almost any outcome can be sustained as an equilibrium if players are patient
enough, and that includes terrible ones. A stable caste system is an
equilibrium. A stable protection racket is an equilibrium. Nothing in the
apparatus says which equilibrium a society lands in, or which one it should.
That job falls to equilibrium selection, and that is exactly where the
contestable philosophical judgment hides. The mathematics does not retire the
disagreement. It relocates it.

The second is geometry. Concepts as regions of a space with real dimensions is a
serious program, and it works nicely for colour, where "red" is a literal
region[^2]. For justice, harm, or autonomy you have to say what the dimensions
are, and what nearness licenses you to infer. A word-embedding space gives you a
distance for free, but that distance tracks co-occurrence in text, not logical
or normative proximity. Two positions can use nearly the same words and be
incompatible. Unless you can say what the open sets *are*, "a topological space
of ideas" [(A.4)](#a4-spaces-topology-and-conceptual-spaces) 
is a metaphor wearing mathematics' clothes.

What both attempts were missing is an invariant [(A.1)](#a1-invariants-and-symmetry). 
A space is empty until you say what is held fixed. This is an old lesson. Klein's Erlangen
program reorganized geometry around it: a geometry is the study of whatever
stays unchanged under a chosen group of transformations, and different
geometries are just different choices of group[^3].

So choose the group first. Let \$G\$ be the transformations that carry one
domain's expression of a judgment to another's: a different culture's framing, a
different tradition's vocabulary, a different surface style. A concept is then a
representation \$f\$ with

$$
f(g\cdot x)=f(x)\qquad\text{for all } g\in G
$$

In practice the strict version is too much to ask, so we use a soft one: a
representation from which an adversary [(A.2)](#a2-representations-domains-and-adversaries), 
trained to guess the domain, cannot do better than chance, while the judgment itself stays
predictable[^4].

That is a much smaller claim than "the true nature of fairness." It is closer
to: *the part of fairness-talk that is not an artifact of who is talking.* A
smaller claim has the advantage that it can be tested.

## 2. The first experiment: does the mechanism work at all?

The simplest test has known ground truth. Generate a judgment label shared
across four domains, and let each domain add its own nuisance signal to the
observed features. Train an encoder [(A.2)](#a2-representations-domains-and-adversaries) 
to predict the judgment while a domain adversary tries to recover which domain each example came from, 
with the encoder rewarded for defeating it.

On the raw input, a classifier recovers the domain 80% of the time (chance is
25%). On the learned representation it recovers the domain 20% of the time,
while the judgment is predicted with accuracy 1.00. With no adversarial
pressure, domain recovery sits at about 50%, so the adversary is doing real
work. The result also survives a nonlinear probe [(A.2)](#a2-representations-domains-and-adversaries): 
a nearest-neighbour classifier recovers the domain 23% of the time from the
trained encoder and 46% from an encoder trained without the adversary.

One success at one setting proves little, so there is a second check with a
different failure mode. Classical canonical correlation analysis 
[(A.6)](#a6-correlation-and-canonical-correlation-analysis)
is a 1936 technique with no neural network and nothing adversarial in it[^5]. It
can find the shared direction across two domains by pairing examples that carry
the same judgment. If two unrelated methods land on the same signal, that is
evidence it is not an artifact of either. They agree with a correlation of
0.986.

Then the part I find most reassuring. I swept how strong the shared signal is
relative to the domain-specific noise. Agreement stays at 0.97 or above whenever
the signal is at least half as strong as the nuisance. When the signal is one
eighth as strong, agreement falls to 0.26. A metric that collapses when the
problem has no real shared structure to find is a metric that is measuring
something.

Hold on to the phrase "with known ground truth." There is a catch in how that
world was built, and section 5 is where it comes due.

## 3. A space of ethical positions

The founding question was whether philosophical positions can form a space. Here
is one real instance, built from standard pieces.

Take a society with \$n\$ positions and an allocation of utilities
\$x=(x_1,\dots,x_n)\$ across them. Call an evaluation rule *impartial* if it
does not depend on which position carries which label, which is to say it is
invariant under permuting the positions. That is the veil of ignorance 
[(A.7)](#a7-the-veil-of-ignorance-utilitarianism-maximin-and-deontology) 
stated as a symmetry.

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
whole family is impartial. And the power mean inequality 
[(A.8)](#a8-power-means-nash-bargaining-and-atkinson) orders it:

$$
p_1 < p_2\;\Longrightarrow\;M_{p_1}(x)\le M_{p_2}(x)
$$

Three named positions sit on this line 
[(A.8)](#a8-power-means-nash-bargaining-and-atkinson):

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

## 4. Inferring values

If \$p\$ is where positions are allowed to differ, the natural inverse problem
is to recover it from behaviour. Suppose an agent chooses between allocations
\$A\$ and \$B\$ noisily:

$$
P(\text{choose } A)=\sigma\Big(\beta\,\big[\log M_p(A)-\log M_p(B)\big]\Big)
$$

where \$\beta\$ is a noise parameter. Given choices, \$p\$ can be estimated by
maximum likelihood [(A.9)](#a9-choice-models-likelihood-and-fisher-information), 
with a likelihood-ratio interval around it.

The interesting finding is about which questions are worth asking. A pair where
one allocation dominates the other, in the sense that its sorted utilities are
larger everywhere, is a bad question: every impartial rule gives the same
verdict, so the answer carries no information about \$p\$. The most informative
pairs are those whose crossover sits near the current estimate. The Fisher
information [(A.9)](#a9-choice-models-likelihood-and-fisher-information) 
of one query makes this exact:

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
true power-mean agent and 0.15 nats per choice [(A.13)](#a13-a-small-glossary) for a
sufficientarian, an agent who simply counts how many positions clear a
threshold. So the model family can tell when it is the wrong shape, at least in
that case.

A fitted \$p\$ is a compact description of revealed choices under a stated
model. It is not a discovery of what anyone ought to value. I will come back to
that.

## 5. Where it failed

The two halves suggested a division of labour. Facts, meaning how well off each
position actually is, should be domain-invariant, so they should be learned as
an invariant representation. Values, meaning \$p\$, should be fitted on top of
that, separately per domain. The testable claim: an invariant factual encoder
should make value inference transfer better to a domain it has never seen.

I tested it leave-one-domain-out [(A.13)](#a13-a-small-glossary). Train a decoder of factual
quantities on three domains, then on the fourth, unseen domain, fit its value
parameter from observed choices using the decoded facts, and compare the error
against an oracle [(A.13)](#a13-a-small-glossary) that sees the true facts.

The hypothesis was not supported. The invariant encoder was worse than the same
architecture with no adversary: parameter error 0.38 against 0.24, with the
oracle at 0.14, and worse decoding of the facts themselves.

The explanation is a known tension [(A.10)](#a10-domain-shift-label-shift-and-marginal-versus-conditional-invariance). 
When domains face different
mixes of allocations, the domain label carries real information about the facts,
so a representation forced to hide the domain throws away signal. Zhao and
coauthors prove a general version of this: when the marginal label distributions
differ across domains, there is a fundamental tradeoff between learning an
invariant representation and keeping the error small on both[^10]. Their result
suggests two things to look for. The penalty should cost nothing when domains
face the same mix, and cost more as they diverge. Both held:

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

## 6. The operator-algebra question

The framework behind Morphix lives in the same neighbourhood as the argument in
[Cognition as Non-Commutative
Geometry](https://saeidaliei.github.io/posts/ncg-cognition/), so it is natural
to ask whether TRL's operators form an algebra of a particular type. The
vocabulary of von Neumann algebras, types I, II and III [(A.11)](#a11-von-neumann-algebras-and-their-types), 
is not decoration in physics. Chandrasekaran, Longo, Penington and Witten show that the
algebra of observables for a static patch of de Sitter space, dressed to an
observer's worldline, is of type II\$_1\$[^11].

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

## 7. What Morphix does and does not claim

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
which has the same shape as the convergence arguments for moral realism
[(A.5)](#a5-the-isought-gap-and-why-invariance-is-not-goodness). 
It is not a proof that the shared thing is right. Getting from
"stable" to "binding" needs a further premise, and that premise is as
contestable as ever. Morphix supplies the first half of that sentence, and
leaves the bridge to be argued, openly, by whoever wants to cross it.

## 8. What comes next

The next steps, in order of how much each would teach.

**Run the case that should favour invariance.** A world with a genuinely harmful
domain-specific shortcut and no difference in scenario mix. If invariance cannot
help there, the idea is in real trouble. If it can, the failure in section 5 is
a statement about regimes, not about the idea.

**Move to real data.** Two candidates [(A.12)](#a12-the-datasets-and-matched-content-versus-matched-label) 
are ready, with loaders
written. The Moral Machine experiment collected 40 million trolley-style
decisions from 233 countries and territories[^12]. Its structure is the useful
one: the scenario factors are held fixed and only the respondent's country
varies, so domain and content are cleanly separated. The ETHICS benchmark is
organized by normative theory, which is closer to the original question[^13].
But each category has its own pool of scenarios, so domain and content vary
together. An encoder invariant across those categories cannot be credited with
finding a content-invariant representation, and given section 5, that kind of
dataset is exactly where label shift should be expected. The paper describes a
separate collection procedure for each of the five tasks, and its annotators
were English speakers from the United States, Canada and Great Britain, so the
benchmark spans theories rather than cultures. That distinction is now a
permanent note: matched-content cross-domain moral data appears to be rare, and
what a result is allowed to claim depends on which kind you have.

**Join the halves properly.** Section 5 joined them and found the join works
mechanically. Making it work *because of* invariance, rather than in spite of
it, is the open problem.

Underneath all of it is a plain observation. Looking for the mathematical
structure of ethics did not dissolve the philosophy. It sharpened it. Every
formalization hit the same wall at a different place: equilibrium selection, the
free exponent between Harsanyi and Rawls, the extra premise between *stable* and
*good*. I do not read that as a failure of the method. It is a map of where the
philosophy actually lives, drawn precisely enough that you can point at it.

## Appendix: The Concepts, Explained

The main text moves quickly and borrows ideas from several fields at once. This
appendix slows down and explains them in plain language. Nothing here is new,
and you can read the entries in any order. Each one says what the idea is, gives
a small example, and says why it matters for Morphix.

### A.1 Invariants and symmetry

A *transformation* is a systematic change: rotating a shape, translating a
sentence into another language, swapping the names of the people in a problem. A
quantity is *invariant* under a transformation if applying it does not change
the quantity. A collection of transformations that can be chained together, and
where each one can be undone, is called a *group*. "Symmetry" just means
invariance under such a group.

The area of a circle is invariant under rotation, while its orientation is not.
The distance between two points is invariant under rotating or sliding the whole
picture, which is why those moves count as "rigid".

Klein's insight in 1872 was that a geometry is nothing more than the study of
what stays unchanged under a chosen group of transformations[^3]. Ordinary
Euclidean geometry studies what survives rigid motions: lengths and angles.
Projective geometry allows a bigger group of transformations, including ones
that stretch and tilt, so fewer things survive. Lengths no longer do, but
straight lines do. The bigger the group, the fewer the invariants.

The equation in section 1 says the same thing in symbols. Here \$x\$ is an
input, say a description of a moral case. The symbol \$g\$ is a transformation
that re-expresses it in another domain's terms, and \$f\$ is the representation
we are looking for. Then \$f(g\cdot x)=f(x)\$ says that re-expressing the case
does not change what \$f\$ outputs.

Morphix chooses the transformations that carry one domain's way of expressing a
judgment to another's, and asks what survives. Adding more domains makes the
demand stricter, so fewer things survive.

### A.2 Representations, domains, and adversaries

A *domain* is a setting that shapes how the same content gets expressed: a
country, a philosophical tradition, a writing style.

A *representation* is a compact summary of an input, usually a list of numbers,
computed by a model called an *encoder*. A good representation keeps what
matters for the task and drops the rest. *Nuisance* is the part of the input
that varies with the domain but has nothing to do with the judgment, such as
phrasing or vocabulary.

To push a representation toward ignoring the domain, we train two models against
each other. The encoder tries to keep the judgment predictable. The *adversary*
looks only at the representation and tries to guess which domain the example
came from. The encoder is rewarded whenever the adversary fails. The technical
trick, called gradient reversal, flips the sign of the update that would have
helped the adversary, so the encoder is pushed in the opposite direction[^4]. If
the adversary cannot beat guessing, the representation carries no usable trace
of the domain.

*Chance level* is the accuracy you get from guessing. With four equally likely
domains it is 25%. A result of 20% against 25% is just noise around chance, not
evidence of anything clever.

A *probe* is a separate classifier trained afterwards, purely as an inspector,
to check whether domain information is still lurking in the representation. A
*linear* probe can only draw straight boundaries between domains. A
*nearest-neighbour* probe makes no assumption about shape: it guesses an
example's domain by majority vote among the most similar examples (here the 15
closest). Passing the second kind of test is stronger evidence than passing the
first. Even so, a probe failing shows only that the information is hard to
recover *by that probe*, not that it is gone.

### A.3 Game theory: equilibria, the folk theorem, and equilibrium selection

A *game*, in this sense, is any situation where each person's outcome depends on
everyone's choices. A *Nash equilibrium* is a combination of choices where
nobody can do better by changing only their own choice. Driving on the right is
an equilibrium, because if everyone else does, you should too. Driving on the
left is equally an equilibrium. There are two stable outcomes, and neither is
"the correct one". That is the whole problem in miniature.

In a *repeated game* the same situation recurs, so players can reward and
punish. Take the prisoner's dilemma. In a single round each player does better
by betraying the other, even though both would prefer mutual cooperation. Now
repeat it indefinitely and suppose each player follows the rule "cooperate as
long as you do, and if you ever betray me I never cooperate again." If players
care enough about the future, betraying now costs more than it gains, so mutual
cooperation becomes an equilibrium.

The *folk theorem* generalizes this. In a repeated game with sufficiently
patient players, essentially any outcome that gives each player at least what
they could guarantee themselves can be sustained as an equilibrium[^14]. The
good news is that cooperation and fairness can be sustained this way. The bad
news is that so can exploitation, because the theorem does not care whether the
outcome is just.

*Equilibrium selection* is the question of which of the many equilibria a group
ends up in, or should. Candidate answers include the outcome everyone expects (a
"focal point"), the one that survives evolutionary pressure, and the one that is
safest under uncertainty. These answers are where the real judgment calls live.

This is why "norms are equilibria" explains how a norm can persist, but not
whether it is a good norm.

### A.4 Spaces, topology, and conceptual spaces

In mathematics a *space* is a set of things together with some notion of
nearness. A *metric* space measures nearness with distances. A *topological*
space is weaker and more general: it only specifies which collections of points
count as *open*, roughly meaning regions with no hard edge, where every point
has some small neighbourhood still inside. Open sets are enough to define
continuity and "nearby" without ever measuring a distance.

A line of numbers, like the exponent \$p\$ in section 3, has a natural *order
topology*: the open sets are generated by open intervals. All it needs is that
"larger than" makes sense. That is why we can call the family of power means a
topological space without inventing a distance between, say, Rawls and Harsanyi.

*Conceptual spaces* are Gärdenfors's proposal that concepts are regions in a
space whose axes are meaningful qualities[^2]. Colour is the standard example,
with axes for hue, saturation and brightness. "Red" is a region where, if two
shades are red, every shade between them is too. That works well for perception.
For abstract notions like justice, the difficulty is deciding what the axes are.

That difficulty is the point behind the phrase "a metaphor wearing mathematics'
clothes". Calling a collection of ideas a "space" buys you nothing unless you
can say what is near what, and why nearness licenses an inference.

### A.5 The is–ought gap, and why invariance is not goodness

Hume observed that statements about how things *are* do not by themselves entail
statements about how things *ought* to be. Getting from one to the other needs
an extra premise that says why the facts should guide action. This is the
*is–ought gap*.

Moore sharpened a version of it[^15]. Suppose someone claims that "good" just
means some natural property, such as being pleasant, being stable, or being
agreed upon. It still seems to make sense to ask "but is that good?", which
suggests the question is not closed by the definition. That is the
*open-question argument*.

*Convergence arguments* for moral realism run the other way. If people starting
from very different places, reasoning carefully, tend to arrive at the same
moral view, that is some evidence the view tracks something real rather than
something parochial. It has exactly the shape of "this representation is
invariant across domains".

Morphix can show that a representation is stable across domains. That is a fact
about data and models. Stable is not the same as correct, and getting from one
to the other would take a further premise, "what is stable across domains is
binding", which would need its own defence. The project does not supply it.

### A.6 Correlation and canonical correlation analysis

*Correlation* is a number between -1 and 1 that measures how closely two
quantities move together in a straight-line way. A value of 1 means they rise
and fall together perfectly, 0 means no straight-line relationship, and -1 means
they move in exact opposition.

*Canonical correlation analysis* (CCA) starts from two sets of measurements on
matched cases[^5]. In section 2 these are descriptions of the same judgment in
two different domains. It finds a weighted combination of the features in each
set so that the two resulting scores are as correlated as possible. Those
combinations reveal what the two sets have in common.

CCA is plain linear algebra: no training loop, no adversary. That is exactly why
it makes a useful independent check. If a method with a completely different way
of failing lands on the same signal as the adversarial one, the signal is
unlikely to be an accident of either method.

When the text says the two methods "agree with a correlation of 0.986", it means
we took the score each method assigns to every example and measured how closely
the two sets of scores move together.

### A.7 The veil of ignorance, utilitarianism, maximin, and deontology

The *veil of ignorance* is a thought experiment: choose the rules of a society
without knowing which position you will occupy in it. Since you might end up
rich or poor, healthy or ill, you cannot tilt the rules toward yourself. The
formal version of "impartial" is a symmetry (see A.1). If you swap the labels of
the positions, the evaluation must not change.

*Utility* here is just a number representing how well off someone is. Taking
utilities as given is itself a substantive assumption, one the main text does
not hide.

*Utilitarianism* picks the allocation with the greatest total, equivalently the
greatest average, well-being. Harsanyi showed that if you imagine each position
as equally likely and then maximize expected well-being, you are led to rank
allocations by their average[^6].

*Maximin* ranks allocations by how well off the worst-off position is. Rawls
argued that behind a thick veil you cannot meaningfully assign probabilities to
positions, and that without probabilities the cautious response is to protect
against the worst case[^7].

Take the allocations from section 3. Allocation A gives four positions the
utilities (100, 100, 100, 1), and allocation B gives (40, 40, 40, 25). The
averages are 75.25 and 36.25, so the utilitarian picks A. The worst-off
positions have 1 and 25, so the maximin theorist picks B. Both rules are
impartial, and they disagree.

A *sufficientarian* cares neither about the average nor about the worst-off
position as such, but about how many people have *enough*, meaning they clear
some threshold.

*Deontology* holds that some acts are required or forbidden whatever their
consequences, such as a rule against lying that holds even when lying would
produce a better outcome. Such "side-constraints" are not about aggregating
well-being at all, which is why they sit off the power-mean line in section 3.

### A.8 Power means, Nash bargaining, and Atkinson

There are three familiar ways to average positive numbers. The *arithmetic* mean
adds them up and divides by the count. The *geometric* mean multiplies them and
takes a root, so for two numbers it is the square root of their product. The
*harmonic* mean is the reciprocal of the average of the reciprocals. For the
numbers 1 and 4 these give 2.5, 2 and 1.6. The smallest number is 1 and the
largest is 4. They always come out in this order: smallest, harmonic, geometric,
arithmetic, largest. That ordering is the *power mean inequality*[^16].

The *power mean* is one formula that contains all of them: take each number to
the power \$p\$, average the results, and take the \$p\$-th root. Setting
\$p=1\$ gives the arithmetic mean, \$p=0\$ gives the geometric mean (as a
limit), and \$p=-1\$ gives the harmonic mean. As \$p\$ becomes very negative the
result approaches the minimum, and as it becomes very positive it approaches the
maximum. So \$p\$ works like a dial. Higher values give more weight to the
best-off, and lower values give more weight to the worst-off. In the main text,
turning the dial down is "more inequality-averse".

Here are the two allocations from the article, scored at several settings of the
dial:

| p | A = (100,100,100,1) | B = (40,40,40,25) | prefers |
|---|--------------------:|------------------:|---------|
| min | 1.0 | 25.0 | B |
| -1 | 3.9 | 34.8 | B |
| 0 | 31.6 | 35.6 | B |
| 0.063 | 35.62 | 35.61 | tie |
| 1 | 75.3 | 36.3 | A |
| max | 100.0 | 40.0 | A |

The preference flips at about \$p=0.063\$, the crossover \$p^*\$ in the text.

The *Nash bargaining solution* says that when parties bargain over a surplus,
relative to what each gets if talks fail, the fair outcome is the one that
maximizes the product of their gains[^8]. Maximizing a product is the same as
maximizing the geometric mean, which is why Nash's solution sits at \$p=0\$.

*Atkinson's* welfare functions are how economists measure inequality[^9]. They
use a parameter \$\varepsilon\$ for how much one dislikes inequality, and they
are the same family with \$p=1-\varepsilon\$. At \$\varepsilon=0\$ you are
indifferent to how well-being is spread, which gives \$p=1\$. A larger
\$\varepsilon\$ cares more about the bottom.

### A.9 Choice models, likelihood, and Fisher information

People do not always pick the option they value more. A *choice model* says that
the probability of choosing A rises with how much better A looks. The *sigmoid*
function, written \$\sigma\$ in the text, turns any number into a probability
between 0 and 1: large positive inputs give probabilities near 1, an input of 0
gives 0.5, and large negative inputs give probabilities near 0. The parameter
\$\beta\$ sets how sharp this is. A large \$\beta\$ means nearly deterministic
choices, and a small \$\beta\$ means nearly coin flips.

The model compares \$\log M_p\$ values rather than the raw means so that only
*relative* differences matter. Multiply every utility by ten and nothing
changes.

*Maximum likelihood* means choosing the parameter values that make the observed
choices most probable. In practice we try every value of \$p\$ on a fine grid
and keep the best. A *likelihood-ratio interval* is the set of values nearly as
good as the best one, those whose log-likelihood is within about 1.92 of the
maximum. It is a standard rule of thumb for a 95% interval. *Coverage* is how
often such intervals contain the true value in simulations, and the article
reports 93% to 100%.

*Fisher information* measures how much a single observation tells you about a
parameter. It is large when the probability of the observed outcome changes
sharply as the parameter wiggles. A question whose answer is the same for every
\$p\$ carries none. That is what happens when one allocation *dominates* the
other, meaning that after sorting both from lowest to highest, each entry of one
is at least the matching entry of the other. The most informative question is
one where the agent is nearly indifferent at the current estimate, because a
small change in \$p\$ would flip the answer. Choosing each next question to
maximize information is called *adaptive* design. More information means
narrower intervals.

### A.10 Domain shift, label shift, and marginal versus conditional invariance

*Domain shift* is the general situation where the data you test on differs from
the data you trained on. *Label shift* is a specific kind: the mix of correct
answers differs between domains. In section 5, one domain typically faces
allocations in which people are generally well off, while another faces
allocations in which they are worse off. The domain then tells you something
about the answer.

*Marginal invariance* asks that the representation look the same overall in
every domain, which is the same as saying an adversary cannot tell the domains
apart. When label shift is present this demand collides with the task. Because
the answers really do differ across domains, hiding the domain means blurring
differences that are real. Zhao and coauthors prove a lower bound: if the label
distributions differ, a representation that is perfectly domain-invariant cannot
have small error on both domains[^10].

An analogy helps. Two hospitals serve different populations, and one sees sicker
patients. A model forbidden from telling which hospital a patient came from must
also become partly blind to how sick the patient is, because sickness and
hospital are tangled together.

*Conditional invariance* asks for something gentler: hide the domain among cases
that have the *same* answer. In practice the adversary is also shown the answer,
so it penalizes only domain information beyond what the answer explains. This is
the "conditional" column in the section 5 table.

### A.11 Von Neumann algebras and their types

An *operator* is a rule that transforms vectors. In finite dimensions an
operator is just a matrix. Matrices can be added and multiplied, and each has an
*adjoint* (the conjugate transpose). Multiplication order matters, so \$AB\$ and
\$BA\$ can differ. A *von Neumann algebra* is a collection of operators closed
under sums, products, adjoints and, in infinite dimensions, certain limits. It
is the mathematical language of quantum observables.

The *trace* of a matrix is the sum of its diagonal entries. It works as a
dimension counter: the identity matrix of size \$n\$ has trace \$n\$. The
*normalized* trace divides by \$n\$, so the identity always has trace 1.

Murray and von Neumann classified these algebras by how "dimension" behaves
inside them[^17]. In **type I** the possible dimensions are whole numbers, like
ordinary matrices, and there are smallest indivisible pieces. In **type II**
dimension can take a continuum of values, for example anything between 0 and 1
in the case called type II\$_1\$. In **type III** there is no sensible notion of
dimension at all.

Algebras of finite matrices are always type I. That is a theorem. To get type II
or III you need an infinite limit.

Here is the standard route to type II\$_1\$. Start with \$n\times n\$ matrices
and embed them into \$2n\times 2n\$ matrices by placing the matrix twice along
the diagonal. For example, the 2-by-2 matrix with rows (1, 2) and (3, 5) has
trace 1+5=6, so its normalized trace is \$6/2=3\$. Its doubled version is a
4-by-4 matrix with trace 12, so its normalized trace is \$12/4=3\$. The
normalized trace is unchanged. Repeat the doubling forever, and the limit is the
*hyperfinite type II\$_1\$ factor*.

Physicists care because the observables of an observer in de Sitter space form a
type II\$_1\$ algebra[^11]. Roughly speaking, that is the kind of algebra that
supports a finite, well-defined notion of entropy, which is why the type labels
are not decoration in physics. It is also why using them for Morphix's finite
matrices would be a mistake.

### A.12 The datasets, and matched content versus matched label

The **Moral Machine** was an online game in which people decided whom a
self-driving car should spare in unavoidable accidents. The scenarios varied
factors such as the number and ages of the people involved. Respondents came
from 233 countries and territories, and the same combinatorial factors were
shown everywhere. The *content* is therefore matched across domains, and the
only thing that varies is who is answering.

**ETHICS** is a collection of sentences labelled for moral acceptability,
organized into five tasks by ethical theory: justice, deontology, virtue,
utilitarianism and commonsense morality. Each task was collected separately, so
the scenarios in one differ from those in another. The *labels* are of a
comparable kind across domains, but the *content* is not matched. Domain and
content vary together.

The distinction matters because the claim you want to make is that a
representation has dropped the domain-specific part and kept the content. To
test that, you want to have seen the same content in different domains. If the
content differs between domains too, you cannot tell whether a difference you
see comes from the domain or from the content. Datasets like this are also
exactly where label shift (A.10) should be expected.

### A.13 A small glossary

- **Held-out data**: examples never used for training or fitting, kept aside
  only to evaluate.
- **Leave-one-domain-out**: train on all domains but one, then test on the one
  left out. It checks whether something transfers to a domain the model has
  never seen.
- **Oracle**: an idealized version of a method that is given information the
  real method would not have, here the true utilities. It is a best-case
  yardstick.
- **Seed**: the starting number for a random number generator. Different seeds
  give different random data and initializations, so averaging over several
  shows how stable a result is.
- **Mean absolute error**: the average size of the mistakes, ignoring their
  sign.
- **RMSE (root mean squared error)**: square each mistake, average, then take
  the square root. It punishes large mistakes more heavily than the mean
  absolute error does.
- **Nat**: the unit for log-probabilities computed with natural logarithms. If a
  model's average log-probability on the observed choices is 0.15 nats per
  choice below the truth's, then it assigns those choices roughly 14% less
  probability, per choice, than the true process does.
- **Confidence (or likelihood-ratio) interval**: a range of parameter values
  consistent with the data. A narrower range means the data pinned the parameter
  down more.
- **Linear versus nonlinear**: a linear method can only draw straight-line
  relationships, while a nonlinear one can draw curved ones.

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

[^14]: Drew Fudenberg and Eric Maskin, The Folk Theorem in Repeated Games with
    Discounting or with Incomplete Information, *Econometrica* 54(3), 1986, pp.
    533-554.

[^15]: G. E. Moore, *Principia Ethica*, Cambridge University Press, 1903.

[^16]: G. H. Hardy, J. E. Littlewood and G. Polya, *Inequalities*, Cambridge
    University Press, 1934.

[^17]: F. J. Murray and J. von Neumann, On Rings of Operators, *Annals of
    Mathematics* 37(1), 1936, pp. 116-229.

