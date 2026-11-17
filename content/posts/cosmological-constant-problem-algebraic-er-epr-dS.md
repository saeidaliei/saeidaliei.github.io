---
title: "CC Problem and ER=EPR in dS"
date: 2026-11-17
---
First the cosmological constant problem: why is the gravitational
effect of the vacuum so extraordinarily small compared with the energy
scales suggested by quantum field theory?

Second the ER=EPR question: what is the relationship between quantum
entanglement and the connectivity of spacetime?

The first concerns the value of a parameter in the gravitational field
equations. The second concerns the structure of quantum correlations and
the emergence of geometry. Yet in de Sitter space, where there is no
spatial asymptotic boundary and physical descriptions are naturally tied
to observers, these questions may intersect in an interesting way.

The central idea explored here is that **the algebra of observables
accessible to an observer may provide a principled description of the
causal region, information and entropy relevant to cosmological selection**.
The cosmological constant would then enter not only through the curvature
of spacetime, but also through the observer's horizon, thermal scale and
accessible algebra.

This is not a proposed solution of the cosmological constant problem.
It is an attempt to identify a mathematical framework in which the
observer, quantum information and cosmological geometry can be studied
together. The distinction between established results and conjectures will be
important throughout.

## 1. The cosmological constant problem

Einstein's field equations can be written as

$$
G_{\mu\nu}+\Lambda g_{\mu\nu} =
8\pi G_N T_{\mu\nu}.
$$

The cosmological constant can equivalently be moved to the matter side
of the equation and interpreted as a vacuum-energy density:

$$
\rho_\Lambda = \frac{\Lambda}{8\pi G_N}.
$$

The problem is not simply that this quantity is small. The difficulty
is that quantum field theory permits large contributions to vacuum
energy, including contributions associated with massive fields and
vacuum phase transitions. Once gravity is included, these contributions
must be reconciled with the extraordinarily small observed effective
vacuum density.[^1]

A schematic expression is

$$
\rho_{\Lambda,\mathrm{eff}} =
\rho_{\Lambda,\mathrm{bare}}
+
\rho_{\mathrm{loops}}
+
\rho_{\mathrm{phase\ transitions}}
+\cdots.
$$

A counterterm can be chosen so that the sum agrees with observation.
The difficulty is explaining why this cancellation is so precise and
why it remains stable under quantum corrections.

There are several logically distinct questions:

1. Why is the effective vacuum energy so small?
2. Why is it positive rather than exactly zero?
3. Why is its value stable under radiative corrections?
4. Why does it become dynamically important around the present
   cosmological epoch?

These are related, but a proposal addressing one does not automatically
solve the others.[^1]
The distinction will matter below. A theory might provide a probability
distribution for different cosmological constants without explaining
radiative stability. Conversely, a theory might make vacuum-energy
contributions insensitive to gravity without selecting the observed
positive value.

## 2. From entanglement to algebraic connectivity

The original ER=EPR proposal associates quantum entanglement with
geometric connectivity. Its familiar example is the thermofield double
state of two quantum systems, whose gravitational description can be a
two-sided black hole connected by an Einstein–Rosen bridge.[^2]
However, entanglement magnitude alone cannot characterize connectivity.
A system can possess parametrically large entanglement without its
semiclassical bulk being connected.

Engelhardt and Liu proposed an algebraic refinement of ER=EPR. Rather
than classifying connectivity only through entanglement entropy, they
use the operator-algebraic structure of the systems.[^3]

A von Neumann algebra is classified, in part, by its type:

- Type I algebras admit ordinary density-matrix descriptions and
  behave like familiar matrix algebras.
- Type II algebras admit faithful normal semifinite traces and have
  a continuous dimension theory.
- Type III algebras have no faithful normal semifinite trace.

The algebraic ER=EPR proposal associates these structures with bulk
connectivity in a specific large-\$N\$, semiclassical holographic
setting. In particular, type I algebras are associated with
disconnected systems, while type III\$_1\$ algebras play a central
role in the description of classical wormhole connectivity.
The proposal also distinguishes classical wormholes from quantum
wormholes, where there is no stable classical geometry.[^3]

The important qualification is that this is not a universal theorem
saying that the abstract type of any two von Neumann algebras
determines whether an arbitrary spacetime is connected. The holographic
setting, the physical representation and the classicality assumptions
are essential.

Nevertheless, the conceptual shift is significant:

$$
\boxed{
\text{Entanglement magnitude}
\quad\longrightarrow\quad
\text{Operator-algebraic structure}.
}
$$

