# Critical dynamics: model H <!-- .element: class="r-fit-text" -->

### Vladi Skokov

### North Carolina state University


<img src="img/modH-3d-both.png"  width="45%"  >

<div class="medmath">

- Model A: T. Schaefer, V. S., 2204.02433  
- Model B: **C. Chattopadhyay**, **J. Ott**, T. Schaefer, V. S., 2304.07279  
- Model H: **C. Chattopadhyay**, **J. Ott**, T. Schaefer, V. S., 2403.10608 and 2411.15994

</div>

---

### Outline

<div class="colorized-list">

- Introduction

- Model H: definition

- Numerical scheme

- Theory expectations

- Numerical results

- Conclusions

</div>

---
### Motivation 



<div class="colorized-list">

* Transition from hadronic matter to QGP along the temperature axis in the QCD phase diagram is a smooth crossover.

* As baryon doping increases, this crossover may transform into a first-order phase transition at a critical endpoint.

* Experimental searches for critical behavior have focused on non-monotonic dependence of fluctuation observables on beam energy/rapidity window. 


* Understanding the dynamical evolution of these observables in HIC requires a hydrodynamic theory that incorporates fluctuation effects.

* A necessary step: numerical simulation of Navier-Stokes equations near critical point  

</div>



---
### Universality classes: statics vs dynamics 



<div class="colorized-list">

* Near-equilibrium  dynamics is universal 

* Unlike static universality classes, dynamical universality classes are governed by additional factors beyond dimensionality, locality, and symmetries.

* Properties of slow modes are crucial determinants of dynamical universality classes.

* Conservation  of an order parameter affects the dynamical universality class.

* Mode-mode couplings among slow modes influence the dynamical universality class.

* Two systems that belong to the same static universality class may belong to different dynamical universality classes.

</div>

---

### Hohenberg and Halperin classification

Stochastic theories near critical point:

<div class="cite">
  Citations to recent literature relevant for HIC community 
</div>


<div class="colorized-list">

- Model A: purely relaxational theories
<div class="smallmath">
$$ \frac{\partial \phi(t, \vec{x})}{\partial t} = - \Gamma\,  \frac {\delta {\cal H}} {\delta \phi(t, \vec{x})} + \zeta (t, \vec{x}), \quad  {\cal H}  = \int d^dx \left[ \frac{1}{2} (\nabla \phi)^2 + \frac{1}{2} m_0^2 \phi^2 + \frac{1}{4} \lambda  \phi^4+  h \phi \right] $$
</div>
<div class="cite">
J. Berges, S. Schlichting, D. Sexty,  0912.3135 <br/>
T. Schaefer, V. S., 2204.02433
</div>


- Model B: critical diffusion
<div class="cite">
D. Schweitzer, S. Schlichting, L. von Smekal, 2110.01696 <br/>
C. Chattopadhyay, J. Ott, T. Schaefer, V. S.,  2304.07279
</div>

- ...

- <span class="att"> **Model G** </span>: critical anti-ferromagnets/QCD near crossover 
<div class="cite">
A. Florio, E. Grossi, A. Soloviev, D. Teaney,  ...,  2111.03640; 2306.06887; 2504.03514;  2504.03516 
</div>

- <span class="att"> **Model H** </span>: critical diffusion coupled to Navier-Stokes/QCD near critical point 
<div class="cite">
 C. Chattopadhyay, J. Ott, T. Schaefer, V. S., 2403.10608 and 2411.15994
</div>

</div>

<br/>
<div class="note">
*Statics of the simplest versions of model A, B and H falls into Ising/Z(2) universality class 
</div>



---

### Dynamical critical exponent, $z$

 Relaxation time of the slowest mode: $\tau \propto \xi^z$ or $\omega \propto k^z$

<div class="colorized-list">

- $\epsilon=4-d$ expansion; $\epsilon$ is not small for physically interesting case of $d=3$
  - Five-loop $\epsilon$-expansion for **model A** (leads to $z$=2.0236(8)):
