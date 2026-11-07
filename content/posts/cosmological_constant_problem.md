---
title: "The Cosmological Constant Problem"
date: 2026-11-07
---
Why is the energy of empty space so small, and what would it mean if there
were no cosmological constant at all?

There is a peculiar mismatch at the heart of modern physics. General
relativity allows empty space to gravitate. Quantum field theory tells us
that empty space is not really empty: fields have vacuum states, fluctuations,
and phase-dependent contributions to their energy. Yet the gravitational
effect associated with the vacuum is extraordinarily small.

The number inferred from cosmology is not merely smaller than the energy
scales of particle physics. It is smaller by roughly 120 orders of magnitude
when compared with the fourth power of the reduced Planck scale. And it is
not exactly zero. The observed value is small enough for galaxies to form,
but large enough to dominate the expansion of the Universe today.

This is the cosmological constant problem. It is often described as the
worst fine-tuning problem in theoretical physics, but that phrase can hide
several distinct questions. Why is the vacuum energy so small? Why is it not
exactly zero? Why does it have the value it does? Why is it becoming
cosmologically important only around the present epoch? And is the thing we
call dark energy really a cosmological constant?

These questions are connected, but they are not identical. A proposal can
address one while leaving the others untouched. The goal here is to separate
them, derive the anthropic argument in a useful form, and examine the main
families of proposed resolutions.

## 1. What is the cosmological constant?

Einstein's field equations can contain a term proportional to the metric:

$$
G_{\mu\nu} + \Lambda g_{\mu\nu} = 8\pi G T_{\mu\nu}.
$$

Here, \$ G_{\mu\nu} \$ describes spacetime curvature, \$T_{\mu\nu}\$ describes
matter and radiation, and \$\Lambda\$ is the cosmological constant. It is
not an extra force acting on objects. It is a term in the gravitational
field equations that changes the relation between geometry and matter.

In a homogeneous and isotropic universe, the acceleration equation is

$$
\frac{\ddot a}{a}
= -\frac{4\pi G}{3}(\rho + 3p),
$$

where \$a(t)\$ is the scale factor, \$\rho\$ is the total energy density,
and \$p\$ is the total pressure. A cosmological constant is equivalent to
a fluid with

$$
\rho_\Lambda = \frac{\Lambda}{8\pi G},
\qquad
p_\Lambda = -\rho_\Lambda.
$$

Its pressure is negative enough that \$\rho_\Lambda + 3p_\Lambda < 0\$.
When it dominates the cosmic energy budget, it therefore causes accelerated
expansion. Unlike matter and radiation, its density does not dilute as the
Universe expands.

This is why the cosmological constant is associated with dark energy.
But the two expressions should not be treated as synonyms. A cosmological
constant is one particular model of dark energy: it has exactly constant
energy density and an equation-of-state parameter

$$
w \equiv \frac{p_{\rm DE}}{\rho_{\rm DE}} = -1.
$$

Dark energy is the broader name for whatever is responsible for the
observed late-time acceleration, assuming general relativity is the correct
theory of gravity on cosmological scales. A dynamical field or a modification
of gravity could produce similar expansion history without a fundamental
\$\Lambda\$ term. [^1]

## 2. The observational fact: the vacuum scale is tiny

The late-time Universe is well described, to a good approximation, by the
\$\Lambda\$CDM model: cold dark matter, ordinary matter, radiation, and a
cosmological constant. Type Ia supernovae, the cosmic microwave background,
baryon acoustic oscillations, and large-scale structure all contribute to
the evidence for this picture. In the standard framework, roughly 70% of
the present cosmic energy density is attributed to dark energy. [^15]

The measured dark-energy density corresponds to an energy scale of about

$$
\rho_{\Lambda,\mathrm{obs}}^{1/4}
\simeq 2.26 \times 10^{-3}\ {\rm eV}.
$$

To compare it with particle-physics scales, use natural units,
\$\hbar = c = 1\$, and express everything in powers of GeV. Since
\$1\ {\rm eV} = 10^{-9}\ {\rm GeV}\$,

$$
\begin{aligned}
\rho_{\Lambda,\mathrm{obs}}
&= (2.26 \times 10^{-3}\ {\rm eV})^4 \\
&= (2.26 \times 10^{-12}\ {\rm GeV})^4 \\
&\simeq 2.6 \times 10^{-47}\ {\rm GeV}^4.
\end{aligned}
$$

Now compare this with the reduced Planck mass,

