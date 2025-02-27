# Premise

## Linear ODE

The probability density evolution in a one-dimensional harmonic trapping potential is governed by the ODE
$$
	i \hbar \psi_t+\frac{\hbar^2}{2 m} \psi_{x x}-V(x) \psi=0
$$
where $\psi$ is the probability density and $V(x) = kx^2/2$ is the harmonic conflicting potential. A typical solution technique for this problem is to assume a solution of the form
$$
	\psi = \sum^N_{1} a_n \psi_n (x) \exp \left( -i \frac{E_n}{2\hbar}t \right)
$$
which is called the eigenfunction expansion solution ($\phi_n = \text{eigenfunction}, \; E_n = \text{eigenvalue}$). Plugging in this solution ansatz to the ODE gives the boundary value problem
$$
	\frac{d^2 \psi_n}{dx^2} - \left[ Kx^2 - \epsilon_n \right] \phi_n = 0
$$
where we expect the solution $\phi_n(x) \to 0$ as $x \to \pm \infty$ and $\epsilon_n$ is the quantum energy. Note here that $K = km/\hbar^2$ and $\epsilon_n = E_n m/\hbar^2$.

## Nonlinear ODE

There has been suggestions that in some cases, nonlinearity plays a role such that
$$
	\frac{d^2 \phi_n}{dx^2} - \left[ \gamma |\phi_n|^2 + Kx^2 - \epsilon_n \right]\phi_n = 0.
$$
Depending on the sign of $\gamma$, the probability density is focused or defocused.

# Analysis

## Linear ODE

We have the second order nonlinear ODE
$$
	\frac{d^2 \phi_n}{dx^2} - [Kx^2 - \epsilon_n] \phi_n = 0
$$

Expect $\phi_n (x) \to 0$ as $x \to \pm \infty$

Take $K = 1$ and normalize such that
$$
	\int^\infty_{-\infty} |\phi_n|^2 dx = 1
$$

For the boundary cases, $x \in \{-L, L\}$,
$$
	\phi_n^{\prime\prime} - [L^2 - \epsilon_n] \phi_n = 0 \\
	\phi_n^\prime - \sqrt{L^2 - \epsilon_n} \phi_n = 0 \\
	\phi_n - \exp(\sqrt{L^2 - \epsilon_n} \phi_n) = 0
$$
$$
	x = -L: \; \phi_n^{\prime\prime} - \sqrt{L^2 - \epsilon_n} \phi_n^\prime = 0 \\
	x = L: \; \phi_n^{\prime\prime} + \sqrt{L^2 - \epsilon_n} \phi_n^\prime = 0
$$


Letting $\psi = \phi', \; \psi' = \phi''$
Yields ODE $\psi' = \sqrt{L^2 - \epsilon_n} \psi$
Thus, solve linear first order ODE for $\psi$

## Nonlinear ODE

We have the second order nonlinear ODE
$$
	\phi^{\prime\prime} = (\gamma|\phi|^2 + Kx^2 - \epsilon)\phi
$$

For the boundary condition
$$
	x = L: \; \phi^\prime = \phi \sqrt{KL^2 - \epsilon}
$$


# Repo Structure
The various Jupyter notebooks in the repository utilize various scientific computing methods to solve the ansatz boundary value problem for eigenfunctions and eigenvalues. Notebooks prefixed with `L` regard the linear ODE, while `N` denotes relation to the nonlinear. 

<sub>For Homework 2 and 3 of "AMATH 481 - Data Driven Modeling & Scientific Computation" taught by J. Nathan Kutz Fall 2024</sub>