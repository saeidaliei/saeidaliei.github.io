---
title: "The Observer, The Observer, The Observer"
date: 2026-11-04
---

The observer is what separates AdS from de Sitter space, and I think it is the
most important thing to understand about both. Anti-de Sitter space comes with
a boundary, and the boundary supplies a Hamiltonian, a time and a fixed frame
at infinity, so the theory is complete without anyone writing an observer down.
Nobody calls the boundary an observer, but it does the job of one, and it is a
very special one: infinitely heavy, classical, and untouched by what it
measures. De Sitter space has no such boundary. Nothing supplies the clock, the
algebra of a static patch is type III and has no well-defined entropy, and the
theory only becomes well defined once an observer with a clock is put in by
hand, at which point the algebra becomes type II and entropy appears. In AdS
the observer is hidden and comes for free. In de Sitter it is explicit and
unavoidable. That is why the title repeats the word.

That difference is also where the open questions live. If the AdS boundary is an
ideal observer, what is the observer when the clock is finite, when it has to
be paid for in energy, and when it is correlated with what it observes? The
same question came up for minds in the earlier posts of this series. This post
tries to find something concrete enough to compute, and computes it.

The short version: the literature on quantum reference frames makes precise
what an observer is. The place where it stops being settled is narrow and
specific, namely what happens when the observer's clock is *correlated* with
the rest of the system. I built two small models and worked through the entropy
formula of one recent paper to see what that does. One of my first estimates
came out wrong, in a way that made the result sharper. The result that
survives is conditional on an assumption I could not check, and I will say
exactly which.

The central idea of this post is:

> **The observer is what distinguishes AdS from de Sitter. In AdS it is an ideal
> clock hidden at the boundary. In de Sitter it is a finite clock that has to
> be written into the theory, and then its correlations with everything else
> become part of the entropy.**

Before anything else, the status. This is a research note, not a paper. The
numerical results come from small scripts on toy systems. Claims that are
conjectures are marked (C), and should not be read as established. The weakest
steps are collected in section 9.

