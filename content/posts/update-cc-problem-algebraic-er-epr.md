---
title: "CC Problem and ER=EPR in dS: Updates"
date: 2026-11-18
---

*This is a follow-up to [^1] and [^2]. It is a status report: what survived further checking, 
what was retracted, and what the checks added.*

## Summary

- **Nothing in the algebraic framework selects \$\Lambda\$.** The reason is now more precise than "we did not find it". 
The algebra of a de Sitter observer is insensitive to \$\Lambda\$ except through a state-independent normalization 
of the trace and through the state on the center. Both are inputs, not outputs.
- **The normalization ambiguity is the measure problem in algebraic form.** For a tracial state the central marginal 
is fixed by the normalization of the trace. The three natural conventions give three different cross-sector weights. 
Two of them are excluded by observation on opposite sides, and the third carries no \$\Lambda\$-dependence at all (Section 3).
- **A single clock records the sector only weakly.** The mutual information between clock energy and a continuous 
sector label is of order one nat, against \$S_{\rm dS}\sim10^{122}\$ (Section 5).
- **Observers sharing a region of space share less than one might expect.** In a finite-dimensional model 
with a quantum relative-position label, the shared algebra is classical in that label (Section 6).
- **Several earlier statements are retracted** (Section 2).

| Item | Status |
|---|---|
| Fixed-volume ensemble gives \$Z(V)\approx e^{2S_{\rm dS}(V)}\$ | exact (saddle point) |
| One observer produces no interior extremum of the weight | numerical (grid) plus exact first-order |
| Three normalization conventions and their implied weights | exact formulas; orders of magnitude from approximate constants |
| Clock energy records a sector label with \$O(1)\$ nats | numerical, Monte Carlo cross-checked |
| Shared algebra classical in relative geometry | exact in a toy; conjecture in de Sitter |
| Frame-loop holonomy equals Haar area | exact |
| Any selection of \$\Lambda\$ | not obtained |

## 1. Where the first note left off

The first note [^1] organized the problem around three structural facts. The observer algebra of Chen and Xu [^3] is type II\$_\infty\$ 
with a nontrivial center encoding causal visibility, and \$\Lambda\$ does not appear in their construction 
(they set \$\ell_{\rm dS}=1\$). A Henneaux–Teitelboim sector [^7] promotes \$\Lambda\$ to a variable conjugate to four-volume. 
The entropy of the observer algebra matches a generalized entropy only up to a state-independent constant [^4][^5]. 
The note's own program was to ask whether any state on the center, or any consistency condition between observers, could constrain \$\Lambda\$.

## 2. Retractions and corrections

These are statements made in intermediate drafts and discussion that did not survive further checking.

1. **"The normalization is fixed by matching to the horizon entropy"** is **[retracted]**. 
In the standard treatment the additive constant \$S_0\$ is a state-independent ambiguity; 
when the clock energy is bounded below it is fixed by \$\mathrm{Tr}(1)=1\$, 
which makes the maximally mixed state have zero entropy [^4][^5]. 
Matching \$S_{\max}=S_{\rm dS}\$ is an additional choice, not part of the construction.
2. **A Jones-index quantization constraint on the overlap of two observers** is **[retracted]**. 
It needed the overlap inclusion to be an irreducible finite-index subfactor inclusion. 
The multi-observer algebra is not a factor, and the QFT part of the overlap is type III\$_1\$ before dressing, 
for which we have no reason to expect finite index.
3. **"The algebra cannot depend on \$\Lambda\$ because the hyperfinite II\$_1\$ factor is unique"** needs restating. 
The relevant algebra is II\$_\infty\$ with a nontrivial center, and hyperfiniteness is not stated. 
What survives is weaker and sufficient: \$\Lambda\$ is not in the construction, so it can enter only through normalization and state.
4. **"\$\Lambda\$ is a free central \$\alpha\$-parameter whose measure is fixed by the gravitational path integral"** is **downgraded to an assumption**. Harlow's abstract states that in higher dimensions the gravitational path integral is too ambiguous to construct well-defined \$\alpha\$-states [^10].
5. **"Mutual visibility is a single projection common to both observers"** is **[retracted]**. 
Visibility of the other observer's geodesic is symmetric, but visibility at the level of 
the relative group element (b's clock reading inside a's patch versus a's inside b's) is not: 
the two sets differ, so the two observers have different walls.
6. **"Entropy production seen through a shared algebra might carry new information"** was tested in a toy model (Section 6). 
It reduces to the entropy production of the overlap region.

