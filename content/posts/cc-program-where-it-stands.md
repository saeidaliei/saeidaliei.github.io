---
title: "Where the Cosmological Constant Program Stands"
date: 2026-11-23
---

*This is the closing note of a series: [^1], [^2] and [^3]. It collects what
survived, what was corrected, and what the follow-up calculations and literature
checks added. Nothing here derives the observed value of \$\Lambda\$.*

## Summary

- **No route examined selects \$\Lambda\$.** The algebraic route, the
  observer-weighting route and the non-anthropic mechanisms all end at the same
  place: a prior over \$\Lambda\$ (or over a cosmic lifetime) that nothing
  derived so far fixes.
- **The observer supplies conditioning, not the low-entropy past.** In de Sitter
  space the theory has observables only relative to an observer, which makes
  conditioning a requirement of the theory. But the restriction to histories
  with a low-entropy past, on which every anthropic calculation relies, is not
  derived. It enters as a typicality assumption (Section 4).
- **A flat prior in today's \$\Lambda\$ is supported, conditionally.** Both the
  no-boundary wave function and the observer algebra of an inflationary universe
  weight sectors by the inflationary horizon, not by today's. The dependence on
  \$\Lambda\$ is then negligible (Sections 5 and 6).
- **The obstruction is conditioning versus summing.** Summing over saddles gives
  Boltzmann observers and a pull toward \$\Lambda\to0\$ by \$e^{10^{122}}\$.
  Conditioning on our history restores the anthropic calculation, but nothing in
  the algebra forces the choice (Sections 3 and 4).
- **The non-anthropic mechanisms examined do not close the gap.** Tracking noise
  of order \$H^2\$ fails even a survival filter. A frozen residual, as in
  sequestering, gives \$\Lambda\propto 1/T^2\$ in the total lifetime, which
  moves the prior problem onto the lifetime (Section 7).
- **Several statements in the earlier posts are corrected** (Section 2).

| Item                                                          | Status                |
| ------------------------------------------------------------- | --------------------- |
| Observer needed for de Sitter observables                     | literature            |
| Conditioning on an observer-supporting macrostate costs \$e^{-D}\$ | derived, checked   |
| No convention for the trace normalization is neutral in-sector | derived, checked     |
| Past hypothesis cannot be imposed as an initial state in dS   | derived (random-overlap estimate) |
| Weights depend on the inflationary, not today's, horizon      | inferred from [^8], [^9] |
| Tracking everpresent \$\Lambda\$ fails the survival filter    | checked (toy model)   |
| Dilation symmetry fixes a log-flat prior                      | tested, fails         |
| Any selection of \$\Lambda\$                                  | not obtained          |

## 1. Where the series left off

The first note [^1] organized the problem around three structural facts. The
observer algebra of a de Sitter observer is type II with a nontrivial center,
and \$\Lambda\$ does not appear in its construction. In Henneaux–Teitelboim
gravity [^23] the cosmological constant is conjugate to a global four-volume.
And the entropy of the observer algebra matches a generalized entropy only up to
a state-independent constant.

The second note [^2] showed that this constant is the measure problem in
algebraic form. A central rescaling of the trace changes absolute entropy but
not relative entropy, so the sector weights are not fixed by modular
consistency. The three natural conventions give three different weights: one
pushes \$\Lambda\$ up, one carries no \$\Lambda\$-dependence, and one reproduces
the Baum–Hawking weight [^17] [^18] that pushes \$\Lambda\to0\$.

The third note [^3] asked whether anthropic reasoning could be derived from the
observer, and tested a lineage weight, a causal-diamond coupling and a
detectability postulate in toy models. The present note revisits those results
with the corrections below.

## 2. Corrections to the series

1. **Hyperfinite uniqueness.** Section 2 of [^3] argued that the observer
   algebra cannot depend on \$\Lambda\$ because the hyperfinite II\$_1\$ factor
   is unique. This was already restated in [^2]: the relevant algebra is
   II\$_\infty\$ with a nontrivial center, and hyperfiniteness is not
   established. What survives is weaker and sufficient. \$\Lambda\$ is not part
   of the construction, so it enters only through the trace normalization and
   the state.
