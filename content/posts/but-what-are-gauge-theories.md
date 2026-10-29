---
title: "But What are Gauge Theories?"
date: 2026-10-29
---

The phrase *gauge theory* appears so often in modern physics that it can begin
to sound like an explanation in itself. Electromagnetism is a gauge theory.
The weak and strong interactions are gauge theories. The Standard Model is
built from them. But what, mathematically, is being gauged? What does a gauge
field actually do, and why should a choice of group such as \$\mathrm{U}(1)\$,
\$\mathrm{SU}(2)\$, or \$\mathrm{SU}(3)\$ have anything to do with the
particles we find in nature?

The shortest answer is geometric: a gauge theory is a theory in which we have
freedom to choose a local description of internal degrees of freedom, together
with a connection that tells us how to compare those descriptions at
neighboring spacetime points. The curvature of that connection is the field
strength. In a quantum field theory, the connection becomes a dynamical field,
and its geometry governs the interactions.

That answer is compact enough to be nearly useless until we unpack it. The
useful part is that the same handful of ideas—groups, representations,
connections, curvature, and invariant actions—builds both Maxwell's theory and
the non-Abelian theories of the Standard Model. The mathematics is not
identical in every case, but the architecture is remarkably reusable.[^1]

## 1. The problem with a phase that changes from place to place

Start with a charged spinor field \$\psi(x)\$, such as the electron field.
Quantum states are complex, and an overall phase does not change the
probability density. If we transform the field by a constant phase,

$$
\psi(x)\longmapsto \psi'(x)=e^{iq\alpha}\psi(x),
$$

nothing dramatic happens. Here \$q\$ is the charge in the chosen normalization
and \$\alpha\$ is a constant. The free Dirac Lagrangian,

$$
\mathcal L_0=\bar\psi(i\gamma^\mu\partial_\mu-m)\psi,
$$

is invariant under this transformation. The derivative does not care about a
constant phase because it differentiates only the spacetime dependence.

Now make one small change. Let the phase depend on position:

$$
\psi(x)\longmapsto \psi'(x)=e^{iq\alpha(x)}\psi(x).
$$

The field is rotated in its complex plane by a different amount at every
point. This is a *local* transformation. The derivative now notices the
change:

$$
\partial_\mu\psi'
=e^{iq\alpha(x)}\left[\partial_\mu\psi+iq(\partial_\mu\alpha)\psi\right].
$$

That extra term, proportional to \$\partial_\mu\alpha\$, ruins the invariance
of the free Lagrangian. The obstacle is not mysterious: an ordinary derivative
compares the value of a field at nearby points as though their phase
conventions had already been aligned. If the convention can vary from point to
point, that comparison needs extra information.

Introduce a field \$A_\mu(x)\$ and replace the ordinary derivative with a
*covariant derivative*:

$$
D_\mu=\partial_\mu-iqA_\mu.
$$

Require the new field to transform as

$$
A_\mu\longmapsto A'_\mu=A_\mu+\partial_\mu\alpha.
$$

Then the derivative term transforms cleanly:

$$
D'_\mu\psi'=e^{iq\alpha(x)}D_\mu\psi.
$$

The unwanted derivative of the phase cancels. We can therefore write a locally
invariant Lagrangian,

$$
\mathcal L=\bar\psi(i\gamma^\mu D_\mu-m)\psi
-\frac14F_{\mu\nu}F^{\mu\nu},
\qquad
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu.
$$

This is the basic structure of quantum electrodynamics. The field \$A_\mu\$ is
the electromagnetic potential, and \$F_{\mu\nu}\$ contains the electric and
magnetic fields. The interaction between the charged matter and the potential
is already present when we expand the covariant derivative. The transformation
of \$A_\mu\$ ensures that the local phase convention cannot affect the
physics.

There is an important qualification. Requiring local gauge covariance does
not, by itself, prove that nature must contain electromagnetism, nor does it
uniquely dictate every term in a Lagrangian. The requirement tells us how
matter derivatives must be modified and constrains the allowed dynamics. We
still choose the field content and action, subject to locality, spacetime
symmetry, consistency, and experiment. The gauge principle is extraordinarily
restrictive, but it is not a substitute for physics.[^3]