## 3. The normalization is the measure problem

### 3.1 The identity

Let the observer algebra over a family of sectors \$\lambda\$ (values of the cosmological constant) 
be a direct integral \$\mathcal A=\int^\oplus\mathcal A_\lambda\,d\mu(\lambda)\$ with \$\lambda\$ in the center. 
A trace on \$\mathcal A\$ is \$\tau_N=\int d\mu\,N(\lambda)\,\tau_\lambda\$ for any positive \$N\$. 
For the tracial state \$\omega=\tau_N/\tau_N(1)\$ (it exists only in the II\$_1\$ case), the marginal on the center is

$$p(\lambda)=\frac{N(\lambda)\,\tau_\lambda(1)}{\tau_N(1)}.$$

Relative entropy and modular data are blind to \$N\$, because rescaling the trace by a central function 
changes the Connes cocycle only by a central phase. The absolute entropy shifts by \$\int p\log N\$ 
(checked numerically in finite dimensions: the shift matched \$\langle\log N\rangle_p\$ to 14 digits). 
So the normalization is not an observable, but when the physical state is the equilibrium state across sectors, it is the prior. 
This is precisely the statement of eq. (3.10) of [^5], applied to a family of sectors.

### 3.2 The explicit form

In the construction of De Vuyst, Eccles, Höhn and Kirklin [^5][^6] the trace for an observer 
with clock \$C_i\$ and KMS state \$\psi_S\$ at inverse temperature \$\beta\$ is

$$\mathrm{Tr}(\cdot)=e^{S_{0,i}}\,\langle\psi_S|\langle0|_i\,(\cdot)\,e^{-\beta H_i}\,|\psi_S\rangle|0\rangle_i ,
\qquad \mathrm{Tr}(1)=e^{S_{0,i}}\frac{Z_i}{2\pi},\quad Z_i=\int_{\sigma_i}e^{-\beta\epsilon}\,d\epsilon .$$

For a clock with energy spectrum \$\sigma_i=[m,\infty)\$ this gives \$Z_i=e^{-\beta m}/\beta\$. 
In de Sitter \$\beta=2\pi R=2\pi\sqrt{3/\Lambda}\$, so \$Z_i\$ depends on \$\Lambda\$.

### 3.3 Three conventions

| Convention | Choice of \$S_0\$ | Sector weight \$\propto\$ | Pushes \$\Lambda\$ |
|---|---|---|---|
| (a) same formula in every sector | \$S_0=0\$ | \$Z/2\pi=e^{-2\pi mR}/(2\pi\beta)\$ | up (small \$R\$) |
| (b) normalized trace, as in [^4] | \$\mathrm{Tr}(1)=1\$ | \$1\$ | no preference |
| (c) maximum entropy equals the horizon entropy | \$S_{\max}=S_{\rm dS}\$ | \$e^{S_{\rm dS}}=e^{\pi R^2/G}\$ | down (\$\Lambda\to0\$) |

Convention (a) is not canonical (the KMS temperature differs between sectors), but it is the naive choice. 
Convention (c) reproduces the Baum–Hawking-type weight [^8][^9]. 
With approximate constants \$\Lambda\approx1.1\times10^{-52}\,\mathrm{m^{-2}}\$, one finds in Planck units \$R\approx1.0\times10^{61}\$ 
and \$S_{\rm dS}\approx3.3\times10^{122}\$. For a proton-mass clock \$\beta m\approx5\times10^{42}\$, 
and for a 70 kg observer \$\beta m\approx2\times10^{71}\$. 
Halving \$R\$ changes the log-weight by about \$+2.5\times10^{42}\$ 
under (a) and about \$-2.5\times10^{122}\$ under (c).

