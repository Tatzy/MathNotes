Introduction
============

This document will serve as a review for the Mathematics Subject GRE. I
am planning on taking the test in October of 2019, and I plan on
reviewing (nearly) all of the topics on the GRE. My background is in
pure mathematics, particularly I enjoy abstact algebra, mathematical
logic, and computational complexity. However I have noticed that
spending a lot of time away from things like calculus ultimately has
slowed me down to unacceptable levels. What follows in the document will
be completed exercises, commentary, and thoughts about the GRE.
Hopefully someone may find this useful.\
To begin, ETS gives us a set of topics to review and their frequencies
on the GRE. It makes sense to predetermine the order of which I go
through these topics and decide which resources I would like to use for
them. Note that this document is being updated as I go through this and
certain review decisions may completely change.

1.  **Calculus - 50%** In this section we will cover the basics of
    calculus up to Real Analysis. The plan is to cover [@Stewart] for
    calculus, [@Rudin] for analysis (the early chapters), and cover some
    calculus problems from the Princeton Review and [@UC] tests.

Pre-Calculus
============

Trigonometric Functions
-----------------------

In mathematics it sometimes helps us to derive results to better
understand where they come from. This in turn anchors the facts in our
memory. Unfortunately, trigonometric identities do not seem to behave in
this way. However, I will derive them now anyways using the exponential
function.

### Some Identities

$$\begin{aligned}
    e^{i\theta} &= \cos(\theta) + i\sin(\theta)\\
    e^{i\theta}e^{i\tau} &= (\cos(\theta) + i\sin(\theta))(\cos(\tau)+i\sin(\tau))\\
    e^{i(\theta+\tau)} &= \cos(\theta)\cos(\tau)-\sin(\theta)\sin(\tau)+i(\sin(\theta)\cos(\tau) + \sin(\tau)\cos(\theta))\end{aligned}$$
Letting $\theta = \tau$ will provide us with some useful identities:
$$\begin{aligned}
    e^{2i\theta} = \cos^{2}(\theta)-\sin^{2}(\theta)+i(2\sin(\theta)\cos(\theta))\end{aligned}$$
Taking real and imaginary parts respectively, $$\begin{aligned}
    \Re(e^{2i\theta}) &= \cos(2\theta) = \cos^{2}(\theta) - \sin^{2}(\theta)\\
    \Im(e^{2i\theta}) &= \sin(2\theta) = 2\sin(\theta)\cos(\theta)\end{aligned}$$
Knowing that $-\sin^{2} = \cos^{2} - 1$ we can now substitute into (5)
to get $$\begin{aligned}
    \cos(2\theta) = 2\cos^{2}(\theta) - 1 \quad \iff \quad \cos^{2}(\theta) = \frac{1 + \cos(2\theta)}{2}\\\end{aligned}$$
Similarly letting $\cos^2 = 1 - \sin^2$ we have $$\begin{aligned}
    \cos(2\theta) = 1 - 2\sin^{2}(\theta) \quad \iff \quad \sin^{2}(\theta) = \frac{1-\cos(2\theta)}{2}\end{aligned}$$
We will find in calculus that is useful to have this ability to reduce
the power of trigonometric functions, particularly as an integration
technique. The formulas which we just derived are known as the *double
angle formulas*. There are also *half angle formulas* by taking
$\theta = \frac{\tau}{2}$ and taking a square root. Continuing on our
identity frenzy it makes sense to talk about the which are closed form
expressions in the case of $e^{i (\theta \pm \tau)}$. We leave this as
an exercise to derive, and they also somewhat rely on properties we will
mention in the following section.

### Extension to $\mathbb{C}$

$$\begin{aligned}
    e^{iz} + e^{-iz}= \cos(z) + i\sin(z) + \cos(z) - i\sin(z) = 2\cos(z) \quad \iff \quad \frac{e^{iz}+e^{-iz}}{2} = \cos(z)\\
    e^{iz} - e^{-iz} = \cos(z) + i\sin(z) - \cos(z) + i\sin(z) = 2i\sin(z) \quad \iff \quad \frac{e^{iz}-e^{-iz}}{2i} = \sin(z)\end{aligned}$$

### Some Properties of Trigonometric Functions

We state the following identities without proof. $$\begin{aligned}
    &\cos(-x) = \cos(x)\\
    &\sin(-x) = -\sin(x)\\
    &\cos(x + 2\pi) = \cos(x)\\
    &\sin(x + 2\pi) = \sin(x)\\
    &\cos\left(x - \frac{\pi}{2}\right) = \sin(x)\\
    &\sin\left( x + \frac{\pi}{2}\right) = \cos(x)\end{aligned}$$ And