The question becomes not merely how much two systems are entangled,
but how their observable algebras are represented, embedded and
related to one another.
That distinction is especially relevant to de Sitter space.

## 3. Why de Sitter changes the algebraic question

Anti-de Sitter space has a spatial asymptotic boundary. In AdS/CFT,
the boundary theory supplies a relatively clear starting point for
identifying the observable algebra.
De Sitter space is different. It has no analogous spatial asymptotic
boundary on which one can simply place the complete theory.

Instead, an observer naturally describes a static patch bounded by
a cosmological horizon. Different observers have different causal
patches, and therefore different accessible observables.

This changes the question:

**Which algebra should represent the physical system when the
observer is itself part of the quantum description?**

### 3.1 The static-patch algebra

In continuum quantum field theory, the local algebra associated with
a suitable spacetime region is generically a type III factor, often
type III\$_1\$.[^4]
Such an algebra has no ordinary density matrix or local von Neumann
entropy in the familiar finite-dimensional sense.

The de Sitter static patch therefore presents an algebraic problem:
how do we define a gravitationally meaningful entropy for an observer
whose observable algebra is not a type I algebra?

### 3.2 The observer and the crossed product

Chandrasekaran, Longo, Penington and Witten addressed this problem
by including an observer's clock in the construction of the
static-patch algebra.
The crossed-product construction produces a type II\$_\infty\$
algebra, and an appropriate positive-energy restriction gives
a type II\$_1\$ algebra.

The latter admits a normalized trace and a corresponding entropy.
For semiclassical states, this entropy agrees with generalized
entropy, up to a state-independent additive constant:

$$
S_{\mathrm{gen}} =
\frac{A}{4G_N}+S_{\mathrm{out}}.
$$

The empty de Sitter state is the maximum-entropy state in their
construction.[^5]
The observer is therefore not simply an external device used to
describe an otherwise observer-independent algebra. The clock
participates in defining the algebra itself.

### 3.3 Covariant observers and fluctuating regions

A particularly relevant development is the construction of Chen
and Xu, *An Algebra for Covariant Observers in de Sitter Space*.

Their central observation is that a fixed static patch is not
preserved by every de Sitter isometry. To implement the full
SO(1,d) constraints, they promote the observer's geodesic to
a quantum degree of freedom.

The observer is described using a reference-frame Hilbert space

$$
\mathcal H_{\mathrm{obs}}=L^2(SO(1,d)).
$$

The observer is consequently in a superposition of geodesics, and
the associated static patch fluctuates.
The gauge-invariant algebra is an averaged modular crossed-product
algebra over these fluctuating patches. The authors construct a
faithful normal trace and establish that the resulting algebra
is type II. For multiple observers, the algebra has a nontrivial
center.[^6]

In the multi-observer construction, the type is more specifically
type II\$_\infty\$. This should not be confused with the type II\$_1\$
algebra obtained by the positive-energy restriction in the
single-observer CLPW construction.

The center contains projections of the schematic form

$$
P_{a\leftarrow b},
$$

which encode whether, and over which parts of a trajectory,
observer \$b\$ is visible to observer \$a\$.

These projections provide an algebraic description of relational
causal accessibility.
They do not, by themselves, establish the existence of an
Einstein–Rosen bridge.
This is an important distinction. The causal structure of two
observer patches and the quantum connectivity of their observable
algebras are related questions, but they are not identical.

## 4. The center, relative information and the measure problem

The nontrivial center of the multi-observer algebra is particularly
interesting because it decomposes the algebra into sectors.

Schematically, suppose we have a family of algebras

$$
\mathcal A =
\int^\oplus
\mathcal A_\lambda\,d\mu_0(\lambda),
$$

where the parameter \$\lambda\$ will eventually be identified
with a cosmological-constant sector.

An operator in the center acts by multiplication on these sectors.

There is a subtlety here: in the Chen–Xu construction,
\$\Lambda\$ is not itself a central operator. Their construction
sets the de Sitter radius to one. A family of different
cosmological-constant sectors would have to be introduced
as an extension of their theory.

### 4.1 Trace normalization is not a probability distribution

Suppose each fibre admits a faithful normal semifinite trace
\$\tau_\lambda\$. We can define a new trace on the direct-integral
algebra:

$$
\tau_N(A) =
\int d\mu_0(\lambda)\,
N(\lambda)\tau_\lambda(A_\lambda),
$$

where \$N(\lambda)>0\$ is a central normalization factor.