$$
M_{\rm Pl} = \frac{1}{\sqrt{8\pi G}}
\simeq 2.435 \times 10^{18}\ {\rm GeV}.
$$

A Planck-scale estimate of vacuum energy is of order \$M_{\rm Pl}^4\$:

$$
M_{\rm Pl}^4
= (2.435 \times 10^{18}\ {\rm GeV})^4
\simeq 3.5 \times 10^{73}\ {\rm GeV}^4.
$$

The ratio is therefore

$$
\begin{aligned}
\frac{M_{\rm Pl}^4}{\rho_{\Lambda,\mathrm{obs}}}
&\simeq \frac{3.5 \times 10^{73}}
{2.6 \times 10^{-47}} \\
&\simeq 1.3 \times 10^{120}.
\end{aligned}
$$

That is the origin of the famous 120-order-of-magnitude discrepancy.
It is a comparison of **energy densities**. Taking the fourth root gives

$$
\frac{M_{\rm Pl}}{\rho_{\Lambda,\mathrm{obs}}^{1/4}}
\simeq 1.1 \times 10^{30},
$$

so the corresponding **energy-scale** hierarchy is about 30 orders of
magnitude, not 120. Both statements describe the same hierarchy, but
refer to different quantities. [^2] [^4]

A small number is not automatically a problem. Physics contains many small
dimensionless parameters. The problem is that quantum field theory seems
to generate contributions to vacuum energy that are vastly larger, and
there is no known symmetry in the observed low-energy theory that explains
why their sum should remain so close to zero.

## 3. Why quantum field theory makes this difficult

In quantum field theory, a field can be viewed, roughly, as an infinite
collection of harmonic oscillators, one for each momentum mode. Even in
its lowest-energy state, each oscillator has zero-point energy. For a
simple free field, the formal vacuum-energy density contains an integral
of the form

$$
\rho_{\rm vac}
= \frac{1}{2}
\int^{k_{\rm max}} \frac{d^3 k}{(2\pi)^3}
\sqrt{k^2 + m^2}.
$$

At large momentum, the integral scales as the fourth power of the cutoff.
For a massless field and a sharp three-momentum cutoff \$K\$, the integral
can be evaluated explicitly:

$$
\begin{aligned}
\rho_{\rm vac}
&= \frac{1}{2}\int_0^K \frac{4\pi k^2\,dk}{(2\pi)^3}\,k \\
&= \frac{1}{4\pi^2}\int_0^K k^3\,dk \\
&= \frac{K^4}{16\pi^2}.
\end{aligned}
$$

The numerical coefficient depends on the field content and regulator,
but the characteristic scaling is

$$
\rho_{\rm vac} \sim K^4.
$$

For \$K = M_{\rm Pl}\$, the dimensional estimate without loop factors is
\$M_{\rm Pl}^4\$, giving the ratio of about \$1.3 \times 10^{120}\$
calculated above. Keeping the \$1/(16\pi^2)\$ from this particular
sharp-cutoff integral instead gives

$$
\frac{M_{\rm Pl}^4}{16\pi^2\rho_{\Lambda,\mathrm{obs}}}
\simeq 8.5 \times 10^{117}.
$$

That is about 118 orders of magnitude. It is still conventionally
summarized as a roughly 120-order problem. The cutoff estimate is not a
regulator-independent prediction of quantum field theory; its purpose is
to show the scale of the naturalness problem. [^2] [^4]

There are also lower-energy contributions, which are important because
they do not rely on extrapolating a field theory all the way to the
Planck scale.

**Electroweak scale.** The electroweak symmetry-breaking scale is of order
\$M_{\rm EW} \sim 200\ {\rm GeV}\$. Its fourth power is

$$
(200\ {\rm GeV})^4 = 1.6 \times 10^9\ {\rm GeV}^4.
$$

Compared with the observed density,

$$
\frac{(200\ {\rm GeV})^4}{\rho_{\Lambda,\mathrm{obs}}}
\simeq \frac{1.6 \times 10^9}{2.6 \times 10^{-47}}
\simeq 6.1 \times 10^{55}.
$$

Thus the electroweak contribution is roughly 55--56 orders of magnitude
larger, before any cancellation with the bare cosmological constant.
The precise coefficient depends on the Higgs potential and the
convention used for the electroweak scale. [^2] [^4]