**Consequence.** Conventions (a) and (c) are excluded by observation on opposite sides, 
one toward Planckian \$\Lambda\$ and one toward \$\Lambda=0\$. 
Convention (b) survives, but it carries no \$\Lambda\$-dependence from the algebra. 
Whatever selects \$\Lambda\$ must therefore enter through the observer weight, not through the counting. 
This relies on the clock's lower bound \$m\$ being \$\Lambda\$-independent and on the tracial-state reading; 
it fails in the multi-observer II\$_\infty\$ case, where \$\mathrm{Tr}(1)=\infty\$ and no tracial state exists.

### 3.4 A sense in which the count can be renormalized

In the semiclassical regime the entropy of a physical state is [^5]

$$S\approx S_0-S_{\rm rel}(\phi_S\Vert\psi_S)-\beta\sum_{C_i\in R}\langle H_i\rangle+S_R .$$

The area term enters through the relative entropy. The same paper shows that in an "antisemiclassical" regime, 
where a clock's energy sits in a very narrow window, the leading entropy is independent of the QFT part of the state, 
so no area term appears; and that the total horizon entropy including all clocks is observer-independent [^5]. 
A count restricted to what a given observer can access can therefore lose the \$S_{\rm dS}\$ dependence, 
while a count of the total keeps it. Which count a measure should use is the same choice as before. 
This as an interpretation, not a result of [^5].

## 4. Baseline joint computation

### 4.1 Fixed-volume ensemble

With \$\Lambda\$ conjugate to four-volume [^7], integrating \$\Lambda\$ 
against the volume constraint gives, on the \$S^4\$ saddle,

$$Z(V)=\int d\Lambda\,\exp\!\Big[\frac{\Lambda V}{8\pi G}+\frac{3\pi}{G\Lambda}\Big]\;\approx\;e^{2S_{\rm dS}(V)},\qquad S_{\rm dS}(V)=\frac{\sqrt{6V}}{4G}.$$

The saddle sits at \$\Lambda_*=2\sqrt6\,\pi/\sqrt V\$, which reproduces \$V=24\pi^2/\Lambda^2\$. 
The second derivative is positive (a minimum along real \$\Lambda\$, as expected for a Legendre transform along a rotated contour). 
The factor 2 is not an error: the \$\Lambda\$-conjugate phase contributes \$e^{S}\$ and the fixed-\$\Lambda\$ sphere contributes another \$e^{S}\$. 
The weight grows with \$V\$, so the ensemble prefers large volume, i.e. small \$\Lambda\$. 
The relation \$S_{\rm dS}=\sqrt{6V}/4G\$ holds identically because all these quantities are functions of the single scale \$R\$; 
it is not independent evidence for anything.

### 4.2 Adding one observer

To first order in \$Gm/R\$ an observer of mass \$m\$ changes the weight to \$e^{S_{\rm dS}-2\pi mR}\$. With \$x=1/\sqrt\Lambda\$ 
the exponent is \$a x^2-bx\$ with \$a=3\pi/G\$ and \$b=2\sqrt3\,\pi m\$, whose stationary point is a minimum at \$R=Gm\$. 
For the exact Schwarzschild–de Sitter cosmological horizon, with the Nariai bound \$R\ge3\sqrt3\,Gm\$, we checked \$dS_c/dR>0\$ 
on a 2000-point grid up to \$R=200\,Gm\$, and that the first-order offset \$S_c-(\pi R^2-2\pi mR)\$ 
approaches a constant near \$-2\pi\$ (\$-6.30\$ at \$R=1000\,Gm\$). 
So a single observer produces no interior extremum in the physical range. 
We ignored one-loop factors and the phase of the sphere path integral; none changes the exponential behaviour.

## 5. What a clock can record about a sector

### 5.1 Weak records of a continuous label

If the sector label is a continuous variable and the clock energy is thermal in each sector, 
\$q\mid\beta\sim\mathrm{Exp}(\beta)\$. For a log-uniform prior on \$\beta\in[1,\rho]\$ the marginal is