<div class="medmath">
$$
z=2+0.013446 \varepsilon^2+0.011037 \varepsilon^3-0.0055791(4) \varepsilon^4+{0 . 0 1 7 7 4 ( 3 1 )} \varepsilon^5+O\left(\varepsilon^6\right)
$$
</div>
<div class="cite">
  L.  Adzhemyan et. al., 2111.04719
</div>
<div class="note">
 *Numerical simulation of Model A: $z = 2.026(56)$, see T. Schaefer, V.S., 2204.02433 
</div>

- Two-loop $\epsilon$-expansion for **model H** (leads to $z=3.071$)
<div class="medmath">
$$z=4-\frac{18 \epsilon}{19}[1-0.0196 \epsilon]$$
</div>
<div class="cite">
  L.  Adzhemyan et. al., 1999
</div>

- FRG: currently only LPA' approximation for model H
<div class="cite">
 Y. Chen, Y. Tan, W.-J. Fu, 2406.00679 <br/>
 J. Roth, Y. Ye, S. Schlichting, L. von Smekal, 2409.14470
</div>

</div>

---

### Model H: definition

<div class="colorized-list">

- Long-time hydrodynamic description of <span class="att">conserved order parameter $\phi$ </span> interacting with the <span class="att">conserved momentum density $\vec{\pi}$ </span>
<div class="smallmath">
\begin{align}
\partial_t\phi &=   \Gamma \nabla^2 \left(\frac{\delta{\cal H}}{\delta \phi}\right) - \left(\nabla_i\phi\right) \frac{\delta{\cal H}}{\delta \pi_i^T}+  \zeta\\ 
\partial_t \pi^T_i &= \eta \nabla^2 \left(\frac{\delta{\cal H}}{\delta \pi^T_i}\right) + P^T_{ij} \left[\left(\nabla_j\phi\right) \frac{\delta{\cal H}} {\delta\phi} \right] -{\color{ProcessBlue}  P^T_{ij}  \left[ \nabla_k\left( \pi^{T}_j \frac{\delta{\cal H}}{\delta \pi^T_k}\right) \right] }  + \xi_i .
\end{align}
</div>

- Hohenberg \& Halperin: model H without <span class="attcomp"> $\vec{\pi}$ self coupling</span> = Model H0 in our notation

- The effective Hamiltonian defines statics of the model
<div class="smallmath">
$$
{\cal H}  = \int d^dx \left[ \frac{1}{2\rho} ( \pi_i^T)^2 +  \frac{1}{2} (\nabla \phi)^2 +  \frac{1}{2} m^2 \phi^2 +  \frac{1}{4} \lambda  \phi^4  + h \phi\right]
$$
</div>

- $\zeta$ and $\xi_i$ are random fields constrained by fluctuation-dissipation relations
<div class="smallmath">
$$
\langle \zeta (t, \vec{x}) \zeta (t', \vec{x}') \rangle = -2 T \Gamma \nabla^2 \delta(\vec{x}-\vec{x}')\delta(t-t')
$$
$$
\langle \xi_i (t, \vec{x}) \xi_j (t', \vec{x}') \rangle = -2 T \eta P^T_{ij} \nabla^2 \delta(\vec{x}-\vec{x}')\delta(t-t')
$$
</div>
</div>

---

### Explicitly conservative form


<div class="colorized-list">

- Equation can be rewritten in explicitly conserving form
<div class="medmath">
$$
\partial_t\phi + \vec\nabla\cdot\vec\jmath = 0,  \hspace{1.5cm} \partial_t\pi_{T,i} + P^T_{ij}\nabla_k \Pi_{jk} = 0
$$
</div>

- Currents have <span class="att"> non-dissipative</span> and <span class="attcomp">dissipative/stochastic</span> parts
<div class="medmath">
$$
\jmath_i = {\color{Orange} \jmath_i^{(0)} } + {\color{ProcessBlue}\jmath_i^{(1)}},  \hspace{1cm} \Pi_{ij} = {\color{Orange} \Pi_{ij}^{(0)} } + {\color{ProcessBlue} \Pi_{ij}^{(1)} } .
$$
$$
    {\color{Orange} \jmath_i^{(0)} = \phi \frac{\delta {\cal H}}{\delta \pi^T_i} = \frac{1}{\rho}\phi \pi^T_{i}}, \quad { \color{ProcessBlue} \jmath_i^{(1)} = -\Gamma \nabla_i \frac{\delta{\cal H}}{\delta \phi} + \Theta_i } 
