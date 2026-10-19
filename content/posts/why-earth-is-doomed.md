---
title: "Why Earth is Doomed?"
date: 2026-09-23
author: Saeid
---

There is a simple reason I think the question “will AGI destroy humanity?” is slightly mis-specified. 
It assumes that the relevant event is destruction, and it may not be. 
The more interesting possibility is that the current political and economic equilibrium of Earth 
is not stable once there exist cognitive systems much more capable than the institutions containing them.

That is a different claim. It does not say that AGI necessarily kills everyone. 
It says that the space of stable civilizations may change, 
and that the civilization we currently call Earth may be doomed even if almost everyone survives.

The simulator I have been building is an attempt to make that intuition concrete. It is not a forecast. 
It is a controllable synthetic world in which I can vary compute, capability, consciousness, political power, 
institutional control, inequality, rights, replication and expansion into space, and watch what happens. 
The interesting part is not that it can produce “doom” scenarios, since any simulator can be made to do that. 
It is that the same world produces radically different trajectories from small changes in the parameters governing power and institutions.

## The wrong question

The common question is roughly

$$
\text{Does AGI cause extinction?}
$$

This is too coarse. A civilization can fail without extinction: it can lose political autonomy, become radically unequal, depend on a handful of cognitive systems, or split into sovereign machine polities. Humans can remain alive but stop controlling the direction of civilization. Conscious digital beings can emerge and be treated as property. Or humans and machine minds can coexist, merge, expand into space, and become something no longer describable as present-day human civilization.

So I find it more useful to write

$$
\mathcal C_t =
(\text{power},\text{capability},\text{institutions},\text{rights},
\text{welfare},\text{information},\text{population})
$$

and ask whether the trajectory \$\mathcal C_t \rightarrow \mathcal C_{t+1}\$ remains inside the same qualitative regime. The question becomes

$$
\boxed{
\text{What civilization does transformative intelligence make stable?}
}
$$

which is much harder to answer, and much more interesting.

## Capability is not power, and the AGI is not one AGI

The first change I made to the simulator was to stop treating intelligence as the same thing as political power. 
An AGI could be extremely capable while having no compute of its own, no energy, no allies and no way to act physically. 
Another system could be less capable but control a giant cluster, financial infrastructure and a political coalition. 
Their geopolitical positions are completely different, so I model the effective power of an actor schematically as

$$
P = f(C_{\rm compute}, C_{\rm cyber}, C_{\rm economic}, C_{\rm military}, C_{\rm political}, C_{\rm infrastructure}, C_{\rm social})
$$

rather than as a single scalar. The same goes for individuals and corporations: a sufficiently powerful actor stops behaving like “one person” 
and starts behaving like a political entity, so the simulator lets actors cross scales from individual to organization to state-like entity to civilizational actor.

The second change was to drop the idea of “the AGI”. There is no reason to expect one homogeneous machine intelligence. 
Instead there are \$A_1,\ldots,A_n\$ with different compute budgets, capability profiles, histories, values and relationships with humanity, 
and consciousness does not arrive for all of them at the same time. 
The simulator contains trigger events such as a self-model breakthrough, continuous identity, embodied integration and recursive self-improvement. 
These are not known mechanisms of consciousness. They are experimental ones, meant to stop hiding the assumption inside a single Bernoulli variable.