2. **The lineage gate.** Sections 3 and 4 of [^3] suggested that requiring a
   growth lineage could exclude Boltzmann observers. For the weights, the
   computation in Section 3 below shows the reverse: in the equilibrium
   (tracial) measure a lineage is suppressed relative to a bare observer. The
   gate removes bare observers from the reference class by definition. It does
   not make them improbable.
3. **The causal-diamond weight.** Sections 6 to 8 of [^3] integrated entropy
   production over a causal diamond, which produced a weight rising toward small
   \$\Lambda\$ and a tension of about a factor of ten with the observed value.
   First-person conditioning on local data, including the age of the universe
   [^9], removes the late-time volume factor. The tension is therefore a feature
   of that counting rule and not a robust result.
4. **Convention (b).** The statement in [^2] that convention (b) carries no
   preference holds for the sector weights only. Once a physical macrostate is
   imposed, an in-sector factor appears (Section 3), and no convention remains
   neutral.

## 3. The cost of conditioning on a macrostate

In the semiclassical regime a macrostate with energy \$E\$ and matter entropy
\$S_m\$ in a patch of radius \$R\$ has entropy [^6]

$$ S \approx S_{\rm dS} - \beta E + S_m, \qquad \beta = 2\pi R . $$

Its deficit from equilibrium is the free energy in units of the de Sitter
temperature,

$$ D = \beta E - S_m . $$

The weight of finding such a macrostate is the trace of its projector, which is
\$e^{-D}\$ under convention (b) and \$e^{S_{\rm dS}-D}\$ under convention (c).
The table uses \$R_0 = 1.0\times10^{61}\$ and \$S_{\rm dS} = 3.1\times10^{122}\$
in Planck units, and the change in log-weight when \$\Lambda\$ is raised by a
factor of four (\$R\to R_0/2\$).

| Macrostate            | \$D\$ (nats)         | \$D/S_{\rm dS}\$     | \$\Delta\ln w\$ (b)  | \$\Delta\ln w\$ (c)    |
| --------------------- | -------------------- | -------------------- | -------------------- | ---------------------- |
| Brain (1.4 kg)        | \$4\times10^{69}\$   | \$10^{-53}\$         | \$+2\times10^{69}\$  | \$-2.4\times10^{122}\$ |
| Human (70 kg)         | \$2\times10^{71}\$   | \$6\times10^{-52}\$  | \$+1\times10^{71}\$  | \$-2.4\times10^{122}\$ |
| Sun                   | \$6\times10^{99}\$   | \$2\times10^{-23}\$  | \$+3\times10^{99}\$  | \$-2.4\times10^{122}\$ |
| Milky Way             | \$9\times10^{111}\$  | \$3\times10^{-11}\$  | \$+4\times10^{111}\$ | \$-2.4\times10^{122}\$ |

Two consequences follow.

- **No convention is neutral.** Under (b) the weight \$e^{-2\pi R E}\$ prefers
  large \$\Lambda\$ with an exponent of \$10^{69}\$ nats for a single brain.
  Under (c) the Baum–Hawking term dominates and the macrostate corrects it only
  by a factor \$E/R\$, about \$10^{-23}\$ for the Sun. The anthropic factor,
  which varies by only 20 to 24 nats across \$\lambda\$ from \$10^{-3}\$ to
  \$10^2\$ (Section 6), is irrelevant against either. Neutrality would require a
  normalization \$N(\lambda)\propto e^{2\pi R E_{\rm sys}}\$ that depends on the
  macrostate.
- **Lineages lose to bare observers.** At the observed radius, the tracial
  weight of a star-supporting lineage relative to a bare brain is
  \$e^{-5.7\times10^{99}}\$. This is the Boltzmann problem in its usual form.

The first-order formula treats the energy as fixed while \$R\$ varies. For a
cosmological macrostate at fixed matter density, \$E\$ grows with \$R^3\$, which
strengthens the conclusion. A point-mass static patch is a poor model of a
matter-filled universe, so the table illustrates scales and is not a
cosmological computation.

## 4. The obstruction

### 4.1 What Harlow shows

Harlow [^7] argues that in higher dimensions the gravitational path integral is
too ambiguous to define \$\alpha\$-states, so \$\Lambda\$ cannot be a free
central parameter with an independent prior. In a landscape the weights of vacua
come from the path integral. For an observer of mass \$m\$ in a de Sitter vacuum
the weight is \$Z_{\rm dS}\approx e^{S_{\rm dS}-m/T_{\rm dS}}\$, which is
convention (c). He also shows that when the sphere partition function is large,
as in de Sitter, the disconnected contribution dominates and observer-dressed
expectation values are insensitive to the initial state. The observer then
almost surely finds itself in de Sitter space, even when the boundary conditions
describe an observer in AdS.