Changing this factor changes absolute entropy. If a state has
 density \$h\$ relative to the original trace, then its density
relative to the rescaled trace is \$h/N\$. Consequently,

$$
S_{\tau_N}(\omega) =
S_{\tau}(\omega) +
\int d p_\omega(\lambda)\log N(\lambda).
$$

But relative entropy is different.

For two normal states \$\omega\$ and \$\sigma\$, Araki relative
entropy is a property of the pair of states on the algebra.
It does not depend on an arbitrary rescaling of the trace.

For a direct-integral decomposition, it has the schematic form

$$
D(\omega\Vert\sigma) =
D(p_\omega\Vert p_\sigma) +
\int d p_\omega(\lambda)\,
D_\lambda(\omega_\lambda\Vert\sigma_\lambda).
$$

Thus common central trace rescalings cannot be determined by
relative entropy alone.[^7]

This is a genuine structural limitation.

It means that imposing consistency of relative modular data
between observers will not, by itself, determine the relative
normalization of different cosmological sectors.

There is also an important conceptual distinction:

- A central state distribution \$p(\lambda)\$ describes how
  likely different sectors are in a physical state.
- A trace normalization \$N(\lambda)\$ specifies how absolute
  entropy is normalized across those sectors.

They are not automatically the same thing.

The algebraic construction does not supply a physical prior
over cosmological constants merely because it has a center.

## 5. The Henneaux–Teitelboim connection:
### Cosmological constant and four-volume

There is another place where the cosmological constant enters
naturally: unimodular gravity.

In the Henneaux–Teitelboim (HT) formulation, the cosmological
constant appears as a constant of motion rather than simply
as a fixed parameter in the action.[^8]

Introduce a vector density \$V^\mu\$, and define

$$
\kappa=8\pi G_N.
$$

A convenient form of the action is

$$
\begin{aligned}
S_{\mathrm{HT}}
={}&
\frac{1}{16\pi G_N}
\int d^4x\sqrt{-g}\,R\\
&+
\frac{1}{\kappa}
\int d^4x\,
\Lambda
\left(
\partial_\mu V^\mu-\sqrt{-g}
\right)
+S_{\mathrm{matter}}.
\end{aligned}
$$

Variation with respect to \$V^\mu\$ gives

$$
\partial_\mu\Lambda=0.
$$

Thus the cosmological constant is constant on shell.

Variation with respect to \$\Lambda\$ gives

$$
\partial_\mu V^\mu=\sqrt{-g}.
$$

Define the spatial integral

$$
T_4(t)=\int_{\Sigma_t}d^3x\,V^0.
$$

For a spacetime region bounded by two hypersurfaces,

$$
\Delta T_4 =
\int d^4x\sqrt{-g}.
$$

The change in \$T_4\$ is the accumulated spacetime four-volume.

The corresponding canonical term is

$$
S_{\mathrm{symp}} =
\frac{1}{\kappa}
\int dt\,\Lambda\dot T_4.
$$

Hence

$$
P_{T_4}=\frac{\Lambda}{8\pi G_N},
$$

and, formally,

$$
\boxed{\{T_4,\Lambda\}=8\pi G_N.}
$$

With canonical quantization, the corresponding formal commutator is

$$
[\hat T_4,\hat\Lambda] =
i\,8\pi G_N.
$$

The cosmological constant is conjugate to a global spacetime
four-volume variable.

There is an important qualification. In covariant HT gravity,
the four-form variable is not automatically ordinary Schrödinger
time. Buchmüller and Dragon explain that the cosmic-time
interpretation emerges semiclassically; the quantum state still
satisfies the Wheeler–DeWitt equation.[^9]

This matters because it prevents us from treating \$T_4\$ as
an ordinary local clock without specifying the quantum state,
boundary conditions and approximation.

### 5.1 What happens to vacuum energy?

Add a constant vacuum-energy density:

$$
S_{\mathrm{vac}} =
-\rho_{\mathrm{vac}}
\int d^4x\sqrt{-g}.
$$

The metric-dependent cosmological term can be rewritten using

$$
\Lambda_{\mathrm{eff}} =
\Lambda+\kappa\rho_{\mathrm{vac}}.
$$

The full action then satisfies

$$
S_{\mathrm{HT}}+S_{\mathrm{vac}} =
S_{\mathrm{HT}}[\Lambda_{\mathrm{eff}}] -
\rho_{\mathrm{vac}}\Delta T_4.
$$

In a Lorentzian path integral, the extra boundary contribution
produces a phase