## 2. Is gauge symmetry a physical symmetry—or a redundancy?

This is where the language can mislead. A rotation of a physical object can
take one physical state to another. A gauge transformation, by contrast, often
changes the mathematical description without changing the physical state at
all. In electromagnetism, \$A_\mu\$ and \$A_\mu+\partial_\mu\alpha\$ describe
the same electromagnetic field strength. They are two potential descriptions
of the same configuration.

The distinction is between a *global symmetry*, which can relate physically
different states, and a *gauge redundancy*, which identifies multiple
descriptions of one state. The phase of a charged field is not independently
measurable at every spacetime point. What is meaningful is how phases are
related, and the gauge potential is part of the structure that makes those
comparisons meaningful.

This is not merely philosophical housekeeping. It explains why a gauge field
can have components that are not themselves observable, why gauge fixing is
needed in many calculations, and why physical predictions must ultimately be
gauge invariant. It also blocks a popular but imprecise slogan: gauge symmetry
does not simply mean that a force is a real rotation happening independently
at every point. The local transformations are redundancies in the description;
the curvature and its quantum consequences carry the physical content.[^3]

## 3. From a potential to geometry

The electromagnetic example generalizes. Let \$G\$ be a Lie group, and let the
field \$\psi(x)\$ transform in some representation of that group.
Infinitesimally, transformations are built from generators \$T^a\$. We collect
the gauge field into a Lie-algebra-valued object,

$$
A_\mu(x)=A^a_\mu(x)T^a,
$$

and define

$$
D_\mu=\partial_\mu-igA_\mu.
$$

The parameter \$g\$ is the coupling constant. The generators describe the
infinitesimal transformations; the representation tells us how those
transformations act on a particular kind of matter field. Yang and Mills made
the crucial non-Abelian step explicit in 1954, by asking what happens when
local isospin rotations—not just local phases—are allowed.[^2] For a
non-Abelian group, the generators need not commute:

$$
[T^a,T^b]=if^{abc}T^c,
$$

where \$f^{abc}\$ are the structure constants of the Lie algebra.

The most revealing object is the commutator of covariant derivatives:

$$
[D_\mu,D_\nu]=-igF_{\mu\nu}.
$$

With the convention above, the field strength is

$$
F_{\mu\nu}
=\partial_\mu A_\nu-\partial_\nu A_\mu
-ig[A_\mu,A_\nu].
$$

For \$\mathrm{U}(1)\$, the commutator vanishes and we recover Maxwell's field
strength. For a non-Abelian group, the extra term is essential. In components
it becomes a term quadratic in the gauge fields, weighted by the structure
constants. The gauge field contributes to its own curvature.

That is the first striking difference between electromagnetism and Yang–Mills
theory. The photon is not electrically charged, so the basic Maxwell
field-strength term contains no direct photon self-interaction. The gluons of
quantum chromodynamics carry color charge and interact with one another. The
weak gauge bosons likewise have non-Abelian interactions. This is not an
additional decorative force law bolted onto the theory; it follows from the
algebra of the group.[^4]

The geometry can be made precise using fiber bundles. Let spacetime be a
manifold \$M\$, and let \$G\$ be the gauge group. A principal bundle is
written

$$
G\longrightarrow P\xrightarrow{\pi}M.
$$

The fiber above a point \$x\in M\$ carries the internal gauge-frame
information at that point. Matter fields typically live in associated bundles,
constructed from representations of \$G\$. A *choice of gauge* is a local
choice of frame, or equivalently a local section of the bundle. Such a choice
lets us write formulas using familiar matrices and functions, but it need not
extend globally over all spacetime. This is one reason the bundle language is
more than a metaphor: it can describe global twisting that no single gauge
choice removes.[^11]

A connection is the structure that tells us how to compare neighboring fibers.
Geometrically, it specifies which directions in the total space \$P\$ count
as horizontal, so a path in spacetime can be lifted to a path in the bundle.
In a chosen local gauge, the connection is represented by the gauge-potential
one-form

