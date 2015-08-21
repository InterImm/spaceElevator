
> [Read on StackViewer](https://stackedit.io/viewer#!url=https://raw.githubusercontent.com/InterImm/spaceElevator/master/docs/spaceElevatorOscillations.md)

## Simulation



### Equations


Even to the simplest model, space elevator is quite unique. Due to the non-homogeneity, the equation of motion for oscillations on space elevator should be rederived.

Here we assume the oscillation wavelength is much larger than the amplitude of the oscillations, thus the small oscillation approximation can be applied.


Take out a small slice of the space elevator string, which is sketched below.

![](https://raw.githubusercontent.com/InterImm/spaceElevator/master/docs/assets/vibration-th.png)
(To be replaced with a new figure)

In this sketch, larger $x$ means higher altitude while $u$ is the transverse deviation from equilibrium. That being said, the direction of  gravity is pointing to the left.


We assume

1. no motion along x direction;
2. the tension is not uniform on the whole string; 
3. oscillations are small so that $\alpha_1$ and $\alpha_2$ are small so that $\cos\alpha_1\sim\cos\alpha_2 \sim 1$, $\sin\alpha_1\sim \alpha_1$  as well as $\sin\alpha_2\sim\alpha_2$.

The equations of motion in $x$ and $u$ directions are

\begin{align}
T_2\cos\alpha_2 - T_1 \cos\alpha_1 &= g \cdot \mathrm{d} m\\
T_2\sin\alpha_2 - T_1\sin\alpha_1 &= u_{tt} \mathrm{d}m,
\end{align}

where $T_1=T(x)$ and $T_2=T(x+\mathrm{d}x)$ are the tensions on the two ends of the string, which is calculated using

\begin{equation}
T(x)= \sigma(x) A(x) ,
\end{equation}

in which we assign $\sigma(x)$ as the stress at position $x$ and $A(x)$ as the cross area at $x$.

We also have the mass element

\begin{align}
\mathrm{d}m &= \rho \mathrm{d}V \\
&= \rho \frac{\pi}{3} \mathrm{d}x( r(x)^2+r(x+\mathrm{d}x)^2 + r(x)r(x+\mathrm{d}x) ) \\
&\approx  \rho \pi r(x)^2 \mathrm{d}x \\
&= \rho A(x) \mathrm{d}x
\end{align}

up to first order of $\mathrm{d}x$.

The equations are simplified to

\begin{align}
T(x+\mathrm d x) - T(x) & = \rho A(x) g \mathrm{d}x \\
T(x+\mathrm dx) u_x \vert_{x+\mathrm{d}x} - T(x) u_x\vert_{x} & = u_{tt} \rho A(x) \mathrm{d}x.
\end{align}

**Assuming constant stress** $\sigma(x+\mathrm d x) = \sigma(x) = \sigma_0$,

\begin{align}
T(x+\mathrm dx) & = \sigma_0 \pi r(x+\mathrm dx)^2 \\
& = \sigma_0 \left(  r(x)^2 + \frac{\mathrm d r(x)^2}{\mathrm dx} \mathrm dx \right) \\
& \approx \sigma_0 A(x) + \sigma \frac{\mathrm A(x)}{\mathrm dx} \mathrm dx,
\end{align}

the reason I keep the $\mathrm dx$ is that we could see more clearly that this will be cancelled.

Plug this into the transverse equation

\begin{equation}
T(x) ( u_x\vert_{x+\mathrm d x} - u_x \vert_x )  + \sigma_0 \frac{\mathrm dA(x)}{\mathrm dx} \mathrm d x u_x\vert_{x+\mathrm dx} = u_{tt} \rho A(x) \mathrm dx,
\end{equation}

Divided throughout by $\mathrm dx$, we have

\begin{equation}
T(x) u_{xx} + \sigma_0  \frac{\mathrm d A(x)}{\mathrm dx} u_x(x) = u_{tt} \rho A(x),
\end{equation}

in which we used the definition that $u_{xx} = \frac{u_x\vert_{x+\mathrm dx} - u_{x}\vert _x}{\mathrm dx}$.

The equation can be simplified when it is divided by $T(x)$ along with the fact that $T(x) = \sigma_0 A(x)$, 

\begin{equation}
u_{xx} + \frac{A(x)'}{A(x)} u_x = u_{tt} \frac{\rho}{\sigma_0},
\end{equation}

where we denote $\mathrm d A(x)/\mathrm dx$ by $A(x)'$.

In the limit that the string is uniform, the equation is reduced to the wave equation

\begin{equation}
u_{xx} - u_{tt} \frac{\rho}{\sigma_0}=0.
\end{equation}




### Analysis of The Equation of Motion

**To do numerical calculations, we need to have a dimensionless equation.**


1. Suppose the total length is $L$, we can define $\hat x = \frac{x}{L}$.
2. Some dimension analysis shows that $\sqrt{\frac{\sigma_0}{\rho}}$ is a velocity scale given by the system, which actually is the wave propagation speed. Define $v=\sqrt{\frac{\sigma_0}{\rho}}$ which is a constant so that the equation becomes
   \begin{equation}
   u_{xx} + \frac{A(x)'}{A(x)} u_x = \frac{1}{v^2} u_{tt}.
   \end{equation}
   A dimensionless time can be defined to be $\hat t = \frac{v t}{L}$.

 
The dimensionless equation that can be used to do simulations is

\begin{equation}
u_{\hat x\hat x} + \frac{A_{\hat x}}{A} u_{\hat x} = u_{\hat t\hat t},
\end{equation}

where we used the notation $A_{\hat x}$ for $\frac{\mathrm dA(x)}{\mathrm d \hat x}$.