since we've been ignoring $\tan$ for some time $$\begin{aligned}
    \tan(\theta + \tau) = \frac{\tan(\theta)+\tan(\tau)}{1-\tan(\theta)\tan(\tau)}\end{aligned}$$
We can see easily how negating $\tau$ would yield another identity. In
terms of power reduction we have the following formula
$$\tan(2\theta) = \frac{2\tan(\theta)}{1-\tan^{2}(\theta)}$$\

### Vieta's Formulas

An extremely useful trick we have for finding roots of polynomials are
*Vieta's Formulas*. Say we have a polynomial
$a_n x^n + a_{n-1}x^{n-1} + ... + a_{0}$ with roots
$r_{1}, r_2, ..., r_n$. Then
$$a_{n}x^n + a_{n-1}x^{n-1} + ... + a_0 = a_{n}(x-r_1)(x-r_2)\cdots(x-r_n)$$
It becomes clear from multiplying all of the constant terms that
$a_{n}\prod_{i=0}^{n}r_i = (-1)^{n}a_0$ in other words
$$r_1 r_2 \cdots r_n = (-1)^{n}\frac{a_0}{a_n}$$ Similarly by counting
coefficients (particularly of
$x$)$$r_0 + r_1 + ... + r_n = (-1)^{n} \frac{a_{n-1}}{a_n}$$

**Example 1.** Assuming all roots of $x^3 - 3x^2 + 6x - 4$ are of the
form $1+bi$, find the maximum value of $b$\
*Solution.* First we note that this polynomial is of degree 3, and it is
not possible that it has all real roots. Thus the roots we are looking
for are $1+bi$, $1-bi$, and $r$. By Vieta
$$1+bi + 1 -bi + r = 3 \rightarrow r = 1$$
$$(1+bi)(1-bi) = 4 \rightarrow b = \sqrt{3}$$

### Problems

**1.** If $x \in \mathbb{R}$ and $\sin\sin(x) = \frac{1}{2}$ with
$2 < x < 3$. Compute $\cos(-\sin(x))$.\
*Solution.* The equation yields
$\sin(x) = \arcsin\left(\frac{1}{2}\right) \Rightarrow \sin(x) = \frac{\pi}{6}$
taking $\cos$ of both sides yields
$\cos(\sin(x)) = \frac{\sqrt{3}}{2}$.\
\
**2.** Define $\sinh(x) = \frac{e^{x}-e^{-x}}{2}$, what is a formula for
$\sinh^{-1}(x)$?\
*Solution.* Let $y = \sin^{-1}(x)$, we wish to solve
$x = \frac{e^{y}-e^{-y}}{2}$: $$\begin{aligned}
    2x &= e^{y}-e^{-y}\\
    2xe^{y} &= e^{2y} - 1 \Rightarrow 0 = e^{2y} - 2xe^{y} - 1 \quad let t = e^{y}\\
    0 &= t^2 - 2xt - 1 \Rightarrow t = x \pm \sqrt{x^2 + 1}\\
    y &= \log(x \pm \sqrt{x^2 + 1})\end{aligned}$$

**3.** For which value $\theta$ is
$\frac{2+3i\sin(\theta)}{1-2\sin(\theta)}$ purely imaginary?\
*Solution.* Multiply the expression by the complex conjugate of the
denominator to yield: $$\begin{aligned}
    \frac{2 - 6\sin^{2}(\theta)+7i\sin^{2}(\theta)}{1 + 4\sin^{2}(\theta)}\end{aligned}$$
It is clear that there is a lot of extraneous information in this
expression, we need only that the real parts 'cancel out'.
$$\begin{aligned}
    2 &= 6\sin^{2}(\theta)\\
    \sqrt{\frac{1}{3}} &= \sin(\theta) \Rightarrow \theta = \arcsin\left(\sqrt{\frac{1}{3}}\right)\end{aligned}$$

The problems seen here are not particularly interesting. The use of
trigonometry is to reduce the complexity of problems in the future for
the most part.

9 University of Chicago. Math GRE Preparation Materials.
[Link](https://math.uchicago.edu/~min/GRE/). Rudin, Walter. Principles
of Mathematical Analysis.
[Link](https://notendur.hi.is/vae11/%C3%9Eekking/principles_of_mathematical_analysis_walter_rudin.pdf).
Stewart, James. Calculus. Physical Copy. GRE Practice Test.
[Link](https://www.ets.org/s/gre/pdf/practice_book_math.pdf).
