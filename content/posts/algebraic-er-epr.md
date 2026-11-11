---
title: "Algebraic ER=EPR in de Sitter: Connectivity, Clocks, and the Observer-Dependent Algebra"
date: 2026-11-11
---

ER=EPR began as a statement about entanglement and geometry: two quantum systems
that are entangled should be connected by an Einstein–Rosen bridge [^1]. In its
algebraic form, however, the statement changes character. It is no longer about
how much entanglement there is. It is about the operator-algebraic type of
the systems involved [^2].

That shift matters enormously in de Sitter space, where there is no spatial
boundary, no global algebra of observables, and no observer-independent notion of
“the” algebra. The algebraic connectivity criterion does not disappear in de
Sitter. It becomes observer-dependent, because the observer’s clock is part
of what makes the algebra well defined.

This article explains what algebraic ER=EPR says, why de Sitter forces the
observer into the structure, and what remains open for a spectral-geometric
realization.

## 1. What algebraic ER=EPR changes

The original ER=EPR proposal associates entanglement with geometric
connectivity. A thermofield double state of two boundary theories is dual to a
two-sided black hole with a classical wormhole [^1]. The entanglement is large,
and the bridge is geometric.

But holographic systems can have entanglement of order \${\cal O}(1/G_N)\$ while
the bulk remains disconnected. Large entanglement alone is not enough. Algebraic
ER=EPR was constructed to resolve this puzzle by classifying connectivity in
terms of algebra type [^2]:

- If both algebras are type I, the bulk is disconnected.
- If both algebras are type III\$_{1}\$ and the spacetime is classical,
  there is a classical wormhole.
- If the algebras are not type I in a quantum volatile spacetime,
  there is a quantum wormhole.

Type III\$_{1}\$ is not a measure of entanglement magnitude. It is a structural
property. The local algebras of continuum quantum field theory are generically
isomorphic to the hyperfinite type III\$_{1}\$ factor [^3]. Such algebras have no
trace, no ordinary density matrix, and no von Neumann entropy for a restricted
state. A finite-dimensional qubit model is always type I, so it is always on the
disconnected side of the classification, regardless of how entangled its state
is.

This is the first lesson for de Sitter: connectivity is not a spectral invariant
of a Dirac operator. It is an invariant of the algebra itself.

## 2. De Sitter has no spatial boundary

In anti-de Sitter space, the boundary supplies a fixed algebra of observables.
Its type is an invariant, and algebraic ER=EPR can be stated cleanly. De Sitter
has no spatial boundary. The relevant algebra is the algebra of a static patch,
and its type is not type I.

The static-patch algebra of a de Sitter observer is type III\$_{1}\$ before
gravitational dressing. It has no trace, and entropy is not well defined in the
ordinary sense. The crossed-product construction changes this. Coupling the
local fields to the observer’s clock turns the type III\$_{1}\$ algebra into a
type II algebra with a trace and a genuine density matrix [^4]. In the static
patch of de Sitter, the observer-dressed algebra is type II\$_{1}\$, and its
entropy agrees with the generalized entropy

$$
S_{\rm gen} = \frac{A}{4G_N} + S_{\rm out}
$$

up to a state-independent additive constant [^5].

The observer is therefore not an optional add-on. The clock is what makes the
algebra type II and the entropy well defined. Without the clock, there is no
trace, no entropy, and no algebraic connectivity criterion in the de Sitter
setting.

## 3. Observer-dependent connectivity

The crossed-product construction is not unique. The natural modular structure of
the type III\$_{1}\$ static-patch algebra carries an \$\mathbb{R}^{+}\$ action,
not an \$\mathbb{R}\$ action. Extending \$\mathbb{R}^{+}\$ to \$\mathbb{R}\$
requires a choice of observer clock, and different clock choices produce
unitarily inequivalent embeddings into the type II algebra [^6].

This is not a technical pathology. It is the algebraic signature of observer
dependence in de Sitter quantum gravity. If connectivity is a property of the
algebra type, and the type II algebra depends on the clock, then connectivity
itself inherits that dependence. Two observers with different clocks may assign
unitarily inequivalent type II algebras to the same static patch.

In de Sitter, algebraic ER=EPR therefore cannot be a statement about a fixed
boundary algebra. It is a statement about the relationship between
observer-dressed algebras and their clocks.

## 4. Time-dependent ER=EPR

The most concrete de Sitter realization of ER=EPR uses two holographic screens
associated with two antipodal observers [^7]. The leading entanglement entropy
between the screens comes from a minimal extremal surface lying between them.
That entanglement is geometrized as an effective Einstein–Rosen bridge.

The time dependence is cosmological, not modular. In the expanding phase, the
screens remain entangled and the bridge persists. In a contracting phase, the
screens disentangle, and the bridge closes off when the minimal extremal surface
hits the Big Crunch singularity at a finite time before the collapse [^7].