$$
A=A_\mu\,dx^\mu.
$$

The local components depend on the gauge choice; the underlying connection
does not. The covariant derivative is the corresponding rule for
differentiating fields while accounting for how their internal frames vary.

The curvature is derived from the connection. In the mathematical convention
where \$D=d+A\$, its two-form is

$$
F=dA+A\wedge A.
$$

With the physics convention used above, \$D_\mu=\partial_\mu-igA_\mu\$,
the same content reads

$$
F=dA-igA\wedge A,
$$

or, in components,

$$
F_{\mu\nu}=\partial_\mu A_\nu-\partial_\nu A_\mu
-ig[A_\mu,A_\nu].
$$

The convention changes the signs and factors of \$i\$ and \$g\$, not the
underlying geometry. Curvature measures the failure of parallel transport
around an infinitesimal closed loop to return a state unchanged. Equivalently,
it is encoded in the commutator of covariant derivatives,

$$
[D_\mu,D_\nu]=-igF_{\mu\nu}.
$$

For \$\mathrm{U}(1)\$, the group is Abelian and the commutator term
vanishes, so \$F=dA\$. For a non-Abelian group, the extra term records the
fact that internal transformations in different directions need not commute.
The connection thus contributes to its own curvature.

Under a non-Abelian gauge transformation, the curvature transforms by
conjugation rather than remaining fixed component by component.
Gauge-invariant quantities can be built from it, for example by taking a
trace. The Yang–Mills action is commonly written

$$
\mathcal L_{\mathrm{YM}}=-\frac12\operatorname{tr}(F_{\mu\nu}F^{\mu\nu}),
$$

with the overall normalization depending on the convention for the generators.
The trace removes dependence on the choice of internal frame.

A useful subtlety is that vanishing curvature means there is no *local*
curvature obstruction to path-independent transport. On a spacetime with
nontrivial topology, a flat connection can still have nontrivial transport
around a large closed loop. The Aharonov–Bohm effect is a familiar physical
reminder that the potential and its global holonomy can carry information not
captured by the field strength at the particle's location.[^1]

The same geometry appears in a Wilson loop,

$$
W(C)=\operatorname{tr}\,\mathcal P\exp\!\left(ig\oint_C A_\mu\,dx^\mu\right),
$$

where \$C\$ is a closed path and \$\mathcal P\$ denotes path ordering.
This quantity records the net parallel transport around the loop. In
non-Abelian theories, path ordering matters because the group elements at
different points need not commute. Wilson loops become especially important in
the study of confinement and the non-perturbative structure of gauge
theories.[^1]

This also clarifies the relationship between gauge curvature and the curvature
of spacetime in general relativity. Both arise from connections, and both can
be expressed in the schematic form

$$
\text{curvature}=d(\text{connection}) +
(\text{connection})\wedge(\text{connection})
$$

In general relativity, the Levi-Civita connection (or a spin connection in a
frame formalism) acts on tangent vectors or spacetime spinors; its curvature
is the Riemann curvature. In an ordinary Yang–Mills theory, the gauge
connection acts on internal degrees of freedom, and its curvature is the
gauge-field strength. These are instances of the same mathematical idea, but
they act on different bundles and have different dynamics. A gauge field can
have nonzero curvature even when the spacetime background is flat. Gravity, by
contrast, makes the spacetime metric itself dynamical.[^11]

## 4. The same geometry on a lattice

The continuum story is elegant, but it leaves a practical problem. In an
interacting quantum field theory, especially quantum chromodynamics (QCD), the
path integral usually cannot be evaluated exactly. Perturbation theory works
beautifully when the coupling is small, but the strong interaction becomes
strongly coupled at low energies—the regime where protons, neutrons, and other
hadrons form. How do we calculate there without expanding around a weakly
interacting theory?

One answer is **lattice gauge theory**, introduced in its modern form by
Kenneth Wilson in 1974.[^9] Replace Euclidean spacetime by a grid with spacing
\$a\$. The lattice is a regulator and a calculational device; it does not
assert that physical spacetime is fundamentally a grid. The key is to
discretize the gauge field in a way that preserves local gauge symmetry
exactly, even before taking the continuum limit.