**QCD scale.** The QCD vacuum changes across the chiral-symmetry-breaking
transition. A characteristic strong-interaction scale is
\$M_{\rm QCD} \sim 0.3\ {\rm GeV}\$. The corresponding dimensional
estimate is

$$
\rho_{\rm QCD} \sim (0.3\ {\rm GeV})^4
= 8.1 \times 10^{-3}\ {\rm GeV}^4.
$$

The ratio is

$$
\frac{\rho_{\rm QCD}}{\rho_{\Lambda,\mathrm{obs}}}
\sim \frac{8.1 \times 10^{-3}}{2.6 \times 10^{-47}}
\simeq 3.1 \times 10^{44}.
$$

So the QCD scale alone gives a mismatch of about 44 orders of
magnitude. Using \$0.2\ {\rm GeV}\$ instead gives about
\$6 \times 10^{43}\$, or roughly 44 orders. This is the commonly
quoted "40- to 45-order" problem: it comes from a known low-energy
scale, not from assuming Planck-scale physics. [^2] [^4]

Strictly speaking, this estimates the change in vacuum energy associated
with the QCD transition, not an independently measurable absolute vacuum
energy. A counterterm can shift the overall zero of energy. But once
gravity is included, the total renormalized vacuum energy must still be
small, so this known phase-transition contribution has to be included in
the required cancellation. [^2] [^4]

There is an important qualification here. The quartically divergent
cutoff integral is not, by itself, a direct observable prediction of
quantum field theory. Its value depends on the regularization and
renormalization prescription. One can absorb cutoff-dependent terms into
a bare cosmological constant. It would therefore be misleading to say
that quantum field theory has made a clean prediction of a huge vacuum
energy and experiment has simply contradicted it.

The deeper problem survives renormalization. In a gravitational effective
field theory, the cosmological constant is an allowed parameter. The
renormalized value is a sum of a bare term and contributions from quantum
fields, symmetry breaking, and phase transitions. Schematically,

$$
\rho_{\Lambda,\mathrm{eff}} =  \rho_{\Lambda,\mathrm{bare}} +  \rho_{\mathrm{loops}} + \rho_{\mathrm{phase\ transitions}} + \cdots .
$$

The observed value requires this sum to be tiny. But known physics gives
large contributions to the individual terms. Even finite contributions
from massive particles, not just a formal Planck-scale cutoff, are
enormous compared with the measured result. The top-quark contribution
alone illustrates the severity of the radiative-stability problem. [^4]

The issue is not that a counterterm cannot be chosen to cancel the
contributions. It can. The issue is that the cancellation must be
extraordinarily precise, and it must keep working whenever quantum
corrections are added or the vacuum changes phase.

This is the naturalness version of the cosmological constant problem:
why is the small observed value stable under the corrections that the
theory itself seems to require?

### 3.1 Why phase transitions matter

The problem is not confined to virtual particles at extremely high energy.
The vacuum state of a field can change when the Universe passes through a
phase transition. The Higgs field, for example, sits in a nonzero vacuum
configuration today. Quantum chromodynamics also has a nontrivial vacuum
structure.

A change in the vacuum state changes the energy attributed to that state.
If gravity responds to vacuum energy in the ordinary way, these changes
should affect the cosmological constant. Yet the late-time value remains
tiny. A successful explanation must account not only for an initial
cancellation, but also for why later changes in the vacuum do not leave
behind a much larger effective cosmological constant. [^4]

### 3.2 The old problem and the coincidence problem

It is useful to distinguish two problems.

The *old cosmological constant problem* is the smallness problem: why is
the effective vacuum energy so close to zero compared with particle-physics
scales?

The *coincidence problem* asks why the vacuum-energy density is becoming
comparable to the matter density at roughly the present epoch. Matter
dilutes as

$$
\rho_m(a) = \rho_{m,0} a^{-3},
$$

whereas a true cosmological constant remains constant:

$$
\rho_\Lambda(a) = \rho_{\Lambda,0}.
$$

There is no obvious reason why these very different components should
have comparable densities now. The first problem concerns an enormous
hierarchy. The second concerns a special-looking cosmic epoch. A theory
that solves one does not automatically solve the other. [^5]

## 4. The anthropic argument

The anthropic approach is often caricatured as saying that the cosmological
constant has its value because otherwise we would not be here. That
statement is too vague to be useful. The serious version is a selection
argument: if different regions or universes realize different values of
the vacuum energy, observers can only measure values compatible with the
formation of structures that eventually produce observers.

