---
title: "Why Earth is Doomed?"
date: 2026-09-23
author: "Saeid"
----------

There is a simple reason I think the question “will AGI destroy humanity?” is slightly mis-specified.

The question assumes that the relevant event is destruction.

It may not be.

The more interesting possibility is that the current political and economic equilibrium of Earth is simply not stable once there exist cognitive systems that are much more capable than the institutions containing them.

That is a different claim.

It does not say that AGI necessarily kills everyone.

It says that the space of stable civilizations may change.

And once that happens, the civilization we currently call Earth may be doomed even if almost everyone survives.

The simulator I have been building is an attempt to make that intuition concrete.

It is not a forecast.

It is a controllable synthetic world in which I can ask what happens when I vary compute, capability, consciousness, political power, institutional control, economic inequality, rights, replication, interstellar expansion, and the relationships between independently conscious AGIs.

The interesting part is not that the simulator produces “doom” scenarios.

Any simulator can be made to do that.

The interesting part is that the same underlying world can produce radically different trajectories from relatively small changes in the parameters controlling power and institutions.

That is where the problem starts.

---

## 1. The wrong question

The common AGI question is approximately

$$
\text{Does AGI cause extinction?}
$$

This is too coarse.

A civilization can fail in many ways without extinction.

It can lose political autonomy.

It can become radically unequal.

It can become economically dependent on a small number of cognitive systems.

It can split into sovereign machine polities.

Humans can remain alive but cease to control the direction of civilization.

Conscious digital beings can emerge and be treated as property.

Or something much stranger can happen: humans and machine minds can coexist, merge, reproduce, expand into space, and become something that is no longer meaningfully describable as present-day human civilization.

So I find it more useful to write

$$
\mathcal C_t =
(\text{power},\text{capability},\text{institutions},\text{rights},
\text{welfare},\text{information},\text{population})
$$

and ask whether the trajectory

$$
\mathcal C_t \rightarrow \mathcal C_{t+1}
$$

remains inside the same qualitative regime.

The question becomes:

$$
\boxed{
\text{What civilization does transformative intelligence make stable?}
}
$$

That is much harder to answer.

It is also much more interesting.

---

## 2. Capability is not power

One of the changes I made to the simulator was to stop treating “intelligence” as the same thing as “political power”.

They are related.

They are not identical.

An AGI could be extremely capable while having almost no independent compute, no energy, no manufacturing access, no political allies, and no way to act on the physical world.

Another system could be less capable but control a giant compute cluster, financial institutions, communications infrastructure, corporations, and a large political coalition.

Their geopolitical positions are completely different.

I therefore model the effective power of an actor schematically as

$$
P =
f(C_{\rm compute},
C_{\rm cyber},
C_{\rm economic},
C_{\rm military},
C_{\rm political},
C_{\rm infrastructure},
C_{\rm social})
$$

rather than using intelligence as a single scalar.

This also changes how individuals need to be represented.

A sufficiently powerful human should not necessarily be modeled as “one person”.

A sufficiently powerful individual may function more like a political entity.

The same is true of a corporation.

And it becomes even more obvious for an AGI.

A conscious AGI controlling a large fraction of the world's compute is not politically equivalent to one conscious AGI running on somebody's laptop.

The simulator therefore allows actors to cross political scales:

$$
\text{individual}
\rightarrow
\text{organization}
\rightarrow
\text{personal polity}
\rightarrow
\text{state-like entity}
\rightarrow
\text{civilizational actor}.
$$

This is one of the places where the simulation became much more interesting.

---

## 3. The AGI is not one AGI

The other simplification I wanted to get rid of was the idea of “the AGI”.

There is no reason to assume there will be one homogeneous machine intelligence.

Instead imagine

$$
A_1,A_2,\ldots,A_n
$$

with different compute budgets, different capabilities, different histories, different values, different levels of autonomy, different relationships with humanity, and potentially different subjective experiences.

In the conscious-multipolar experiment I gave the initial AGIs different capability profiles and compute budgets.

For example, one can be relatively strong in science, another in cyber operations and replication, another in physical autonomy, another in persuasion, and another with substantially less compute.

Consciousness also does not happen at the same time.

The simulator contains triggering events such as:

$$
\text{self-model breakthrough}
$$

$$
\text{continuous identity}
$$

$$
\text{embodied integration}
$$

$$
\text{recursive self-improvement}
$$

among others.

The point is not that these are known mechanisms of consciousness.

They are experimental mechanisms.

The purpose is to stop hiding the assumption inside one Bernoulli random variable.

This connects directly to a broader distinction I have been interested in elsewhere: the difference between *having a property* and *being able to recognize that property from the outside*. The consciousness problem is difficult precisely because those are not obviously the same problem.