$$f(q)=\frac{e^{-q}-e^{-\rho q}}{q\ln\rho},\qquad I(\Lambda;q)=h(q)-1+\tfrac12\ln\rho .$$

| \$\rho=R_2/R_1\$ | 2 | 10 | 100 | \$10^4\$ | \$10^8\$ |
|---|---|---|---|---|---|
| \$I\$ in nats | 0.019 | 0.165 | 0.437 | 0.888 | 1.459 |

The marginal normalizes to \$1.000000\$ and a Monte Carlo estimate at \$\rho=100\$ gives \$0.4368\pm0.0021\$. 
A scalar record of a continuous label carries a few nats at most, while \$S_{\rm dS}\sim10^{122}\$. 
The posterior over sectors given the clock energy is \$p(\Lambda\mid x)\propto p(\Lambda)\,\beta e^{-\beta x}\$, 
whose log-weight with the entropy prior is \$S_{\rm dS}-\beta x\$, the weight of Section 4.2.

### 5.2 Visibility labels and the charge relation

The center of the multi-observer algebra of [^3] is generated by event-level visibility projections: 
conditions on the relative angle and on the other observer's clock time lying inside a window. 
For two observers and no QFT excitations the constraints reduce to \$d_{a,i}+d_{b,i}=0\$ for the three generators, 
which [^3] notes forces the observers to be antipodal. 
Using the classical charge vector of b, \$E_b(\cos\varphi\cosh s,\ \sin\varphi\cosh s,\ \sinh s)\$, and of a, \$(q_a,0,0)\$, 
the three constraints give \$\sinh s=0\$ and \$\sin\varphi=0\$: b is either coincident with a or antipodal, with \$q_a=\mp E_b\$.

Writing the left boost generator along a's geodesic in terms of b's right generators gives exactly

$$\mathrm{Ad}(g^{-1})B_1=a\,R+b\,B_1+c\,B_2,$$

$$a=-\sin\varphi\sinh t-\cos\varphi\sinh s\cosh t,\quad b=\cos\varphi\cosh s,\quad c=-\sin\varphi\cosh t-\cos\varphi\sinh s\sinh t,$$

with \$b^2+c^2-a^2=1\$. The \$B_1\$ coefficient is the classical relation \$q_a=-E_b\cos\varphi\cosh s\$; 
the other two components carry b's remaining right charges, which do not commute (\$[R_{B_2},R_R]\propto E_b\$) and so fluctuate 
by at least \$\sim\sqrt{E_b}\$. This supports the classical relation for heavy observers and says nothing 
for \$E_b\sim O(1)\$. Positivity \$E_b\ge0\$ cannot be an operator statement on \$L^2(SO(1,2))\$, 
since boost generators have spectrum on all of \$\mathbb R\$ in unitary irreducible representations, so it must be imposed by projection.

### 5.3 Degradation with QFT energy

When the QFT carries boost energy \$h\$, \$q_a=-(h+d_{b,1})\$ and \$h\$ is not sign-definite. 
Modeling \$q_a=-h-\sigma e\$ with \$h\sim\mathcal N(0,w^2)\$ and \$\sigma=\pm1\$ for coincident 
versus antipodal b, the fraction of the visibility bit recoverable from the clock energy is:

| Thermal clock, \$e\sim\mathrm{Exp}(1)\$ (units of \$T_{\rm dS}\$), noise \$w\$ | 0.01 | 0.1 | 0.3 | 1 | 3 | 10 |
|---|---|---|---|---|---|---|
| \$I/\ln2\$ | 0.987 | 0.879 | 0.686 | 0.318 | 0.069 | 0.007 |

| Heavy clock \$e=m\$, ratio \$m/w\$ | 0.5 | 1 | 2 | 3 | 4 |
|---|---|---|---|---|---|
| \$I/\ln2\$ | 0.161 | 0.486 | 0.913 | 0.994 | 1.000 |

Normalizations are \$1.000000\$, and Monte Carlo agrees (\$0.4763\pm0.0019\$ 
against \$0.47575\$ at \$w=0.3\$; \$0.2200\pm0.0020\$ against \$0.22024\$ at \$w=1\$). 
The record is robust for heavy clocks and fragile for thermal-scale ones. 
The model assumes \$h\$ is independent of the visibility label, which real excitations need not satisfy.