The argument does not require the Universe to be designed for life. It
requires an ensemble of physically realized possibilities, a distribution
of values across that ensemble, and a selection effect that changes what
observers are likely to measure. Weinberg showed that galaxy formation
places a quantitative upper bound on a positive cosmological constant.
[^6]

### 4.1 Why a large positive value prevents galaxies

In the early Universe, matter dominates over vacuum energy. Small
primordial density fluctuations can then grow under gravity. In the
matter-dominated era, the linear growth of a density perturbation is
approximately proportional to the scale factor:

$$
\delta(a) \propto a.
$$

Eventually, a sufficiently overdense region becomes nonlinear, collapses,
and forms a gravitationally bound object. Galaxies and their stars require
this process.

A positive cosmological constant changes the story. Since matter density
falls as \$a^{-3}\$ while vacuum density remains constant, the vacuum
eventually dominates. Once this happens, the expansion accelerates and
the growth of density perturbations becomes strongly suppressed. Existing
bound objects survive, but new large-scale structures become much harder
to form.

Define \$a_\Lambda\$ as the scale factor at which matter and vacuum
densities are equal. Then

$$
\rho_{m,0} a_\Lambda^{-3} = \rho_\Lambda,
\qquad
a_\Lambda =
\left(\frac{\rho_{m,0}}{\rho_\Lambda}\right)^{1/3}.
$$

Increasing \$\rho_\Lambda\$ makes \$a_\Lambda\$ smaller. Vacuum domination
begins earlier, leaving less time for primordial fluctuations to grow.
For a region to collapse before growth is suppressed, its linearly
extrapolated density contrast must reach the collapse threshold,

$$
\delta_{\rm lin}(t_\Lambda) \gtrsim \delta_c,
\qquad
\delta_c \simeq 1.686.
$$

This is the basic physical mechanism behind the anthropic upper bound.
A sufficiently large positive vacuum energy prevents ordinary density
fluctuations from producing enough gravitationally bound structures.
[^6]

The bound can be made more quantitative. If galaxy formation has already
begun by redshift \$z_c\$, the matter density at that time is

$$
\rho_m(z_c) = \rho_{m,0}(1+z_c)^3.
$$

A vacuum density much larger than the matter density at that epoch would
have dominated too early and strongly inhibited collapse. Weinberg's
classic estimate gives, for a spatially flat model,

$$
\rho_\Lambda \lesssim
\frac{\pi^2}{3}(1+z_c)^3 \rho_{m,0}.
$$

Taking \$z_c = 4\$ gives an upper bound of order
\$4 \times 10^2 \rho_{m,0}\$. This is an order-of-magnitude argument,
not a precision prediction of the observed value. It says that a
cosmological constant vastly larger than the present matter density would
make galaxy formation difficult. [^6]

A large negative cosmological constant creates a different problem. It
eventually causes the Universe to recollapse. If the recollapse happens
before galaxies, stars, heavy elements, and observers can develop, that
value is also excluded by the selection condition. The positive and
negative sides of the allowed interval therefore have different physical
bounds.

### 4.2 From a bound to a probability distribution

An upper bound alone does not tell us what value an observer should
expect. For that, we need a probability distribution.

Suppose a theory admits many vacua with different values of
\$\rho_\Lambda\$. Let

- \$p_{\rm prior}(\rho_\Lambda)\$ be the probability density before
  applying observer selection;
- \$n_{\rm obs}(\rho_\Lambda)\$ be the expected number of observers, or
  a proxy such as the amount of matter ending up in suitable galaxies.

The probability density for an observer to measure a particular value is
then

$$
P_{\rm obs}(\rho_\Lambda) =
\frac{
p_{\rm prior}(\rho_\Lambda)n_{\rm obs}(\rho_\Lambda)
}{
\displaystyle \int d\rho'_\Lambda\,
p_{\rm prior}(\rho'_\Lambda)n_{\rm obs}(\rho'_\Lambda)
}.
$$

This is the central equation of the anthropic argument. It is a
conditional probability: the prior distribution is reweighted by how
many observers can arise in each kind of universe.

Now make two assumptions.

First, suppose the underlying theory produces a dense set of possible
vacuum energies near zero, and the prior is nearly constant across the
very narrow range compatible with galaxy formation:

$$
p_{\rm prior}(\rho_\Lambda) \simeq \mathrm{constant}.
$$

Second, suppose the number of observers is roughly proportional to the
amount of matter that ends up in galaxies capable of forming stars and
planets. Then \$n_{\rm obs}\$ falls rapidly when the vacuum energy is so
large that structure formation is suppressed.