$$
\exp(-i\rho_{\mathrm{vac}}\Delta T_4).
$$

This shows how a constant vacuum-energy contribution can be
represented as a shift of the effective integration constant
together with a four-volume phase.

However, this is not automatically a solution of the
cosmological constant problem. If the integration constant is
fixed by boundary or initial data, the shift still affects
the effective cosmological constant.

The physical question becomes how the global zero mode and
the boundary conditions are treated.

Unimodular gravity changes the status of \$\Lambda\$, but
does not automatically explain its observed value.[^9][^10]

## 6. De Sitter thermodynamics:
### the cosmological constant as an observer's scale

The HT construction becomes especially interesting when
combined with de Sitter observer thermodynamics.

For four-dimensional de Sitter space,

$$
R_{\mathrm{dS}} =
\sqrt{\frac{3}{\Lambda}}.
$$

The Gibbons–Hawking temperature of a static observer is

$$
T_{\mathrm{dS}} =
\frac{1}{2\pi R_{\mathrm{dS}}},
$$

and the horizon entropy is

$$
S_{\mathrm{dS}} =
\frac{A_{\mathrm{dS}}}{4G_N} =
\frac{3\pi}{G_N\Lambda}.
$$

Eliminating the de Sitter radius gives

$$
\boxed{\Lambda=12\pi^2T_{\mathrm{dS}}^2.}
$$

Thus the cosmological constant determines the thermal scale
experienced by a static observer.

If the observer's state is KMS at inverse temperature
\$\beta_{\mathrm{dS}}\$, its modular automorphism group is
related to physical time evolution by

$$
\sigma_s^\omega =
\alpha_{\beta_{\mathrm{dS}}s}^\omega,
$$

up to the sign convention.

The modular parameter \$s\$ is dimensionless. Physical proper
time is calibrated by the inverse temperature.

This gives us three distinct notions of time:

1. Observer proper time, measured along a geodesic.
2. Modular time, generated by the state and observable algebra.
3. HT four-volume time, conjugate to the cosmological constant.

They should not be identified with one another.

However, a quantum state with different \$\Lambda\$-sectors
would also have different modular thermal scales. This makes
the observer's clock a natural way to formulate relational
comparisons between cosmological sectors.

The unresolved problem is how to construct the physical
Hilbert-space maps between those sectors. The Chen–Xu
construction itself treats a fixed de Sitter radius.

## 7. Horizon corners and the geometry of observer space

There is another potentially useful connection.

In gravitational edge-mode theory, the area of a codimension-two
corner is conjugate to a relative Lorentzian boost angle
\$\eta\$ between its normal frames.

The corner symplectic form takes the form

$$
\Omega_{\mathrm{corner}} =
\frac{1}{8\pi G_N}\,
\delta A\wedge\delta\eta.
$$

The corresponding momentum is

$$
p_\eta=\frac{A}{8\pi G_N}.
$$

For the de Sitter cosmological horizon,

$$
p_\eta =
\frac{A_{\mathrm{dS}}}{8\pi G_N} =
\frac{S_{\mathrm{dS}}}{2\pi}.
$$

This is a striking relation: the same entropy that characterizes
the de Sitter horizon is proportional to the momentum conjugate
to the normal-frame boost.[^11]

The space of oriented timelike geodesics in four-dimensional
de Sitter can be represented as

$$
\mathcal G_{\mathrm{geo}} =
\frac{SO_0(1,4)}{SO_0(1,1)\times SO(3)}.
$$

This is a six-dimensional homogeneous space.

The coadjoint-orbit construction suggests a natural symplectic
form on this space, with a possible level

$$
c=\frac{A_{\mathrm{dS}}}{8\pi G_N}.
$$

This is a promising mathematical connection between the
gravitational horizon corner and the quantum reference frame
of a de Sitter observer.

But the physical identification is not yet derived from the
complete joint gravitational and observer action. We must
derive the moving-horizon boundary terms and avoid counting
the same gravitational surface charge twice.

There is also a useful negative result. Two oppositely
oriented observer orbits, by themselves, can reduce to a
single point after imposing the common de Sitter constraint.
Matter and clock degrees of freedom are needed for nontrivial
physical relative observables.

So the horizon orbit is not, by itself, an entanglement
mechanism or a wormhole criterion.

## 8. The spectral-geometric perspective

Noncommutative geometry offers another way to express the
curvature scale.

The Euclidean continuation of four-dimensional de Sitter
space is the round four-sphere \$S^4_R\$.