$$
$$
     {\color{Orange} \Pi_{ij}^{(0)} = \frac{1}{\rho}  \pi^T_{i}\pi^T_{j} + (\nabla_i\phi)(\nabla_j\phi )}, \quad      {\color{ProcessBlue}  \Pi_{ij}^{(1)} = -\eta \left[ \nabla_i \frac{\delta{\cal H}}{\delta\pi^T_{j}} +\nabla_j \frac{\delta{\cal H}}{\delta\pi^T_{i}} \right] + \Lambda_{ij} } 
$$
with $\langle\Theta_i\Theta_j\rangle \sim 2\Gamma T\delta_{ij}$ and $\langle\Lambda_{ij}\Lambda_{kl}\rangle \sim 2\eta T (\delta_{ik}\delta_{jl}+\delta_{il}\delta_{jk})$.

</div>

</div>

---

### Conservation Laws in Numerics 


<div class="colorized-list">

- The goal is to discretize the equation on uniform lattice spacing $\vec{x} = a \vec{n}$   
- When solving equations of motion numerically, it is crucial to maintain as many conservation laws and symmetries as possible 
- In continuum theory, the equations can be written in forms that manifestly conserve momentum and order parameter 
- <span class="att">Symplectic structure of advection term implies conservation of  Hamiltonian </span>

</div>

---

### Continuum Advection Terms

<div class="colorized-list">

- Consider simplified theory: advection only ($\Gamma =0$ and $\eta=0$) 
- The advection term for $(\phi, \vec{\pi}^T)$ in the continuum:
\begin{align}
\dot{\phi} &= - \nabla_i \left( \phi  \frac{\pi^T_i}{\rho} \right) = - \frac{\pi^T_i}{\rho}  \nabla_i \phi \\\\
\dot{\pi}^T_{i} &= - P^T_{ij} \left[ \nabla_k \left( \frac{1}{\rho}  \pi^T_{k} \pi^T_{j} \right) + \nabla_j \phi \nabla^2 \phi \right]
\end{align}

</div>
---

### Energy Conservation in Continuum

<div class="colorized-list">

  - Time derivative of the Hamiltonian:
