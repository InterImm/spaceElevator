
> [Read on StackViewer](https://stackedit.io/viewer#!url=https://raw.githubusercontent.com/InterImm/spaceElevator/master/docs/spaceElevatorOscillations.md)



[toc]


## Simulation


A few papers have already done some research on the topic of oscillations. [^2] [^3]


### Oscillation Equations


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

We assume a simple boundary condition for $u(x,t)$ that

\begin{align}
u(0,t) &= 0 \\
u(L,t) & = 0,
\end{align}

where $L$ is the upper end of the cable.

**This boundary condition imposes the cable to be stationary on both ends. It makes sense since the lower end with be a ground station while the upper end will be attached to a very heavy space station.**


### Cross Area

Cross area of the cable is determined under the assumption that the stress is the same across all the cable.

Applying second Newton's law,

\begin{equation}
\frac{dT}{dx} = -\rho A(x) g(x),
\end{equation}

where and $dT$ is the tension on the cross area $A(x)$ at height $x$  and the effective acceleration $g(x)$ is

\begin{equation}
g(x) = -\frac{GM}{x^2} + x\Omega^2.
\end{equation}


The tension is defined as $dT = d(\sigma A)$. The assumption of constant stress $\sigma(x) = \sigma_0$ takes us to the result that

\begin{equation}
\frac{dA(x)}{dx} = -\frac{\rho}{\sigma_0} A(x) g(x).
\end{equation}

Integrate over the equation we have [^1]

\begin{equation}
A(x)  = A _ 0 \exp{\left(- \frac{\rho}{\sigma} \left[ G M \left( \frac{1}{x} - \frac{1}{x _ 0} \right) + \frac{1}{2} \Omega^2 (x^2 - x _ 0^2) \right] \right)},
\end{equation}

where subscript ${}_0$ stands for the value at the surface. Take Earth as an example, we have $x_0=R_E$.  The cross area at surface is $A(x_0)=A_0$.

The cross area at GEO is given by $A(x_{GEO})$ which is

\begin{equation}
A(x_{GEO}) = A _ 0\exp\left( 0.776 R_E g _ 0 \frac{\rho}{\sigma} \right),
\end{equation}

where $g_0$ is the surface gravity.

Pearson defined $\frac{A(x)}{A_0}$ to be the taper ratio. [^3]


The term $\frac{A(x)'}{A(x)}$ we need in EoM is given by

\begin{equation}
\frac{A(x)'}{A(x)} = -\frac{\rho}{\sigma_0} \left(  -\frac{GM}{x^2} + x \Omega^2 \right).
\end{equation}

The two terms in the parentheses is the tension per unit mass on the cross area.

To determine whether we could drop the first order term in the oscillation equation, the value of $A(x)'/A(x)$ should be determined.



Or the distance can be scaled by radius of the celestial body to simplify the expression,

\begin{align}
&-\frac{GM}{x^2} + x \Omega^2 \\
= & - \frac{G M}{R^2} \frac{R^2}{x^2} + \frac{x}{R} R \Omega^2 \\
= & - g_0 \left(\frac{1}{x/R}  \right)^2+ \frac{x}{R} R \Omega^2.
\end{align}

The two contributions are comparable at a distance

\begin{equation}
\frac{x_{m}}{R} = \sqrt[3]{ \frac{g_0}{\Omega^2 R} }.
\end{equation}


#### Space Elevator on The Earth

> Earth radius: 6367000m

The constants for Earth are $\frac{G M}{R_E^2}  = g_0 = 9.8 \mathrm{m/s^2}$ and $\Omega^2 R_E = 0.034\mathrm{m/s^2}$. The point where the gravity and centrifugal are balanced is

\begin{align}
\frac{x_{mE}}{R_E} \approx 6.6.
\end{align}

As a reminder, the geosynchronous orbit is the orbit that gravity is the same as the centrifugal force if the system is rotating with the same angular velocity of earth.

The term $A(x)'/A(x)$ is

\begin{equation}
\frac{A(x)'}{A(x)} = \frac{A(\hat x_E)'}{R_E A(\hat x_E)} = \frac{\rho}{\sigma_0}\left(  -9.8 /\hat x_E^2 + 3.4\times 10^{-2} \hat x_E \right) \mathrm{m/s^2},
\end{equation}

where $\hat x_E = \frac{x}{R_E}$.

Just for convenience, the function in terms of distance from the center of the center of Earth (not scaled) is

\begin{align}
-\frac{GM}{x^2} + x \Omega^2 &= - \frac{4.0\times 10^{14} \mathrm{ m^3/s^2 }}{x^2} + 5.3\times 10^{-9} \mathrm{s^2} \cdot x .
\end{align}

#### Space Elevator on Mars

> Mars Facts
> 1. Mass: $6.4\times 10^{23}\mathrm{kg}$ ; 
> 2. Radius: $3386000\mathrm{m}$ ;
> 3. Newton's constant: $6.67\times 10^{-11}\mathrm{N m^2/kg^2}$;
> 4. Angular velocity of Mars rotation: $7.1\times 10^{-5} \mathrm{rad/s}$;
> 5. Geosynchronous orbit radius of Mars: $20430000\mathrm{m}$.

The constants for Mars are $\frac{G M}{R_M^2}  = g_M = 3.7\mathrm{m/s^2} $ and $\Omega^2 R_M = 0.017 \mathrm{m/s^2}$.

Thus the radius where the gravity and centrifugal force are balanced is

\begin{equation}
\frac{x_{mM}}{R_M} = 6.0,
\end{equation}

which gives us the geosynchronous radius of Mars.

The expression of $A(x)'/A(x)$ is

\begin{equation}
\frac{A(\hat x)'}{A(\hat x)} = \frac{\rho}{\sigma_0} \left(  - 3.7 /\hat x^2 + 0.017 \hat x \right) \mathrm{m/s^2},
\end{equation}

where $\hat x = \frac{x}{R_M}$. At geosynchronous orbit the term becomes the largest and vanishes. At surface $\hat x = 1$ we have

\begin{align}
\frac{A(\hat x)'}{A(\hat x)} &= \frac{\rho}{\sigma_0} \left(  - 3.7  + 0.017  \right) \mathrm{m/s^2} \\
&\approx \frac{\rho}{\sigma_0} 3.7 \mathrm{m/s^2},
\end{align}

which is usually much smaller than 1 if we explore the maximum strength of the material (which we do). [^4]

As some examples,

1. Steel: $\frac{\rho}{\sigma_m} \sim 10^{-5}$ for max stress.
2. Carbon fiber: $\frac{\rho}{\sigma_m} \sim 10^{-7}$ for max stress.

**The reason we explore the max stress of the material is to save money on it since we could use the least amount of material.** So the final elevator cable should have almost max stress when the cargo is loaded. For safety reasons we probably would use one or two order of magnitude smaller than the max which doesn't change the fact that this term $A(x)'/A(x)$ is very small.






















### Analysis of The Equation of Motion



#### Analytical Attempt for The Complete Oscillation


Assuming separable variables $u(x,t) = X(x)T(t)$, we have

\begin{equation}
\frac{X''}{x}+\frac{A'}{A} \frac{X'}{X} = \frac{T''}{T} v^2,
\end{equation}

where $v=\sqrt{\frac{\rho}{\sigma_0}}$. The boundary condition becomes

\begin{align}
X(0) &= 0 \\
X(L) & = 0.
\end{align}

Thus the only possibility is that

\begin{align}
\frac{X''}{x}+\frac{A'}{A} \frac{X'}{X} &=-g ,\\
 \frac{T''}{T} v^2&=-g .
\end{align}

The equation for $T$ has a simple solution

\begin{equation}
T(t) = A_+ \exp\left( i\sqrt{g}/v  t \right) + A_- \exp\left(  -  i\sqrt{g}/v  t  \right).
\end{equation}

The parameter $g$ should be determined using the equation for $X$ since it has got enough boundary conditions.

Plug in the expression for $A(x')/A(x)$ we have the equation for $X$,

\begin{equation}
X'' + \frac{\rho}{\sigma_0} \left( -\frac{GM}{x^2} + x\Omega^2 \right) X' + g X =0,
\end{equation}

which has a Sturm-Liouville form as it has a vanishing boundary condition at both ends

\begin{equation}
\frac{d}{x} \left(  p(x) \frac{d X}{dx} \right)  + q(x)X = 0, 
\end{equation}

where 

\begin{align}
p(x) & = \exp\left( \frac{\rho}{\sigma_0} \left(  \frac{GM}{x} + \frac{1}{2} \Omega^2 x^2 \right)  \right) \\
q(x) & = g \cdot p(x).
\end{align}


Since we don't really need to solve the complete oscillation due to the fact that $A(x)'/A(x)\ll 1$, it doesn't make a difference whether we could find the analytical solution.


#### Approximation


So, just drop $A(x)'/A(x)$.

As we have seen previously, at the limit that $\frac{A(x)'}{A(x)}n\ll 1$, the equation of motion is

\begin{equation}
u_{xx} - u_{tt} \frac{\rho}{\sigma_0}=0.
\end{equation}

The period of the system is given by $P = \frac{2 L}{m}\sqrt{ \frac{\rho}{\sigma_0} }$, in which $L$ is the total length, $m=0,\pm 1,\pm 2,\cdots$ is the oscillation mode.

The solution to the wave equation is, in general,

\begin{equation}
u(x,t) = \sum_{n=1}^{\infty} \left(  A_n \cos \frac{n\pi v t}{L} + B_n \sin \frac{n\pi v t}{L} \right) \sin \frac{n\pi x}{L},
\end{equation}

where $v=\sqrt{\frac{\rho}{\sigma_0}}$ is the wave speed.


To determine the coefficients we need to apply the initial condition

\begin{align}
u(x,0) & = u_0(x) \\
\dot u(x,0) & = u_1(x).
\end{align}

As an example we assume that we have a initial condition that the first mode of the oscillation has been excited,

\begin{align}
u(x,0) & = \Phi \sin(\pi x/L) \\
\dot u(x,0) & = 0.
\end{align}

Only the $A_1=\Phi$ will be part of the solution

\begin{equation}
u(x,t) = \Phi \cos \frac{\pi v t}{L} \sin \frac{\pi x}{L} .
\end{equation}


In fact, all we need to do is to find the coefficients given any initial condition, which is not alway an easy task.

As a general discussion, initial condition

\begin{align}
u(x,0) & = u_0(x) \\
\dot u(x,0) & = u_1(x),
\end{align}

together with the solution

\begin{align}
u(x,t) &= \sum_{n=1}^{\infty} \left(  A_n \cos \frac{n\pi v t}{L} + B_n \sin \frac{n\pi v t}{L} \right) \sin \frac{n\pi x}{L}\\
& = \sum_{n=1}^{\infty} \left(  A_n \cos ( k_n v t)+ B_n \sin (k_n vt) \right) \sin ( k_n  x),
\end{align}

in which $k_n = \frac{n\pi }{L}$,  result in

\begin{align}
u_0(x) &= \sum_{n=1}^{\infty} A_n \sin (k_n x) , \\
u_1(x) & = \sum_{n=1}^{\infty} B_n k_n v \sin(k_n x).
\end{align}



> Orthogonality of trigonometric functions are
> \begin{align} \int_0^{2\pi} \cos m x \cos n x dx &= 0 ,\\ \int_0^{2\pi} \sin m x \sin n x dx &= 0, \\ \int_0^{2\pi} \sin nx \cos m x dx & = 0.  \end{align}
> Also notice that
> \begin{align}  \int_0^{2\pi} \sin n x \cos n x dx &= 0 , \\ \int_0^{2\pi} \sin n x \sin n x  dx & = \pi ,\\   \int_0^{2\pi} \cos n x \cos n x  dx & = \pi .  \end{align}

We apply the orthogonality of sines and cosines to the initial condition,

\begin{align}
A_m  & = \frac{1}{L} \int_0^{2L} u_0(x) \sin ( k_m x), \\
B_m &= \frac{1}{m \pi v} \int_0^{2L} u_1(x) \sin(k_m x).
\end{align}





### Numerical


#### Approximated Equation

Given a complicated initial condition, the analytical approach is not easily solvable. So we turn to numerical method for help.

*If the large scale oscillations are the concern, we only need the small ${}_n$s.*



#### Exact Equation

**We could also do the simulation for the oscillation with $A'/A$ term.**

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






[^1]: Pugno, N. M. (2006). On the Strength of the Carbon Nanotube-Based Space Elevator Cable: From Nano- to Mega-Mechanics, 1971. doi:10.1088/0953-8984/18/33/S14

[^2]: Jerome Pearson, The orbital tower: A spacecraft launcher using the Earth's rotational energy, Acta Astronautica, Volume 2, Issues 9–10, September–October 1975, Pages 785-799, ISSN 0094-5765, http://dx.doi.org/10.1016/0094-5765(75)90021-1.

[^3]: Edwards B C and Westling E A 2003 The Space Elevator: A Revolutionary Earth-to-Space Transportation System Spageo Inc.

[^4]: [Space Elevator Notes by Probe](https://www.zybuluo.com/probe/note/101784)