For the ordinary spin Dirac operator on this sphere, the
eigenvalues are

$$
\lambda_n^\pm =
\pm\frac{n+2}{R},
\qquad n=0,1,\ldots.
$$

The smallest absolute eigenvalue is

$$
\lambda_{\min}=\frac{2}{R}.
$$

Since \$R^2=3/\Lambda\$,

$$
\boxed{\Lambda=\frac{3}{4}\lambda_{\min}^2.}
$$

This is an exact relation for the round four-sphere.
It demonstrates that the Dirac spectrum encodes the curvature
scale of a specified de Sitter geometry.
But it does not select that geometry.
The spectral action has the schematic form

$$
S_{\mathrm{spec}}[D] =
\operatorname{Tr}
f\left(\frac{D}{\Lambda_{\mathrm{cut}}}\right),
$$

where \$\Lambda_{\mathrm{cut}}\$ is a spectral cutoff,
not the cosmological constant.
In four dimensions its heat-kernel expansion contains terms
of the form

$$
S_{\mathrm{spec}}
\sim
f_4\Lambda_{\mathrm{cut}}^4a_0
+
f_2\Lambda_{\mathrm{cut}}^2a_2
+
f_0a_4+\cdots.
$$

The leading coefficient is related to volume, the next
contains curvature, and higher terms contain curvature
combinations.[^12]

This is useful for reconstructing or studying geometry once
a spectral triple is specified.

It does not, by itself, determine which value of \$R\$ or
\$\Lambda\$ the universe should occupy.

The distinction is important:

$$
\boxed{
\text{Algebra and representation}
\longrightarrow \text{relational structure},
}
$$

$$
\boxed{
D
\longrightarrow \text{spectral geometry},
}
$$

$$
\boxed{
\text{Quantum state and dynamics}
\longrightarrow \text{sector selection}.
}
$$

The Dirac operator can measure the curvature of a de Sitter
sector. It does not supply the probability of occupying that
sector without additional dynamics.

## 9. The observer-weighting idea:
### A bridge to the causal entropic principle

This is perhaps the most promising connection between
algebraic ER=EPR and the cosmological constant problem.

The causal entropic principle proposes that cosmological
parameters should be weighted by the entropy produced within
a causally connected region.

Bousso, Harnik, Kribs and Perez used this principle to
construct an observer-weighted probability distribution for
the cosmological constant. In their calculation, entropy
production from dust heated by stars dominates the weighting.[^13]

The observer's causal diamond is therefore not merely a
geometrical object. It is the region in which the relevant
entropy production is counted.

This is precisely the kind of region described by the
de Sitter observer algebra.

Let \$\mathcal A_a\$ denote the algebra accessible to observer
\$a\$, and let

$$
\mathcal N_{ab}=\mathcal A_a\cap\mathcal A_b
$$

denote the algebra shared by two observers, where the
intersection is defined in a common physical representation.

The shared algebra provides a candidate notion of
intersubjective accessibility: the observables that both
observers can measure.

For a non-equilibrium state \$\omega_t\$, one might attempt
to define an observer entropy production

$$
\Delta S_a(t) =
S_{\mathrm{cg}}
\left(\omega_t|_{\mathcal A_a}\right) -
S_{\mathrm{cg}}
\left(\omega_0|_{\mathcal A_a}\right).
$$

Likewise, the common observer entropy production would be

$$
\Delta S_{ab}(t) =
S_{\mathrm{cg}}
\left(\omega_t|_{\mathcal N_{ab}}\right) -
S_{\mathrm{cg}}
\left(\omega_0|_{\mathcal N_{ab}}\right).
$$

The subscript \$\mathrm{cg}\$ is important. It indicates
that a coarse-graining prescription is required.

For type III algebras, ordinary von Neumann entropy is
not available without a regulator or additional structure.
Relative entropy remains well-defined for suitable normal
states:

$$
D_{\mathcal A}(\omega\Vert\sigma) =
S_{\mathcal A}(\omega\Vert\sigma).
$$

It can measure how distinguishable two states are using
only the observables in \$\mathcal A\$.

But relative entropy is not automatically thermodynamic
entropy production. A dynamical model and a coarse-graining
prescription are still required.

### 9.1 What our toy model actually showed

We tested this idea in a finite-dimensional model consisting
of two observers on a ring, with a quantum label describing
their relative position.

We constructed their observable algebras and their common
algebra, then evolved the system with random two-site
unitaries.

The entropy production measured through the shared algebra
was smaller than that measured by either observer separately.
When the regions had no overlap, the shared entropy production
vanished.