## 6. Shared algebras of non-complementary observers

### 6.1 What the literature gives

De Vuyst et al. show that algebras for different clock sets \$R_1,R_2\$ 
in the same region satisfy \$r(\mathcal A_{R_1})\cap r(\mathcal A_{R_2})=r(\mathcal A_{R_1\cap R_2})\$, 
which is trivial for disjoint sets when the modular flow is ergodic, while the algebras still do not commute [^5]. 
They also state that they assume each clock has access to a single fixed subregion, 
and that clocks with access to different subregions are a separate source of observer dependence [^5]. 
The patches of Chen and Xu [^3] differ, so the overlap problem sits in that gap.

### 6.2 A finite-dimensional model

Take four qubits on a ring plus a four-state label \$x\$ for b's offset. 
Observer a has \$\mathcal A_a=B(\text{label})\otimes B(\text{sites }0,1)\$, 
and b's algebra is its conjugate by the controlled translation \$U=\sum_x|x\rangle\langle x|\otimes T^x\$, 
so b's region is \$\{x,x+1\}\$. We computed everything by linear algebra, with rank thresholds of \$10^{-8}\$ against clear gaps.

| Version | \$\dim\mathcal A_a=\dim\mathcal A_b\$ | \$\dim(\mathcal A_a\cap\mathcal A_b)\$ | Center of the intersection | \$\dim(\mathcal A_a\otimes_N\mathcal A_b)\$ |
|---|---|---|---|---|
| label always accessible | 256 | 25 | 4 blocks, sizes \$n_k=1,2,4,2\$ | 6400 |
| wall at \$x=2\$ (scalar block) | 160 | 25 | same | 1552 |
| asymmetric walls | 160 | 25 | same | 1680 (blocks lopsided: 16 vs 48 and 48 vs 16) |

The intersection is exactly the classical-label structure \$\bigoplus_x B(\mathcal H_{\rm overlap}(x))\$, 
with dimension \$16+4+1+4=25\$ matching the expectation for a classical label: only the diagonal label projections are shared, 
never the coherences \$|x\rangle\langle x'|\$. 
The relative entropy between a state with coherence between two labels and its dephased version, restricted to each algebra, is:

| Pair | on \$\mathcal A_a\$ | on \$\mathcal A_b\$ | on the intersection |
|---|---|---|---|
| both labels visible | \$0.642\$ nats | \$0.01\$–\$0.11\$ (state-dependent) | \$\sim10^{-15}\$ |
| across a wall of that observer | \$\sim10^{-16}\$ | \$\sim10^{-16}\$ | \$\sim10^{-15}\$ |

Values near \$10^{-15}\$ are floating-point noise; the pattern of zeros is robust and the nonzero entries 
depend on the random site state. Monotonicity \$D_N\le\min(D_a,D_b)\$ held in every case. 
Coherence between relative geometries is therefore perspective-dependent: each observer sees some of it and the shared algebra sees none.

**Conjecture (de Sitter).** If each observer has access to the relative-frame variables, 
the QFT part of \$\mathcal A_a\cap\mathcal A_b\$ is the overlap algebra \$\mathcal A(M_a\cap M_{b(g)})\$ fibered 
over the relative position \$g\$, with \$g\$ central, and off-diagonal shift operators are excluded because they differ 
by a global isometry. In the opposite case of no operational access, De Vuyst et al. give the trivial intersection [^5]. 
The clock generators are unresolved.

### 6.3 Correspondences and holonomy

The overlap-induced correspondence \$L^2(\mathcal A_a)\otimes_N L^2(\mathcal A_b)\$ has dimension \$\sum_k\dim(\mathcal A_aq_k)\dim(q_k\mathcal A_b)/n_k^2\$, 
which we verified against explicit counts for four size choices (64, 144, 144, 144). 
It is invertible only if \$N=\mathcal A_a=\mathcal A_b\$, so distinct observers' overlap correspondences 
are not invertible and the Picard group is the wrong home for them.