### 4.2 Why a past hypothesis does not help

Conditioning restores a cylinder-dominated regime only if the state's overlap
with the normalized Hartle–Hawking state is smaller than for a random state in a
Hilbert space of dimension \$e^{S_{\rm dS}}\$ [^7]. If the Hartle–Hawking state
is modeled as a random vector, then for any fixed unit state \$\psi\$ the mean
squared overlap is exactly \$1/\dim\mathcal H = e^{-S_{\rm dS}}\$, independent
of how small the entropy of \$\psi\$'s macrostate is. A low-entropy initial
condition therefore does not make the overlap anomalously small. The cylinder
and the sphere come out comparable, and no macrostate property selects the
cylinder.

The conclusion is that the restriction to a quasiclassical, low-entropy history
has to be imposed. This is the Past Hypothesis problem in algebraic form, and it
is why the state principle proposed at the end of [^2] is not an optional extra:
it is the premise on which any anthropic calculation rests.

### 4.3 How the literature handles it

Hartle and Hertog [^9] treat anthropic selection as an inevitable part of
prediction in quantum cosmology, with probabilities conditioned on our local
data. They exclude Boltzmann observers by an explicit typicality assumption, to
be tested like any other assumption [^13], and not by derivation. This matches
the finding above. Conditioning is a choice with a name and a testable status,
and the algebra does not supply it.

## 5. Observers in an inflationary universe

### 5.1 The algebra

Kudler-Flam, Leutheusser and Satishchandran [^8] construct the algebra of
dressed observables for a comoving observer in an FLRW universe that is
asymptotically de Sitter in the past. The inflaton zero mode \$\tilde q\$ is
quantized and fluctuates the effective cosmological constant during inflation.
The algebra is type II\$_\infty\$ with \$\tilde q\$ central, has no
maximum-entropy state, and its trace is

$$ \mathrm{Tr}(\hat a) = \langle \Omega_{\rm BD}, 0_\tau |\,
e^{\frac{2\pi}{H_0}(\tilde q - \varepsilon)}\, \hat a\, | \Omega_{\rm BD},
0_\tau \rangle . $$

The trace is unique only up to functions of the center, which is exactly the
normalization ambiguity of [^2]. The authors fix it by requiring that the von
Neumann entropy of semiclassical states equal the generalized entropy of the
observer's causal diamond, a quantity they describe as sensitive to the initial
conditions of the universe. Three points follow.

1. **The center is not today's \$\Lambda\$.** It is the inflationary effective
   cosmological constant, with \$H_0^2 = (\Lambda+\Lambda_{\rm eff})/3\$ during
   inflation.
2. **The area term is the inflationary horizon.** Today's \$\Lambda\$ enters the
   trace only through the sum \$\Lambda+\Lambda_{\rm eff}\$, which
   \$\Lambda_{\rm eff}\$ dominates. This is an inference from the formulas,
   since the paper does not compute the \$\Lambda\$-dependence.
3. **The deficit is defined.** The entropy contains
   \$-S_{\rm rel}(\psi\Vert\Omega_{\rm BD}) - (2\pi/H_0)\varepsilon\$, so the
   deficit \$D\$ of Section 3 has a precise definition with \$\beta = 2\pi/H_0\$
   set by the inflationary rate.

For an inflationary scale \$H_0\sim10^{13}\$ GeV (an assumption), the scales
differ sharply from those of the late-time sphere:

| Quantity                      | Late-time dS (Section 3)            | Inflationary horizon                 |
| ----------------------------- | ----------------------------------- | ------------------------------------ |
| Entropy scale                 | \$3.1\times10^{122}\$               | \$4.7\times10^{12}\$                 |
| Observer cost \$\beta m\$ (70 kg) | \$2\times10^{71}\$              | \$2.5\times10^{16}\$                 |
| Dependence on today's \$\Lambda\$ | \$e^{S_{\rm dS}(\Lambda)}\$     | \$\delta S\sim10^{-97}\$ nats        |