The late-time results agreed with the ordinary finite-size
Page entropy of the overlap region.

This is a useful negative result. In that model, shared
entropy production was simply the entropy production of the
common subsystem. It did not reveal additional wormhole
structure.

It does not prove that the same result holds in continuum
de Sitter quantum gravity. The toy model is type I and does
not reproduce the full Chen–Xu crossed-product construction.

Nevertheless, it tells us what a successful algebraic
proposal must improve upon: it must identify information
shared by observers that cannot be reduced to ordinary
geometric overlap.

### 9.2 A possible observer-weighting functional

A candidate connection to the causal entropic principle
would be

$$
W_{\mathrm{obs}}(\Lambda) =
\int_{\mathcal D_a(\Lambda)}
d^4x\sqrt{-g}\,
\sigma_{\mathrm{prod}}(x),
$$

where \$\mathcal D_a(\Lambda)\$ is the observer's causal
diamond and \$\sigma_{\mathrm{prod}}\$ is a coarse-grained
entropy-production density.

The observer algebra could determine which observables
are accessible within the diamond, while matter dynamics
would determine the entropy production.

A probability distribution could then take the form

$$
p_{\mathrm{obs}}(\Lambda)
\propto
p_{\mathrm{prior}}(\Lambda)
N(\Lambda)
W_{\mathrm{obs}}(\Lambda).
$$

Here:

- \$p_{\mathrm{prior}}\$ is the distribution supplied by
  the underlying theory.
- \$N(\Lambda)\$ is a relative sector-normalization factor,
  if a common Hilbert-space or path-integral prescription
  defines one.
- \$W_{\mathrm{obs}}\$ is the observer weighting.

The algebraic contribution would be to define the
observer-accessible coarse-graining more precisely.

It would not automatically determine the prior or the
entropy-production dynamics.

This is where the causal entropic principle and
algebraic ER=EPR could genuinely complement one another.

## 10. Why the usual Euclidean weighting does not solve the problem

The Euclidean de Sitter saddle gives a familiar candidate
weight.

For a round four-sphere,

$$
I_E(S^4)=-S_{\mathrm{dS}} = -\frac{3\pi}{G_N\Lambda}.
$$

The formal semiclassical saddle contribution is therefore

$$
e^{-I_E} =
e^{S_{\mathrm{dS}}} = 
\exp\left(\frac{3\pi}{G_N\Lambda}\right).
$$

If this is interpreted naively as a probability weight
over positive cosmological constants, it diverges as
\$\Lambda\rightarrow0^+\$.

Indeed,

$$
\int_0^\epsilon d\Lambda\,
\exp\left(\frac{3\pi}{G_N\Lambda}\right)
$$

does not converge.

This is the familiar Baum–Hawking difficulty.

There are deeper issues as well. The gravitational Euclidean
path integral has contour and conformal-factor problems,
and a saddle contribution cannot simply be identified with
a normalized probability distribution.

Thus the factor \$e^{S_{\mathrm{dS}}}\$ is a useful
baseline for discussing possible cosmological measures,
but it is not a derived physical prior.[^14]

The same caution applies to proposals involving
baby universes and \$\alpha\$-parameters. Their interpretation
in higher-dimensional quantum gravity remains actively
debated, and should not be assumed to provide a unique
measure over cosmological constants.[^15]

## 11. What have we actually established?

It is worth separating the results from the ideas that remain
conjectural.

### Established ingredients

1. The algebraic ER=EPR proposal replaces entanglement magnitude
   with a structural analysis of observable algebras in its
   specified holographic setting.

2. A gravitationally dressed de Sitter static-patch algebra
   can be constructed as a type II$_1$ algebra, with entropy
   matching generalized entropy up to an additive constant.[^5]

3. A covariant multi-observer construction in de Sitter
   produces a fluctuating-region algebra of type II with
   a nontrivial center encoding causal accessibility.[^6]

4. In Henneaux–Teitelboim gravity, the cosmological constant
   is conjugate to a global four-volume variable.[^8]

5. De Sitter horizon entropy, thermal scale and curvature
   radius are related by

   $$
   R^2=\frac{3}{\Lambda},
   \qquad
   T_{\mathrm{dS}}=\frac{1}{2\pi R},
   \qquad
   S_{\mathrm{dS}}=\frac{3\pi}{G_N\Lambda}.
   $$

6. Relative entropy is insensitive to common central
   trace rescalings. Consequently, modular consistency
   alone cannot determine an arbitrary relative normalization
   of cosmological sectors.