Here “time” means the cosmological scale factor, not modular flow. Modular flow
is the kinematic structure that makes each screen’s algebra type II. Cosmological
evolution is the dynamical parameter that drives the entanglement between the
screens. The bridge exists or fails to exist as a function of cosmic time because
the entanglement between the observer screens is a function of cosmic time.

A complementary algebraic realization comes from dS/CFT. The Euclidean vacuum of
de Sitter is dual to a thermofield double state in two copies of the dual CFT,
and the global de Sitter geometry emerges from the entanglement between those
copies [^8]. Tracing over one copy gives a mixed thermal state describing a
single static patch. This is the de Sitter analogue of the AdS thermofield
double, but with temporal rather than spatial boundaries.

## 5. What this means for spectral geometry

The algebraic results sharpen the division of labor:

$$
\text{algebra type and observer clock}
\quad\longrightarrow\quad
\text{connectivity,}
$$

$$
D
\quad\longrightarrow\quad
\text{metric.}
$$

Connectivity is not a spectral invariant of \$D\$. It is an invariant of the
algebra and its type. A Dirac operator is a metric object. It encodes distances,
dimension, and differential structure, but it does not encode whether two
algebraic sectors are connected in the sense of algebraic ER=EPR.

This has a further consequence. In the quantum wormhole phase, the spacetime
is quantum volatile: diffeomorphism-invariant quantities such as proper lengths
and areas fluctuate by powers of \$G_N^{-1}\$, so there may be no stable classical
metric for \$D\$ to encode [^2]. A spectral-geometric reconstruction is therefore
most naturally a construction for the classical wormhole phase, not for the
most general connected phase.

The open question is not whether \$D\$ can carry connectivity. It cannot. The
open question is:

> Given two observer-dressed type II algebras in de Sitter whose algebraic
> structure identifies a connected phase, what real spectral triple realizes the
> metric of that connection?

And the companion question:

> Does the observer-dependence of the crossed product—the \$\mathbb{R}^{+}\$ versus
> \$\mathbb{R}\$ gap—translate into an observer-dependence of the emergent metric?

These are concrete research directions. They sit at the intersection of
operator-algebraic quantum gravity, modular theory, and noncommutative geometry.
They do not require ER=EPR to be an AdS/CFT statement. They require only that
connectivity be read algebraically, and that the metric be reconstructed
spectrally after connectivity has been established.

## Conclusion

Algebraic ER=EPR in de Sitter is not a statement about entanglement magnitude. It
is a statement about the operator-algebraic type of observer-dressed algebras.
Type III\$_{1}\$ signals classical connectivity; type I signals disconnectivity;
non-type-I algebras in a quantum volatile spacetime signal a quantum wormhole
[^2]. In de Sitter, the observer’s clock is what makes the algebra type II and
the entropy well defined [^5]. Different clocks give unitarily inequivalent
algebras, so connectivity itself becomes observer-dependent [^6].

The spectral-geometric layer enters afterward. It does not create connectivity.
It realizes the metric of a connectivity that the algebra has already
determined.

## References

[^1]: J. Maldacena and L. Susskind, “Cool horizons for entangled black holes,”
    arXiv:1306.0533. <https://arxiv.org/abs/1306.0533>

[^2]: N. Engelhardt and H. Liu, “Algebraic ER=EPR and Complexity Transfer,”
    arXiv:2311.04281. <https://arxiv.org/abs/2311.04281>

[^3]: J. Yngvason, “The Role of Type III Factors in Quantum Field Theory,”
    arXiv:math-ph/0411058. <https://arxiv.org/abs/math-ph/0411058>

[^4]: E. Witten, “Gravity and the Crossed Product,” arXiv:2112.12828.
    <https://arxiv.org/abs/2112.12828>

[^5]: V. Chandrasekaran, R. Longo, G. Penington, and E. Witten, “An Algebra of
    Observables for de Sitter Space,” arXiv:2206.10780.
    <https://arxiv.org/abs/2206.10780>

[^6]: D. Gogishvili, “Observer Dependence and the \$\mathbb{R}^{+}\$ vs
    \$\mathbb{R}\$ Crossed Product Gap in de Sitter Space,” Zenodo.
    <https://zenodo.org/records/18905169>

[^7]: V. Franken, H. Partouche, F. Rondeau, and N. Toumbas, “Closed FRW
    holography: a time-dependent ER=EPR realization,” arXiv:2310.20652,
    JHEP05(2024)219. <https://arxiv.org/abs/2310.20652>

[^8]: J. Cotler and A. Strominger, “Cosmic ER=EPR in dS/CFT,” arXiv:2302.00632.
    <https://arxiv.org/abs/2302.00632>