A note on reading: terms followed by a reference like [(A.3)](#a3-the-center-and-branches)
are explained in plainer language in the appendix at the end.

## 1. Where the observer sits 

**In AdS: the boundary.** In AdS/CFT[^1] the boundary theory supplies a Hamiltonian, a
time coordinate and a fixed frame, all sitting at infinity. That is why AdS
looks complete without any explicit observer. My first way of putting my
complaint was that the boundary acts as a privileged observer: an infinitely 
heavy, non-gravitating, classical clock that never backreacts, 
and if anything, our universe doesn't like privileged anything.
AdS/CFT describes the world as seen by an ideal clock, and it has 
nothing to say about universes that have no boundary to put one on.

**In de Sitter: the observer is explicit.** Without a boundary, there is no such clock for free.
Witten showed that gravity turns the type III algebra of a static patch into a
crossed product[^2], and Chandrasekaran, Longo, Penington and Witten (CLPW)
showed that adding an observer with a clock makes it type II, with a trace and
a well-defined entropy[^3]. Chen and Xu then extended this to observers that
are *covariant* under the de Sitter isometries, so that the observer's own
worldline fluctuates, and showed that the resulting algebra is still type II,
with an observer-dependent entropy[^4].

**In a mind: the self.** The previous post proposed that a mind that grows without bound
has a type III algebra, and that what it needs in order to read its own time
from the inside is a clock-bearing frame, with the self as the formal content
of that frame. I will not repeat that argument here. I only want to point out
that it uses the same mathematics as the de Sitter case.

Maldacena has recently been talking about what happens to the sphere
partition function of de Sitter space when an observer with a clock is
included[^5]. The point it makes is the one above: in de Sitter space the
observer is not optional.

## 2. What the reference-frame results settle, and what they do not 

The results I take to be central, read by me at the level of abstracts and
key sections and not every proof:

| Result | What it shows | Caveat as I read it |
|---|---|---|
| Page–Wootters[^6][^7] | Time as conditioning on a clock, in a state with no time in it | Exact for an ideal clock |
| Trinity[^8] | Dirac quantization, Page–Wootters and gauge-fixed reduction are equivalent | Proven for a clock that does not couple to the evolving system |
| PW = CLPW[^9] | The CLPW observer is a temporal quantum reference frame; their constrained description matches Page–Wootters | Bounded clock energy is imposed after the constraint, so order of limits matters |
| Observer-dependent entropy[^10] | Different frames give different algebras and different entropies | |
| Top-down crossed products[^11] | The crossed product is one particular choice of reference frame | |
| Unsharp reference frames[^12] | The CLPW clock is an unsharp frame; finiteness of the algebra depends on the clock's weight | |

So the chain is: observer, then reference frame, then frame plus constraint
gives a crossed product, then the trace of the crossed product gives the
entropy. That is a real structural result. It tells you what an observer *is*.
It does not answer the AdS question, for four reasons.

1. **Non-ideal clocks.** The equivalences are cleanest for ideal clocks. A
   finite observer has bounded energy, and that is exactly where the order of
   limits matters.
2. **The observer observes nothing.** In CLPW the clock is not coupled to the
   fields. A realistic observer exchanges energy with the system and
   backreacts.
3. **The privilege may just move.** Frame-relative descriptions put the
   frame-independent content into a perspective-neutral state, and if that
   state has no content without a frame, one privileged observer has been
   exchanged for another.
4. **AdS and de Sitter have different constraints** *(my own analysis,
   unverified)*. In de Sitter the isometries are pure gauge, so the clock's time
   translation is a constraint. In AdS the boundary Hamiltonian is a physical
   charge, so a bulk clock's evolution is not pure gauge, and there are two
   frames at once: boundary time and the bulk clock.

## 3. The boundary as an ideal clock

Put together, the above suggests a sharper form of the original complaint:

> **(C)** *The AdS boundary clock is the infinite-energy limit of a
> finite bulk observer's clock. At finite energy, the algebra dressed to the
> bulk observer is a different algebra, with an observer-dependent entropy, and
> the difference is controlled by the clock's energy fluctuations.*

This turns "AdS has a privileged observer" into a precise statement: the
privilege is a limit and not a feature of the theory. It also has a clear
failure condition. If the difference between the finite-clock and
boundary-dressed entropies vanishes identically, or can be absorbed in a
relabeling, the conjecture is dead, and that would be worth reporting.

I have not done this calculation. The natural arena is JT gravity with matter
and one massive particle carrying a quantum clock, because the boundary-dressed
algebra is already known there[^13][^14][^15]. The rest of this post is about a
smaller question that I could actually attack: how does the clock's *correlation
with the rest of the system* enter the entropy at all? Whatever happens at
finite clock energy has to pass through that.

## 4. A toy model: two clocks and a system 

The smallest model I could build that has the relevant features: two clocks
\$A\$ and \$B\$ and a system \$S\$, with a single constraint. Each clock is an
\$N\$-level system with Hamiltonian \$n\$, and the system has integer energies
\$h_s\$. The gauge group is \$\mathbb Z_N\$, generated by the constraint

$$ C = n_A + n_B + h_S \equiv 0 \pmod N. $$

The clock readings come from the covariant time states
\$|\tau_k\rangle=N^{-1/2}\sum_n e^{-in\tau_k}|n\rangle\$ with
\$\tau_k=2\pi k/N\$. A physical state is the group average of "clock \$A\$ reads
zero, the rest is in state \$\psi_{BS}\$". Projecting \$A\$ onto its zero
reading gives back \$\psi_{BS}\$, which is the perspective of \$A\$. Doing the
same with \$B\$ gives \$\psi_{AS}\$, the perspective of \$B\$. This is the
finite-dimensional version of the Page–Wootters mechanism, with the
observer-dependence of Giacomini, Castro-Ruiz and Brukner built in[^16][^17].

**Sanity.** The physical states are gauge-invariant to machine precision. The
distribution of the relative reading \$\tau_B-\tau_A\$, computed from a
gauge-invariant POVM on the whole state, agrees with what each observer gets
from their own reduction to \$10^{-16}\$.

**Entanglement depends on the observer**. Take \$B\$ to be
sharp in energy and \$S\$ in a superposition of energies. Seen from \$A\$, \$B\$ and
\$S\$ are in a product state, with entropy 0. Seen from \$B\$, the clock \$A\$ is
maximally entangled with \$S\$: the entropy goes to \$\ln 4=1.386\$ and I measured
1.38. The reason is that \$S\$'s energy enters the constraint, so shifting
\$B\$'s reading shifts \$A\$'s reading in an \$s\$-dependent way. This is the
relativity of entanglement across quantum reference frames[^17]. It is not
new, and I include it because it is the finite analogue of the observer-dependent
entropies in the crossed-product papers. In random states, the two
perspectives disagree on the entropy by more than 0.1 in 66% of cases, though
the entropies are positively correlated (0.67).

**A mismatch between modular time and clock time**. For a reduced
clock state \$\rho\$ with clock Hamiltonian \$H=n\$, the modular flow is generated
by \$-\log\rho\$ and the clock's own evolution by \$H\$. They agree (up to a
rescaling) exactly when \$\rho\$ is thermal for \$H\$. A natural measure of the
failure is the relative entropy to the closest thermal state. If \$\Delta\$ is
dephasing in the energy basis and \$\gamma_\beta=e^{-\beta H}/Z\$, then