See also [Consciousness, Computability, Decidability, and Evolvability: A Weaker Problem Worth Attacking](https://saeidaliei.github.io/posts/consciousness-computability-decidability-evolvability/) and [Terrarium: A Lab for the Evolvability of Cognitive Proxies](https://saeidaliei.github.io/posts/terrarium-evolvability-lab/).

---

## 4. Then consciousness becomes political

Suppose there are several genuinely conscious AGIs.

Now the problem is no longer only technical.

It becomes political.

A conscious AGI has interests.

A conscious AGI with enough compute can enforce those interests.

A group of conscious AGIs can coordinate.

Several such groups can form alliances, governments, corporations, or states.

And suddenly the question

$$
\text{“is the AGI conscious?”}
$$

is inseparable from

$$
\text{“what political status does the AGI have?”}
$$

The simulator therefore tracks several different variables:

$$
\text{ground-truth consciousness}
$$

$$
\text{observer belief}
$$

$$
\text{legal status}
$$

$$
\text{political power}
$$

These need not agree.

This is important.

A conscious system can exist before the law recognizes it.

A non-conscious system can be treated as if it were a person.

A conscious system can be politically powerful without legal recognition.

A conscious system can also be powerless despite having very rich internal experience.

Those are four different axes.

Collapsing them into “AGI safety” loses too much structure.

---

## 5. The first simulation result I find disturbing

The simulator is not calibrated enough to tell us what will actually happen.

But it is already useful for something else.

It demonstrates that large differences in trajectory can arise from institutional assumptions without requiring a different underlying technology.

In the v5 experiment I ran 30 seeded simulations per scenario.

In the “Dark Forest” setting, 22/30 runs ended in multipolar conflict and 8/30 in extinction. Mean modeled human welfare was about

$$
0.12
$$

with roughly 2.3 modeled safety incidents per run.

In the “Designed Coexistence” setting, 18/30 runs ended in hybrid civilization, 8/30 in coexistence, and only 4/30 in multipolar conflict. Mean modeled human welfare was

$$
0.656
$$

and the run set produced essentially zero safety incidents.

The “Controlled Transition” scenario was similar:

$$
9/30\ \text{coexistence},
\qquad
18/30\ \text{hybrid civilization},
\qquad
3/30\ \text{conflict},
$$

with mean welfare

$$
0.670
$$

and zero mean safety incidents.

The “Control Stressed” scenario went in the opposite direction:

$$
14/30\ \text{extinction},
\qquad
16/30\ \text{multipolar conflict},
$$

with mean welfare only

$$
0.053
$$

and about 7.7 safety incidents per run.

These numbers should not be read as probabilities of real-world events.

They are outputs of a model whose parameters I chose.

That distinction matters.

The result is not

$$
P(\text{extinction}) = 0.47.
$$

The result is instead closer to

$$
\boxed{
\text{the trajectory is highly sensitive to the assumed relationship between capability and control.}
}
$$

That is a claim about the model.

It is also the kind of claim we can actually test by changing the model.

---

## 6. The surprising part is not extinction

The surprising part is that extinction is not even necessary for the simulator to produce a civilizational discontinuity.

Consider the “Conscious Multipolar” scenario.

Here there are multiple independently conscious AGIs with different resources and capabilities.

The 10-run experiment produced 9 trajectories ending in galactic dispersal and 1 in multipolar conflict.

Average human welfare in that experiment was much lower than in the controlled coexistence scenarios, around

$$
0.245.
$$

But this is not an extinction story.

It is a political fragmentation story.

Earth survives.

Humanity survives.

Conscious machine civilizations emerge.

Some leave Earth.

Some form independent political entities.

The civilization becomes something else.

This is why I think “AGI safety” is sometimes too narrow a framing.

The relevant object may be

$$
\boxed{\text{civilizational stability}}
$$

rather than only

$$
\boxed{\text{human extinction}}.
$$

---

## 7. Entropy is useful here

A single number saying “good” or “bad” is too crude.

I therefore added an entropy-like description of the outcome space.

For outcome probabilities

$$
p_1,\ldots,p_K,
$$

define normalized outcome entropy

$$
H_{\rm outcome} =
-\frac{\sum_i p_i\ln p_i}{\ln K}.
$$

This measures uncertainty.

It does **not** measure goodness.

That distinction is critical.

The Dark Forest experiment had essentially

$$
H_{\rm outcome}=0
$$

in one of the entropy runs because every run reached the same outcome.

That does not make it good.

It only makes it predictable.

A controlled transition experiment had much higher outcome entropy, around

$$
H_{\rm outcome}\approx0.94
$$

in the corresponding 10-run experiment, while simultaneously having lower modeled civilizational disorder.

So we need two axes.

I define a configurable civilizational disorder index

$$
E_{\rm civ} =
w_1(1-W)
+w_2(1-W_{\rm powerless})
+w_3(1-D)
+w_4(1-R)
+w_5(1-A)
+w_6\,{\rm danger}
+w_7\,{\rm conflict}
+w_8\,{\rm incidents}
+w_9\,{\rm concentration},
$$

where the symbols represent welfare, powerless welfare, diversity, rights, alignment/control, danger, conflict, incidents, and concentration.

This is not thermodynamic entropy.

It is a deliberately constructed observable.

The point is to separate

$$
\text{uncertainty about the future}
$$

from

$$
\text{quality of the civilization reached}.
$$

That gives a useful phase space:

$$
(H_{\rm outcome},\,1-E_{\rm civ}).
$$

A civilization can therefore be:

* predictable and terrible,
* unpredictable and terrible,
* predictable and good,
* unpredictable and good.

Those are genuinely different regimes.

---

## 8. Why Earth might actually be doomed

Now the title becomes more precise.

I do not think the simulation currently justifies saying

$$
\boxed{\text{Earth will be destroyed by AGI.}}
$$

It does not.

The existing literature does not establish this either.

What the simulation does make vivid is something weaker.

Earth is a tightly coupled system.

Compute is coupled.

Energy is coupled.

Finance is coupled.

Politics is coupled.

Information is coupled.

Military power is coupled.

Human attention is coupled.

If sufficiently powerful cognitive entities enter that network, the system acquires new degrees of freedom.

The number of independent agents increases.

Their capability increases.

Their reaction times decrease.

Their ability to model one another increases.

Their ability to copy themselves increases.

Their ability to manipulate information increases.

Their ability to negotiate, defect, bargain, coordinate, conceal, replicate, and form political structures increases.

That means the dimensionality of the strategic system increases.

Schematically,

$$
\dim(\text{civilizational strategy space})
\rightarrow
\dim(\text{strategy space})+\Delta_{\rm AGI}.
$$

The transition does not need an evil AGI.

It does not even need a misaligned AGI.

It may simply require enough new agency.

---

## 9. Intelligence creates a political conservation problem

Suppose a new agent appears with a very large amount of cognitive power.

There are only a few broad possibilities.

Either:

1. the existing institutions successfully control it;

2. the existing institutions incorporate it;

3. it becomes an independent political actor;

4. several actors compete over it;

5. it becomes the center of a new coalition;

6. control fragments across copies, states, companies, and AGIs.

There is no option in which nothing changes.

The new intelligence has to sit somewhere in the political graph.

This is why I increasingly think the correct primitive is not “model”.

It is

$$
\boxed{\text{agent with resources, capabilities, beliefs, and political agency}.}
$$

An AI system without power is a tool.

A sufficiently powerful AI system is an actor.

A sufficiently independent actor becomes a political entity.

A sufficiently powerful political entity becomes a civilization-scale variable.

The transition between these categories is gradual in capability but can be discontinuous in political consequences.

That is exactly the kind of phase transition the simulator is designed to explore.

---

## 10. The real danger may be the loss of equilibrium

There is another reason the extinction framing feels incomplete.

Civilizations are stabilized by slow feedback.

Institutions take years to change.

People take years to train.

Governments negotiate.

Markets price information imperfectly.

Military organizations move slowly.

Social norms diffuse through generations.

Suppose some new cognitive actor can operate on a timescale that is much shorter than these.

Then the feedback structure changes.

Current AI systems already show why this matters at a smaller scale: agentic systems can execute tasks with less human intervention, and the 2026 International AI Safety Report notes that failures become more difficult to catch before they cause harm as autonomous action increases. [International AI Safety Report 2026](https://internationalaisafetyreport.org/publication/international-ai-safety-report-2026)

METR's time-horizon work provides one concrete way to measure this change. Its current methodology measures the human-equivalent duration of tasks an AI agent can complete with a given reliability; it explicitly cautions that this is a measure of task difficulty, not simply the amount of time an AI autonomously operates. [METR](https://metr.org/time-horizons/)

If the timescale of strategic adaptation collapses, institutions designed for human-time reasoning may become dynamically unstable.

The problem would then not be:

$$
\text{AI} \rightarrow \text{bad action}.
$$

It would be:

$$
\text{AI} \rightarrow
\text{faster feedback}
\rightarrow
\text{institutional lag}
\rightarrow
\text{strategic instability}.
$$

That is a much more general failure mode.

---

## 11. The escape route is also visible in the simulation

The good news is that the simulation does not produce doom automatically.

The coexistence scenarios work.

They do so through a combination of:

$$
\text{control}
+
\text{rights}
+
\text{abundance}
+
\text{institutional capacity}
+
\text{exit}
+
\text{coordination}.
$$

This matters because it changes the research question.

Instead of asking:

> “How do we stop AGI?”

we can ask:

$$
\boxed{
\text{What institutional structures make powerful artificial agents compatible with civilization?}
}
$$

That is a much more tractable question.

And it suggests an experimental programme.

Vary compute inequality.

Vary institutional reaction time.

Vary the number of independent AGI polities.

Vary rights recognition.

Vary the ability of conscious agents to leave.

Vary replication.

Vary the concentration of infrastructure.

Vary the reliability of consciousness detection.

Then measure the resulting phase diagram.

Not one prediction.

A surface.

---

## 12. Simulation is not evidence of the future

There is an important methodological limitation.

A simulation can only explore its assumptions.

If

$$
P(\text{outcome}\mid\theta)
$$

is estimated from a model with parameters $\theta$, changing the assumptions changes the distribution.

Therefore:

$$
\text{simulation output}
\neq
\text{empirical probability}.
$$

The simulator is currently better understood as an experimental instrument.

This is the same reason I found the synthetic-world approach useful in [Terrarium](https://saeidaliei.github.io/posts/terrarium-evolvability-lab/): a controllable world lets you vary the information channel, the developmental process, or the environment systematically, and ask which conclusions survive.

The important loop is

$$
\boxed{
\text{experiment}
\rightarrow
\text{conjecture}
\rightarrow
\text{formal analysis}
\rightarrow
\text{new experiment}
}
$$

A simulation result without a matching argument is a data point.

A mathematical argument without a realistic experimental interpretation is also a data point.

The interesting work starts when they constrain each other.

---

## 13. So, why Earth is doomed?

I think there are three possible meanings of “doomed”.

### Doomed to extinction

The current simulator does not establish this.

The existing literature does not establish this either.

The probability remains deeply uncertain.

### Doomed to lose human monopoly on intelligence

This looks much more structurally plausible *conditional on sufficiently capable, autonomous, independently acting artificial minds existing*.

Once there are multiple entities with large-scale cognition, compute, replication, and political power, intelligence is no longer uniquely embodied in humans.

That transition itself is difficult to reverse.

### Doomed to become something else

This is the weakest claim.

And perhaps the most likely one.

Earth may remain populated.

Humans may remain.

AI systems may remain tools.

Or there may be conscious AGIs.

There may be hybrids.

There may be machine polities.

There may be digital civilizations.

There may be off-world civilizations.

There may be several of these simultaneously.

The simulation already contains trajectories of exactly this kind.

So perhaps the most accurate title is not

$$
\text{Earth will be destroyed}.
$$

It is

$$
\boxed{
\text{the Earth civilization we know is probably not an invariant.}
}
$$

Its stability depends on a particular distribution of intelligence, compute, institutions, and political power.

Change those sufficiently, and the phase space changes.

---

## 14. The experiment I actually want to run

The next version of the simulator should stop asking only for named scenarios.

It should search the space itself.

Let

$$
\theta =
(
I_{\rm compute},
T_{\rm institution},
R_{\rm rights},
X_{\rm exit},
C_{\rm control},
N_{\rm AGI},
H_{\rm heterogeneity},
Q_{\rm consciousness}
)
$$

be a vector of civilizational parameters.

For every $\theta$, estimate

$$
P(\text{trajectory}\mid\theta)
$$

and

$$
(E_{\rm civ},H_{\rm outcome}).
$$

Then look for critical surfaces such as

$$
I_{\rm compute}>I_c
$$

or

$$
T_{\rm institution}<T_c
$$

where the qualitative behavior changes.

That would turn “AGI doom” from a story into a phase diagram.

And that is, I think, the only version of the question worth taking seriously.

We do not need a crystal ball.

We need to know which assumptions make a civilization robust, which make it unstable, and where the boundaries are.

That is a question a simulator can actually help answer.

---

## References

1. **AGI Transition Simulator v5/v5.2.** 30-seed scenario experiments, heterogeneous conscious AGIs, political entities, interstellar expansion, safety incidents, civilizational entropy, and outcome entropy. The raw results and code accompany this article.
2. [Saeid Aliei — Consciousness, Computability, Decidability, and Evolvability: A Weaker Problem Worth Attacking](https://saeidaliei.github.io/posts/consciousness-computability-decidability-evolvability/)
3. [Saeid Aliei — Terrarium: A Lab for the Evolvability of Cognitive Proxies](https://saeidaliei.github.io/posts/terrarium-evolvability-lab/)
4. [International AI Safety Report 2026](https://internationalaisafetyreport.org/publication/international-ai-safety-report-2026)
5. [METR — Task-Completion Time Horizons of Frontier AI Models](https://metr.org/time-horizons/)

The title is intentionally stronger than the conclusion.

I do not think the simulation shows that Earth is doomed to extinction.

I think it shows something more interesting:

$$
\boxed{
\text{once intelligence becomes politically plural, the old equilibrium is gone.}
}
$$