The matter fields live on lattice sites \$x\$. The gauge field lives on the
links connecting neighboring sites, but instead of assigning an unconstrained
matrix-valued potential to each link, we assign a group element

$$
U_\mu(x)\in G.
$$

Think of \$U_\mu(x)\$ as the finite parallel transporter from \$x\$ to
\$x+a\hat\mu\$. For a smooth continuum gauge field, it is approximately

$$
U_\mu(x)\simeq \exp\!\left(-iga A_\mu(x)\right),
$$

with generator and sign conventions understood. This is the discrete version
of the connection: rather than storing the infinitesimal rule for comparing
fields, we store the group element that transports one field value to its
neighbor.

Under a gauge transformation \$\Omega(x)\in G\$, a link transforms at its two
endpoints:

$$
U_\mu(x)\longmapsto U'_\mu(x)
=\Omega(x)U_\mu(x)\Omega^\dagger(x+a\hat\mu).
$$

The endpoint factors are exactly what we need. If
\$\psi(x)\mapsto\Omega(x)\psi(x)\$, then the lattice difference

$$
D_\mu^{(a)}\psi(x)=\frac{1}{a}\left[U_\mu(x)\psi(x+a\hat\mu)-\psi(x)\right]
$$

transforms like \$\psi(x)\$ at the site \$x\$. It is the lattice analogue of a
covariant derivative. Gauge covariance did not disappear when spacetime was
discretized; it determined how the variables on links must transform.

Now take the smallest closed path on a hypercubic lattice: one square, called
a **plaquette**. Moving around its four directed links gives

$$
\begin{aligned}
U_{\mu\nu}(x)={}&U_\mu(x)\,U_\nu(x+a\hat\mu)\\
&\times U_\mu^\dagger(x+a\hat\nu)\,U_\nu^\dagger(x).
\end{aligned}
$$

This is a discrete holonomy. It transforms by conjugation at the base point,
\$U_{\mu\nu}(x)\mapsto\Omega(x)U_{\mu\nu}(x)\Omega^\dagger(x)\$, so its trace
is gauge invariant. For small lattice spacing, the plaquette is the lattice
version of curvature:

$$
U_{\mu\nu}(x)=\exp\!\left(-iga^2F_{\mu\nu}(x)+O(a^3)\right).
$$

The connection was stored on links; its curvature is measured around faces.
This is the continuum geometry translated almost literally into combinatorics.

For \$G=\mathrm{SU}(N)\$, a common choice of action is the Wilson plaquette
action,

$$
S_W[U]=\beta\sum_{x,\,\mu<\nu}
\left(1-\frac{1}{N}\operatorname{Re}\operatorname{Tr}U_{\mu\nu}(x)\right),
\qquad \beta=\frac{2N}{g_0^2},
$$

where \$g_0\$ is the bare lattice coupling and the stated relation uses a
standard normalization. Because every plaquette trace is gauge invariant, the
action is gauge invariant at nonzero lattice spacing. Expanding the plaquette
for small \$a\$ shows that, with the coupling tuned appropriately, this action
approaches the continuum Yang–Mills action as \$a\to0\$. The continuum field
strength is not guessed separately: it emerges from the small-square limit of
the parallel transport around a plaquette.[^9]

The corresponding Euclidean path integral takes the form

$$
Z=\int\!\prod_{\text{links }\ell}dU_\ell\;e^{-S_W[U]},
$$

where each \$dU_\ell\$ is the invariant Haar measure on the gauge group. On a
finite lattice this is a finite-dimensional, though enormous, integral over
group variables. Monte Carlo algorithms can sample it, letting us estimate
expectation values numerically. This gives us access to phenomena that are
difficult or impossible to derive by ordinary perturbation theory, including
the low-energy spectrum of QCD and many properties of hadrons.[^10]