Under these assumptions, the observer-weighted distribution is largest
at values small enough to allow structure formation, but it need not be
peaked at exactly zero. A typical observer can find a positive value
that is not far below the upper anthropic range. This is the essence of
Weinberg's prediction. [^7]

The probability of observing a value no larger than ours is

$$
P(\rho_\Lambda \leq \rho_{\Lambda,\rm obs})
= \int_{-\infty}^{\rho_{\Lambda,\rm obs}}
P_{\rm obs}(\rho_\Lambda)\,d\rho_\Lambda.
$$

The result depends on the prior, the model of galaxy formation, and the
choice of observer proxy. In one semi-analytic galaxy-formation study,
assuming a flat prior and weighting observers by stellar mass, the
observed value lay in the lower 6.7% of the predicted distribution. That
is not a parameter-free prediction, but it illustrates that the
selection argument can be made quantitative. [^8]

### 4.3 What the anthropic argument does and does not explain

The argument is impressive because it turns a vague statement about
observers into a calculation involving structure formation. It also
explains why a positive vacuum energy should not be arbitrarily large.

But it has demanding prerequisites.

There must be an ensemble of vacua or regions in which the vacuum energy
actually varies. The values must scan densely enough that at least some
lie within the narrow structure-forming range. The prior distribution
must be understood, or at least be smooth over that range. Finally, we
must have a defensible way to count observers or to use galaxies as their
proxy.

String theory's landscape is sometimes invoked as a possible source of
such an ensemble. Different compactifications and flux choices may
produce many metastable vacua with different low-energy parameters.
If the resulting values of vacuum energy densely sample the region near
zero, anthropic selection could explain why observers see a small value.
But the existence and cosmological realization of the required ensemble,
as well as the measure used to assign probabilities, remain unsettled.
[^9]

There is also a conceptual limitation. The anthropic argument does not
show why the vacuum energy of an individual vacuum is small. It says that
observers are selected from a larger set of possibilities. It explains
an observation only if the underlying ensemble and probability measure
are part of a credible physical theory.

In that sense, anthropic reasoning is not a dynamical cancellation
mechanism. It is an explanation based on selection.

## 5. Candidate resolutions

There is no accepted solution to the cosmological constant problem.
Different proposals attack different parts of it. Some try to cancel
vacuum energy, some alter its gravitational effect, some make it
dynamical, and others explain why observers should measure a small value.

### 5.1 Supersymmetry and other symmetries

Supersymmetry relates bosons and fermions. In an exactly supersymmetric
vacuum, their zero-point contributions cancel, and the vacuum energy can
vanish. This is attractive because a symmetry can protect a small
quantity against quantum corrections.

The difficulty is that supersymmetry is not observed as an exact symmetry
of the low-energy world. If it is broken, the cancellation is incomplete.
A breaking scale at or above the TeV scale typically gives a vacuum-energy
contribution enormously larger than the observed value. Supersymmetry
therefore illustrates the kind of protection one would like, but known
four-dimensional versions do not solve the problem simply by being
present. [^4]

Other proposed symmetries include scale symmetries and more exotic
relations between positive- and negative-energy sectors. These ideas
face their own problems: the symmetry must survive quantum corrections,
be compatible with gravity, and avoid instabilities or unwanted new
degrees of freedom.

### 5.2 Dynamical relaxation and adjustment mechanisms

Another idea is that the vacuum energy is not fixed once and for all.
A new field could evolve in response to vacuum energy and drive the
effective cosmological constant toward a small value.

The simplest versions introduce a scalar field whose potential energy
changes over cosmic time. In principle, the field can roll toward a
region of small effective vacuum energy. This is the intuition behind
relaxation and adjustment mechanisms.

The obstacle is that a field which cancels an arbitrary constant must
continue doing so after quantum corrections and phase transitions.
Many simple local adjustment mechanisms run into no-go results or
produce unacceptable cosmological behavior. More sophisticated
constructions use extra dimensions, nonlocal ingredients, special
couplings, or time-dependent solutions to evade the assumptions behind
those results. [^1] [^4]

### 5.3 Quintessence: perhaps dark energy is not constant

Quintessence replaces the cosmological constant as the source of
acceleration with a slowly rolling scalar field \$\phi\$. Its energy
density and pressure are