### Proposed connections

1. A family of observer algebras over different cosmological
   constants could describe a quantum state spread over
   different de Sitter radii.

2. The HT four-volume variable could provide a global
   relational clock shared by multiple observers.

3. Gravitational horizon-corner symplectic structures may
   induce a coadjoint-orbit geometry on the space of
   observer geodesics.

4. Relative entropy and common observer algebras may provide
   a quantum definition of the coarse-graining region used
   in causal-entropic selection.

5. The algebraic observer framework may help distinguish
   observer-dependent information from information that
   is genuinely shared between observers.

These proposals need to be derived from a common constrained
quantum-gravitational model. They are not yet consequences
of the cited constructions.

## 12. What has not been solved

Despite the mathematical structure developed above, we have
not derived the observed value of the cosmological constant.

We have not shown that:

- The HT measure is normalizable over positive
  cosmological constants.
- The observer algebra fixes a prior over \$\Lambda\$.
- The horizon-corner orbit selects a preferred value.
- Relative modular consistency determines cross-sector
  normalization.
- The entropy of a shared algebra generates a new
  observer-selection mechanism.
- The spectral action selects the observed de Sitter radius.

Several tempting routes have actually produced useful
negative results.

The distinction between type and state has ruled out the
idea that changing entanglement alone changes the algebraic
connectivity class of a finite-dimensional model.

The trace-rescaling analysis showed that relative modular
data cannot determine an arbitrary central normalization.

The ring model showed that shared entropy production can
reduce to ordinary overlap entropy.

The simple HT-plus-observer models have not produced a
normalizable distribution peaked at the observed
cosmological constant.

And the entropy-weighted coadjoint orbit remains a candidate
geometric structure, not a derived mechanism for selecting
\$\Lambda\$.

These negative results narrow the space of plausible
directions. They are not solutions, but they help identify
which assumptions must be changed.

## 13. The research direction: a quantum measure over observers

The most promising question emerging from this programme
is not whether algebraic ER=EPR directly determines the
cosmological constant.

It is whether a relational observer algebra can provide
the correct physical framework for defining the measure
over cosmological sectors.

The desired structure would contain

$$
\boxed{
\begin{gathered}
\text{Global cosmological variable:}
\quad
(\Lambda,T_4),\\[2mm]
\text{Observer algebra:}
\quad
\mathcal A_a(\Lambda),\\[2mm]
\text{Shared observables:}
\quad
\mathcal N_{ab}(\Lambda) =
\mathcal A_a(\Lambda)\cap\mathcal A_b(\Lambda),\\[2mm]
\text{Physical state:}
\quad
\Psi(\Lambda,\text{observers},\text{matter}).
\end{gathered}
}
$$

The state would determine how the cosmological sectors are
populated. The observer algebras would determine what
information can be accessed in each sector. The global
four-volume variable would relate the cosmological constant
to a relational notion of time.

The main task would be to derive the measure, rather than
postulate one.

A concrete calculation would begin with a joint
HT-plus-observer path integral,

$$
Z =
\int
\mathcal Dg\,
\mathcal DV\,
\mathcal D\Lambda\,
\mathcal D(\text{observers})\,
 e^{iS_{\mathrm{HT}}+iS_{\mathrm{observer}}}.
$$

One would then:

1. Impose the full de Sitter gravitational constraints.
2. Include the observer clock and its causal-patch algebra.
3. Derive the horizon boundary and corner terms without
   double-counting gravitational charges.
4. Integrate over the global four-volume mode.
5. Derive the measure over cosmological-constant sectors.
6. Determine whether the observer-dependent entropy
   production changes that measure.

The decisive outcome would be a factor

$$
Z =
\int d\Lambda\,
p_{\mathrm{prior}}(\Lambda)
N(\Lambda)
W_{\mathrm{obs}}(\Lambda)
Z_{\mathrm{grav}}(\Lambda),
$$

where every factor follows from a specified physical
construction rather than being independently chosen.

Only then would it make sense to ask whether the resulting
distribution is normalizable, whether it is stable under
quantum corrections, and whether it can peak near the
observed positive cosmological constant.

## Conclusion

The connection between algebraic ER=EPR and the cosmological
constant problem is not yet a solution of either problem.

What it offers is a different way of organizing the questions.

In de Sitter space, the observer is structurally important.
Its clock defines a relational reference frame, its causal
patch determines which observables are accessible, and its
horizon carries a thermodynamic entropy.