The calculation is not simply “make a grid and read off the answer.” A
reliable result requires controlling several limits and errors: finite lattice
spacing, finite volume, numerical sampling, and the choice and tuning of quark
masses. One performs simulations at several lattice spacings and volumes, then
extrapolates toward the continuum and infinite-volume limits. The lattice is
powerful precisely because the approximations are explicit and can be
systematically tested.[^10]

Wilson loops reappear naturally. Multiply link variables along a closed
lattice contour \$C\$, and take the trace:

$$
W(C)=\operatorname{Tr}\!\left(\prod_{\ell\in C}U_\ell\right).
$$

This is the discrete counterpart of the continuum Wilson loop introduced
earlier. In the pure-gauge theory, the scaling of large Wilson loops can
diagnose confinement; in full QCD, dynamical quark-antiquark pair creation
complicates the simplest area-law picture, so the observable has to be
interpreted with care. The broader lesson is more important than any one
diagnostic: a lattice preserves the group, parallel transport, holonomy, and
gauge invariance while making non-perturbative calculations possible.

## 5. The Standard Model gauge group

In the usual shorthand, the Standard Model gauge group is

$$
G_{\mathrm{SM}}=
\mathrm{SU}(3)_C\times\mathrm{SU}(2)_L\times\mathrm{U}(1)_Y.
$$

The subscript \$C\$ refers to color, \$L\$ to the left-handed weak
interaction, and \$Y\$ to hypercharge. At the level of Lie algebras, the
structure is

$$
\mathfrak g_{\mathrm{SM}}
=\mathfrak{su}(3)_C\oplus\mathfrak{su}(2)_L\oplus\mathfrak u(1)_Y,
$$

with dimension

$$
8+3+1=12.
$$

That is the first count to remember: the Standard Model has twelve gauge-field
directions before electroweak symmetry breaking. Eight belong to color, three
to weak isospin, and one to hypercharge. The corresponding fields are
conventionally called \$G^A_\mu\$ (\$A=1,\ldots,8\$), \$W^a_\mu\$
(\$a=1,2,3\$), and \$B_\mu\$.

| Sector | Gauge group | Number of generators | Gauge fields |
|---|---|---:|---|
| Strong interaction | \$\mathrm{SU}(3)_C\$ | 8 | 8 gluon fields \$G^A_\mu\$ |
| Weak interaction | \$\mathrm{SU}(2)_L\$ | 3 | 3 fields \$W^a_\mu\$ |
| Hypercharge | \$\mathrm{U}(1)_Y\$ | 1 | 1 field \$B_\mu\$ |

The three factors have different jobs. \$\mathrm{SU}(3)_C\$ acts on quark
color and produces quantum chromodynamics. \$\mathrm{SU}(2)_L\$ acts on
left-handed weak doublets. \$\mathrm{U}(1)_Y\$ assigns hypercharge, which
combines with the third weak-isospin generator to give electric charge. For
the convention \$Q=T_3+Y\$, the up and down components of a left-handed quark
doublet have charges \$+2/3\$ and \$-1/3\$ respectively.

The matter fields are not arbitrary decorations. They sit in particular
representations of the product group. For one generation, with the hypercharge
convention just stated, a left-handed quark doublet transforms under both
color and weak isospin, while a right-handed up quark transforms as a color
triplet and weak singlet. Writing the representations out explicitly,

$$
\begin{aligned}
Q_L&\sim(\mathbf 3,\mathbf 2)_{1/6}, &
 u_R&\sim(\mathbf 3,\mathbf 1)_{2/3}, &
 d_R&\sim(\mathbf 3,\mathbf 1)_{-1/3},\\
L_L&\sim(\mathbf 1,\mathbf 2)_{-1/2}, &
 e_R&\sim(\mathbf 1,\mathbf 1)_{-1}, &
 H&\sim(\mathbf 1,\mathbf 2)_{1/2}.
\end{aligned}
$$

Here each ordered triple labels the representation under \$\mathrm{SU}(3)_C\$,
\$\mathrm{SU}(2)_L\$, and \$\mathrm{U}(1)_Y\$. The bold numbers denote the
familiar fundamental representation or a singlet, and the subscript denotes
hypercharge. Different texts normalize hypercharge differently; the
electric-charge formula must be adjusted with that convention. The minimal
renormalizable Standard Model has no right-handed neutrino field, although
neutrino masses motivate extending that minimal field content or adding
effective operators. The point is that a gauge group does not tell us which
particles exist by itself. We must also specify the representations and the
Lagrangian.