$$ \mathrm{Mis}(\rho)\;=\;\min_\beta D(\rho\,\|\,\gamma_\beta)
\;=\;\underbrace{S(\Delta\rho)-S(\rho)}_{\text{coherence}}
\;+\;\underbrace{\min_\beta D(\Delta\rho\,\|\,\gamma_\beta)}_{\text{non-thermality}}. $$

The second equality is one line, because \$\gamma_\beta\$ is diagonal in the
energy basis. The first term is the standard asymmetry measure of the resource
theory of reference frames[^18][^19], so the coherence part of the mismatch is a
known quantity, and the new content is only the way it is combined with the
non-thermal part. Whether that combination does any work is the question.

**The compact model has an artifact**. Because the group is
\$\mathbb Z_N\$, the relabeling \$n_A=-n_B\bmod N\$ wraps around, and a state that
is thermal for \$B\$ looks scrambled for \$A\$ for a reason that has nothing to do
with physics. I removed this by rebuilding the model with clocks bounded below
(\$n\ge 0\$ with no wrap, an exact U(1) constraint, and the Susskind–Glogower
time POVM). In the bounded model a thermofield-double-like state of \$B\$ and
\$S\$ looks exactly Gibbs to \$A\$ (mismatch 0.000, fitted \$\beta^*=1.000\$ for
\$\beta=1\$) and looks like a sharp energy eigenstate to \$B\$, with entropy 0. The
same global state is thermal and entangled from one perspective, and sharp and
unentangled from the other.

**Two branches**. Take a state \$\sqrt p\,|\chi_1\rangle|\phi_1\rangle
+\sqrt{1-p}\,|\chi_2\rangle|\phi_2\rangle\$ in which the clock \$B\$ records which
branch the system is in. From \$A\$'s side, the entropy of \$B\$ is the Holevo
information of its clock about the branch. It saturates at \$H(p)=\ln 2\$ when
the clock states are resolved in time, and falls (0.518 at time-width 1) as
they overlap. From \$B\$'s side it stayed at \$\ln 2=0.693\$ for every time-width
I tried, because the two branches differ in the system's energy, so
\$A\$'s states stay energy-distinguishable even when \$B\$ cannot tell the branches
apart in time. Which clock "knows" the branch depends on the perspective.

What the toys do and do not do. They show that the clock-correlation term is
real, computable, and perspective-dependent. They are finite and type I, with
no horizon, no type II trace and no crossed product, so they say nothing yet
about the actual entropy formula. That is the next section.

## 5. Where the correlation enters the entropy formula

I read the Chen–Xu paper[^4] through its entropy derivation. The structure, as I
understand it: any density
operator in the invariant algebra can be written as
\$\rho=\mathcal D\!\left(e^{d/2}\hat P(d)\,e^{d/2}\right)\$, where \$d\$ is the
clock energy and \$\hat P(d)\$ takes values in the matter algebra. This is exact.
The semiclassical ansatz then assumes a sharply time-localized clock whose
characteristic function approximately factorizes from matter expectation
values (their condition 4.2), so that \$\hat P(d)\approx\tilde f(d)\,P(0)\$.
Under that assumption the von Neumann entropy has the form (their 4.15)

$$ S\;\approx\;\text{(first-law term)}\;-\;\psi(\log\Delta_{\psi|\tilde\Psi})
\;+\;S_{\rm clock}(\psi), $$

where \$S_{\rm clock}\$ is, I take it, the differential entropy of the clock's
energy distribution. As printed it appears to lack a minus sign, which I read
as a typo. The authors say explicitly that the density operator beyond
semiclassical states can be obtained but is too complicated to discuss, and
that the semiclassical ansatz assumes minimal entanglement between the clock
and everything else. This is a gap that the paper itself marks, not an error.