<div class="medmath">
$$
\dot{{\cal H}} = \int d^3x  \left[ - \dot{\phi}   \nabla^2 \phi + \frac{1}{\rho}   \pi^T_{i} \dot{\pi}^T_{i} + V'(\phi)   \dot{\phi} \right]
$$
</div>

- Using the eqs. of motion
<div class="medmath">
$$
  \dot{{\cal H}} = \int d^3x   \left[ (\nabla^2\phi)   \frac{\pi^T_i}{\rho} \nabla_i \phi - \frac{\pi^T_i}{\rho} \left( \frac{\pi^T_j}{\rho} \nabla_j \right) \pi^T_i - (\nabla^2\phi)   \frac{\pi^T_i}{\rho} \nabla_i \phi - \nabla_i \left( V(\phi) \frac{\pi^T_i}{\rho} \right) \right]
  $$
</div>

- First and third terms cancel; second term becomes a divergence
<div class="medmath">
$$
   { \color{Orange}
    \pi^T_i \left( \pi^T_j \nabla_j \right) \pi_i^T = \nabla_i  \left( \pi_i^T \frac{\pi^T_j\pi^T_j}{2 } \right)}
$$
</div>

-  <span class="att"> Energy is conserved </span>
</div>

---

### Conservation of Energy: Challenges in Discrete Theory

<div class="colorized-list">

- Vector identities from continuum may not hold in discretized theory
- Integration by parts identities may fail
- Need special discretization to maintain conservation laws
</div>


---

### $\pi$ Self-advection Only: Skew-Symmetric Form

<div class="colorized-list">

- The "skew-symmetric" form:
$$
\nabla_\mu \left(\frac{1}{\rho} \pi^T_{\mu} \pi^T_{\nu} \right)  \equiv \frac{1}{2}   \nabla_\mu ( \frac{1}{\rho} \pi^T_{\mu} \pi^T_{\nu} ) + \frac{1}{2}   \frac{\pi^T_{\mu}}{\rho}   \nabla_\mu \pi^T_{\nu}
$$

- Observation 1: Conserves kinetic energy independent of $\nabla_k\pi^T_k=0$


- Observation 2:
<div class="medmath">
$$
\frac{1}{2}  \frac{d}{dt}  \left(\pi^T_{\nu}\pi^T_\nu\right) =  \left.\pi^T_{\nu} \nabla_\mu \left(\frac{1}{\rho} \pi^T_{\mu} \pi^T_{\nu} \right) \right|_{\it skew} = \frac{1}{2}  \nabla_\mu^{1/2} \Big[(\overline{\pi^T_{\mu}})^{\hat{\mu}} (\widetilde{\pi^T_{\nu}\pi^T_{\nu}})^{\hat{\mu}}\Big]
$$
</div>

- <span class="att"> Ensures the advection step conserves kinetic energy ${\cal H}  = \int d^dx \frac{1}{2\rho} ( \pi_i^T)^2 $
 </span>

</div>

<div class="cite">
 Y.  Morinishi, T.  Lund, O. Vasilyev, P. Moin, P., J. of Comp. Phys., 143(1), 90-124, 1998

</div>



---

### Mutual Advection of $\phi$ and $\pi$

For mutual advection with centered derivatives:

<div class="medmath">

\begin{align}
\dot\phi &= - \frac{1}{\rho} \pi^T_{\mu} \nabla^c_{\mu} \phi \\\\ 
\dot\pi^T_\mu &= - \left(\nabla_\mu^c\phi\right) \left(\nabla_\nu^c\nabla_\nu^c\phi\right)
\end{align}

</div>

<div class="colorized-list">

- <span class="att">This update conserves the Hamiltonian (kinetic part) exactly: </span>
<div class="medmath">
$$
{\cal H}_\pi+ {\cal H}^c_{\partial\phi} = \sum_{\vec{x}} [ \frac{1}{2\rho} \pi^T_\mu(\vec{x})\pi^T_\mu(\vec{x}) + \frac{1}{2} \nabla^c_\mu\phi(\vec{x}) \nabla^c_\mu \phi(\vec{x}) ]
$$
</div>

- <span class="attcomp">However this updates does not exactly conserve potential energy</span>

- Total energy is conserved only in the continuum $a\to0$ 

- <span class="att">Skew-symmetric derivative reduces aliasing errors which destabilize simulations </span>

</div>
---

### Final Spatial Discretization


<div class="colorized-list">

* Summary of spatial discretization for the advection step:
\begin{align}
\dot{\phi} &= - \frac{1}{\rho}  \pi^T_{\mu}   \nabla^c_{\mu} \phi \\\\
\dot{\pi}^T_{\mu} &= - \left[ \frac{1}{2} \nabla^c_{\nu} \left( \frac{1}{\rho} \pi^T_\nu \pi^T_\mu \right) + \frac{1}{2\rho} \pi^T_\nu   \nabla^c_{\nu} \pi^T_\mu + \left(\nabla^c_\mu \phi\right) \left(\nabla^c_\nu\nabla^c_\nu\phi\right) \right]
\end{align}



* After each discrete time step, apply transverse projection: $\nabla_\mu^c\pi^T_\mu(\vec{x})=0$

* Time-stepper: 3d order Runge-Kutta method with the transverse projector applied after each substep
</div>

---

### Dissipative Update: Metropolis Algorithm

<div class="colorized-list">

- Diffusive step and noise term implemented via a single Metropolis update
- Guarantees fluctuation-dissipation relations
- Converges to equilibrium distribution: $P[\phi_\mu]\sim \exp(-\mathcal{H}[\phi_\mu]/T)$
</div>

<div class="cite">
Y. Gao et. al., arXiv:1806.05282 [math.PR] </br>
  A. Florio, E. Grossi, A. Soloviev, and D. Teaney, arXiv:2111.03640 
</div>

---

### Metropolis Update for Scalar Field $\phi$

Trial update:



<div class="box-container top-aligned">
  <div data-id="box1" class="box blue-box"> +q ⇇ </div>
  <div data-id="box2" class="box red-box"> ⇇ -q </div>
</div>

<div class="colorized-list">


- ${\color{Orange} \phi^{\text{trial}}(\vec{x},t+\Delta t) = \phi(\vec{x},t) + q_\mu } $
- ${\color{ProcessBlue} \phi^{\text{trial}}(\vec{x}+\hat\mu,t+\Delta t) = \phi(\vec{x}+\hat{\mu},t) - q_\mu} $
- $q_\mu = \sqrt{2\Gamma T(\Delta t)}  \xi$
</div>

Where:
<div class="colorized-list">

- $\xi$ is a Gaussian random variable with unit variance
- $\hat{\mu}$ is an elementary lattice vector
</div>

Accept with probability $\min(1,e^{-\Delta\mathcal{H}/T})$

Similar procedure for the momentum density 

---

### Renormalization of Viscosity: self-advection

<div class="colorized-list">

- Self-advection of momentum density (shear modes) renormalizes viscosity:
  one loop calculation $\eta_R = \eta + \frac{7}{60\pi^2} \frac{\rho T\Lambda}{\eta}$
  where $\Lambda \simeq \pi/a$ is a UV momentum-space cutoff
<div class="cite"> 
    P. Kovtun, G. Moore, P. Romatschke, 1104.1586 <br/>
    C. Chafin, T. Schafer, 1209.1006
</div>

- Minimum renormalized viscosity:
  $\left.\eta_R\right|_{\text{min}} = \sqrt{\frac{7}{15\pi}}  \sqrt{\frac{\rho T}{a}}$

- In units where $T=a=1$: $\eta_R|_{\text{min}} \simeq 0.39\sqrt{\rho}$
</div>

---

### Renormalization of Viscosity:
###  coupling to order parameter 

<div class="colorized-list">

- Switch off the momentum self-coupling 

- Coupling to scalar field also renormalizes viscosity:
  $\eta_{R} = \eta + \frac{1}{160\pi} \frac{T\xi^0}{\Gamma}$

- For typical parameters $\eta_R - \eta \approx 0.0002$, i.e.   much smaller correction than self-advection 

</div>




---
### Tuning to critical point 

- Adjust $m^2$ of the order parameter to get to critical point 
- Non-conserved order parameter: Binder cumulants

- Example in 2d:

<img src="img/binder_reweight.pdf.png" alt="binder_reweight.pdf.png"  width="50%"  >

- How to make sure conservation does not shift critical point? 

---

### Model A: Probability distribution $P(M)$


<img src="img/Hist_model_A.pdf.png" alt="Hist_model_A.pdf.png"  width="47.2%" >
<img src="img/Hist_model_A_res.pdf.png" alt="Hist_model_A_res.pdf.png"  width="49%">

- $M = \frac{1}{V} \sum_{\vec{x}} \phi(\vec{x})$
- Negative  kurtosis (manifested by universal Binder ratio) 

---
### Model B: Probability distribution $P(M)$

<img src="img/Hist_model_B.pdf.png" alt="Hist_model_B.pdf.png"  width="47.2%" >
<img src="img/Hist_model_B_res.pdf.png" alt="Hist_model_B_res.pdf.png"  width="49%" >

- $M = \frac{2}{V}\sum_{\vec{x}\in V_{1/2}} \phi(\vec{x})$
- Positive/near zero kurtosis 


---

### Order Parameter Dynamics


<div class="colorized-list">

- Order parameter correlation function:
  $C_\phi(t,\vec{k}) = \langle \phi(0,\vec{k})\phi(t,-\vec{k})\rangle$
- Wave-number dependent ralexation rate: $C_\phi \propto \exp(-\Gamma_k t )$ 



- Kawasaki approximation (meanfield for shear and order parameter modes):  
  $\Gamma_k = {\color{Orange} \frac{\Gamma}{\xi^4}(k\xi)^2(1+(k\xi)^2)} + {\color {ProcessBlue}\frac{T}{6\pi\eta_R\xi^3}  K(k\xi)}$ where $K(x) = \frac{3}{4} [ 1 + x^2 + (x^3-x^{-1})\arctan x ]$ 
  - <span class="att">relaxation rate in pure diffusive theory; $z_{K}=4$ </span>
  - <span class="attcomp">relaxation due to coupling to momentum density; $z_{K} = 3$</span>

</div>

---

### Critical Viscosity

<div class="colorized-list">

- Viscosity diverges at critical point in Kawasaki approximation:
  $\eta_R = \eta[1 + \frac{8}{15\pi^2}\log(\xi/\xi_0)]$
- ➲  scaling: $\eta_R \sim \xi^{x_\eta}$ with $x_\eta = \frac{8}{15\pi^2} \simeq 0.054$
- $\epsilon$-expansion (two loops): $x_\eta \simeq 0.071$
- For weak viscosity divergence, Kawasaki approximation remains approximately self-consistent

</div>


---

# Numerical results 

---

### Renormalized viscosity



- Viscosity can be extracted through the analysis of the momentum density decay
$C_{\pi}(t,\vec{k}) =  (\delta_{ij}-\hat{k}_i\hat{k}_j)  \langle \pi_i^T(0,\vec{k})\pi_j^T(t,-\vec{k})\rangle$ with $k \to 0 $

- Linear diffusion: $C_{\pi} \propto \exp(- \eta k^2 t)$

- Renormalized viscosity $\eta_R  = - \frac{1}{k^2} \frac{d \ln C_\pi}{dt}$  

<img src="img/ViscExt.pdf.png" alt="ViscExt.pdf.png" width="50%">

---

### Renormalized viscosity

- Self-advection = $\phi$ field is turned off
- Model $H_0$ = classic model H without self-advection term  $\pi_k \nabla_k \pi_i$ 

<img src="img/EffectiveViscosity.pdf.png" alt="EffectiveViscosity.pdf.png"  width="50%"  >
  



---

### Dynamic Critical Exponent, $d=3$ 

- Time dependence of the correlation function $ C_\phi(t,\vec{k}) = \langle \phi(0,\vec{k})\phi(t,-\vec{k})\rangle,  \quad k \to 0 $
- Dynamic scaling: $ C_\phi(t,k, \xi) = \tilde C(t/\xi^z, k \xi) $
- At the critical point, on a finite lattice of size $L$: $\xi = L$
- Calculations at smallest momentum mode $k \xi = 2\pi$ 

<img src="img/Ctime.pdf.png" alt="Ctime.pdf.png"  width="50%" >

<div class="note"> Model $H_0$ </div>

- The data clearly excludes $z$ near four 

---

### Dynamic Critical Exponent, $d=2$ 

- Even more drastic difference in $d=2$: 

<img src="img/Ctime2d.pdf.png" alt="Ctime2d.pdf.png" width="50%">


---

### Dynamic Critical Exponent for various $\eta$  
-   $\Gamma_k = {\color{Orange} \frac{\Gamma}{\xi^4}(k\xi)^2(1+(k\xi)^2)} + {\color {ProcessBlue}\frac{T}{6\pi\eta_R\xi^3} K(k \xi )}$ 

- Varying  $\eta_R$ to cross-over from <span class="att">$z=4$ (Model B scaling) </span> to <span class="attcomp">$z\approx 3$ (Model H scaling) </span>

<img src="img/zefftc.pdf.png" alt="zefftc.pdf.png"  width="49%">
<img src="img/EffectiveViscosity.pdf.png" alt="EffectiveViscosity.pdf.png"  width="49%"  >


---

### Dynamic Critical Exponent as a function of  $\eta_R$  
<img src="img/zefftc_R.pdf.png" alt="zefftc_R.pdf.png"  width="59%">


- Our result: $z=3.013±0.058 $ vs two loop $\varepsilon$-expansion $z ≃ 3.0712$  

---

### Conclusions

- Stable numeric scheme with exact conservation of kinetic energy 

- Renormalization of viscosity: minimum viscosity for self-advection beyond one loop 

- First non-perturbative calculation of dynamic critical exponent in model H
<div class="colorized-list">

  - $z_{d=3} = 3.013\pm 0.058$ 
  - $z_{d=2} = 2.11\pm 0.015$ (see 2411.15994)
</div>

- Outlook: 
<div class="colorized-list">

  - Detailed calculation of transport coefficients  
  - More detailed framework: longitudinal mode, bulk viscosity, renormalization of the equation of state   
  - Non-trivial and relativistic background flow
</div>


---

# Backup

---

### Critical Behavior of Scalar Field

- Scalar field $\phi$ in Ising model universality class
- At critical point ($m^2 = m_c^2$), two-point function:
  $\langle \phi(0,\vec{x})\phi(0,\vec{x}^{ \prime})\rangle \sim |\vec{x}-\vec{x}^{ \prime}|^{-d+2-\eta^*}$

  where $\eta^* \simeq 0.0363$ in 3D

- Away from critical point, correlation length:
  $\xi \sim |m^2-m_c^2|^{-\nu}$ with $\nu \simeq 0.62999(5)$ in 3D

---

### Susceptibility

- Defined as integral of two-point function:
  $\chi = \int d^dx  \langle \phi(0,\vec{0})\phi(0,\vec{x})\rangle$
- Critical scaling: $\chi \sim |m^2-m_c^2|^{-\gamma}$ with $\gamma=\nu(2-\eta)$

- Small value of $\eta^*$ means susceptibility close to mean field prediction $\chi\sim\xi^2$

- Two-point function in momentum space approximately follows Ornstein-Zernike form:
  $\langle \phi(0,\vec{k})\phi(0,-\vec{k})\rangle \sim \xi^2/(1+(k\xi)^2)$


---
### Binder cumulant analysis, $d=2$

<img src="img/intersect_fit.pdf.png" alt="intersect_fit.pdf.png"  width="50%" >


---
### Model H and Model B matching 

<img src="img/StatCorr.pdf.png" alt="StatCorr.pdf.png">

---
### Dynamic critical exponent in 2d 

<img src="img/zefftc2d.pdf.png" alt="zefftc2d.pdf.png">


---

### Lattice Discretization

<div class="colorized-list">

- Fields $\phi(\vec{x})$ and $\vec\pi(\vec{x})$ are discretized on a $d$-dimensional lattice with step size $a=1$ 

- Forward and backward derivatives in the direction $\mu=1,2,3$
<div class="medmath">
$$
\nabla^R_\mu\phi(\vec{x}) = \frac{1}{a} [\phi(\vec{x}+\hat{\mu}a)-\phi(\vec{x}) ],
\hspace{0.5cm} \nabla^L_\mu \phi(\vec{x}) = \frac{1}{a} [\phi(\vec{x})-\phi(\vec{x}-\hat{\mu}a) ].
$$
</div>

- The Laplacian is defined as $\nabla^2=\nabla^L_\mu\nabla^R_\mu = \nabla^R_\mu\nabla^L_\mu$

- This lattice derivative satisfies
  $
\sum_{\vec{x}} \nabla^R_\mu\phi(\vec{x}) \nabla^R_\mu\phi(\vec{x}) = -\sum_{\vec{x}} \phi(\vec{x}) \nabla^2\phi(\vec{x})
$

- Operators $\nabla_\mu^{R,L}$ are not anti-hermitian,
  but their sum is
  $
\nabla_\mu^c=\frac{1}{2}\left(\nabla^L_\mu+\nabla^R_\mu\right)
$

- Centered Laplacian
$
\left(\nabla_\nu^c\right)^2\phi(\vec{x}) = \frac{1}{4} \sum_\nu \Big\\{ \phi(\vec{x} + 2 \hat{\nu}) + \phi(\vec{x} - 2 \hat{\nu}) - 2 \phi(\vec{x}) \Big\\}
$
</div>