It is important not to read these labels as ordinary spatial symmetries. The
groups \$\mathrm{SU}(3)_C\$ and \$\mathrm{SU}(2)_L\$ act on internal color and
weak-isospin indices, not on the coordinates of physical space. The fact that
quarks come in three colors does not mean color is ordinary rotation in
three-dimensional space. It is an internal symmetry, and its representation
assignments are part of the physical content of the theory.

The Standard Model's gauge group is also slightly more subtle than the product
notation suggests. Its Lie algebra does not, on its own, determine the global
form of the group. Depending on hypercharge normalization and on how one
specifies the faithful action on all fields, one may describe the group using
a discrete quotient of the centers of the three factors; a familiar
possibility is a \$\mathbb Z_6\$ quotient. Such quotients leave the local Lie
algebra unchanged but can affect global and topological questions.[^5][^6]

## 6. Where did the photon go? The Higgs mechanism

If each generator comes with a gauge field, why do we not observe twelve
massless gauge bosons? Because the electroweak theory contains a Higgs field,
and its nonzero vacuum expectation value changes the pattern of symmetry
realized in the vacuum. The gauge symmetry is not simply deleted; the fields
reorganize, and three gauge fields acquire mass through the Higgs mechanism.

The three weak fields and the hypercharge field mix. Two combinations become
the charged \$W^+\$ and \$W^-\$ bosons. The remaining neutral combinations
become the \$Z\$ boson and the photon. In schematic terms, the unbroken
electromagnetic generator is

$$
Q=T_3+Y,
$$

in the convention used above. The photon is associated with this surviving
\$\mathrm{U}(1)_{\mathrm{em}}\$ symmetry. The \$W^\pm\$ and \$Z\$ are massive;
the photon remains massless. The eight gluons belong to the unbroken color
sector, although confinement means that we do not observe isolated gluons as
asymptotic particles.

This is why the phrase “a generator gives a gauge boson” needs care. It is a
powerful counting principle in the unbroken gauge theory, but after symmetry
breaking the fields can mix, and physical mass eigenstates need not match
the original group generators one by one. The group sets the architecture;
the Higgs sector determines how that architecture is realized in the vacuum.[^7]

## 7. Why these groups—and what lies beyond?

Gauge theory does not say that every imaginable Lie group describes nature. It
gives us a mathematical framework for building consistent local interactions.
The empirical question is which group, representations, couplings, and scalar
fields reproduce the particles and forces we measure. The Standard Model is
astonishingly successful, but its group and matter assignments are inputs
constrained by experiment and by quantum consistency.

One of those consistency conditions is anomaly cancellation. A classical
Lagrangian may appear gauge invariant, yet quantization can spoil that
invariance unless the contributions of its chiral matter fields fit together
correctly. The Standard Model's charge assignments satisfy a set of nontrivial
cancellation conditions. Gauge symmetry is therefore not just a pretty
notation for the forces: it constrains which quantum theories are
mathematically viable.

There are several directions beyond the Standard Model. Grand unified theories
embed the familiar factors into a larger group such as \$\mathrm{SU}(5)\$,
aiming to explain why the strong, weak, and hypercharge structures fit
together as they do. These are interesting proposals, not established
extensions of the Standard Model; their additional predictions must survive
experimental tests.[^8] Other possibilities add new \$\mathrm{U}(1)\$ factors,
hidden gauge sectors, or new matter representations. In condensed matter
physics, gauge fields can also emerge as effective descriptions of collective
degrees of freedom, rather than being fundamental fields in the same sense
assumed in particle physics.

And then there is the geometry itself. Once gauge fields are understood as
connections, the theory opens onto questions that are not visible in the
elementary covariant derivative: nontrivial bundles, magnetic monopoles,
instantons, topological terms, confinement, and the relation between local
equations and global structure. The Standard Model is not the end of gauge
theory; it is one particularly successful realization of a much larger
mathematical idea.