The last entry comes from \$\Lambda/\Lambda_{\rm eff}\sim10^{-110}\$. If the
weights really depend on the inflationary horizon, the trace is flat in today's
\$\Lambda\$ to extraordinary precision, and the neutrality that [^2] could only
assume as convention (b) follows from the construction. Convention (c) is also
the normalization that Witten's background-independent algebra [^11] and its
realization by Blommaert, Kudler-Flam and Urbach [^10] suggest, with the
observer's no-boundary state playing the role of the identity operator and
entropies defined as relative entropies against it. Whether that reproduces the
same flat dependence on today's \$\Lambda\$ has not been checked.

### 5.2 Conditioned versus summed

The construction of [^8] is a fixed-background construction around one
inflationary history. It conditions and does not weigh backgrounds against each
other. Harlow's analysis sums over saddles. Comparing an ordinary-history
observer in the inflationary no-boundary saddle (weight \$e^{S_{\rm infl}}W\$,
an assumption) with a bare observer in the late-time sphere (weight
\$e^{S_{\rm dS}-2\pi Rm}\$):

| \$\lambda/\lambda_0\$ | \$10^{-3}\$           | \$1\$                 | \$10^{3}\$            |
| --------------------- | --------------------- | --------------------- | --------------------- |
| \$\ln w_B - \ln w_A\$ | \$3\times10^{125}\$   | \$3\times10^{122}\$   | \$3\times10^{119}\$   |

The bare observer stops dominating only for
\$\Lambda\gtrsim10^{102}\Lambda_{\rm obs}\$ (\$H_0=10^{13}\$ GeV) or
\$4\times10^{101}\Lambda_{\rm obs}\$ (\$H_0=10^{9}\$ GeV), where the horizon
radius is comparable to the observer's own size. So the two papers do not
contradict each other. They describe different regimes, and the physical
question is which regime applies. Neither paper settles which regime is
physical. Chen and Penington [^12] show that a rolling inflaton acts as a
physical clock and stress the role of out-of-equilibrium dynamics, which echoes
the driven-arrow requirement of the observer ladder [^4]. That link is a
conjecture.

One gap remains. The algebra of [^8] assumes non-eternal inflation, while Hartle
and Hertog find the dominant histories at the eternal-inflation threshold [^9].
The two regimes have not been connected.

## 6. The first-person calculation and the prior

Hartle and Hertog [^9] find that the no-boundary prior depends on \$\Lambda\$
only through the sum of \$\Lambda\$ and the inflationary potential at the start
of eternal inflation, so it is approximately flat in \$\Lambda\$ across the
anthropic range. Combined with the structure factor, it restores Weinberg's
prediction [^14]. This agrees with the flat dependence inferred in Section 5.

With the collapsed-fraction factor \$F(\lambda)\$ of [^3] (flat \$\Lambda\$CDM
growth, Press–Schechter threshold, galaxy-scale rms of 2 at the observed
\$\lambda_0 = \rho_\Lambda/\rho_m \approx 2.2\$), the posterior depends on the
prior as follows.

| Prior on \$\lambda\$                          | \$P(\lambda\le\lambda_0)\$ | median \$\lambda\$ | 16–84% range    |
| --------------------------------------------- | -------------------------- | ------------------ | --------------- |
| Flat, no floor                                | 0.089                      | 24.9               | 4.6–89          |
| Flat, detectability floor \$\varepsilon=0.05\$ | 0.087                      | 25.0               | 4.7–89          |
| Log-flat, range \$10^{-4}\$ to \$10^{4}\$ only | 0.893                     | 0.016              | 0.000–0.94      |
| Log-flat, floor \$\varepsilon=0.05\$          | 0.733                      | 0.54               | 0.10–5.2        |

The flat row reproduces the result of [^2] and [^15]: structure formation gives
an upper edge, and the observed value sits in the lower tail but is not
excluded. The coincidence required differs sharply with the prior:

| Prior                                      | Probability of landing in the window \$0.05<\lambda<30\$ |
| ------------------------------------------ | -------------------------------------------------------- |
| Flat over a Planck-width range             | \$\sim3\times10^{-121}\$                                 |
| Log-flat over 10 decades below \$\lambda\sim1\$  | 0.24                                               |
| Log-flat over 30 decades                   | 0.088                                                    |
| Log-flat over 122 decades                  | 0.022                                                    |