$$
\rho_\phi = \frac{1}{2}\dot\phi^2 + V(\phi),
\qquad
p_\phi = \frac{1}{2}\dot\phi^2 - V(\phi).
$$

If the potential energy dominates over the kinetic energy, then
\$p_\phi \simeq -\rho_\phi\$, and the field behaves much like a
cosmological constant. But unlike a true \$\Lambda\$, its density can
change with time.

Quintessence can address the question of what drives the observed
acceleration if future data show that \$w\$ differs from \$-1\$ or
changes with time. It does not, by itself, solve the old cosmological
constant problem. A scalar field can roll on top of a large vacuum
energy, and the theory must still explain why that baseline contribution
is so small. [^10]

This is a recurring distinction: explaining the *dynamics* of dark
energy is not the same as explaining the *smallness* of vacuum energy.

### 5.4 Modified gravity and self-tuning

Perhaps the problem is not the vacuum energy, but our assumption about
how gravity responds to it. General relativity may be an excellent
approximation on Solar-System and astrophysical scales while requiring
modification on cosmological scales.

Scalar-tensor theories, braneworld models, massive gravity, and more
general modifications of the gravitational action have all been studied.
Some attempt to make the gravitational response insensitive to a
constant vacuum-energy contribution, while still allowing ordinary
matter to gravitate normally. This is often called self-tuning.

The difficulty is severe. A viable theory must reproduce the observed
expansion history, the growth of cosmic structure, gravitational lensing,
gravitational-wave propagation, and the many successful local tests of
general relativity. Some self-tuning constructions also encounter
instabilities, strong coupling, or hidden fine-tuning. Modified gravity
is a broad research program, not a single established solution. [^11]

### 5.5 Unimodular gravity: Lambda as an integration constant

In unimodular gravity, the gravitational field equations are written in
a trace-free form. Taking their divergence and using energy-momentum
conservation recovers Einstein's equations with a cosmological constant
that appears as an integration constant.

This changes the status of \$\Lambda\$. Instead of being a parameter
inserted directly into the action, it arises from the integration of
the field equations. That is conceptually interesting: the value of
\$\Lambda\$ can be viewed as part of the initial or global data of the
theory.

But changing the place where a constant enters the equations is not
automatically the same as explaining why its value is small. Whether
unimodular gravity addresses the radiative problem depends on the
formulation, the global constraints, and how quantum corrections are
treated. It is therefore a candidate framework, not a settled solution.
[^12]

### 5.6 Vacuum-energy sequestering

Sequestering proposals attempt to make gravity insensitive to vacuum
energy generated by matter loops. They introduce global variables or
constraints into the action. These constraints can cancel contributions
that would otherwise appear as a large cosmological constant in the
gravitational field equations.

The attraction is that the cancellation is designed to survive quantum
corrections from a protected matter sector, rather than requiring a
separate fine-tuning after every correction. The price is structural:
the theory uses global or nonlocal ingredients, and one must understand
their consistency, cosmological implications, and interpretation.
Sequestering is one of the more direct attempts to address the old
problem itself. [^13]

### 5.7 Causal sets and a fluctuating Lambda

Causal set theory proposes that spacetime has a fundamentally discrete
structure, with the number of elementary spacetime events related to
spacetime volume. In some versions, the cosmological constant is not
perfectly fixed but fluctuates.

The characteristic estimate is

$$
\Delta\Lambda \sim \frac{1}{\sqrt{V}},
$$

where \$V\$ is a spacetime four-volume. For a cosmological region,
\$V\$ is roughly of order \$H^{-4}\$, so

$$
\Delta\Lambda \sim H^2.
$$

This is intriguing because the observed cosmological constant is of the
same order as the present Hubble scale squared. It offers a possible
connection between the smallness of \$\Lambda\$ and the enormous
spacetime volume of the observable Universe.

The idea remains speculative. Specific ever-present-\$\Lambda\$ models
face observational constraints, including constraints from the isotropy
of the cosmic microwave background. The scaling is suggestive, but it
is not yet a demonstrated derivation of the observed value. [^14]

### 5.8 Quantum cosmology and vacuum selection

There are also proposals in which the value of the cosmological constant
is selected by a quantum-cosmological probability distribution. Older
ideas involving Euclidean path integrals and wormholes, for example,
suggested an enhancement of the probability near zero vacuum energy.

These proposals are conceptually ambitious, but their conclusions depend
on difficult questions: how to define the gravitational path integral,
which boundary conditions to use, how to interpret the resulting
probabilities, and whether the calculation describes the real Universe.
They are interesting possibilities, not established predictions. [^1]