This connects to a distinction I have explored elsewhere, between *having a property* and *being able to recognize it from the outside*; see 
[Consciousness, Computability, Decidability, and Evolvability](https://saeidaliei.github.io/posts/consciousness-computability-decidability-evolvability) 
and [Terrarium](https://saeidaliei.github.io/posts/terrarium-evolvability-lab).

## Then consciousness becomes political

Suppose several AGIs are genuinely conscious. A conscious AGI has interests, one with enough compute can enforce them, 
and groups of them can form alliances, governments or states. The question “is the AGI conscious?” becomes inseparable 
from “what political status does it have?”, so the simulator tracks four variables that need not agree:

$$
\text{ground-truth consciousness},\quad
\text{observer belief},\quad
\text{legal status},\quad
\text{political power}.
$$

A conscious system can exist before the law recognizes it, a non-conscious one can be treated as a person, 
and a conscious one can be politically powerful without legal recognition or powerless despite a rich inner life. 
Collapsing all of this into “AGI safety” loses too much structure.

## The first simulation result I find disturbing

The simulator is not calibrated enough to say what will happen, but it shows that large differences 
in trajectory can come from institutional assumptions alone, without any change in the underlying technology. 
In the first batch of experiments (version 5) I ran 30 seeded simulations per scenario:

| Scenario | Outcomes in 30 runs | Mean welfare | Safety incidents per run |
|---|---|---|---|
| Dark Forest | 22 multipolar conflict, 8 extinction | 0.12 | about 2.3 |
| Control Stressed | 16 multipolar conflict, 14 extinction | 0.053 | about 7.7 |
| Designed Coexistence | 18 hybrid civilization, 8 coexistence, 4 conflict | 0.656 | about 0 |
| Controlled Transition | 18 hybrid civilization, 9 coexistence, 3 conflict | 0.670 | 0 |

These are not probabilities of real-world events. They are outputs of a model whose parameters I chose, so the result is not \$P(\text{extinction}) = 0.47\$. It is closer to

$$
\boxed{
\text{the trajectory is highly sensitive to the assumed relationship between capability and control.}
}
$$

That is a claim about the model, and the kind of claim we can test by changing the model. Note also that extinction is not needed to get a civilizational discontinuity. In the “Conscious Multipolar” scenario, with several independently conscious AGIs, 9 of 10 runs ended in galactic dispersal and only 1 in conflict. Human welfare was low, around \$0.245\$, but this is a story of political fragmentation, not extinction: Earth and humanity survive, machine civilizations emerge, some leave, and the civilization becomes something else.

**A correction.** When I later audited the simulator, I found that multipolar conflict is the most common label in nearly every scenario, including benign ones. Much of this comes from how the outcome classifier is written: it checks its rules in a fixed order, and AGI forking produces many small copies that trigger the conflict rule. The counts above are therefore better read as evidence of *sensitivity* than of *prevalence*. Welfare, incidents and household metrics separate the scenarios more reliably than the labels do. The direction of the argument survives, but the specific shares should not be quoted.

## Entropy is useful here

A single number saying “good” or “bad” is too crude, so I added an entropy-like description of the outcome space. 
For outcome probabilities \$p_1,\ldots,p_K\$, define the normalized outcome entropy

$$
H_{\rm outcome} = -\frac{\sum_i p_i\ln p_i}{\ln K}.
$$

It measures uncertainty, not goodness. The Dark Forest runs had \$H_{\rm outcome}\approx 0\$ in one experiment because every run reached the same outcome, 
which makes them predictable, not good. A controlled-transition experiment had \$H_{\rm outcome}\approx 0.94\$ while also having lower modeled disorder. 
To capture quality I use a configurable civilizational disorder index

$$
E_{\rm civ} = w_1(1-W)+w_2(1-W_{\rm powerless})+w_3(1-D)+w_4(1-R)+w_5(1-A)+w_6\,{\rm danger}+w_7\,{\rm conflict}+w_8\,{\rm incidents}+w_9\,{\rm concentration},
$$

over welfare, powerless welfare, diversity, rights, alignment and control, danger, conflict, incidents and concentration. 
This is not thermodynamic entropy but a deliberately constructed observable. 
Together the two give a phase space \$(H_{\rm outcome},\,1-E_{\rm civ})\$ in which a civilization can be predictable and terrible, 
unpredictable and terrible, predictable and good, or unpredictable and good, and these are genuinely different regimes.

## Why Earth might actually be doomed

I do not think the simulation justifies saying that Earth will be destroyed by AGI, and the existing literature does not establish it either. 
What it makes vivid is something weaker. Earth is a tightly coupled system in which compute, energy, finance, politics, information, 
military power and human attention all depend on one another. If sufficiently powerful cognitive entities enter that network, 
the number of independent agents grows, their reaction times fall, and their ability to model one another, copy themselves, 
manipulate information, bargain, defect and form political structures grows with it. Schematically,

$$
\dim(\text{civilizational strategy space}) \rightarrow \dim(\text{strategy space})+\Delta_{\rm AGI}.
$$

This needs no evil or even misaligned AGI, only enough new agency. A new intelligence has to sit somewhere in the political graph: existing institutions control it, 
incorporate it, or lose it to an independent actor, to competition among several actors, or to a fragmentation of control across copies, states and companies. 
There is no option in which nothing changes, which is why I think the right primitive is not “model” but

$$
\boxed{\text{agent with resources, capabilities, beliefs, and political agency}.}
$$

An AI system without power is a tool, a powerful one is an actor, an independent one is a political entity, and a sufficiently powerful political entity is a civilization-scale variable. The step between these categories is gradual in capability but can be discontinuous in political consequence.

There is a second reason the extinction framing feels incomplete. Civilizations are stabilized by slow feedback: institutions take years to change, 
people take years to train, and norms diffuse over generations. If a new cognitive actor operates on a much shorter timescale, the feedback structure changes. 
Current systems already show a small version of this, since agentic systems act with less human intervention and the 
[2026 International AI Safety Report](https://internationalaisafetyreport.org/publication/international-ai-safety-report-2026) 
notes that failures become harder to catch before they cause harm as autonomy increases. 
[METR's time-horizon work](https://metr.org/time-horizons) gives one concrete measure of this shift, 
though it cautions that it measures task difficulty and not simply how long an AI operates alone. 
If the timescale of strategic adaptation collapses, institutions built for human-time reasoning may become dynamically unstable:

$$
\text{AI} \rightarrow \text{faster feedback} \rightarrow \text{institutional lag} \rightarrow \text{strategic instability}.
$$

## The escape route is also visible

The simulation does not produce doom automatically. The coexistence scenarios work through a combination of control, rights, abundance, 
institutional capacity, exit and coordination, which changes the research question from “how do we stop AGI?” to

$$
\boxed{
\text{What institutional structures make powerful artificial agents compatible with civilization?}
}
$$

That suggests an experimental programme: vary compute inequality, institutional reaction time, the number of independent AGI polities, rights recognition, 
the ability of conscious agents to leave, replication, infrastructure concentration and the reliability of consciousness detection, 
and measure the resulting phase diagram. The goal is not one prediction but a surface. 
Since writing the first version I have started doing this with a second, smaller instrument.

## A second instrument: the lab

The Python simulator is detailed, and detail makes it hard to see through, so I built a deliberately small model that runs in a browser tab. 
It has eight levers (takeoff feedback, race pressure, safety investment, institutional capacity, verification, openness of deployment, 
redistribution and a pause trigger) and three *beliefs*, which are uncertain facts about the world rather than choices:

$$
\text{alignment difficulty},\qquad \text{hazard steepness},\qquad \text{underlying rate of progress}.
$$

Moving a slider re-runs 400 simulated worlds of thirty years each, in which capability grows, oversight tries to keep up, 
race tension rises and falls, incidents happen, institutions react and households are displaced or supported. 
The heart of the model is a single gap. If \$C\$ is capability, \$O\$ is oversight capacity and \$D\$ is how hard alignment is, then

$$
\text{control gap} = \frac{D\,C\,(1+0.3\,\text{open}) - O}{0.6+0.4\,C},
$$

and the chance of losing control in a quarter grows with the square of that gap and with race pressure. 
Three details matter for the argument here: catastrophes come in tiers, so a severe failure can be *contained* and leave a setback and tougher institutions; 
institutions learn, so a warning shot strengthens oversight; and risk can be retired, 
since if oversight stays ahead of capability for long enough most of the remaining risk disappears. 
The outcomes are no longer “doom or not” but flourishing, managed transition, strained, stalled, concentrated power, 
conflict or misuse, and loss of control, which is exactly the point of section 1.

## What drives the outcomes, and what does not

I ran the lab over its whole input space, five thousand random settings with twenty worlds each, 
and asked how much of the variance of each output is explained by each input alone. The answer is two different stories. 
For the chance of a good outcome, the underlying rate of progress, race pressure and institutional capacity dominate, 
each explaining on the order of a fifth, while alignment difficulty explains almost none. For the chance of losing control, 
alignment difficulty alone explains about 38% of the variance.

> **A single headline probability hides two questions with different drivers. Whether catastrophe happens is mostly about one thing nobody can measure. Whether the transition goes well is mostly about timing, racing and institutions.**

The first is a fact about the world, the second is partly a choice. 
To see how strong the first effect is, take the baseline lever settings and move *only* alignment difficulty across the range current evidence leaves open: 
the chance of losing control goes from about 1% to about 56%. Same world, same institutions, one unobservable number.

I also asked whether this is an artifact of how I wrote the model. I built seven structurally different versions 
(a linear hazard, a logistic hazard, a saturating control requirement, no AI-assisted oversight, no learning from incidents, no containment, and the reference), 
each recalibrated so its baseline loss-of-control rate matched the reference, which separates the *form* of a model from its *level*. 
The ranking of strategies, the direction of every lever's effect and the biggest drivers did not change. 
That is weaker evidence than it sounds, because all seven share one skeleton, a single world with risk driven by a capability-oversight gap, 
and agreement among variants of one idea is not independent confirmation. 
The real test is a structurally different model, for example one with strategic actors who choose and learn.

## Can public data pin the coefficients down?

If the coefficients are the problem, the natural question is whether we can measure them. 
So I built an evidence-gathering step that runs before the simulation. 
It maps observable indicators to coefficients through an explicit table, weights each by source reliability and recency, 
and combines them with a broad prior in a Bayesian update. A study counts once however many numbers it reports, 
indicators of the same quantity are discounted because they are correlated, and every coefficient comes back labeled 
*evidence*, *weak* or *prior-only*. A first pass over the public data found, among other things:

- Frontier training compute doubling roughly every five months ([Epoch AI](https://epoch.ai/data/trends)).
- The best open-weight models trailing the closed frontier by about four months ([Epoch AI](https://epoch.ai/data-insights/open-closed-eci-gap)).
- Roughly a quarter of US firms reporting AI use in a given two-week window ([Census BTOS, via a business-data summary](https://startbusinessbystate.com/?p=16329)).
- A median of about five percent for extremely bad outcomes among AI researchers surveyed in 2023 ([AI Impacts](https://arxiv.org/pdf/2401.02843)).

These tell me about the *present*: how fast the field moves, how widely systems are deployed, how far apart the labs are. 
They tell me almost nothing about the thing that matters most. Alignment difficulty has no observable indicator, 
only elicited opinion that disagrees with itself, and hazard steepness has none at all. When I propagate the evidence through the lab, 
the chance of a good outcome comes out at about 45%, with a 10th to 90th percentile range of roughly 10% to 85%; with no evidence at all, 
a broad prior gives about 46% and a range of roughly 3% to 90%. The anchors that map indicators to coefficients are my judgments, 
so the posterior means are partly shaped by me, but the narrowing is the informative part, and it is small.

$$
\boxed{
\text{The public evidence constrains the present, not the difficulty of the problem.}
}
$$

## The coordination problem

There is a thought I keep returning to. Suppose a headline says there is a 40% chance of human extinction in the form we know, 
and that the remaining 60% depends on humans doing very specific things, probably in unison. 
How likely is it that they will? My gut says not very, and if so the 40% starts to look like the default outcome.

There is something right in this and something that needs care. First, what does the 40% mean? If it is an unconditional estimate, 
it already averages over whether humans coordinate and the argument double counts; if it means “extinction if we do nothing special”, 
the argument applies. Headline numbers often mix the two readings. Writing \$q\$ for the probability that the needed coordination happens,

$$
P(\text{survive}) = q\,P(\text{survive}\mid\text{coordination}) + (1-q)\,P(\text{survive}\mid\text{no coordination}),
$$

so if \$q\$ is small the outcome is close to the baseline. In the lab, the baseline under current evidence is about 28% loss of control and 45% good outcomes, 
while a full coordination package (more safety effort, better verification, stronger institutions, less racing and a pause) brings 
loss of control down to about 4% and good outcomes up to about 91%. Mixing the two, assuming the package applies to every world:

| Chance of package-level coordination | Loss of control | Good outcome |
|---|---|---|
| 0% | 28% | 45% |
| 10% | 25% | 50% |
| 25% | 22% | 57% |
| 50% | 16% | 68% |
| 75% | 10% | 80% |

So my gut is right in one respect: if coordination is as unlikely as I fear, the baseline stands. 
But three things temper the fatalism. First, “in unison” is often not required. 
Compute depends on a handful of chokepoints and a few labs, some safety wins need one actor to succeed and not everyone, 
and technical progress on alignment needs no coordination at all. 
Second, coordination is not binary. In the lab, lowering race pressure alone adds about 17 points to the chance of a good outcome, 
a pause alone adds about 15 while removing about 10 points of loss-of-control risk, and each of race reduction, 
a pause, stronger institutions and slower takeoff feedback helped in at least 87% of the plausible worlds I sampled. 
You do not need everything, only the large levers and a few of the large players. 
Third, \$q\$ is not fixed: it depends partly on what people decide to do, and treating it as a constant can make it low.

There is a real counterweight to this optimism. Past shocks have produced reactive coordination, 
but a shock from this technology may not be survivable, so we may not get the lesson. 
A simulation cannot settle that. What it shows is that the answer is extremely 
sensitive to \$q\$, and that \$q\$ is exactly what the current model cannot estimate.

## Simulation is not evidence of the future

A simulation can only explore its assumptions. If \$P(\text{outcome}\mid\theta)\$ is estimated from a model with parameters \$\theta\$, 
changing the assumptions changes the distribution, so

$$
\text{simulation output} \neq \text{empirical probability}.
$$

The simulator is better understood as an experimental instrument, and the analysis in sections 8 to 11 is a small example of using it that way. 
It does not say how likely catastrophe is. It says which inputs the answer depends on, which of them we can measure, 
and which conclusions survive when the model changes. This is the same reason the synthetic-world approach was useful in 
[Terrarium](https://saeidaliei.github.io/posts/terrarium-evolvability-lab): a controllable world lets you vary one thing 
at a time and ask what survives. The loop that matters is

$$
\boxed{
\text{experiment}\rightarrow\text{conjecture}\rightarrow\text{formal analysis}\rightarrow\text{new experiment}
}
$$

A simulation result without a matching argument is a data point, and so is a mathematical argument without 
a realistic experimental interpretation. The interesting work starts when they constrain each other.

## So, why Earth is doomed?

I think “doomed” has three possible meanings. *Doomed to extinction* is not established by the simulator or by the existing literature, 
and the sensitivity analysis adds that the figure is driven mostly by an input nobody can currently measure. 
*Doomed to lose the human monopoly on intelligence* looks much more structurally plausible, conditional on sufficiently capable, 
autonomous, independently acting artificial minds existing: once several entities have large-scale cognition, compute, 
replication and political power, intelligence is no longer uniquely embodied in humans, and that transition is difficult to reverse. 
*Doomed to become something else* is the weakest claim and perhaps the most likely. 
Earth may stay populated, with tools, conscious AGIs, hybrids, machine polities, digital or off-world civilizations, 
or several of these at once, and the simulation already contains trajectories of exactly this kind. 
So perhaps the most accurate title is not that Earth will be destroyed but that

$$
\boxed{
\text{the Earth civilization we know is probably not an invariant.}
}
$$

Its stability depends on a particular distribution of intelligence, compute, 
institutions and political power, and when those change enough, the phase space changes.

## The experiment I want to run next

Some of this is now done: there is a lab, a global sensitivity analysis, a structural-robustness test and an evidence step. 
What is missing is a simulator that stops asking only for named scenarios and searches the space itself. Let

$$
\theta = (I_{\rm compute}, T_{\rm institution}, R_{\rm rights}, X_{\rm exit}, C_{\rm control}, N_{\rm AGI}, H_{\rm heterogeneity}, Q_{\rm consciousness})
$$

be a vector of civilizational parameters. For each \$\theta\$, estimate \$P(\text{trajectory}\mid\theta)\$ 
and \$(E_{\rm civ},H_{\rm outcome})\$, then look for critical surfaces such as \$I_{\rm compute}>I_c\$ or 
\$T_{\rm institution}<T_c \$ 
where the qualitative behavior changes. That would turn “AGI doom” from a story into a phase diagram.

Three additions would improve it most. The first is strategic actors: blocs and labs that choose between racing, 
restraint and defection and learn from what happens, so that race pressure, verification and 
pauses emerge from incentives and \$q\$ becomes something the model computes. 
The second is time-varying policy, such as a pause that begins after an incident or safety spending 
that rises after a warning shot, so that timing matters and not only levels. 
The third is a structurally different companion model, because agreement within one family of models is not enough.

I think this is the only version of the question worth taking seriously. We do not need a crystal ball. 
We need to know which assumptions make a civilization robust, which make it unstable, 
and where the boundaries are, and that is something a simulator can actually help answer.

---

## References

1. **SI Transition Simulator** (formerly AGI Transition Simulator v5). Scenario experiments with heterogeneous conscious AGIs, political entities, interstellar expansion, safety incidents, civilizational entropy and outcome entropy, plus a macro-economic and household layer, a browser lab, an evidence-gathering step and a written sensitivity and robustness report. The code, data and report accompany this article.
2. Saeid Aliei, [Consciousness, Computability, Decidability, and Evolvability: A Weaker Problem Worth Attacking](https://saeidaliei.github.io/posts/consciousness-computability-decidability-evolvability)
3. Saeid Aliei, [Terrarium: A Lab for the Evolvability of Cognitive Proxies](https://saeidaliei.github.io/posts/terrarium-evolvability-lab)
4. [International AI Safety Report 2026](https://internationalaisafetyreport.org/publication/international-ai-safety-report-2026)
5. METR, [Task-Completion Time Horizons of Frontier AI Models](https://metr.org/time-horizons)
6. Epoch AI, [Data on AI trends](https://epoch.ai/data/trends) and [open versus closed model gap](https://epoch.ai/data-insights/open-closed-eci-gap)
7. US Census Bureau Business Trends and Outlook Survey, [as summarized](https://startbusinessbystate.com/?p=16329)
8. [Thousands of AI Authors on the Future of AI](https://arxiv.org/pdf/2401.02843) (AI Impacts survey)

---

The title is intentionally stronger than the conclusion. 
I do not think the simulation shows that Earth is doomed to extinction. 
I think it shows something more interesting:

$$
\boxed{
\text{once intelligence becomes politically plural, the old equilibrium is gone.}
}
$$