The entire cosmological constant problem therefore lives in the prior. A flat
prior over a Planck-scale range gives the original tuning. A scale-free prior
reduces it to a few percent, but it has no lower edge from structure formation,
so the posterior piles up at tiny \$\Lambda\$ unless a floor such as
detectability is added. That floor is a selection on the measured outcome, which
is the weakest step of this route.

## 7. The non-anthropic route

### 7.1 Tracking noise fails a survival filter *(toy model)*

If \$\Lambda\$ tracks \$H^2\$ with random sign, as in everpresent-\$\Lambda\$
proposals [^21] [^22], then \$\omega = \Lambda/3H^2\$ is a stationary process of
unit variance times an amplitude \$s\$, with correlation \$\sqrt{V_1/V_2}\$ in
the past-cone volume \$V\sim t^4\$. This is an Ornstein–Uhlenbeck process in
\$\ln V\$ with correlation \$e^{-|\Delta\ln V|/2}\$. A history survives if the
universe never stalls (\$\omega>-1\$ at all times, since \$\Lambda<-\rho_m\$
makes \$H^2<0\$) and \$\omega<3\$ during galaxy formation (0.2 to 2 Gyr).
Starting from \$\ln V=0\$ and running to today's \$\ln V\approx559\$:

| Amplitude \$s\$   | \$\le0.2\$ | 0.25 | 0.3  | 0.4                 | \$\ge0.5\$ |
| ----------------- | ---------- | ---- | ---- | ------------------- | ---------- |
| Survival fraction | \$\approx1\$ | 0.92 | 0.42 | \$3.5\times10^{-4}\$ | 0          |

Reaching the observed \$\omega_0\approx2.2\$ would need \$s\gtrsim0.7\$, where
survival is essentially zero. Any prior on \$s\$ piles up at the cliff, so the
predictive distribution for today's \$\omega\$ has 5% and 95% quantiles of
\$-0.3\$ and \$+0.29\$. The cause is the negative barrier, which a symmetric
process of order-one amplitude hits within a few correlation times, and the
result depends only logarithmically on when the mechanism switches on. The model
is crude (open-loop, background-normalized, assumed correlation structure), so
the cliff location is approximate. The conclusion is that the data favor a
frozen positive \$\Lambda\$ and not a tracking one, which is the opposite time
dependence from what a volume-driven mechanism wants.

### 7.2 Sequestering and the dilation idea *(checked against the action)*

Vacuum-energy sequestering [^19] [^20] makes the matter-sector scales
functionals of the 4-volume, with action

$$ S=\int d^4x\sqrt{g}\Big[\tfrac{M_{\rm Pl}^2}{2}R-\Lambda-\lambda^4\mathcal
L(\lambda^{-2}g^{\mu\nu},\Phi)\Big]
+\sigma\!\Big(\frac{\Lambda}{\lambda^4\mu^4}\Big), $$

where \$\Lambda\$ and \$\lambda\$ are global variables without local dynamics.
Varying them gives \$\sigma'/(\lambda^4\mu^4)=\int d^4x\sqrt g\equiv V\$ and
\$4\Lambda V=\int d^4x\sqrt g\,T\$, so
\$\Lambda=\tfrac14\langle T^\mu{}_\mu\rangle\$. In a bang–crunch universe the
average is dominated by the turnaround,
\$\langle T\rangle\simeq O(1)M_{\rm Pl}^2H_{\rm age}^2\$, and the residual
cosmological constant is naturally small in a large, old universe. The authors
state that this does not automatically fit the data but makes the needed tunings
gentler.

The scaling \$\lambda\to\Omega\lambda\$, \$g\to\Omega^{-2}g\$,
\$\Lambda\to\Omega^4\Lambda\$ acts on the Henneaux–Teitelboim pair as
\$V\to\Omega^{-4}V\$ and \$\Lambda\to\Omega^4\Lambda\$, leaving \$\Lambda V\$
invariant. A scale-free state of that pair is a dilation eigenstate, log-flat in
both \$V\$ and \$\Lambda\$, so the scaling looked like a symmetry that could
justify a log-flat prior. The action rules this out for three reasons.

1. **The scaling is not a symmetry.** The Einstein–Hilbert term breaks it
   explicitly, so no symmetry protects a \$d\lambda/\lambda\$ measure.
2. **The dilation charge is not free.** \$\Lambda V=\tfrac14\int\sqrt g\,T\$ is
   fixed by the matter history, not a free eigenvalue.