## The central idea

A gauge theory begins with a Lie group specifying the allowed local
transformations of internal degrees of freedom. Its representations say how
matter fields transform. A connection \$A_\mu\$ tells us how to compare those
fields at neighboring points, and its curvature \$F_{\mu\nu}\$ measures the
obstruction to trivial parallel transport. The action is built from quantities
that respect the gauge redundancy, and the resulting quantum theory predicts
the interactions.

That is the shared skeleton behind Maxwell theory, Yang–Mills theory, and the
gauge sector of the Standard Model. The Standard Model uses
\$\mathrm{SU}(3)_C\times\mathrm{SU}(2)_L\times\mathrm{U}(1)_Y\$, with twelve
gauge-field directions, a specific set of chiral representations, and a Higgs
field that reorganizes the electroweak fields. Lattice gauge theory then shows
how the very same connection-and-curvature structure can be defined on a
finite grid while preserving gauge invariance and enabling non-perturbative
calculations.

The eerie simplicity is that one geometric recipe—choose a group, choose
representations, introduce a connection, take its curvature, and write an
invariant action—can describe interactions as different as electromagnetism
and the strong nuclear force. The same recipe survives the move from continuum
equations to lattice links and plaquettes. The symbols are compact. What they
encode is not.

## References

[^1]: **Tong, David.** *Gauge Theory.* Lecture notes, University of Cambridge.
<https://davidtong.org/teaching/gauge-theory/>.
A detailed introduction to connections, Yang–Mills theory, Wilson loops,
confinement, and related topics.

[^2]: **Yang, Chen Ning, and Robert L. Mills.** “Conservation of Isotopic Spin
and Isotopic Gauge Invariance.” *Physical Review* 96 (1954): 191–195.
<https://doi.org/10.1103/PhysRev.96.191>.

[^3]: **“Gauge Theories in Physics.”** *Stanford Encyclopedia of
Philosophy.*
<https://plato.stanford.edu/entries/gauge-theories/>.
Useful for the distinction between gauge redundancy, gauge invariance, and
physical interpretation.

[^4]: **Tong, David.** *Gauge Theory*, especially the chapter on Yang–Mills
theory.
<https://davidtong.org/teaching/gauge-theory/>.

[^5]: **Tong, David.** *The Standard Model.* Lecture notes.
<https://www.davidtong.org/teaching/standard-model/>.
For the standard gauge factors, their representations, and the electroweak
structure.

[^6]: **Li, Hao-Lin, and Ling-Xiao Xu.** “Understanding the SM gauge group
from SMEFT.” *Journal of High Energy Physics* (2024), 199.
<https://doi.org/10.1007/JHEP07(2024)199>.
Discusses why the Standard Model Lie algebra does not by itself fix the global
gauge group.

[^7]: **Particle Data Group.** *Review of Particle Physics* (2026).
<https://pdg.lbl.gov/>. Reference source for the
established particle content and measured properties of the Standard Model.

[^8]: **Georgi, Howard, and Sheldon L. Glashow.** “Unity of All
Elementary-Particle Forces.” *Physical Review Letters* 32 (1974): 438–441.
<https://doi.org/10.1103/PhysRevLett.32.438>.

[^9]: **Wilson, Kenneth G.** “Confinement of Quarks.” *Physical Review D* 10
(1974): 2445–2459.
<https://doi.org/10.1103/PhysRevD.10.2445>.
The foundational lattice-gauge-theory paper, introducing a gauge-invariant
discretization of Euclidean spacetime.

[^10]: **Particle Data Group.** “Lattice quantum chromodynamics.” *Review of
Particle Physics* (2026).
<https://pdg.lbl.gov/2026/reviews/standard_model_and_related.html>.
The current PDG review index, including its lattice-QCD review.

[^11]: **Noonan, Patrick.** *Notes on Gauge Field Theory.* Cornell University.
<https://pi.math.cornell.edu/~noonan/notes/ym.pdf>.
A mathematical treatment of principal bundles, connections, curvature, and
gauge theory.