For the geometric holonomy, with \$g(\varphi,s,t)=e^{-\varphi R}e^{-sB_2}e^{-tB_1}\$ the Maurer–Cartan form is

$$g^{-1}dg=\big(-\cosh s\cosh t\,d\varphi-\sinh t\,ds\big)R+\big(\sinh s\,d\varphi-dt\big)B_1+\big(-\sinh t\cosh s\,d\varphi-\cosh t\,ds\big)B_2,$$

so a horizontal lift has \$dt=\sinh s\,d\varphi\$ and a closed loop in \$(\varphi,s)\$ shifts the proper time by the Haar area

$$\Delta t=\oint\sinh s\,d\varphi=\iint\cosh s\,ds\wedge d\varphi$$

The proper-time shift is modular flow on the ungauged type III\$_1\$ algebra (outer) and 
is implemented by \$e^{-itq}\$ in the gauged algebra (inner), so geometric holonomy is trivial 
in the Picard group after gauging.

### 6.4 Entropy production through a shared algebra

Under brickwork random circuits the entropy produced through \$\mathcal A_a\$, \$\mathcal A_b\$ and the intersection 
saturates at the finite-size Page values (\$0.92\$ for two of four qubits, exact \$0.922\$; \$0.60\$ for one qubit, 
exact \$0.600\$), and is exactly zero for the intersection when the regions do not overlap. 
The shared quantity is just the entropy production of the overlap region.

## 7. The environmental factor

To see where a scale can come from, we reproduced a Weinberg-style estimate [^11] with a Press–Schechter-like collapsed fraction. 
For flat \$\Lambda\$CDM linear growth with fixed matter density, the asymptotic growth is exactly

$$D_\infty(\lambda)=\frac56\,\frac{\Gamma(5/6)\Gamma(2/3)}{\Gamma(3/2)}\,\lambda^{-1/3},\qquad F(\lambda)=\mathrm{erfc}\!\Big(\frac{\delta_c}{\sqrt2\,\sigma_\infty(\lambda)}\Big),\quad \sigma_\infty=\sigma_0\frac{D_\infty(\lambda)}{D_{\rm today}},$$

with \$\lambda=\rho_\Lambda/\rho_m\$, \$\delta_c=1.686\$, and the closed form checked against 
numerical growth to six digits (\$K=1.437283\$). With a flat prior in \$\rho_\Lambda\$:

| \$\sigma_{\rm gal}\$ today | \$F\$ at observed \$\Lambda\$ | median \$\Lambda\$ / observed | \$P(\Lambda\le\text{obs})\$ | \$P(\Lambda\ge10\times\text{obs})\$ |
|---|---|---|---|---|
| 2.0 | 0.548 | 11 | 0.089 | 0.53 |
| 2.8 | 0.668 | 31 | 0.037 | 0.76 |
| 4.0 | 0.764 | 89 | 0.014 | 0.89 |

The observed value lies in the lower tail but is not excluded, and the sensitivity to \$\sigma_{\rm gal}\$ is large. 
This is not the calculation of the causal entropic principle [^12], whose weight is entropy production in a causal diamond. 
It illustrates that the scale in such arguments comes from the fluctuation amplitude and matter density. 
A flat prior in \$\rho_\Lambda\$ is the assumption in the landscape discussions of [^11][^12][^13], 
and it is incompatible with an \$e^{S_{\rm dS}}\$ weight, which is why the normalization choice of Section 3 matters.

## 8. A two-dimensional laboratory

A two-dimensional analogue of the Henneaux–Teitelboim sector exists: unimodular JT gravity has a unimodular time conjugate 
to the cosmological constant [^14]. 
In the JT action \$\tfrac12\int\sqrt{-g}\,[\phi(R-2\lambda_J)-2\Lambda]\$ the shift \$\phi'=\phi+\Lambda/\lambda_J\$ removes 
the vacuum term and leaves a topological term,

