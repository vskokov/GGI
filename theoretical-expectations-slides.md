# Theoretical Expectations for Model H

---

## Static Behavior

- Governed by partition function: $Z = \int D\phi\, D\vec\pi^T\, \exp\left(-\frac{\mathcal{H}}{T}\right)$
- No coupling between scalar field $\phi$ and momentum density $\vec\pi^T$ in Hamiltonian
- Momentum density correlation: 
  $\langle \pi^T_i(0,\vec{x})\pi^T_j(0,\vec{x}^{\,\prime})\rangle = T\rho\, P^T_{ij}\delta^3(\vec{x}-\vec{x}^{\,\prime})$
- Spectral density independent of $\vec{k}$ (classical equidistribution)

---

## Critical Behavior of Scalar Field

- Scalar field $\phi$ in Ising model universality class
- At critical point ($m^2 = m_c^2$), two-point function:
  $\langle \phi(0,\vec{x})\phi(0,\vec{x}^{\,\prime})\rangle \sim |\vec{x}-\vec{x}^{\,\prime}|^{-d+2-\eta^*}$
  
  where $\eta^* \simeq 0.0363$ in 3D

- Away from critical point, correlation length:
  $\xi \sim |m^2-m_c^2|^{-\nu}$ with $\nu \simeq 0.62999(5)$ in 3D

---

## Susceptibility

- Defined as integral of two-point function:
  $\chi = \int d^dx\, \langle \phi(0,\vec{0})\phi(0,\vec{x})\rangle$
  
- Critical scaling: $\chi \sim |m^2-m_c^2|^{-\gamma}$ with $\gamma=\nu(2-\eta)$

- Small value of $\eta^*$ means susceptibility close to mean field prediction $\chi\sim\xi^2$

- Two-point function in momentum space approximately follows Ornstein-Zernike form:
  $\langle \phi(0,\vec{k})\phi(0,-\vec{k})\rangle \sim \xi^2/(1+(k\xi)^2)$

---

## Dynamics: Momentum Density

- Transverse momentum correlation function:
  $C_{ij}(t,\vec{k}) = \langle \pi_i^T(0,\vec{k})\pi_j^T(t,-\vec{k})\rangle$
  
- Transversality implies $C_{ij}(t,\vec{k})= (\delta_{ij}-\hat{k}_i\hat{k}_j) C_\pi(t,k)$

- In linearized hydrodynamics (shear mode):
  $C_\pi(t,k) = \rho T\, \exp\left(-(\eta/\rho)k^2t\right)$

---

## Renormalization of Viscosity

- Self-advection of momentum density (shear modes) renormalizes viscosity:
  $\eta_R = \eta + \frac{7}{60\pi^2} \frac{\rho T\Lambda}{\eta}$
  
  where $\Lambda \simeq \pi/a$ is momentum-space cutoff

- Minimum renormalized viscosity:
  $\left.\eta_R\right|_{\text{min}} = \sqrt{\frac{7}{15\pi}}\, \sqrt{\frac{\rho T}{a}}$
  
- In units where $T=a=1$: $\eta_R|_{\text{min}} \simeq 0.39\sqrt{\rho}$

---

## Additional Renormalization Effects

- Coupling to scalar field also renormalizes viscosity:
  $\eta_{R} = \eta + \frac{1}{160\pi} \frac{T\xi^0}{\Gamma}$
  
  (much smaller correction than self-advection for typical parameters)

- Long-time behavior modified by non-linear effects:
  - Long time tail scales as $t^{-3/2}\exp(-D_\eta k^2t/2)$
  - In non-perturbative regime: $C_\pi \sim \exp(-\sqrt{\alpha D_\eta k^2 t})$

---

## Order Parameter Dynamics

- Order parameter correlation function:
  $C_\phi(t,\vec{k}) = \langle \phi(0,\vec{k})\phi(t,-\vec{k})\rangle$
  
- Wave-number dependent relaxation rate:
  $\Gamma_k = \frac{\Gamma}{\xi^4}(k\xi)^2(1+(k\xi)^2) + \frac{T}{6\pi\eta_R\xi^3}\, K(k\xi)$
  
  where $K(x)$ is the Kawasaki function

---

## Kawasaki Function

- $K(x) = \frac{3}{4}[1+x^2+(x^3-x^{-1})\tan^{-1}(x)]$
  
- Asymptotic behavior:
  - $K(x) \simeq x^2$ for $x \ll 1$
  - $K(x) \simeq (3\pi/8)x^3$ for $x \gg 1$

- First term in $\Gamma_k$: mean field relaxation rate (model B)
- Second term: coupling to fluid momentum density

---

## Dynamical Critical Exponent

- Model B: $z = 4$ (mean field), $z = 4-\eta$ (with fluctuations)
  
- Model H (with momentum coupling): $z \simeq 3$
  
  - $\epsilon$-expansion at two loops: $z \simeq 3.0712$
  - Kawasaki approximation: wave number dependence $\Gamma_k \sim k^2$ (small $k\xi$), $\Gamma_k \sim k^3$ (large $k\xi$)

---

## Critical Viscosity

- Viscosity diverges at critical point:
  $\eta_R = \eta[1 + \frac{8}{15\pi^2}\log(\xi/\xi_0)]$
  
- Scaling: $\eta_R \sim \xi^{x_\eta}$ with $x_\eta = \frac{8}{15\pi^2} \simeq 0.054$
  
- $\epsilon$-expansion (two loops): $x_\eta \simeq 0.071$
  
- Divergence is weak, Kawasaki approximation remains approximately self-consistent

---

## Physical Argument for z ≈ 3

1. Define renormalized conductivity $\Gamma_R$ by $\Gamma_k = \Gamma_R\chi^{-1}k^2$ (for $k\xi < 1$)
   
2. Critical scaling: $\Gamma_R \sim \xi^{x_\Gamma}$ (Kawasaki: $x_\Gamma = 1$)
   
3. Balance of diffusion and convection in external field gives:
   $x_\Gamma + x_\eta = 4-d-\eta^*$
   
4. For small $x_\eta$ and $\eta^*$ in 3D: $x_\Gamma \simeq 1$
   
5. Matching relaxation rates: $z = 4-x_\Gamma-\eta$
   
6. Result: $z = d+x_\eta \simeq d = 3$ for small $x_\eta$