3. **\$\lambda\$ is not the scanning variable.** It is degenerate with the bare
   masses and fixed observationally, and the hierarchy is carried by the
   phenomenological function \$\sigma\$. For a lifetime of \$10/H_0\$ the
   authors need \$\sigma'\sim(10\mu/H_0)^4\$.

What survives is structural: \$\Lambda\propto1/T_{\rm life}^2\$ with
\$T_{\rm life}\$ the total lifetime including the future. This is the same
dependence as in causal-set everpresent \$\Lambda\$, with one difference.
Sequestering gives a single frozen number, while tracking noise fails the
survival filter. The prior on \$\Lambda\$ becomes a prior on the lifetime, and
the same question reappears:

| Prior on lifetime                       | What it gives                                                   |
| --------------------------------------- | --------------------------------------------------------------- |
| Flat up to \$T_{\max}\$                 | probability of landing near our age \$\sim T_0/T_{\max}\$; typical \$\Lambda\$ far below observed |
| Log-flat from the Planck time to now    | window probability of about 1%, no lower edge                   |

Neither can be justified from the action. The tuning has moved from \$\Lambda\$
to the lifetime and to the form of \$\sigma\$.

## 8. Where the program stands

### 8.1 What the series established

1. In de Sitter space the observer is needed for the theory to have observables,
   so anthropic conditioning is a requirement of the theory and not an added
   postulate *(literature plus argument)*.
2. The trace normalization across sectors is not determined by modular data and
   acts as the prior over sectors [^2].
3. Conditioning on an observer-supporting macrostate costs \$e^{-D}\$ in the
   tracial measure, and no convention for the normalization is neutral against
   it (Section 3).
4. A past hypothesis cannot be imposed as an initial state in de Sitter space,
   because the overlap with a random Hartle–Hawking state does not depend on the
   macrostate's entropy (Section 4).
5. In an inflationary universe the observer algebra and the no-boundary prior
   weight sectors by the inflationary horizon, which makes the prior
   approximately flat in today's \$\Lambda\$, conditionally on the inflationary
   history (Sections 5 and 6).
6. With that conditioning, the anthropic calculation reproduces the Weinberg
   result, with the observed \$\Lambda\$ in the lower tail of the allowed range.
7. Tracking noise fails a survival filter, and the dilation measure suggested by
   sequestering fails against the action (Section 7).

### 8.2 What remains unresolved

The obstruction is not the flat prior. It is the choice of conditioning over
summing, which nothing in the algebra forces, together with the prior over
\$\Lambda\$ or the lifetime. A selection of \$\Lambda\$ would need both a
principle that picks the conditioned regime and a derivation of the prior. Open
problems, in order of tractability:

1. **Which regime applies.** Whether the typicality assumption that excludes
   Boltzmann observers can be replaced by a derived principle, for instance the
   cylinder-dominance condition of Section 4.2 with the correct Hartle–Hawking
   norm for an inflationary history.
2. **The center weight and the no-boundary prior.** Whether the trace weight
   \$e^{2\pi\tilde q/H_0}\$ of [^8] equals the Hartle–Hertog prior [^9],
   including the unit conventions, which have not been compared.
3. **Eternal inflation.** Extending the algebra of [^8] to the eternal-inflation
   threshold, where the dominant no-boundary histories sit.
4. **Fluctuation dominance in type II\$_\infty\$.** Whether Harlow's argument
   survives when the algebra has a non-compact center and no maximum-entropy
   state.
5. **The trace as typicality.** Whether the self-sampling assumption has the
   tracial weight as its mathematical counterpart, which remains an unverified
   conjecture [^3].
6. **The prior.** Flat versus scale-free, on \$\Lambda\$ or on the lifetime. No
   derivation exists.

## Conclusion

The series set out to ask whether putting the observer inside the theory could
explain the smallness of the cosmological constant. It can explain why
conditioning on an observer is not optional, why the trace normalization is the
measure problem, and why the weights relevant to an inflationary history do not
depend on today's \$\Lambda\$. It cannot explain why the history is a
low-entropy one, and it does not say what the prior over \$\Lambda\$ is.

The non-anthropic mechanisms examined converge on the same gap from the other
side. They replace the smallness of \$\Lambda\$ by a prior over a lifetime or an
amplitude, and the survival test excludes the version that tracks the expansion.
What a selection of \$\Lambda\$ would need is a derived principle for the
conditioned regime together with a derived prior, and neither exists in the
framework as it stands.