## 6. Does the cosmological constant actually exist?

The question is ambiguous, because it can mean several different things.

First, perhaps there is no fundamental cosmological-constant term in
the gravitational action. That is logically possible. A theory such
as unimodular gravity can place the effective constant in an integration
constant rather than a coupling. But the observable gravitational
equations can still contain an effective term with exactly the behavior
of a cosmological constant.

Second, perhaps the observed acceleration is real, but is not caused by
a constant vacuum energy. A slowly evolving scalar field, an interacting
dark sector, or modified gravity could produce a similar expansion
history. In that case, \$\Lambda\$ might be zero while the effective
dark-energy component is not.

Third, perhaps there is no cosmic acceleration at all, and the apparent
acceleration is an artifact of treating the Universe as homogeneous
when it is not. Inhomogeneous cosmologies and backreaction proposals
explore versions of this possibility. The challenge is to reproduce
the full set of observations, not just the supernova distance-redshift
relation. Within the standard homogeneous cosmology and general
relativity, the evidence for late-time acceleration is strong. [^2]

The current observational situation is worth stating carefully. As of
November 2026, DESI baryon-acoustic-oscillation measurements by
themselves remain broadly consistent with flat \$\Lambda\$CDM. When
combined with cosmic microwave background and supernova data, some
analyses prefer a time-dependent dark-energy equation of state. A
November 2026 review describes this as a moderate preference, not a
definitive detection of dynamical dark energy. [^15]

The details depend on the data combination and the supernova calibration.
For example, a 2026 reanalysis of the Dark Energy Survey supernova
sample reduced one previously reported preference for evolving dark
energy from \$4.2\sigma\$ to \$3.2\sigma\$, corresponding to Bayesian
odds of only about 5:1 in favor of the more flexible model. That is
interesting evidence, but it is not a discovery. [^16]

Even if future observations establish that dark energy evolves, the old
cosmological constant problem will remain. A dynamical field does not
explain why the vacuum contribution from quantum fields is so small.
It changes the description of cosmic acceleration; it does not
automatically solve the vacuum-energy hierarchy.

So the most defensible statement is not that the cosmological constant
has been proved to exist, nor that it has been disproved. The data
strongly support late-time acceleration within general relativity.
Whether the source is a true constant, a dynamical component, or a
modification of gravity is still an empirical question.

## 7. What would count as a solution?

A convincing solution should do more than reproduce the observed
number by choosing a counterterm. It should explain why the small value
is stable under quantum corrections and vacuum phase transitions. It
should be compatible with the Standard Model and general relativity
where those theories have been tested. It should also give a coherent
account of the observed cosmic acceleration and, ideally, make
predictions that distinguish it from competing models.

This gives us a way to evaluate proposals.

A symmetry-based solution should identify the symmetry and show how it
protects the vacuum energy after the symmetry is broken. A dynamical
solution should explain why the field evolves to the right value and
why it does not spoil the early Universe. A modified-gravity solution
must pass local and cosmological tests. An anthropic explanation must
provide a physical ensemble, a sufficiently dense scan of vacuum
energies, and a defensible probability measure. A sequestering or
unimodular construction must show precisely how quantum corrections
enter its global constraints.

No proposal has yet met all of these requirements in a way accepted
by the community.

## 8. The deeper lesson

The cosmological constant problem sits at an unusual intersection.
General relativity tells us that spacetime responds to energy and
pressure. Quantum field theory tells us that vacuum states carry energy
and that their contributions change when the microscopic theory changes.
Cosmology tells us that the effective vacuum energy is tiny, positive,
and dynamically important today.

The tension is not simply that a number is small. It is that the
quantity appears to be sensitive to every energy scale in the theory,
while observation asks for an almost perfect cancellation that remains
stable across the history of the Universe.

Anthropic reasoning offers a striking possibility: perhaps the observed
value is not typical of all vacua, but typical among the rare vacua
where galaxies and observers can exist. Dynamical fields, modified
gravity, unimodular theories, sequestering, and causal-set ideas offer
different ways to change the underlying physics. None has yet become
the accepted answer.

There is also a possibility that the question itself is pointing in
the wrong direction. Perhaps vacuum energy is not what gravitates in
the naive way suggested by combining quantum field theory with general
relativity. Perhaps the cosmological constant is emergent, or the
observed acceleration is not a cosmological constant at all.