$$\tfrac12\int\sqrt{-g}\,[\phi(R-2\lambda_J)-2\Lambda]\;=\;\tfrac12\int\sqrt{-g}\,[\phi'(R-2\lambda_J)]\;-\;\frac{\Lambda}{2\lambda_J}\int\sqrt{-g}\,R ,$$

which in two dimensions is proportional to the Euler characteristic. 
So a vacuum-energy ensemble is an ensemble over the topological coupling \$S_0\$ (the sign depends on conventions), 
and with the usual \$e^{S_0\chi}\$ weighting [^15] one expects Baum–Hawking-type unbounded growth. 
This makes the laboratory useful for testing the machinery of normalization 
and shared algebras in a solvable setting, not for selecting \$\Lambda\$.

## 9. What remains

The pattern of the negative results is consistent. The structures examined so far are kinematical: they describe how sectors fit 
together given a state, and \$\Lambda\$ enters only through \$S_{\rm dS}\$, 
the trace normalization and the state on the center. A selection needs one more ingredient, 
and the most concrete candidate is a state principle. Equilibrium states appear throughout the algebraic constructions, 
in which an observer is a fluctuation costing the entropy deficit, while our universe has an observer-supporting low-entropy past. 
The relative entropy to the equilibrium state is the available entropy budget. 
A principled statement of the initial condition as a condition on that observer-independent total relative entropy is a natural target.

Open problems, in order of tractability:

1. Prove or refute the de Sitter intersection conjecture of Section 6.2, including the clock generators.
2. Read and use the long companion paper [^6] on degenerate-clock superselection, which may already contain the clock-correlation corrections of [^2].
3. Carry out the 2D laboratory computation with an observer, with the sign conventions checked.
4. Formulate the entropy-budget condition algebraically and test whether it constrains the sector weights.

## References

[^1]: S. Aliei, "CC Problem and ER=EPR in dS", blog post (November 2026), <https://saeidaliei.github.io/posts/cosmological-constant-problem-algebraic-er-epr-ds/>.
[^2]: S. Aliei, "The Observer, The Observer, The Observer", blog post, <https://saeidaliei.github.io/posts/the-observer/>.
[^3]: Chen and Xu, "An algebra for covariant observers in de Sitter space", arXiv:2511.00622; JHEP 09 (2026) 240.
[^4]: V. Chandrasekaran, R. Longo, G. Penington and E. Witten, "An algebra of observables for de Sitter space", JHEP 02 (2023) 082, arXiv:2206.10780.
[^5]: J. De Vuyst, S. Eccles, P. A. Höhn and J. Kirklin, "Gravitational entropy is observer-dependent", arXiv:2405.00114 (v3, April 2025).
[^6]: J. De Vuyst, S. Eccles, P. A. Höhn and J. Kirklin, "Crossed products and quantum reference frames: on the observer-dependence of gravitational entropy", arXiv:2412.15502; JHEP 07 (2025) 063.
[^7]: M. Henneaux and C. Teitelboim, "The cosmological constant and general covariance", Phys. Lett. B 222 (1989) 195.
[^8]: S. W. Hawking, "The cosmological constant is probably zero", Phys. Lett. B 134 (1984) 403.
[^9]: S. Coleman, "Why there is nothing rather than something: a theory of the cosmological constant", Nucl. Phys. B 310 (1988) 643.
[^10]: D. Harlow, "Observers, \$\alpha\$-parameters, and the Hartle–Hawking state", arXiv:2602.03835.
[^11]: S. Weinberg, "Anthropic bound on the cosmological constant", Phys. Rev. Lett. 59 (1987) 2607.
[^12]: R. Bousso, R. Harnik, G. D. Kribs and G. Perez, "Predicting the cosmological constant from the causal entropic principle", arXiv:hep-th/0702115.
[^13]: R. Bousso and J. Polchinski, "Quantization of four-form fluxes and dynamical neutralization of the cosmological constant", JHEP 06 (2000) 006, arXiv:hep-th/0004134.
[^14]: Alexandre, Etkin and Rassouli, "Unimodular JT gravity and de Sitter quantum cosmology", arXiv:2501.17213.
[^15]: J. Maldacena, G. J. Turiaci and Z. Yang, "Two dimensional nearly de Sitter gravity", arXiv:1904.01911.