Unimodular gravity adds another layer: the cosmological
constant is conjugate to a global four-volume variable.
The observer's proper time calibrates how that volume
accumulates, while modular theory relates the observer's
state to the thermal structure of the static patch.

The possible synthesis is therefore

$$
\boxed{
\begin{aligned}
\text{Observer algebra}
&\longrightarrow \text{accessible information},\\
\text{Modular structure}
&\longrightarrow \text{thermal and relational time},\\
\text{HT gravity}
&\longrightarrow \text{volume--}\Lambda\text{ conjugacy},\\
\text{Observer dynamics}
&\longrightarrow \text{entropy production and selection}.
\end{aligned}
}
$$

The missing ingredient is the physical state or measure over
the different cosmological sectors.

My current view is that algebraic ER=EPR is a promising
language for understanding the relational structure of
de Sitter quantum gravity. Its contribution to the
cosmological constant problem may lie in defining what an
observer can access and how information is shared between
observers, rather than in producing the numerical value
of \$\Lambda\$ directly.

The next step is therefore not another attempt to extract
the cosmological constant from an algebraic type or a
Dirac eigenvalue. It is to derive the quantum measure over
observer-accessible cosmological sectors from a common
gravitational theory.

That is where the observer, the algebra and the cosmological
constant may finally become parts of the same problem.

## References

[^1]: S. Weinberg, "The Cosmological Constant Problem,"
    *Reviews of Modern Physics* 61, 1–23 (1989).
    https://doi.org/10.1103/RevModPhys.61.1

[^2]: J. Maldacena and L. Susskind, "Cool Horizons for
    Entangled Black Holes," Fortschritte der Physik 61,
    781–811 (2013).
    https://arxiv.org/abs/1306.0533

[^3]: N. Engelhardt and H. Liu, "Algebraic ER=EPR and
    Complexity Transfer," JHEP 07 (2024) 013.
    https://arxiv.org/abs/2311.04281

[^4]: J. Yngvason, "The Role of Type III Factors in
    Quantum Field Theory," Reports on Mathematical Physics
    55, 135–147 (2005).
    https://arxiv.org/abs/math-ph/0411058

[^5]: V. Chandrasekaran, R. Longo, G. Penington and
    E. Witten, "An Algebra of Observables for de Sitter
    Space," JHEP 02 (2023) 082.
    https://arxiv.org/abs/2206.10780

[^6]: B. Chen and J. Xu, "An Algebra for Covariant
    Observers in de Sitter Space," JHEP 09 (2026) 240.
    https://arxiv.org/abs/2511.00622

[^7]: H. Araki, "Relative Entropy of States of von Neumann
    Algebras," Publications of the Research Institute for
    Mathematical Sciences 11, 809–833 (1976).

[^8]: M. Henneaux and C. Teitelboim, "The Cosmological
    Constant as a Canonical Variable," Physics Letters B
    143, 415–420 (1984).
    https://doi.org/10.1016/0370-2693(84)91493-X

[^9]: W. Buchmüller and N. Dragon, "The Cosmological
    Constant as a Boundary Term," JHEP 08 (2022) 167.
    https://arxiv.org/abs/2203.15714

[^10]: P. Jiroušek, "Unimodular Approaches to the
     Cosmological Constant Problem," Universe 9, 131 (2023).
     https://arxiv.org/abs/2301.01662

[^11]: L. Freidel, M. Geiller and D. Pranzetti,
     "Edge Modes of Gravity. Part I. Corner Potentials
     and Charges," JHEP 11 (2020) 026.
     https://arxiv.org/abs/2006.12527

[^12]: A. H. Chamseddine and A. Connes,
     "The Uncanny Precision of the Spectral Action,"
     Communications in Mathematical Physics 293,
     867–889 (2010).
     https://arxiv.org/abs/0812.0165

[^13]: R. Bousso, R. Harnik, G. D. Kribs and G. Perez,
     "Predicting the Cosmological Constant from the
     Causal Entropic Principle," Physical Review D 76,
     043513 (2007).
     https://arxiv.org/abs/hep-th/0702115

[^14]: G. W. Gibbons and S. W. Hawking,
     "Action Integrals and Partition Functions in
     Quantum Gravity," Physical Review D 15, 2752 (1977).
     https://doi.org/10.1103/PhysRevD.15.2752

[^15]: D. Harlow, "Observers, Alpha-Parameters, and the
     Hartle-Hawking State," (2026).
     https://arxiv.org/abs/2602.03835