## References

[^1]: Saeid Aliei, CC Problem and ER=EPR in dS, 2026,
    https://saeidaliei.github.io/posts/cosmological-constant-problem-algebraic-er-epr-ds/.

[^2]: Saeid Aliei, CC Problem and ER=EPR in dS: Updates, 2026,
    https://saeidaliei.github.io/posts/update-cc-problem-algebraic-er-epr/.

[^3]: Saeid Aliei, Can Anthropic Principle be Derived From The Observer?, 2026,
    https://saeidaliei.github.io/posts/anthropic-principle-from-the-observer/.

[^4]: Saeid Aliei, A Mind's Own Clock: Modular Time, Growth, and the Self, 2026,
    https://saeidaliei.github.io/posts/a-minds-own-clock/. See also The
    Observer, https://saeidaliei.github.io/posts/the-observer/.

[^6]: Julian De Vuyst, Stefan Eccles, Philipp A. Höhn and Josh Kirklin,
    Gravitational entropy is observer-dependent, 2024,
    https://arxiv.org/abs/2405.00114.

[^7]: Daniel Harlow, Observers, alpha-parameters, and the Hartle-Hawking state,
    2026, https://arxiv.org/abs/2602.03835.

[^8]: Jonah Kudler-Flam, Samuel Leutheusser and Gautam Satishchandran, Algebraic
    Observational Cosmology, 2024, https://arxiv.org/abs/2406.01669.

[^9]: James B. Hartle and Thomas Hertog, Anthropic Bounds on Lambda from the
    No-Boundary Quantum State, 2013, https://arxiv.org/abs/1309.0493.

[^10]: Andreas Blommaert, Jonah Kudler-Flam and Erez Urbach, Absolute entropy
    and the observer's no-boundary state, *Journal of High Energy Physics*
    2025(11), 113, https://arxiv.org/abs/2505.14771.

[^11]: Edward Witten, A background-independent algebra in quantum gravity, 2023,
    https://arxiv.org/abs/2308.03663.

[^12]: Hong Zhe Chen and Geoff Penington, A clock is just a way to tell the
    time: gravitational algebras in cosmological spacetimes, 2024,
    https://arxiv.org/abs/2406.02116.

[^13]: James B. Hartle and Mark Srednicki, Are we typical?, *Physical Review D*
    75, 2007, 123523, https://arxiv.org/abs/0704.2630.

[^14]: Steven Weinberg, Anthropic bound on the cosmological constant, *Physical
    Review Letters* 59, 1987, pp. 2607-2610.

[^15]: Hugo Martel, Paul R. Shapiro and Steven Weinberg, Likely values of the
    cosmological constant, *The Astrophysical Journal* 492, 1998, pp. 29-40,
    https://arxiv.org/abs/astro-ph/9701099.

[^17]: Stephen W. Hawking, The cosmological constant is probably zero, *Physics
    Letters B* 134, 1984, pp. 403-404.

[^18]: Eduard Baum, Zero cosmological constant from minimum action, *Physics
    Letters B* 133, 1983, pp. 185-186.

[^19]: Nemanja Kaloper and Antonio Padilla, Sequestering the Standard Model
    Vacuum Energy, *Physical Review Letters* 112, 2014, 091304,
    https://arxiv.org/abs/1309.6562.

[^20]: Nemanja Kaloper and Antonio Padilla, Vacuum Energy Sequestering: The
    Framework and Its Cosmological Consequences, *Physical Review D* 90, 2014,
    084023, https://arxiv.org/abs/1406.0711.

[^21]: Maqbool Ahmed, Scott Dodelson, Patrick B. Greene and Rafael Sorkin,
    Everpresent Lambda, *Physical Review D* 69, 2004, 103523,
    https://arxiv.org/abs/astro-ph/0209274.

[^22]: Rafael D. Sorkin, Is the cosmological constant a nonlocal quantum residue
    of discreteness of the causal set type?, *AIP Conference Proceedings* 957,
    2007, pp. 142-153, https://arxiv.org/abs/0710.1675.

[^23]: Marc Henneaux and Claudio Teitelboim, The cosmological constant and
    general covariance, *Physics Letters B* 222, 1989, pp. 195-199.