That is why the problem remains so important. It may be telling us that
one of our most successful theories is incomplete, not because it fails
where we have tested it, but because we do not yet understand how its
most basic ingredients fit together.

## References

[^1]: S. Weinberg, "The Cosmological Constant Problem," *Reviews of Modern
  Physics* **61**, 1–23 (1989).
  https://doi.org/10.1103/RevModPhys.61.1

[^2]: S. M. Carroll, "The Cosmological Constant," *Living Reviews in
  Relativity* **4**, 1 (2001).
  https://doi.org/10.12942/lrr-2001-1

[^3]: V. Sahni, "The Cosmological Constant Problem and Quintessence,"
  *Classical and Quantum Gravity* **19**, 3435–3448 (2002).
  https://doi.org/10.1088/0264-9381/19/13/304

[^4]: N. Craig, "Naturalness: Past, Present, and Future,"
  *European Physical Journal C* **83**, 825 (2023).
  https://doi.org/10.1140/epjc/s10052-023-11928-7

[^5]: P. J. E. Peebles and B. Ratra, "The Cosmological Constant and Dark
  Energy," *Reviews of Modern Physics* **75**, 559–606 (2003).
  https://doi.org/10.1103/RevModPhys.75.559

[^6]: S. Weinberg, "Anthropic Bound on the Cosmological Constant,"
  *Physical Review Letters* **59**, 2607–2610 (1987).
  https://doi.org/10.1103/PhysRevLett.59.2607

[^7]: S. Weinberg, "A Priori Probability Distribution of the Cosmological
  Constant," *Physical Review D* **61**, 103505 (2000).
  https://doi.org/10.1103/PhysRevD.61.103505

[^8]: T. Sudoh, T. Totani, R. Makiya, and M. Nagashima, "Testing Anthropic
  Reasoning for the Cosmological Constant with a Realistic Galaxy Formation
  Model," *Monthly Notices of the Royal Astronomical Society* **464**,
  1563–1568 (2017).
  https://doi.org/10.1093/mnras/stw2401

[^9]: R. Bousso and J. Polchinski, "Quantization of Four-form Fluxes and
  Dynamical Neutralization of the Cosmological Constant," *Journal of
  High Energy Physics* **2000** (06), 006 (2000).
  https://doi.org/10.1088/1126-6708/2000/06/006

[^10]: E. J. Copeland, M. Sami, and S. Tsujikawa, "Dynamics of Dark
  Energy," *International Journal of Modern Physics D* **15**, 1753–1936
  (2006). https://doi.org/10.1142/S021827180600942X

[^11]: "Modified Gravity Approaches to the Cosmological Constant Problem,"
  *Universe* **9**, 63 (2023).
  https://doi.org/10.3390/universe9020063

[^12]: P. Jiroušek, "Unimodular Approaches to the Cosmological Constant
  Problem," *Universe* **9**, 131 (2023).
  https://doi.org/10.3390/universe9030131

[^13]: N. Kaloper and A. Padilla, "Vacuum Energy Sequestering: The Framework
  and Its Cosmological Consequences," *Physical Review D* **90**, 084023
  (2014).
  https://doi.org/10.1103/PhysRevD.90.084023

[^14]: S. Das, A. Nasiri, and Y. K. Yazdi, "Aspects of Everpresent
  Lambda. Part I: A Fluctuating Cosmological Constant from Spacetime
  Discreteness," *Journal of Cosmology and Astroparticle Physics*
  **2023** (10), 047 (2023).
  https://doi.org/10.1088/1475-7516/2023/10/047
  See also J. D. Barrow, "Strong Constraint on Ever-Present Lambda,"
  *Physical Review D* **75**, 067301 (2007).
  https://doi.org/10.1103/PhysRevD.75.067301

[^15]: X. Zhang, "Diagnosing Dark Energy in the Post-DESI Era: From Effective
  Dynamics to Multi-Probe Consistency Tests," *Science China Physics,
  Mechanics & Astronomy* **69**, 120401 (2026).
  https://doi.org/10.1007/s11433-026-3116-4

[^16]: DES Collaboration, "The Dark Energy Survey Supernova Program: A
  Reanalysis of Cosmology Results and Evidence for Evolving Dark Energy
  with an Updated Type Ia Supernova Calibration," *Monthly Notices of the
  Royal Astronomical Society* **548**, stag632 (2026).
  https://doi.org/10.1093/mnras/stag632
