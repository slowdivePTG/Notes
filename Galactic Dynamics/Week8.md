# Week7: Orbits

## Angular-action variables

Since elementary Newtonian or Lagrangian mechanics restricts our choice of coordinates to ones that are rarely integrals, we work in the more general framework of Hamiltonian mechanics.

Thus, we shall focus on a particular set of canonical coordinates, called **angular-action** variables.

- The three momenta are integrals - **actions**
- The conjugate variables - **angles**
- An orbit fortunate enough to possess angle-action variables is called a **regular orbit**

Let us denote the angle-action variables by $(\vec\theta,\vec J)$. We assume that the momenta $\vec J=(J_1,J_2,J_3)$ are integrals of motion, then Hamilton's equations read
$$
0=\dot J_i=-\frac{\partial H}{\partial\theta_i}
$$
Therefore, the Hamiltonian must be independent of the coordinates $\vec\theta$. Consequently,
$$
\dot\theta_i=\frac{\partial H}{\partial J_i}\equiv\Omega_i(\vec J)
$$
is independent of $\vec\theta$, so
$$
\theta_i(t)=\theta_i(0)+\Omega_it
$$


### Orbital tori

We restrict our attention to bound orbits, so that $x_i$ are periodic functions of the $\theta_i$. We can scale $\theta_i$ so that $\vec x$ returns to its original value every time $\theta_i$ has increased by $2\pi$. Then we can expand $\vec x$ in a Fourier series
$$
\vec x\left(\vec \theta,\vec J\right)=\sum_{\vec n}\vec X_{\vec n}(\vec J)\mathrm e^{i\vec n\cdot\vec\theta}
$$
where the sum is over all vectors $\vec n$ with integer comopents.