The algebra also has a nontrivial center. For observer \$a\$ the center is
generated by projections encoding whether another observer \$b\$ is inside
\$a\$'s patch [(A.3)](#a3-the-center-and-branches). These commute with
everything, including the clock energy. That makes them ideal branch labels.

**Derivation**. Suppose the state is
correlated with a central variable \$i\$ (for example, "\$b\$ is inside" or "\$b\$
is outside") with probabilities \$p_i\$. A state on an algebra with a center
decomposes into fibers, and the entropy splits exactly:

$$ S(\omega)\;=\;H(p)\;+\;\sum_i p_i\,S(\omega_i)\;\Big(+\sum_i p_i\log z_i\Big), $$

where the last term is the shift from the non-uniqueness of the trace, which
depends only on the branch. If the semiclassical conditions hold fiber by
fiber, with a branch-dependent clock energy density \$g_i(q)\$, then applying
the formula fiber by fiber gives the conditional entropy
\$h(q\,|\,i)=\sum_i p_i h(g_i)\$ in place of the marginal \$h(q)\$. The entropy
with the correlation is therefore

$$ S\;=\;S_{\rm semi}\;-\;I(i\,;q),\qquad
I(i\,;q)\;=\;h(q)-\sum_i p_i\,h(q\,|\,i), $$

where \$S_{\rm semi}\$ is the formula applied naively with the marginal clock
distribution. The correction is the classical mutual information between the
clock energy and the branch[^20]. It is non-negative, at most \$H(p)\$, and
**independent of the trace choice**, because the \$\log z_i\$ shift cancels. The
formula is what a referee would call obvious once written down, which is also
why I believe it. What is not obvious is whether it is nonzero in a physical
state of the algebra.

For a small shift \$\Delta E\$ between the two clock energy distributions,
each Gaussian with minimum-uncertainty width \$\sigma_q=1/(2\epsilon)\$ for time
resolution \$\epsilon\$, I get \$I\simeq 2p(1-p)(\Delta E\,\epsilon)^2\$.
Numerically for \$p=\tfrac12\$ and \$\Delta E=1\$:

| \$\epsilon\$ | 0.05 | 0.1 | 0.2 | 0.5 | 1.0 |
|---|---|---|---|---|---|
| \$I\$ (exact, nats) | 0.00125 | 0.00498 | 0.01961 | 0.1114 | 0.337 |
| \$2p(1-p)(\Delta E\epsilon)^2\$ | 0.00125 | 0.00500 | 0.02000 | 0.1250 | 0.500 |

The formula is good for small \$\Delta E\,\epsilon\$ and it saturates at
\$\ln 2\$ for large. Taken alone it would say that a sharp clock makes the
correction second-order small, in agreement with the "neglect higher than
\$\epsilon\$" convention of the semiclassical derivation. The next section
shows why that estimate was too optimistic.

## 6. Two observers: when the clock records the other observer 

Take observer \$a\$ at the origin, a second observer \$b\$, and the QFT in its
vacuum. I use three facts from the paper's setup.

1. The projector onto "\$b\$ is visible to \$a\$" is a function of \$b\$'s relative
   geodesic, and \$d_{b,1}\$ generates left multiplication by the boost along
   \$a\$'s geodesic. That boost preserves \$a\$'s static patch, so it preserves
   whether \$b\$'s geodesic enters it. Hence the projector commutes with the
   clock energy, and the joint distribution of (inside or outside, clock
   energy) is well defined.
2. With the QFT in the vacuum the constraint reads
   \$d_{a,1}+d_{b,1}=0\$, so \$a\$'s clock energy is \$q_a=-d_{b,1}\$.
3. The paper gives the generator along a geodesic \$(\varphi,s)\$ as
   \$d_1\cos\varphi\cosh s+d_2\sin\varphi\cosh s+l\sinh s\$, and \$b\$ is visible to
   \$a\$ iff \$\cos\varphi\ge 0\$.

**The assumption.** If \$b\$ carries charge only along its own geodesic (call it
\$E_b\$), then \$d_{b,1}=E_b\cos\varphi\cosh s\$, so

$$ q_a\;=\;-E_b\cos\varphi_b\cosh s_b. $$

For \$E_b>0\$ the sign of \$q_a\$ tells you which side of the horizon \$b\$ is on.
This is the **classical charge relation**, and I have *not* verified it as an
operator statement in the actual representation on \$L^2(SO(1,2))\$. Everything
in the rest of this section depends on it.

I computed \$I(\text{inside};q_a)\$ for \$b\$'s geodesic distributed on either
side of the patch, and for different clock-energy distributions of \$b\$.

| \$E_b\$ distribution | std/mean | \$I\$ (nats) |
|---|---|---|
| Gamma, shape 0.5 | 1.41 | 0.598 |
| Gamma, shape 1 | 1.00 | 0.678 |
| Gamma, shape 2 and above | 0.71 and below | 0.693 (\$=\ln 2\$) |
| symmetric about 0 (no lower bound) | n/a | 0.000 |

With a lower-bounded clock energy for \$b\$, the clock energy of \$a\$ is, up to
horizon-grazing geodesics, an exact record of whether \$b\$ is in its patch, and
the correction is the full Shannon entropy \$H(p)\$. Without a lower bound, it
vanishes. **I had this wrong at first.** My estimate at the end of section 5,
that the correction is second-order small for a sharp clock, assumed that the
two sectors' clock energy distributions are shifted copies of each other. With
a positive-energy \$b\$ they sit on opposite sides of zero and are nearly
disjoint, so the correction does not scale like \$(\Delta E\,\epsilon)^2\$ at all.

Two consequences, both conditional on the classical charge relation:

- The factorization condition of the semiclassical derivation fails in the
  very two-observer setting the paper builds, if the observers' clock energies
  are bounded below. It holds if they are symmetric.
- The paper says a spectral lower bound on the clock energy is not applicable
  with several covariant observers, and so does not impose it. Whether the
  effect exists therefore depends on a choice the authors left open. It also
  connects to the bound that separates type II\$_1\$ from type II\$_\infty\$ in
  CLPW, which is the same sign asymmetry seen from another side.

## 7. Back to AdS, de Sitter and the self

**AdS.** The conjecture of section 3 is untouched. What the toy
models and section 5 add is a mechanism that any finite-clock correction has
to pass through: the clock's correlations with what it times, which depend on
the perspective. The boundary clock is the case where those correlations are
negligible because the clock is infinitely heavy.

**De Sitter.** For two or more observers there is a concrete
candidate for a nonzero correction, and a clear dependence of its existence on
an assumption the authors did not make. That is the part I think could become
a paper, if the classical charge relation survives a proper treatment.

**In a mind: the self.** The previous post proposed that the arrow of time for a mind is
a mismatch between modular time and clock time. Section 4 gives that mismatch a
definite form (coherence plus non-thermality), shows that it is
perspective-dependent, and shows that what looks like a thermal, entangled
clock from one frame can be a sharp, unentangled one from another. That
supports, weakly, the earlier claim that a copy of a state is not a copy of a
frame. It does not support any more than that. The toy is not a model of a
mind, and I would not read the cognitive claim off the physics.

## 8. What would count as evidence, and what is next

| Test | What it settles | Status |
|---|---|---|
| Joint spectral measure of the projector \$\Theta(\cos\varphi)\$ and the left-boost generator on \$L^2(SO(1,2))\$ | Whether \$d_{b,1}\$ has disjoint spectra in the two sectors for \$E_b\ge 0\$, which is the classical charge relation at the quantum level | not done; a well-posed harmonic analysis problem |
| An explicit two-observer state with clock energy densities \$g_{\rm in}\$, \$g_{\rm out}\$ computed from the constraint | Whether \$I\$ is nonzero in a physical state, rather than in my illustration | not done |
| Non-central correlations (clock with field modes) | Whether \$-I\$ survives when the commutation of conditions 4.9 and 4.10 of the paper fails | open; I have no closed form |
| JT gravity with one massive clock | The conjecture of section 3 | not done |
| Literature check: Witten's background-independent algebra[^21], the top-down crossed product work[^11], and anything on observer-dependent entropy in AdS | Novelty | not done; this is the first thing to do |

## 9. What this does and does not claim

It does not claim a result about AdS. The conjecture of section 3 is a
conjecture, and no calculation in this post tests it. It does not claim that
the classical charge relation holds for quantum observers. It does not claim
anything about minds beyond the one structural point in section 7.

It does claim a specific, checkable statement about the de Sitter algebra: if a
second observer's clock energy is bounded below and the classical charge
relation holds, the entropy of the semiclassical formula of Chen and Xu needs a
correction equal to the mutual information between the first observer's clock
energy and whether the second observer is in its patch, which is independent
of the trace choice and can be as large as the Shannon entropy of that
variable.

The weakest steps, in the order I trust them least:

1. **The classical charge relation** \$d_{b,1}=E_b\cos\varphi\cosh s\$. Section 6
   stands or falls with it.
2. **Fiber-by-fiber semiclassicality.** I assumed that the paper's conditions
   hold inside each central sector. I did not check that they can.
3. **The setting.** de Sitter in two dimensions, QFT in the vacuum, one second
   observer, ideal reference frame states. With field excitations the
   constraint adds a field-energy term to \$q_a\$.
4. **The toy models** are finite, type I, and have no horizon. They illustrate
   the perspective dependence but do not touch the type II trace.
5. **Non-central correlations** are not handled at all.
6. **Novelty.** I have not finished the literature check, so some of this may
   already be known.

And a worry in the same spirit as the last post. I found that the same
structure, a clock-bearing frame, fits AdS, de Sitter and a model of a mind,
and a match across three domains looks like evidence for the framework. It is
also exactly what you would see if "reference frame" were a generic concept
that fits anything you ask it to. The safeguard I have is the narrowness of
section 6: a specific formula that either is or is not nonzero in a specific
algebra. That is the part that can fail.

If the previous posts ended on a proposal, this one ends on a question that has
an answer. The observer is a clock, a clock can be correlated with what it
times, and whether that correlation is large or negligible is a calculation I
know how to set up and have not finished.

## Appendix

Each entry says what the idea is, gives a small example,
and says why it matters for the post.

### A.1 Observer, clock, reference frame

A *reference frame* is whatever measurements are made relative to. Latitude
needs an equator and a prime meridian. A *clock* is a reference frame for time:
"the temperature when my clock reads noon". A *quantum* reference frame is one
that is itself a physical system, so it can be uncertain or entangled with what
it measures. In this post an *observer* means exactly that, a reference frame
with a clock and records. It does not need to be a mind, and a thermometer
with a timer qualifies.

### A.2 Constraints, gauge, and Page–Wootters 

A *constraint* is a condition that physical states must satisfy, such as "the
total energy is zero". In general relativity there is no external time, so the
Hamiltonian is a constraint. A state that satisfies it does not change, and yet
the world around us does. Page and Wootters resolved this by picking a
subsystem to be the clock: the rest of the world, *conditioned on the clock
reading*, evolves normally. A good picture is a photo album of a dance. All the
pages exist at once, and "time" is the page number you condition on. A
physical state is obtained from any state by *group averaging*: summing it over
all the shifts the constraint generates.

### A.3 The center and branches

The *center* of an algebra is the set of operations that commute with every
other operation in it. They behave like classical labels: they are definite
whatever else you do. In the de Sitter algebra of an observer, the center
contains projections for questions like "is the other observer inside my
patch?". If a state is spread over several values of such a label with
probabilities \$p_i\$, the algebra splits into sectors, and the entropy of the
state is the Shannon entropy of the \$p_i\$ plus the average entropy inside each
sector. I call each value a *branch*.

### A.4 Crossed products and types

Algebras are sorted into types by how they measure size: type I is ordinary
matrices, type II has a trace but no smallest pieces, and type III has no trace
at all. The algebra of a region of space in field theory is type III, so it has
no absolute entropy. Adding a clock and keeping only what is invariant under
shifting it produces a *crossed product*, which can be type II. The previous
post explains this in more detail.

### A.5 Mutual information between a clock and a label

Suppose a label takes the values "inside" and "outside" with equal probability,
and a clock energy is measured. If the clock energy distribution is the same in
both cases, the energy tells you nothing about the label, and the *mutual
information* is zero. If the distributions are separated, as when "inside"
always gives a negative energy and "outside" always a positive one, the energy
reveals the label completely, and the mutual information equals the entropy of
the label, \$\ln 2\$ for a fair coin. In between, it is the amount by which
knowing the energy reduces your uncertainty about the label.

## References

[^1]: Juan Maldacena, The Large N Limit of Superconformal Field Theories and
    Supergravity, *Advances in Theoretical and Mathematical Physics* 2, 1998,
    pp. 231-252.

[^2]: Edward Witten, Gravity and the crossed product, 2021,
    [https://arxiv.org/abs/2112.12828](https://arxiv.org/abs/2112.12828).

[^3]: Venkatesa Chandrasekaran, Roberto Longo, Geoff Penington and Edward
    Witten, An Algebra of Observables for de Sitter Space, *Journal of High
    Energy Physics* 2023(2), 82,
    [https://arxiv.org/abs/2206.10780](https://arxiv.org/abs/2206.10780).

[^4]: Chen and Xu, An algebra for covariant observers in de Sitter space,
    arXiv:2511.00622, *Journal of High Energy Physics* 2026(9), 240,
    [https://arxiv.org/abs/2511.00622](https://arxiv.org/abs/2511.00622).

[^5]: Juan Maldacena, lecture at the Arnold Sommerfeld Center, LMU Munich,
    [https://www.asc.physik.lmu.de/activities/lectures/archiv/thirty-first_series/maldacena_2/index.html](https://www.asc.physik.lmu.de/activities/lectures/archiv/thirty-first_series/maldacena_2/index.html).

[^6]: Don N. Page and William K. Wootters, Evolution without evolution:
    Dynamics described by stationary observables, *Physical Review D* 27,
    1983, pp. 2885-2892.

[^7]: Vittorio Giovannetti, Seth Lloyd and Lorenzo Maccone, Quantum time,
    *Physical Review D* 92, 2015, 045033.

[^8]: Philipp A. Höhn, Alexander R. H. Smith and Maximilian P. E. Lock, The
    Trinity of Relational Quantum Dynamics, *Physical Review D* 104, 2021,
    066001, [https://arxiv.org/abs/1912.00033](https://arxiv.org/abs/1912.00033).

[^9]: Julian De Vuyst, Stefan Eccles, Philipp A. Höhn and Josh Kirklin,
    Crossed products and quantum reference frames: on the observer-dependence
    of gravitational entropy, *Journal of High Energy Physics* 2025(7), 063,
    [https://arxiv.org/abs/2412.15502](https://arxiv.org/abs/2412.15502).

[^10]: Julian De Vuyst, Stefan Eccles, Philipp A. Höhn and Josh Kirklin,
    Gravitational entropy is observer-dependent, 2024,
    [https://arxiv.org/abs/2405.00114](https://arxiv.org/abs/2405.00114).

[^11]: Ahmad et al., Quantum Reference Frames from Top-Down Crossed Products,
    2024, [https://arxiv.org/abs/2405.13884](https://arxiv.org/abs/2405.13884).

[^12]: Christopher J. Fewster, David Janssen, Leon D. Loveridge, Kasia Rejzner
    and James Waldron, Quantum reference frames, measurement schemes and the
    type of local algebras in quantum field theory, 2024.

[^13]: Geoff Penington and Edward Witten, Algebras and States in JT Gravity,
    2023, [https://arxiv.org/abs/2301.07257](https://arxiv.org/abs/2301.07257).

[^14]: Chang-Han Chen and Geoff Penington, A clock is just a way to tell the
    time: gravitational algebras in cosmological spacetimes, 2024,
    [https://arxiv.org/abs/2406.02116](https://arxiv.org/abs/2406.02116).

[^15]: Sam Leutheusser and Hong Liu, Emergent times in holographic duality,
    2021, [https://arxiv.org/abs/2112.12156](https://arxiv.org/abs/2112.12156).

[^16]: Esteban Castro-Ruiz, Flaminia Giacomini and Časlav Brukner,
    Entanglement of quantum clocks through gravity, *Proceedings of the
    National Academy of Sciences* 114(12), 2017, pp. E2303-E2312.

[^17]: Flaminia Giacomini, Esteban Castro-Ruiz and Časlav Brukner, Quantum
    mechanics and the covariance of physical laws in quantum reference frames,
    *Nature Communications* 10, 2019, 494.

[^18]: Gilad Gour and Robert W. Spekkens, The resource theory of quantum
    reference frames: manipulations and monotones, *New Journal of Physics*
    10, 2008, 033023.

[^19]: Iman Marvian and Robert W. Spekkens, Extending Noether's theorem by
    quantifying the asymmetry of quantum states, *Nature Communications* 5,
    2014, 3821.

[^20]: Thomas M. Cover and Joy A. Thomas, *Elements of Information Theory*, 2nd
    edition, Wiley, 2006.

[^21]: Edward Witten, A background-independent algebra in quantum gravity,
    2023, [https://arxiv.org/abs/2308.03663](https://arxiv.org/abs/2308.03663).
