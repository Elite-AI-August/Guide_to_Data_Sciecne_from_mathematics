# Numerical Optimization

IN [A Few Useful Things to Know about Machine Learning](https://homes.cs.washington.edu/~pedrod/papers/cacm12.pdf), Pedro Domingos put up a relation:
$\color{aqua}{LEARNING = REPRESENTATION + EVALUATION + OPTIMIZATION}.$

* Representation as the core of the note is the general (mathematical) **model** that computer can handle.
* Evaluation is  **criteria**. An evaluation function (also called objective function, cost function or scoring function) is needed to distinguish good classifiers from bad ones.
* Optimization is to aimed to find the parameters taht optimizes the evaluation function, i.e.
    $$
    \arg\min_{\theta} f(\theta)=\{\theta^*|f(\theta^*)=\min f(\theta)\}\,\text{or}\,\arg\max_{\theta}f(\theta)=\{\theta^*|f(\theta^*)=\max f(\theta)\}.
    $$

***********************************************

The objective function to be minimized is also called cost function.

Evaluation is always attached with optimization; the evavluation which cannot be optimized is not a good evaluation in machine learning.

* https://www.wikiwand.com/en/Mathematical_optimization
* https://web.stanford.edu/~boyd/cvxbook/bv_cvxbook.pdf
* http://www.cs.cmu.edu/~pradeepr/convexopt/

## Gradient Descent and More

Each iteration of a line search method computes a search direction $p^{k}$ and then decides how
far to move along that direction. The iteration is given by
$$
x^{k+1}=x^{k}+\alpha_{k}p^{k}\tag{Line search}
$$
where the positive scalar $\alpha^{k}$ is called the step length. The success of a line search method
depends on effective choices of both the direction $p^{k}$ and the step length $\alpha_{k}$.

$\color{lime}{Note}$: we use the notation $x^{k}$ and $\alpha_k$ to represent the $k$th iteration of the vector variables $x$ and $k$th step length, respectively.
Most line search algorithms require pk to be a descent direction—one for which
$\left< {p^k},\nabla f_k \right> < 0$ — because this property guarantees that the function $f$ can be reduced along this direction, where $\nabla f_k$ is the gradient of objective function $f$ at the $k$th iteration point $x_k$ i.e. $\nabla f_k=\nabla f(x^{k})$.
***
Gradient descent and its variants are to find the local solution of  the unconstrained optimization problem:
$$
\min f(x)
$$
where $x\in \mathbb{R}^{n}$.

Its iterative procedure is:
$$
x^{k+1}=x^{k}-\alpha_{k}\nabla_{x}f(x^k)
$$
where $x^{k}$ is the $k$th iterative result, $\alpha_{k}\in\{\alpha|f(x^{k+1})< f(x^{k})\}$ and particularly $\alpha_{k}=\arg\min_{\alpha}f(x^{k}-\alpha\nabla_{x}f(x^{k}))$.
****
Some variants of gradient descent methods are not line search method.
For example, the **heavy ball method**:
$$
x^{k+1}=x^{k}-\alpha_{k}\nabla_{x}f(x^k)+\rho_{k}(x^k-x^{k-1})
$$
where the momentum coefficient $\rho_k\in[0,1]$ generally and the step length $\alpha_k$ cannot be determined by line search.

**Nesterov accelerated gradient method**:
$$
\begin{align}
x^{k}=y^{k}-\alpha^{k+1}\nabla_{x}f(y^k) \qquad &\text{Descent} \\
y^{k+1}=x^{k}+\rho^{k}(x^{k}-x^{k-1})   \qquad  &\text{Momentum}
\end{align}
$$
where the momentum coefficient $\rho_k\in[0,1]$ generally.

|Inventor of Nesterov accelerated Gradient|
|:---:|
|![Yurii Nesterov](https://upload.wikimedia.org/wikipedia/commons/thumb/9/9e/Nesterov_yurii.jpg/440px-Nesterov_yurii.jpg)}|
****

* https://www.wikiwand.com/en/Gradient_descent
* http://wiki.fast.ai/index.php/Gradient_Descent
* https://blogs.princeton.edu/imabandit/2013/04/01/acceleratedgradientdescent/
* https://blogs.princeton.edu/imabandit/2015/06/30/revisiting-nesterovs-acceleration/
* http://awibisono.github.io/2016/06/20/accelerated-gradient-descent.html
* https://jlmelville.github.io/mize/nesterov.html
* https://smartech.gatech.edu/handle/1853/60525
* https://zhuanlan.zhihu.com/p/41263068
* https://zhuanlan.zhihu.com/p/35692553
* https://zhuanlan.zhihu.com/p/35323828

## Mirror Gradient Method

It is often called **mirror descent**.
It can be regarded as non-Euclidean generalization of **projected gradient descent** to solve some constrained optimization problems.

### Projected Gradient Descent

**Projected gradient descent** is aimed to solve convex optimization problem with explicit constraints, i.e.
$$
\arg\min_{x\in\mathbb{S}}f(x)
$$
where $\mathbb{S}\subset\mathbb{R}^n$.
It has two steps:
$$
\begin{align}
z^{k+1} = x^{k}-\alpha_k\nabla_x f(x^{k}) &\qquad \text{Gradient descent}\\
x^{k+1} = Proj_{\mathbb{S}}(z^{k+1})=\arg\min_{x\in \mathbb{S}}\|x-z^{k+1}\|^{2} &\qquad\text{Projection}
\end{align}
$$

### Mirror descent

**Mirror descent** can be regarded as the non-Euclidean generalization via replacing the $\ell_2$ norm or Euclidean distance in projected gradient descent by [Bregman divergence](https://www.mdpi.com/1099-4300/16/12/6338/htm).

Bregman divergence is induced by convex smooth function $f$:
$$
B(x,y)=f(x)-f(y)-\left<\nabla f(y),x-y\right>
$$
where $\left<\cdot,\cdot\right>$ is inner product.
Especially, when $f$ is quadratic function, the Bregman divergence induced by $f$ is
$$
B(x,y)=x^2-y^2-\left<2y,x-y\right>=x^2+y^2-2xy=(x-y)^2
$$
i.e. the Euclidean distance.
A wonderful introduction to **Bregman divergence** is **Meet the Bregman Divergences** by [Mark Reid](http://mark.reid.name/) at <http://mark.reid.name/blog/meet-the-bregman-divergences.html>.
***
It is given by:
$$
\begin{align}
z^{k+1} = x^{k}-\alpha_k\nabla_x f(x^{k}) &\qquad \text{Gradient descent}\\
x^{k+1} = \arg\min_{x\in\mathbb{S}}B(x,z^{k+1}) &\qquad\text{Bregman projection}
\end{align}.
$$
One special method is called **entropic mirror descent** when $f=e^x$ and $\mathbb{S}$ is simplex.

See more on the following link list.

* http://users.cecs.anu.edu.au/~xzhang/teaching/bregman.pdf
* https://zhuanlan.zhihu.com/p/34299990
* https://blogs.princeton.edu/imabandit/2013/04/16/orf523-mirror-descent-part-iii/
* https://blogs.princeton.edu/imabandit/2013/04/18/orf523-mirror-descent-part-iiii/
* https://www.stat.berkeley.edu/~bartlett/courses/2014fall-cs294stat260/lectures/mirror-descent-notes.pdf

## Variable Metric Methods

### Newton's Method

NEWTON’S METHOD and QUASI-NEWTON METHODS are classified to variable metric methods.

It is also to find the solution of unconstrained optimization problems, i.e.
$$\min f(x)$$
where $x\in \mathbb{R}^{n}$.
***
**Newton's method** is given by
$$
x^{k+1}=x^{k}-\alpha^{k+1}H^{-1}(x^{k})\nabla_{x}\,{f(x^{k})}
$$
where $H^{-1}(x^{k})$ is inverse of the Hessian matrix of the function $f(x)$ at the point $x^{k}$.
It is called **Newton–Raphson algorithm** in statistics.
Especially when the log-likelihood function $\ell(\theta)$ is well-behaved,
a natural candidate for finding the MLE is the **Newton–Raphson algorithm** with quadratic convergence rate.


### The Fisher Scoring Algorithm

In maximum likelihood estimation, the objective function is the log-likelihood function, i.e.
$$
\ell(\theta)=\sum_{i=1}^{n}\log{P(x_i|\theta)}
$$
where $P(x_i|\theta)$ is the probability of realization $X_i=x_i$ with the unknown parameter $\theta$.
However, when the sample random variable $\{X_i\}_{i=1}^{n}$ are not observed or realized, it is best to
replace negative Hessian matrix (i.e. -$\frac{\partial^2\ell(\theta)}{\partial\theta\partial\theta^{T}}$) of the likelihood function with the  
**observed information matrix**:
$$
J(\theta)=\mathbb{E}(\color{red}{\text{-}}\frac{\partial^2\ell(\theta)}{\partial\theta\partial\theta^{T}})=\color{red}{-}\int\frac{\partial^2\ell(\theta)}{\partial\theta\partial\theta^{T}}f(x_1, \cdots, x_n|\theta)\mathrm{d}x_1\cdots\mathrm{d}x_n
$$
where $f(x_1, \cdots, x_n|\theta)$ is the joint probability density function of  $X_1, \cdots, X_n$ with unknown parameter $\theta$.

And the **Fisher scoring algorithm** is given by
$$
\theta^{k+1}=\theta^{k}+\alpha_{k}J^{-1}(\theta^{k})\nabla_{\theta} \ell(\theta^{k})
$$
where $J^{-1}(\theta^{k})$ is the inverse of observed information matrix at the point $\theta^{k}$.

See <http://www.stats.ox.ac.uk/~steffen/teaching/bs2HT9/scoring.pdf> or <https://wiseodd.github.io/techblog/2018/03/11/fisher-information/>.

**Fisher scoring algorithm** is regarded  as an example of **Natural Gradient Descent** in
information geometry  such as <https://wiseodd.github.io/techblog/2018/03/14/natural-gradient/>
and <https://www.zhihu.com/question/266846405>.

### Quasi-Newton Methods

Quasi-Newton methods, like steepest descent, require only the gradient of the objective
function to be supplied at each iterate.
By measuring the changes in gradients, they construct a model of the objective function
that is good enough to produce superlinear convergence.
The improvement over steepest descent is dramatic, especially on difficult
problems. Moreover, since second derivatives are not required, quasi-Newton methods are
sometimes more efficient than Newton’s method.[^11]

In optimization, quasi-Newton methods (a special case of **variable-metric methods**) are algorithms for finding local maxima and minima of functions. Quasi-Newton methods are based on Newton's method to find the stationary point of a function, where the gradient is 0.
In quasi-Newton methods the Hessian matrix does not need to be computed. The Hessian is updated by analyzing successive gradient vectors instead. Quasi-Newton methods are a generalization of the secant method to find the root of the first derivative for multidimensional problems. In multiple dimensions the secant equation is under-determined, and quasi-Newton methods differ in how they constrain the solution, typically by adding a simple low-rank update to the current estimate of the Hessian.
One of the chief advantages of quasi-Newton methods over Newton's method is that the Hessian matrix (or, in the case of quasi-Newton methods, its approximation) $B$ does not need to be inverted. The Hessian approximation $B$ is chosen to satisfy
$$
\nabla f(x^{k+1})=\nabla f(x^{k})+B(x^{k+1}-x^{k}),
$$
which is called the **secant equation** (the Taylor series of the gradient itself).
In more than one dimension B is underdetermined. In one dimension, solving for B and applying the Newton's step with the updated value is equivalent to the [secant method](https://www.wikiwand.com/en/Secant_method).
The various quasi-Newton methods differ in their choice of the solution to the **secant equation** (in one dimension, all the variants are equivalent).

![BFGS](http://aria42.com/images/bfgs.png)
***

* [Wikipedia page](https://www.wikiwand.com/en/Newton%27s_method_in_optimization)
* [Newton-Raphson Visualization (1D)](http://bl.ocks.org/dannyko/ffe9653768cb80dfc0da)
* [Newton-Raphson Visualization (2D)](http://bl.ocks.org/dannyko/0956c361a6ce22362867)
* [Newton's method](https://www.wikiwand.com/en/Newton%27s_method)
* [Quasi-Newton method](https://www.wikiwand.com/en/Quasi-Newton_method)
* [Using Gradient Descent for Optimization and Learning](http://www.gatsby.ucl.ac.uk/teaching/courses/ml2-2008/graddescent.pdf)
* http://fa.bianp.net/teaching/2018/eecs227at/quasi_newton.html

### Natural Gradient Descent

Natural gradient descent is to solve the optimization problem $\min_{\theta} L(\theta)$ by
$$
\theta^{(t+1)}=\theta^{(t+1)}-\alpha_{(t)}F^{-1}(\theta^{(t)})\nabla_{\theta}L(\theta^{(t)})
$$
where $F^{-1}(\theta^{(t)})$ is the inverse of Remiann metric at the point $\theta^{(t)}$.
And **Fisher scoring** algorithm is a typical application of **Natural Gradient Descent** to statistics.  
**Natural gradient descent** for manifolds corresponding to
exponential families can be implemented as a first-order method through **mirror descent** (https://www.stat.wisc.edu/~raskutti/publication/MirrorDescent.pdf).

| Originator of Information Geometry |
|:----:|
|![Shun-ichi Amari](https://groups.oist.jp/sites/default/files/imce/u34/images/people/shun-ichi-amari.jpg)|

* http://www.yann-ollivier.org/rech/publs/natkal.pdf
* http://www.dianacai.com/blog/2018/02/16/natural-gradients-mirror-descent/
* https://www.zhihu.com/question/266846405
* http://bicmr.pku.edu.cn/~dongbin/Conferences/Mini-Course-IG/index.html
* http://ipvs.informatik.uni-stuttgart.de/mlr/wp-content/uploads/2015/01/mathematics_for_intelligent_systems_lecture12_notes_I.pdf
* http://www.luigimalago.it/tutorials/algebraicstatistics2015tutorial.pdf
* http://www.yann-ollivier.org/rech/publs/tango.pdf
* http://www.brain.riken.jp/asset/img/researchers/cv/s_amari.pdf

## Expectation Maximization Algorithm

**Expectation-Maximization algorithm**, popularly known as the  **EM algorithm** has become a standard piece in the statistician’s repertoire.
It is used in incomplete-data problems or latent-variable problems such as Gaussian mixture model in maximum likelihood  estimation.
The basic principle behind the **EM** is that instead of performing a complicated optimization,
one augments the observed data with latent data to perform a series of simple optimizations.

Let $\ell(\theta|Y_{obs})\stackrel{\triangle}=\log{L(\theta|Y_{obs})}$ denote the log-likelihood function of observed datum $Y_{obs}$。
We augment the observed data $Y_{obs}$ with latent variables $Z$ so that both the
complete-data log-likelihood $\ell(\theta|Y_{obs}, Z)$ and the conditional predictive distribution $f(z|Y_{obs}, \theta)$ are available.
Each iteration of the **EM** algorithm consists of an expectation step (E-step) and a maximization step (M-step)
Specifically, let $\theta^{(t)}$ be the current best guess at the MLE $\hat\theta$. The E-step
is to compute the **Q** function defined by
$$
\begin{align}
Q(\theta|\theta^{(t)}) &= \mathbb{E}(\ell(\theta|Y_{obs}, Z)|Y_{obs},\theta^{(t)}) \\
                       &= \int_{Z}\ell(\theta|Y_{obs}, Z)\times f(z|Y_{obs}, \theta^{(t)})\mathrm{d}z,
\end{align}
$$
and the M-step is to maximize **Q** with respect to $\theta$ to obtain
$$
\theta^{(t+1)}=\arg\max_{\theta} Q(\theta|\theta^{(t)}).
$$

* https://www.wikiwand.com/en/Expectation%E2%80%93maximization_algorithm
* http://cs229.stanford.edu/notes/cs229-notes8.pdf

|Diagram of EM algorithm|
|:---------------------:|
|![](https://i.stack.imgur.com/v5bqe.png)|

### Generalized EM Algorithm

Each iteration of the **generalized EM** algorithm consists of an expectation step (E-step) and a maximization step (M-step)
Specifically, let $\theta^{(t)}$ be the current best guess at the MLE $\hat\theta$. The E-step
is to compute the **Q** function defined by
$$
\begin{align}
Q(\theta|\theta^{(t)}) &= \mathbb{E}(\ell(\theta|Y_{obs}, Z)|Y_{obs},\theta^{(t)}) \\
                       &= \int_{Z}\ell(\theta|Y_{obs}, Z)\times f(z|Y_{obs}, \theta^{(t)})\mathrm{d}z,
\end{align}
$$
and the another step is to find  $\theta$ that satisfies
$$
\theta^{(t+1)}\in \{\theta|Q(\theta|\theta^{(t+1)} \geq Q(\theta|\theta^{(t)}) \}.
$$

It is not to maximize the conditional expectation.

See more on the book [The EM Algorithm and Extensions, 2nd Edition
by Geoffrey McLachlan , Thriyambakam Krishna](https://www.wiley.com/en-cn/The+EM+Algorithm+and+Extensions,+2nd+Edition-p-9780471201700).

* https://www.stat.berkeley.edu/~aldous/Colloq/lange-talk.pdf

## Alternating Direction Method of Multipliers

Alternating direction method of multipliers is called **ADMM** shortly.
It is aimed to solve the following convex optimization problem:
$$
\begin{align}
  \min F(x,y) \{&=f(x)+g(y)\} \tag {cost function} \\
          Ax+By &=b \tag{constraint}
\end{align}
$$
where $f(x)$ and $g(y)$ is convex; $A and $B$ are matrices.

Define the augmented Lagrangian:
$$
L_{\mu}(x,y)=f(x)+g(y)+\lambda^{T}(Ax+By-b)+\frac{\mu}{2}\|Ax+By-b\|_{2}^{2}.
$$
***
It is iterative procedure:

> 1. $x^{k+1}=\arg\min_{x}L_{\mu}(x,y^{\color{aqua}{k}},\lambda^{\color{aqua}{k}});$
> 2. $y^{k+1}=\arg\min_{y} L_{\mu}(x^{\color{red}{k+1}}, y, \lambda^{\color{aqua}{k}});$
> 3. $\lambda^{k+1} = \lambda^{k}+\mu (Ax^{\color{red}{k+1}} + By^{\color{red}{k+1}}-b).$

***
$\color{aqua}{\text{Thanks to Professor He Bingsheng who taught me this.}}$[^9]

* https://www.ece.rice.edu/~tag7/Tom_Goldstein/Split_Bregman.html
* http://maths.nju.edu.cn/~hebma/
* http://stanford.edu/~boyd/admm.html
* http://shijun.wang/2016/01/19/admm-for-distributed-statistical-learning/
* https://www.wikiwand.com/en/Augmented_Lagrangian_method
* https://blog.csdn.net/shanglianlm/article/details/45919679
* http://www.optimization-online.org/DB_FILE/2015/05/4925.pdf


## Stochastic Gradient Descent

Stochastic gradient descent takes advantages of stochastic or estimated gradient to replace the true gradient in gradient descent.
It is **stochastic gradient** but may not be **descent**.
The name **stochastic gradient methods**  may be more appropriate to call the methods with stochastic gradient.
It can date back upto **stochastic approximation**.

It is aimed to solve the problem with finite sum optimization problem, i.e.
$$
\arg\min_{\theta}\frac{1}{n}\sum_{i=1}^{n}f(\theta|x_i)
$$
where $n<\infty$ and $\{f(\theta|x_i)\}_{i=1}^{n}$ are in the same function family and $\{x_i\}_{i=1}^{n}\subset \mathbb{R}^{d}$ are constants  while $\theta\in\mathbb{R}^{p}$ is the variable vector.

The difficulty is $p$, that the dimension of $\theta$, is tremendous. In other words, the model is **overparameterized**. And the number $n$ is far larger than $p$ generally, i.e. $n \gg  p\gg d$.
What is worse, the functions  $\{f(\theta|x_i)\}_{i=1}^{n}$ are not convex in most case.
***
The stochastic gradient method is defined as
$$
\theta^{k+1}=\theta^{k}-\alpha_{k}\frac{1}{m}\sum_{j=1}^{m}\nabla f(\theta^{k}| x_{j}^{\prime})
$$
where $x_{j}^{\prime}$ is stochastically draw from $\{x_i\}_{i=1}^{n}$ and $m\ll n$.

It is the fact $m\ll n$ that makes it possible to compute the gradient of finite sum objective function and its side effect is that the objective function is not always descent.
There is fluctuations in the total objective function as gradient steps with respect to mini-batches are taken.

******************************************************************

|The fluctuations in the objective function as gradient steps with respect to mini-batches are taken|
|:------------------------------------:|
|![](https://upload.wikimedia.org/wikipedia/commons/f/f3/Stogra.png)|

***
An heuristic proposal for avoiding the choice and for modifying the learning rate while the learning task runs is the **bold driver (BD) method**[^14].
The learning rate increases *exponentially* if successive steps reduce the objective function $f$, and decreases rapidly if an “accident” is encountered (if objective function $f$ increases), until a suitable value is found.
After starting with a small learning rate, its modifications are described by the following equation:
$$
  \alpha_{k+1}=
   \begin{cases}
       \rho \alpha_{k}, & {f(\theta^{k+1})< f(\theta^{k})}; \\
       \eta^n \alpha_{k}, & {f(\theta^{k+1})> f(\theta^{k})} \text{using ${\alpha}_k$},
   \end{cases}
$$

where $\rho$ is close to 1 such as $\rho=1.1$  in order to avoid frequent “accidents” because the
objective function computation is wasted in these cases, $\eta$ is chosen to provide a rapid reduction
($\eta = 0.5$), and $n$ is the minimum integer such that the reduced rate $\eta^n$ succeeds in diminishing the objective function.[^13]
***
The fact that the sample size is far larger than the dimension of parameter, $n\gg p$,  that makes it expensive to compute total objective function $f(\theta)=\sum_{i=1}^{n}f(\theta|{x}_i)$.
Thus it is not clever to determine the learning rate $\alpha_k$ by line search. 
And most stochastic gradient methods are to find  proper step length $\alpha_{k}$ to make it converge at least in convex optimization.
The variants of gradient descent such as momentum methods or mirror gradient methods have their stochastic counterparts.

* It is simplest to set the step length a constant, such as ${\alpha}_k=3\times 10^{-3}\, \forall k$.
* There are decay schemes, i.e. the step length ${\alpha}_k$ diminishes such as ${\alpha}_k=\frac{\alpha}{k}$, where $\alpha$ is constant.
* And another strategy is to tune the step length adaptively such as *AdaGrad, ADAM*.

$\color{lime}{PS}$: the step length  $\alpha_k$ is called **learning rate** in machine learning and stochastic gradient descent is also named as [increment gradient methods](http://www.mit.edu/~dimitrib/Incremental_Survey_LIDS.pdf) in some case.

See the following links for more information on *stochastic gradient descent*.

* https://www.wikiwand.com/en/Stochastic_gradient_descent
* https://www.bonaccorso.eu/2017/10/03/a-brief-and-comprehensive-guide-to-stochastic-gradient-descent-algorithms/
* https://leon.bottou.org/projects/sgd
* https://leon.bottou.org/research/stochastic
* http://ruder.io/optimizing-gradient-descent/
* http://ruder.io/deep-learning-optimization-2017/
* https://zhuanlan.zhihu.com/p/22252270
* https://henripal.github.io/blog/stochasticdynamics
* https://henripal.github.io/blog/langevin
* http://fa.bianp.net/teaching/2018/eecs227at/stochastic_gradient.html

|The Differences of Gradient Descent and Stochastic Gradient Descent|  
|:-----------------------------------------------------------------:|
|![](https://wikidocs.net/images/page/3413/sgd.png)|

***

|The Differences of Stochastic Gradient Descent and its Variants|  
|:-------------------------------------------------------------:|
|![](http://beamandrew.github.io//images/deep_learning_101/sgd.gif)|