- [Recommender System](#recommender-system)
  - [Collaborative Filtering](#collaborative-filtering)
    - [Matrix Completion](#matrix-completion)
    - [Maximum Margin Matrix Factorization](#maximum-margin-matrix-factorization)
    - [SVD and Beyond](#svd-and-beyond)
    - [Probabilistic Matrix Factorization](#probabilistic-matrix-factorization)
    - [Poisson Factorization](#poisson-factorization)
    - [Collaborative Less-is-More Filtering(CliMF)](#collaborative-less-is-more-filteringclimf)
    - [Matrix Factorization for Implicit Feedback](#matrix-factorization-for-implicit-feedback)
    - [Discrete Collaborative Filtering](#discrete-collaborative-filtering)
    - [Recommendation with Implicit Information](#recommendation-with-implicit-information)
    - [Inductive Matrix Completion](#inductive-matrix-completion)
    - [Beyond Matrix Completion](#beyond-matrix-completion)
  - [Factorization Machines(FM)](#factorization-machinesfm)
    - [Field-aware Factorization Machine(FFM)](#field-aware-factorization-machineffm)
    - [Convex Factorization Machines](#convex-factorization-machines)
    - [Higher-Order Factorization Machines](#higher-order-factorization-machines)
  - [Deep Learning for Recommender System](#deep-learning-for-recommender-system)
    - [Restricted Boltzmann Machines for Collaborative Filtering](#restricted-boltzmann-machines-for-collaborative-filtering)
    - [AutoRec for Collaborative Filtering](#autorec-for-collaborative-filtering)
    - [Deep crossing](#deep-crossing)
    - [Neural collaborative filtering](#neural-collaborative-filtering)
    - [Collaborative deep learning for RecSys](#collaborative-deep-learning-for-recsys)
    - [Wide & Deep Model](#wide--deep-model)
    - [Deep FM](#deep-fm)
    - [Neural Factorization Machines](#neural-factorization-machines)
    - [Attentional Factorization Machines](#attentional-factorization-machines)
    - [xDeepFM](#xdeepfm)
    - [RepeatNet](#repeatnet)
    - [Deep Matrix Factorization](#deep-matrix-factorization)
    - [Deep Matching Models for Recommendation](#deep-matching-models-for-recommendation)
  - [Embedding methods for RecSys](#embedding-methods-for-recsys)
    - [Hyperbolic Recommender Systems](#hyperbolic-recommender-systems)
    - [Prod2Vec](#prod2vec)
    - [Item2vec](#item2vec)
    - [Meta-Prod2Vec](#meta-prod2vec)
    - [Graph Embeddings for RecSys](#graph-embeddings-for-recsys)
      - [proNet](#pronet)
      - [Modularize Graph Embedding for Recommendation](#modularize-graph-embedding-for-recommendation)
  - [Graph-based RecSys](#graph-based-recsys)
    - [Deep Geometric Matrix Completion](#deep-geometric-matrix-completion)
    - [PinSage](#pinsage)
    - [Spectral Collaborative Filtering](#spectral-collaborative-filtering)
    - [LightGCN](#lightgcn)
    - [GraphRec](#graphrec)
  - [Feature Interaction Selection in RecSys](#feature-interaction-selection-in-recsys)
    - [AutoCross](#autocross)
    - [Product-based Neural Network](#product-based-neural-network)
    - [Deep Crossing](#deep-crossing-1)
    - [AutoGroup](#autogroup)
    - [AutoFIS](#autofis)
    - [AutoFeature](#autofeature)
    - [Automated Embedding](#automated-embedding)
  - [Ensemble Methods for Recommender System](#ensemble-methods-for-recommender-system)
    - [BellKor's Progamatic Chaos](#bellkors-progamatic-chaos)
    - [BoostFM](#boostfm)
    - [Adaptive Boosting Personalized Ranking (AdaBPR)](#adaptive-boosting-personalized-ranking-adabpr)
    - [Gradient Boosting Factorization Machines](#gradient-boosting-factorization-machines)
      - [Gradient Boosted Categorical Embedding and Numerical Trees](#gradient-boosted-categorical-embedding-and-numerical-trees)
      - [Deep Embedding Networks and Gradient Boosting Decision Trees](#deep-embedding-networks-and-gradient-boosting-decision-trees)
  - [Tree-based Deep Model for Recommender Systems](#tree-based-deep-model-for-recommender-systems)
  - [Context-aware Recommendations](#context-aware-recommendations)
    - [Context-Aware Factorization Machines](#context-aware-factorization-machines)
  - [Sequential Recommender Systems](#sequential-recommender-systems)
  - [Top-N recommendation](#top-n-recommendation)
  - [Explainable Recommendations](#explainable-recommendations)
  - [Social Recommendation](#social-recommendation)
    - [SocialMF: MF with social trust propagation](#socialmf-mf-with-social-trust-propagation)
    - [Algorithmic Bias in Search and Recommendation](#algorithmic-bias-in-search-and-recommendation)
  - [Knowledge Graph and Recommender System](#knowledge-graph-and-recommender-system)
    - [RippleNet](#ripplenet)
  - [Reinforcement Learning and Recommender System](#reinforcement-learning-and-recommender-system)
  - [Adversarial Learning for  Recommender Systems](#adversarial-learning-for--recommender-systems)
    - [Generative Adversarial Networks for Recommender Systems](#generative-adversarial-networks-for-recommender-systems)
    - [Adversarial Attacks](#adversarial-attacks)
    - [Adversarial Training](#adversarial-training)
  - [Health Recommender Systems](#health-recommender-systems)
    - [Recommdender System for Doctor](#recommdender-system-for-doctor)
      - [Patient-Doctor Matchmaking](#patient-doctor-matchmaking)
    - [DeepReco](#deepreco)
  - [Resource on RecSys](#resource-on-recsys)
    - [Labs](#labs)
    - [Workshop](#workshop)
    - [Implementation](#implementation)
- [Preference Learning](#preference-learning)
  - [Pairwise Preference Learning and Ranking](#pairwise-preference-learning-and-ranking)
  - [Collaborative Preference Learning](#collaborative-preference-learning)
  - [Preference Learning and Gaussian Processes](#preference-learning-and-gaussian-processes)
  - [Preference Learning and Choice Model](#preference-learning-and-choice-model)
    - [Modeling Users’ Preferences](#modeling-users-preferences)
- [Computational Advertising](#computational-advertising)
  - [Click-Through Rate Modeling](#click-through-rate-modeling)
  - [Conversion Rate Modeling](#conversion-rate-modeling)
  - [Bid Optimization](#bid-optimization)
  - [User Engagement](#user-engagement)
  - [User Modeling](#user-modeling)
  - [Resource](#resource)
    - [Labs](#labs-1)
    - [Courese](#courese)


# Recommender System


Recommender Systems (RSs) are software tools and techniques providing suggestions for items to be of use to a user.
RSs are primarily directed towards individuals who lack sufficient personal experience or competence to evaluate the potentially overwhelming number of alternative items 
that a Web site, for example, may offer.

[Xavier Amatriain discusses the traditional definition and its data mining core.](https://www.kdd.org/exploration_files/V14-02-05-Amatriain.pdf)

Traditional definition: The **recommender system** is to estimate a utility  function that automatically predicts how a user will like an item.

User Interest is **implicitly** reflected in `Interaction history`, `Demographics` and `Contexts`, 
which can be regarded as a typical example of data mining. 
Recommender system should match a context to a collection of information objects. 
There are some methods called `Deep Matching Models for Recommendation`.
It is an application of machine learning, which is in the *representation + evaluation + optimization* form. 
And we will focus on the `representation and evaluation`.

<img src= "https://pic1.zhimg.com/80/v2-c0953af315e5108bc60bb30a4e38a37c_720w.jpg" width="70%" />

- [ ] https://github.com/hongleizhang/RSPapers
- [ ] https://github.com/chihming/competitive-recsys
- [ ] https://rsbd2019.wordpress.com/
- [ ] https://github.com/familyld/AwesomeRecSysPaper/
- [ ] https://github.com/benfred/implicit
- [ ] https://github.com/YuyangZhangFTD/awesome-RecSys-papers
- [ ] https://github.com/daicoolb/RecommenderSystem-Paper
- [ ] https://github.com/grahamjenson/list_of_recommender_systems
- [ ] https://www.zhihu.com/question/20465266/answer/142867207
- [ ] http://www.mbmlbook.com/Recommender.html
- [ ] https://wiki.recsys.acm.org/index.php/Main_Page  
- [X] [直接优化物品排序的推荐算法](https://blog.csdn.net/u013166160/article/details/17935193)
- [ ] [推荐系统遇上深度学习](https://www.jianshu.com/c/e12d7195a9ff)
- [ ] [Large-Scale Recommender Systems@UTexas](http://bigdata.ices.utexas.edu/project/large-scale-recommender-systems/)
- [ ] [Alan Said's publication](https://www.alansaid.com/publications.html)
- [ ] [MyMediaLite Recommender System Library](http://www.mymedialite.net/links.html)
- [ ] [Recommender System Algorithms @ deitel.com](http://www.deitel.com/ResourceCenters/Web20/RecommenderSystems/RecommenderSystemAlgorithms/tabid/1317/Default.aspx)
- [ ] [Workshop on Recommender Systems: Algorithms and Evaluation](http://sigir.org/files/forum/F99/Soboroff.html)
- [ ] [Semantic Recommender Systems. Analysis of the state of the topic](https://www.upf.edu/hipertextnet/en/numero-6/recomendacion.html)
- [ ] [Recommender Systems (2019/1)](https://homepages.dcc.ufmg.br/~rodrygo/recsys-2019-1/)
- [ ] [Recommender systems & ranking](https://sites.google.com/view/chohsieh-research/recommender-systems)
- [ ] [Large scale recommender systems](https://bigdata.oden.utexas.edu/project/large-scale-recommender-systems/)
- [ ] [Symposium on Semantic Computing and Personalization](http://dasfaa-secop.org/)
- [ ] [International Workshop on Web Personalization, Recommender Systems, and Social Media (WPRSM2018)](http://www.webpres-workshop.com/)
- [ ] https://www.comp.hkbu.edu.hk/mdm2019/files/slides/keynote_xie.pdf

Evolution of the Recommender Problem:
- Rating
- Ranking
- Page Optimization
- Context-aware Recommendations

**********
|------------------|
|:---:|
|Collaborative Filtering (CF)|
|Content-Based Filtering (CBF)|
|Demographic Filtering (DF)|
|Knowledge-Based Filtering (KBF)|
|Hybrid Recommendation Systems|

**Evaluation of Recommendation System**

The evaluation of machine learning algorithms depends on the tasks.
The evaluation of recommendation system can be regarded as some machine learning models such as regression, classification and so on.
We only take the mathematical convenience into consideration in the following methods.
`Gini index, covering rate` and more realistic factors are not discussed in the following content.

- [Recommendation Strategies](https://datawarrior.wordpress.com/2019/06/19/strategies-of-recommendation-systems/)
- [Evaluating recommender systems](http://fastml.com/evaluating-recommender-systems/)
- [Distance Metrics for Fun and Profit](https://www.benfrederickson.com/distance-metrics/)
- [Recsys2018 evaluation: tutorial](https://github.com/jeanigarcia/recsys2018-evaluation-tutorial)

## Collaborative Filtering

There are 3 kinds of collaborative filtering: user-based, item-based and model-based collaborative filtering.

The user-based methods are based on the similarities of users. If user ${u}$ and ${v}$ are very similar friends, we may recommend the items which user ${u}$ bought to the user ${v}$ and explains it that your friends also bought it.

The item-based methods are based on the similarity of items. If one person added a brush to shopping-list, it is reasonable to recommend some toothpaste to him or her. And we can explain that you bought item $X$ and the people who bought $X$ also bought $Y$.
And we focus on the model-based collaborative filtering.

- [协同过滤详解](https://www.cnblogs.com/ECJTUACM-873284962/p/8729010.html)
- [深入推荐引擎相关算法 - 协同过滤](https://www.ibm.com/developerworks/cn/web/1103_zhaoct_recommstudy2/index.html)


### Matrix Completion

Matrix completion is to complete the matrix $X$ with missing elements, such as

$$
\min_{Z} Rank(Z) \\
s.t. \sum_{(i,j):Observed}(Z_{(i,j)}-X_{(i,j)})^2\leq \delta
$$

Note that the rank of a matrix is not easy or robust  to compute.

We can apply [customized PPA](http://maths.nju.edu.cn/~hebma/Talk/Unified_Framework.pdf) to matrix completion problem

$$
\min \{ {\|Z\|}_{\ast}\} \\
s.t. Z_{\Omega} = X_{\Omega}
$$

We let ${Y}\in\mathbb{R}^{n\times n}$ be the the Lagrangian multiplier to the constraints $Z_{\Omega} = X_{\Omega}$
and Lagrange function is
$$
L(Z,Y) = {\|Z\|}_{\ast} - Y(Z_{\Omega} - X_{\Omega}).
$$

1. Producing $Y^{k+1}$ by
   $$Y^{k+1}=\arg\max_{Y} {L([2Z^k-Z^{k-1}],Y)-\frac{s}{2}\|Y-Y^k\|};$$
2. Producing $Z^{k+1}$ by
    $$Z^{k+1}=\arg\min_{Z} {L(Z,Y^{k+1}) + \frac{r}{2}\|Z-Z^k\|}.$$

<img title = "Netflix DataSet" src=https://pic3.zhimg.com/80/dc9a2b89742a05c3cd2f025105ba1c4a_hd.png width = 80% />

[Rahul Mazumder, Trevor Hastie, Robert Tibshirani](http://www.jmlr.org/papers/v11/mazumder10a.html) reformulate it as the following:

$$
\min f_{\lambda}(Z)=\frac{1}{2}{\|P_{\Omega}(Z-X)\|}_F^2 + \lambda {\|Z\|}_{\ast}
$$

where $X$ is the observed matrix, $P_{\Omega}$ is a projector and ${\|\cdot\|}_{\ast}$ is the nuclear norm of matrix.


* [A SINGULAR VALUE THRESHOLDING ALGORITHM FOR MATRIX COMPLETION](https://www.zhihu.com/question/47716840/answer/110843844)
* [Matrix and Tensor Decomposition in Recommender Systems](http://delab.csd.auth.gr/papers/RecSys2016s.pdf)
* [Low-Rank Matrix Recovery](http://www.princeton.edu/~yc5/ele538b_sparsity/lectures/matrix_recovery.pdf)
* [ECE 18-898G: Special Topics in Signal Processing: Sparsity, Structure, and Inference Low-rank matrix recovery via nonconvex optimization](https://users.ece.cmu.edu/~yuejiec/ece18898G_notes/ece18898g_nonconvex_lowrank_recovery.pdf)

<img title = "MMM" src=https://pic3.zhimg.com/80/771b16ac7e7aaeb50ffd8a8f5cf4e582_hd.png width = 80% />


* [Matrix Completion/Sensing as NonConvex Optimization Problem](http://sunju.org/research/nonconvex/)
* [Exact Matrix Completion via Convex Optimization](http://statweb.stanford.edu/~candes/papers/MatrixCompletion.pdf)
* [A SINGULAR VALUE THRESHOLDING ALGORITHM FOR MATRIX COMPLETION](http://statweb.stanford.edu/~candes/papers/SVT.pdf)
* [Customized PPA for convex optimization](http://maths.nju.edu.cn/~hebma/Talk/Unified_Framework.pdf)
* [Matrix Completion.m](http://www.convexoptimization.com/wikimization/index.php/Matrix_Completion.m)

### Maximum Margin Matrix Factorization

> A  novel approach to collaborative prediction is presented, using low-norm instead of low-rank factorizations. The approach is inspired by, and has strong connections to, large-margin linear discrimination. We show how to learn low-norm factorizations by solving a semi-definite program, and present generalization error bounds based on analyzing the Rademacher complexity of low-norm factorizations.

Consider the soft-margin learning, where we minimize a trade-off between the trace norm of $Z$ and its
hinge-loss relative to $X_O$:
$$
\min_{Z} { \| Z \| }_{\Omega} + c \sum_{(ui)\in O}\max(0, 1 - Z_{ui}X_{ui}).
$$

And it can be rewritten  as  a semi-definite optimization problem (SDP):
$$
\min_{A, B} \frac{1}{2}(tr(A)+tr(B))+c\sum_{(ui)\in O}\xi_{ui}, \\
s.t.  \, \begin{bmatrix} A & X \\ X^T & B \\ \end{bmatrix} \geq 0, Z_{ui}X_{ui}\geq 1- \xi_{ui},
\xi_{ui}>0 \,\forall ui\in O
$$
where $c$ is a trade-off constant.

- [Maximum Margin Matrix Factorization](https://ttic.uchicago.edu/~nati/Publications/MMMFnips04.pdf)
- [Fast Maximum Margin Matrix Factorization for Collaborative Prediction](https://ttic.uchicago.edu/~nati/Publications/RennieSrebroICML05.pdf)
- [Maximum Margin Matrix Factorization by Nathan Srebro](https://ttic.uchicago.edu/~nati/mmmf/)

This technique is also called **nonnegative matrix factorization**.

$\color{red}{Note:}$ The data sets we more frequently encounter in collaborative prediction problem are of `ordinal ratings` $X_{ij} \in \{1, 2, \dots, R\}$ such as $\{1, 2, 3, 4, 5\}$.
To relate the real-valued $Z_{ij}$ to the
discrete $X_{ij}$. we use $R − 1$ thresholds $\theta_{1}, \dots, \theta_{R-1}$.

### SVD and Beyond

If we have collected user ${u}$'s explicit evaluation score to the item ${i}$ ,  $R_{[u][i]}$, and all such data makes up a matrix $R=(R_{[u][i]})$ while the user $u$ cannot evaluate all the item so that the matrix is incomplete and missing much data.
**SVD** is to factorize the matrix into the multiplication of matrices so that
$$
\hat{R} = P^{T}Q.
$$

And we can predict the score $R_{[u][i]}$ via
$$
\hat{R}_{[u][i]} = \hat{r}_{u,i} = \left<P_u, Q_i\right> = \sum_f p_{u,f} q_{i,f}
$$

where $P_u, Q_i$ is the ${u}$-th column of ${P}$ and the ${i}$-th column of ${Q}$, respectively.
And we can define the cost function

$$
C(P,Q) = \sum_{(u,i):Observed}(r_{u,i}-\hat{r}_{u,i})^{2}=\sum_{(u,i):Observed}(r_{u,i}-\sum_f p_{u,f}q_{i,f})^{2}\\
\arg\min_{P_u, Q_i} C(P, Q)
$$

where $\lambda_u$ is always equal to $\lambda_i$.

Additionally, we can add regular term into the cost function to void over-fitting

$$
C(P,Q) = \sum_{(u,i):Observed}(r_{u,i}-\sum_f p_{u,f}q_{i,f})^{2}+\lambda_u\|P_u\|^2+\lambda_i\|Q_i\|^2.
$$

It is called [the regularized singular value decomposition](https://www.cs.uic.edu/~liub/KDD-cup-2007/proceedings/Regular-Paterek.pdf)  or **Regularized SVD**.


**Funk-SVD** considers the user's preferences or bias.
It predicts the scores by
$$
\hat{r}_{u,i} = \mu + b_u + b_i + \left< P_u, Q_i \right>
$$
where $\mu, b_u, b_i$ is biased mean, biased user, biased item, respectively.
And the cost function is defined as
$$
\min\sum_{(u,i): Observed}(r_{u,i} - \hat{r}_{u,i})^2 + \lambda (\|P_u\|^2+\|Q_i\|^2+\|b_i\|^2+\|b_u\|^2).
$$

**SVD ++** predicts the scores by

$$
\hat{r}_{u,i} = \mu + b_u + b_i + (P_u + |N(u)|^{-0.5}\sum_{i\in N(u)} y_i) Q_i^{T}
$$
where $y_j$ is the implicit  feedback of item ${j}$ and $N(u)$ is user ${u}$'s item set.
And it can decompose into 3 parts:

* $\mu + b_u + b_i$ is the base-line prediction;
* $\left<P_u, Q_i\right>$ is the SVD of rating matrix;
* $\left<|N(u)|^{-0.5}\sum_{i\in N(u)} y_i, Q_i\right>$ is the implicit feedback where $N(u)$ is user ${u}$'s item set, $y_j$ is the implicit feedback of item $j$.

We learn the values of involved parameters by minimizing the regularized squared error function.

* [Biased Regularized Incremental Simultaneous Matrix Factorization@orange3-recommender](https://orange3-recommendation.readthedocs.io/en/latest/scripting/rating.html)
* [SVD++@orange3-recommender](https://orange3-recommendation.readthedocs.io/en/latest/widgets/svdplusplus.html)
* [矩阵分解之SVD和SVD++](https://cloud.tencent.com/developer/article/1107364)
* [SVD++：推荐系统的基于矩阵分解的协同过滤算法的提高](https://www.bbsmax.com/A/KE5Q0M9ZJL/)
* https://zhuanlan.zhihu.com/p/42269534
* [使用SVD++进行协同过滤（算法原理部分主要引用自他人）](https://www.cnblogs.com/Xnice/p/4522671.html)
* [SVD++推荐系统](https://blog.csdn.net/turing365/article/details/80544594)

### Probabilistic Matrix Factorization

In linear regression, the least square methods is equivalent to maximum likelihood estimation of the error in standard normal distribution.  


|Regularized SVD|
|:-------------:|
|$C(P,Q) = \sum_{(u,i):Observed}(r_{(u,i)}-\sum_f p_{(u,f)} q_{(i,f)})^{2}+\lambda_u\|P_u\|^2+\lambda_i\|Q_i\|^2$|

|Probabilistic model|
|:-----------------:|
|$r_{u,i}\sim N(\sum_f p_{(u,f)} q_{(i,f)},\sigma^2), P_u\sim N(0,\sigma_u^2 I), Q_i\sim N(0,\sigma_i^2 I)$|

And $\sigma_u^2$ and $\sigma_i^2$ is related with the regular term $\lambda_u$ and $\lambda_u$.

So that we can reformulate the optimization problem as maximum likelihood estimation.

* [Latent Factor Models for Web Recommender Systems](http://www.ideal.ece.utexas.edu/seminar/LatentFactorModels.pdf)
* [Regression-based Latent Factor Models @CS 732 - Spring 2018 - Advanced Machine Learning by Zhi Wei](https://web.njit.edu/~zhiwei/CS732/papers/Regression-basedLatentFactorModels_KDD2009.pdf)
* [Probabilistic Matrix Factorization](https://papers.nips.cc/paper/3208-probabilistic-matrix-factorization.pdf)
* [Indexable Probabilistic Matrix Factorization for Maximum Inner Product Search](http://ulrichpaquet.com/Papers/fraccaro16aaai.pdf)

### Poisson Factorization

[We develop a Bayesian Poisson matrix factorization model for forming recommendations from sparse user behavior data.](https://arxiv.org/abs/1311.1704)
 These data are large user/item matrices where each user has provided feedback on only a small subset of items, either explicitly (e.g., through star ratings) or implicitly (e.g., through views or purchases). 
 In contrast to traditional matrix factorization approaches, Poisson factorization implicitly models each user's limited attention to consume items. 
 Moreover, because of the mathematical form of the Poisson likelihood, the model needs only to explicitly consider the observed entries in the matrix, leading to both scalable computation and good predictive performance. 
 We develop a variational inference algorithm for approximate posterior inference that scales up to massive data sets. 
 This is an efficient algorithm that iterates over the observed entries and adjusts an approximate posterior over the user/item representations. 
 We apply our method to large real-world user data containing users rating movies, users listening to songs, and users reading scientific papers. 
 In all these settings, Bayesian Poisson factorization outperforms state-of-the-art matrix factorization methods.

+ https://lkpy.readthedocs.io/en/stable/hpf.html
+ https://hpfrec.readthedocs.io/en/latest/
+ [Scalable Recommendation with Hierarchical Poisson Factorization](http://jakehofman.com/inprint/poisson_recs.pdf)
+ [Dynamic Poisson Factorization](https://dl.acm.org/citation.cfm?doid=2792838.2800174)
+ [Coupled Poisson Factorization Integrated with User/Item Metadata for Modeling Popular and Sparse Ratings in Scalable Recommendation](https://aaai.org/ocs/index.php/AAAI/AAAI18/paper/view/16637)
+ [Coupled Compound Poisson Factorization](https://arxiv.org/pdf/1701.02058.pdf)
+ https://github.com/mehmetbasbug/ccpf

### Collaborative Less-is-More Filtering(CliMF)

Sometimes, the information of user we could collect is implicit such as the clicking at some item.

In `CLiMF` [the model parameters are learned by directly maximizing the Mean Reciprocal Rank (MRR).](https://github.com/gamboviol/climf)

Its objective function is
$$
F(U,V)=\sum_{i=1}^{M}\sum_{j=1}^{N} Y_{ij} [\ln g(U_{i}^{T}V_{j})+\sum_{k=1}^{N}\ln (1 - Y_{ij} g(U_{i}^{T}V_{k}-U_{i}^{T}V_{j}))] \\-\frac{\lambda}{2}({\|U\|}^2 + {\|V\|}^2)
$$

where ${M, N}$ is the number of users and items, respectively. Additionally, $\lambda$ denotes the regularization coefficient and $Y_{ij}$ denotes the binary relevance score of item ${j}$ to user ${i}$, i.e., $Y_{ij} = 1$ if item ${j}$ is relevant to user ${j}$, 0 otherwise. The function $g$ is logistic function $g(x)=\frac{1}{1+\exp(-x)}$.
The vector $U_i$ denotes a d-dimensional latent factor vector for
user ${i}$, and $V_j$ a d-dimensional latent factor vector for item ${i}$.

|Numbers||Factors||Others||
|:------:|---|:---:|---|:---:|---|
|$M$|the number of users|$U_i$|latent factor vector for user ${i}$|$Y_{ij}$|binary relevance score|
|$N$|the number of items|$V_j$|latent factor vector for item ${i}$|$f$|logistic function|


We use stochastic gradient ascent to maximize the objective function.

* [Collaborative Less-is-More Filtering@orange3-recommendation](https://orange3-recommendation.readthedocs.io/en/latest/scripting/ranking.html)
* https://dl.acm.org/citation.cfm?id=2540581
* [Collaborative Less-is-More Filtering python Implementation](https://github.com/gamboviol/climf)
* [CLiMF: Collaborative Less-Is-More Filtering](https://www.ijcai.org/Proceedings/13/Papers/460.pdf)

###  Matrix Factorization for Implicit Feedback


Another advantage of collaborative filtering or matrix completion is that even the element of matrix is binary or implicit information such as

* [BPR: Bayesian Personalized Ranking from Implicit Feedback](https://arxiv.org/ftp/arxiv/papers/1205/1205.2618.pdf),
* [Applications of the conjugate gradient method for implicit feedback collaborative filtering](http://rs1.sze.hu/~gtakacs/download/recsys_2011_draft.pdf),
* [Intro to Implicit Matrix Factorization](https://www.ethanrosenthal.com/2016/10/19/implicit-mf-part-1/)
* [a curated list in github.com](https://github.com/benfred/implicit).

|Explicit and implicit feedback|
|:---:|
|![](https://www.msra.cn/wp-content/uploads/2018/06/knowledge-graph-in-recommendation-system-i-8.png)|

[**WRMF**](https://www.ethanrosenthal.com/2016/10/19/implicit-mf-part-1/) is simply a modification of this loss function:

$$
{C(P,Q)}_{WRMF} = \sum_{(u,i):Observed}c_{u,i}(I_{u,i} - \sum_f p_{u,f}q_{i,f})^{2} + \underbrace{\lambda_u\|P_u\|^2 + \lambda_i\|Q_i\|^2}_{\text{regularization terms}}.
$$

We make the assumption that if a user has interacted at all with an item, then $I_{u,i} = 1$. Otherwise, $I_{u,i} = 0$.
If we take $d_{u,i}$ to be the number of times a user ${u}$ has clicked on an item ${i}$ on a website, then
$$c_{u,i}=1+\alpha d_{u,i}$$
where $\alpha$ is some hyperparameter determined by cross validation.
The new  term in cost function $C=(c_{u,i})$ is called confidence matrix.

WRMF does not make the assumption that a user who has not interacted with an item does not like the item. WRMF does assume that that user has a negative preference towards that item, but we can choose how confident we are in that assumption through the confidence hyperparameter.

[Alternating least square](http://suo.im/4YCM5f) (**ALS**) can give an analytic solution to this optimization problem by setting the gradients equal to 0s.


* [Faster Implicit Matrix Factorization](https://www.benfrederickson.com/fast-implicit-matrix-factorization/)
* [CUDA Tutorial: Implicit Matrix Factorization on the GPU](https://www.benfrederickson.com/implicit-matrix-factorization-on-the-gpu/)
* [Intro to Implicit Matrix Factorization: Classic ALS with Sketchfab Models](https://www.ethanrosenthal.com/2016/10/19/implicit-mf-part-1/)
* [Logistic Matrix Factorization for Implicit Feedback Data](http://stanford.edu/~rezab/nips2014workshop/submits/logmat.pdf)



### Discrete Collaborative Filtering


- [Discrete Collaborative Filtering](https://www.comp.nus.edu.sg/~xiangnan/papers/sigir16-dcf-cm.pdf)
- https://arxiv.org/abs/2003.10719
- https://github.com/hanwangzhang/Discrete-Collaborative-Filtering
- [Discrete Content-aware Matrix Factorization](https://datasciences.org/publication/Lian-kdd17.pdf)
- [Discrete Factorization Machines for Fast Feature-based Recommendation](https://www.ijcai.org/Proceedings/2018/0479.pdf)
- [Binomial Matrix Factorization for Discrete Collaborative Filtering](https://ieeexplore.ieee.org/document/5360354)
- [Discrete Matrix Factorization and Extension for Fast Item Recommendation](http://staff.ustc.edu.cn/~liandefu/paper/dmf_fast.pdf)
- [Discrete Ranking-based Matrix Factorization with Self-Paced Learning](https://bigdata.ustc.edu.cn/paper_pdf/2018/Yan-Zhang-KDD2018.pdf)
- https://github.com/yixianqianzy/drmf-spl

### Recommendation with Implicit Information

* [Collaborative Filtering for Implicit Feedback Datasets](http://yifanhu.net/PUB/cf.pdf)
* [A Generic Framework for Learning Explicit and Implicit User-Item Couplings in Recommendation](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=8815704)
* [Recommending Based on Implicit Feedback](https://www.researchgate.net/publication/324895157_Recommending_Based_on_Implicit_Feedback)
* [Fast Collaborative Filtering from Implicit Feedback with Provable Guarantees](http://proceedings.mlr.press/v63/Dasgupta79.pdf)
* http://nicolas-hug.com/blog/matrix_facto_1
* http://nicolas-hug.com/blog/matrix_facto_2
* http://nicolas-hug.com/blog/matrix_facto_3
* [A recommender systems development and evaluation package by Mendeley](https://github.com/Mendeley/mrec)
* https://mendeley.github.io/mrec/
* [Fast Python Collaborative Filtering for Implicit Feedback Datasets](https://github.com/benfred/implicit)
* [Alternating Least Squares Method for Collaborative Filtering](https://bugra.github.io/work/notes/2014-04-19/alternating-least-squares-method-for-collaborative-filtering/)
* [Implicit Feedback and Collaborative Filtering](http://datamusing.info/blog/2015/01/07/implicit-feedback-and-collaborative-filtering/)
- [BPR: Bayesian Personalized Ranking from Implicit Feedback](https://arxiv.org/ftp/arxiv/papers/1205/1205.2618.pdf)
- [Collaborative Filtering for Implicit Feedback Datasets](http://yifanhu.net/PUB/cf.pdf)
- [Improving Pairwise Learning for Item Recommendation from Implicit Feedback](http://webia.lip6.fr/~gallinar/gallinari/uploads/Teaching/WSDM2014-rendle.pdf)
- [A-RecSys : a Tensorflow Toolkit for Implicit Recommendation Tasks](https://github.com/skywaLKer518/A-Recsys)
- http://lyst.github.io/lightfm/docs/examples/warp_loss.html


***

* [Matrix factorization for recommender system@Wikiwand](https://www.wikiwand.com/en/Matrix_factorization_(recommender_systems)})
* http://www.cnblogs.com/DjangoBlog/archive/2014/06/05/3770374.html
* [Learning to Rank Sketchfab Models with LightFM](https://www.ethanrosenthal.com/2016/11/07/implicit-mf-part-2/)
* [Finding Similar Music using Matrix Factorization](https://www.benfrederickson.com/matrix-factorization/)
* [Top-N Recommendations from Implicit Feedback Leveraging Linked Open Data ?](https://core.ac.uk/display/23873231)

### Inductive Matrix Completion

One possible improvement of this cost function is that we may design more appropriate loss function other than the squared  error function.

![utexas.edu](http://bigdata.ices.utexas.edu/wp-content/uploads/2015/09/IMC.png)

**Inductive Matrix Completion (IMC)** is an algorithm for recommender systems with side-information of users and items. The IMC formulation incorporates features associated with rows (users) and columns (items) in matrix completion, so that it enables predictions for users or items that were not seen during training, and for which only features are known but no dyadic information (such as ratings or linkages).

IMC assumes that the associations matrix is generated by applying feature vectors associated with
its rows as well as columns to a low-rank matrix ${Z}$.
The goal is to recover ${Z}$ using observations from ${P}$.

The  inputs $x_i, y_j$ are feature vectors.
The entry $P_{(i, j)}$ of the matrix is modeled as $P_{(i, j)}=x_i^T Z  y_j$ and ${Z}$ is to recover in the form of $Z=WH^T$.

$$
\min \sum_{(i,j)\in \Omega}\ell(P_{(i,j)}, x_i^T W H^T y_j) + \frac{\lambda}{2}(\| W \|^2+\| H \|^2)
$$
The loss function $\ell$ penalizes the deviation of estimated entries from the observations.
And $\ell$ is diverse such as the squared error $\ell(a,b)=(a-b)^2$, the logistic error $\ell(a,b) = \log(1 + \exp(-ab))$.

* [Inductive Matrix Completion for Recommender Systems with Side-Information](http://bigdata.ices.utexas.edu/software/inductive-matrix-completion/)
* [Inductive Matrix Completion for Predicting Gene-Diseasev Associations](http://www.cs.utexas.edu/users/inderjit/public_papers/imc_bioinformatics14.pdf)

**More on Matrix Factorization**

- [The Advanced Matrix Factorization Jungle](https://sites.google.com/site/igorcarron2/matrixfactorizations)
- [Non-negative Matrix Factorizations](http://www.ams.org/publicoutreach/feature-column/fc-2019-03)
- http://people.eecs.berkeley.edu/~yima/
- [New tools for recovering low-rank matrices from incomplete or corrupted observations by Yi Ma@UCB](http://people.eecs.berkeley.edu/~yima/matrix-rank/home.html)
- [DiFacto — Distributed Factorization Machines](https://www.cs.cmu.edu/~muli/file/difacto.pdf)
- [Learning with Nonnegative Matrix Factorizations](https://sinews.siam.org/Details-Page/learning-with-nonnegative-matrix-factorizations)
- [Nonconvex Optimization Meets Low-Rank Matrix Factorization: An Overview](http://www.princeton.edu/~yc5/publications/NcxOverview_Arxiv.pdf)
- [Taming Nonconvexity in Information Science, tutorial at ITW 2018.](https://www.princeton.edu/~yc5/slides/itw2018_tutorial.pdf)
- [Nonnegative Matrix Factorization by Optimization on the Stiefel Manifold with SVD Initialization](https://user.eng.umd.edu/~smiran/Allerton16.pdf)
- [Matrix and Tensor Completion Algorithms](http://swoh.web.engr.illinois.edu/software/optspace_v1/papers.html)
- [Parallel matrix factorization for low-rank tensor completion](https://www.math.ucla.edu/~wotaoyin/papers/tmac_tensor_recovery.html)
- https://canyilu.github.io/publications/
- http://people.eecs.berkeley.edu/~yima/matrix-rank/references.html
- [A Library of ADMM for Sparse and Low-rank Optimization](https://github.com/canyilu/LibADMM)
- https://arxiv.org/abs/1603.06038

### Beyond Matrix Completion

There are 2 common techniques in recommender systems:

1.  The goal of `matrix factorization` techniques in RS is to determine a low-rank approximation of the user-item rating matrix by decomposing it into a product of (user and item) matrices of lower dimensionality (latent factors).
2.  The idea of `ensemble methods` is to combine multiple alternative machine learning models to obtain more accurate predictions.

There are 2 disadvantages of Matrix Completion:
1. $Postdiction \not= prediction$
   - Need initial post data
   - Predict poorly on a random set of items the user has not rated.
   - Repeated recommendation of purchased items
   - The evaluation method of Netflix Prize is misleading. RMSE(regression) vs Rank-based measures(sorting)
2. Quality factors beyond accuracy
   - Introduce why we use the quality factors:
   - Novelty, diversity and unexpectedness(How to recommend new things to users exactly)
   - Depend on context and different problems
   - Interact with users: conversational recommender systems
   - Example of context and interaction:To Be Continued: Helping you find shows to continue watching on Netflix(search the “context”)
   - Manipulation resistance
   - Recommendation is optimal to sellers not users - transparency and explanation strategy (nearly a moral problem).


**From Algorithms to Systems**

Beyond the computer science perspective.


Putting the user back in the loop.


Toward a more comprehensive characterization of the recommendation task.

***

Collaborative filtering has become a key tool in recommender systems. The Netflix competition was instrumental in this context to further development of scalable tools. 
At its heart lies the minimization of the Root Mean Squares Error (RMSE) which helps to decide upon the quality of a recommender system. Moreover, minimizing the RMSE comes with desirable guarantees of statistical consistency. 
[In this talk I make the case that RMSE minimization is a poor choice for a number of reasons: firstly, review scores are anything but Gaussian distributed, often exhibiting asymmetry and bimodality in their scores. Secondly, in a retrieval setting accuracy matters primarily for the top rated items. Finally, such ratings are highly context dependent and should only be considered in interaction with a user. I will show how this can be accomplished easily by relatively minor changes to existing systems.](http://www.ueo-workshop.com/invited-speakers/)


- https://www.researchgate.net/project/Proactive-Recommendation-Delivery
- [Beyond Matrix Completion of the traditional Recommender System](https://www.ijert.org/beyond-matrix-completion-of-the-traditional-recommender-system)
- [Recommender systems---: Recommender systems---: beyond matrix completion](https://www.researchgate.net/publication/309600906_Recommender_systems---_beyond_matrix_completion)
- [Notes of "Recommender Systems - Beyond Matrix Completion"](https://typewind.github.io/2017/04/05/rsbmc-notes/)
- [Toward the Next Generation of Recommender Systems: A Survey of the State-of-the-Art and Possible Extensions](http://people.stern.nyu.edu/atuzhili/pdf/TKDE-Paper-as-Printed.pdf)

*****************

## Factorization Machines(FM)

The matrix completion used in recommender system are linear combination of some features such as regularized SVD and they only take the user-user interaction and item-item similarity.
`Factorization Machines(FM)` is inspired from previous factorization models.
It represents each feature an embedding vector, and models the second-order feature interactions:
$$
\hat{y}
= w_0 + \sum_{i=1}^{n} w_i x_i+\sum_{i=1}^{n-1}\sum_{j=i+1}^{n}\left<v_i, v_j\right> x_i x_j\\
= \underbrace{w_0  + \left<w, x\right>}_{\text{First-order: Linear Regression}} + \underbrace{\sum_{i=1}^{n-1}\sum_{j=i+1}^{n}\left<v_i, v_j\right> x_i x_j}_{\text{Second-order: pair-wise interactions between features}}
$$

where the model parameters that have to be estimated are
$$
w_0 \in \mathbb{R}, w\in\mathbb{R}^n, V\in\mathbb{R}^{n\times k}.
$$

And $\left<\cdot,\cdot\right>$ is the dot (inner) product of two vectors so that $\left<v_i, v_j\right>=\sum_{f=1}^{k}v_{i,f} \cdot v_{j,f}$.
A row $v_i$ within ${V}$ describes the ${i}$-th latent variable with ${k}$ factors for $x_i$.

And the linear regression $w_0 + \sum_{i=1}^{n} w_i x_i$ is called `the first order part`; the pair-wise interactions between features
$\sum_{i=1}^{n}\sum_{j=i+1}^{n}\left<v_i, v_j\right> x_i x_j$ is called the `second order part`.

However, why we call it `factorization machine`? Where is the _factorization_?
If ${[W]}_{ij}=w_{ij}= \left<v_i, v_j\right>$, $W=V V^T$, 
the second order part $\sum_{i=1}^{n-1}\sum_{j=i+1}^{n}\left<v_i, v_j\right> x_i x_j$ is equivalent to the following relationship:
$$\sum_{i=1}^{n-1}\sum_{j=i+1}^{n}\left<v_i, v_j\right> x_i x_j=\frac{1}{2}x^TWx=\frac{1}{2}\sum_{i,j}w_{ij}x_i x_j$$
thus it is to factorize the matrix $W$ into the product of the $V$ and $V^T$.


In order to reduce the computation complexity, the second order part $\sum_{i=1}^{n-1}\sum_{j=i+1}^{n}\left<v_i, v_j\right> x_i x_j$ is rewritten in the following form
$$\frac{1}{2}\sum_{l=1}^{k}\{[\sum_{i=1}^{n}(v_{il}x_i))]^2-\sum_{i=1}^{n}(v_{il}x_i)^2\}.$$
This show that we can use less resource to compute the model.

The next step is to find the optimal parameters of the model using the numerical optimization methods.
Optimality of model parameters is usually defined with a loss function $\ell$ where the task is to minimize the sum of losses over the observed data $S=\{(x_i,y_i)\}_{i=1}^N$.
$$\arg\min_{\Theta}\sum_{(x_i,y_i)\in  S}\ell(\hat{y}(x_i), x_i)$$

<img src="https://img-blog.csdn.net/20150506130413304" width="80%"/>

* [第09章：深入浅出ML之Factorization家族](http://www.52caml.com/head_first_ml/ml-chapter9-factorization-family/)
* [FM算法（Factorization Machine）](https://blog.csdn.net/g11d111/article/details/77430095)
* [分解机(Factorization Machines)推荐算法原理 by 刘建平Pinard](https://www.cnblogs.com/pinard/p/6370127.html)
* [Factorization Machines for Recommendation Systems](https://getstream.io/blog/factorization-recommendation-systems/)
* http://www.libfm.org/
* https://github.com/ibayer/fastFM
* https://www.d2l.ai/chapter_recommender-systems/fm.html


[Factorization Machines]: https://www.csie.ntu.edu.tw/~b97053/paper/Rendle2010FM.pdf

FMs model all interactions between variables using factorized parameters. 
Thus they are able to estimate interactions even in problems with huge sparsity (like recommender systems) where SVMs fail. 
It is shown that the model equation of FMs can be calculated in linear time and thus FMs can be optimized directly.

In [Factorization Machines], the factorization machine models all nested variable interactions (comparable to a polynomial kernel in
SVM), but uses a factorized parametrization instead of a
dense parametrization like in SVMs.

And [sparse factorization machines]((http://jiayuzhou.github.io/papers/jxuSDM16b.pdf)) enforce group sparsity to remove the effect of a feature of user or a feature of item.

> Polynomial networks and factorization machines are two recently-proposed models that can efficiently use feature interactions in classification and regression tasks. In this paper, we revisit both models from a unified perspective. Based on this new view, we study the properties of both models and propose new efficient training algorithms. Key to our approach is to cast parameter learning as a low-rank symmetric tensor estimation problem, which we solve by multi-convex optimization. We demonstrate our approach on regression and recommender system tasks.

* https://arxiv.org/abs/1607.08810
* [Polynomial Networks and Factorization Machines: New Insights and Efficient Training Algorithms](http://mblondel.org/talks/mblondel-erato-2016-08.pdf)
* https://www.csie.ntu.edu.tw/~cjlin/talks/sdm2015.pdf
* https://www.ismll.uni-hildesheim.de/pub/pdfs/RendleFreudenthaler2010-FPMC.pdf
* https://mlconf.com/speakers/steffen-rendle/
* http://www.cs.cmu.edu/~wcohen/10-605/2015-guest-lecture/FM.pdf
* [Synergies that Matter: Efficient Interaction Selection via Sparse Factorization Machine](http://jiayuzhou.github.io/papers/jxuSDM16b.pdf)
* http://csse.szu.edu.cn/staff/panwk/recommendation/Sequence/FPMC.pdf

### Field-aware Factorization Machine(FFM)

In FMs, every feature has only one latent vector to learn the latent effect with any other features.
In FFMs, each feature has several latent vectors. Depending on the field of other features, one of them is used to do the inner product.
Mathematically,
$$
\hat{y}=\sum_{j_1=1}^{n}\sum_{j_2=i+1}^{n}\left<v_{j_1,f_2}, v_{j_2,f_1}\right> x_{j_1} x_{j_2}
$$
where $f_1$ and $f_2$ are respectively the fields of $j_1$ and $j_2$.

* https://www.csie.ntu.edu.tw/~cjlin/
* https://github.com/ycjuan/libffm
* [Yuchin Juan at ACEMAP](https://www.acemap.info/author/page?AuthorID=7E61F31B)
* [Field-aware Factorization Machines for CTR Prediction](https://www.csie.ntu.edu.tw/~cjlin/papers/ffm.pdf)
* https://blog.csdn.net/mmc2015/article/details/51760681
* https://www.aaai.org/ojs/index.php/AAAI/article/view/4267/4145
* https://ailab.criteo.com/ctr-prediction-linear-model-field-aware-factorization-machines/

### Convex Factorization Machines

> Factorization machines are a generic framework which allows to mimic many factorization models simply by feature engineering. In this way, they combine the high predictive accuracy of factorization models with the flexibility of feature engineering. 
> Unfortunately, factorization machines involve a non-convex optimization problem and are thus subject to bad local minima. 
> [In this paper](https://www.researchgate.net/publication/300544530_Convex_Factorization_Machines), we propose a convex formulation of factorization machines based on the nuclear norm.
>  Our formulation imposes fewer restrictions on the learned model and is thus more general than the original formulation. 
> To solve the corresponding optimization problem, we present an efficient globally-convergent two-block coordinate descent algorithm. 
> Empirically, we demonstrate that our approach achieves comparable or better predictive accuracy than the original factorization machines on 4 recommendation tasks and scales to datasets with 10 million samples.

<img src="https://maidousj.github.io/assets/images/2020-06-02-Convex-FM/image-20200629175631089.png" width="70%"/>

And the objective function to optimize is the regularized empirical loss function or structured empirical loss function:
$$\sum_{i}\ell(\hat{y}(x_i), y_i)+\frac{\alpha}{2}\|w\|_2^2+\beta\|Z\|_{\ast}$$
where $\|Z\|_{\ast}$ is the nuclear norm of the matrix $Z$.


- [Online Compact Convexified Factorization Machine](https://arxiv.org/abs/1802.01379)
- http://mblondel.org/talks/mblondel-cambridge-2015-09.pdf
- https://bigdata.nii.ac.jp/eratokansyasai4/wp-content/uploads/2017/09/929e8b7e82a0043cc993d328bfbb400e.pdf
- https://maidousj.github.io/2020/06/02/Convex-FM/
- http://www.yichang-cs.com/yahoo/KDD17_FM.pdf
- https://arxiv.org/abs/1507.01073
- http://talks.cam.ac.uk/talk/index/60262

### Higher-Order Factorization Machines

In [Factorization Machines], the d-way factorization machines are proposed in the following form:
$$\hat{y}=w_0+\left<x, w\right>+\sum_{m=2}^d\sum_{n_1=1}^n\cdots\sum_{n_m}^n(\prod_{j=1}^{m}x_j)(\sum_{f}^k\prod_{j=1}^{m}v_{m_j,f}^{(m)}).$$
Unfortunately, despite increasing interest in FMs, there exists to date no efficient training algorithm for higher-order FMs (HOFMs).

The FM can be considered as the second order polynomial regression with lower computation complexity.
And FM is also considered as the ANOVA kernel regression of degree 2.
So we can generalize the FM into `Higher-Order Factorization Machines` (HOFM) based on ANOVA kernel.

- https://people.eecs.berkeley.edu/~jordan/kernels/0521813972c09_p291-326.pdf
- http://mblondel.org/talks/mblondel-stair-2016-09.pdf
- https://rdrr.io/cran/FactoRizationMachines/man/010-FactoRizationMachines.html
- https://papers.nips.cc/paper/6144-higher-order-factorization-machines.pdf
- http://mblondel.org/talks/mblondel-stair-2016-09.pdf
- https://ideas.repec.org/p/zbw/iwqwdp/132017.html
- http://www.kecl.ntt.co.jp/as/members/ueda/
- https://papers.nips.cc/paper/6144-higher-order-factorization-machines.pdf




## Deep Learning for Recommender System

Deep learning is powerful in processing visual and text information so that it helps to find the interests of users such as
[Deep Interest Network](http://www.cnblogs.com/rongyux/p/8026323.html), [xDeepFM](https://www.jianshu.com/p/b4128bc79df0)  and more.

Deep learning models for recommender system may come from the restricted Boltzman machine.
And deep learning models are powerful information extractors.
Deep learning is really popular in recommender system such as [spotlight](https://github.com/maciejkula/spotlight).

What is the role deep learning plays in recommender system? At one hand, deep learning helps to match the user and items based on the history of their interactions such as `deep matching` and `deep collaborative learning`. 
In mathematics, it is a function that evaluates the how likely the user would interact with the items in some context: $f(X_U, X_I, X_C)$ where $X_U, X_I, X_C$ is the features of user, item and context, respectively.
At another hand, deep learning leads a role as one representation methods to embedded high dimensional sparse data into semantics space.

* [A review on deep learning for recommender systems: challenges and remedies](https://daiwk.github.io/assets/Batmaz2018_Article_AReviewOnDeepLearningForRecomm.pdf)
* [Deep Learning Recommendation Model for Personalization and Recommendation Systems](https://github.com/facebookresearch/dlrm)
* http://tw991.github.io/
* https://dlp-kdd.github.io/
* https://recsys.acm.org/recsys17/workshops/
* https://recsys.acm.org/recsys17/dlrs/
* https://dl.acm.org/citation.cfm?id=3125486
* [The 1st International Workshop on Deep Learning Practice for High-Dimensional Sparse Data with KDD 2019 (DLP-KDD 2019）](https://dlp-kdd.github.io/)
* https://recsys.acm.org/recsys19/session-3/
* http://bdsc.lab.uic.edu/docs/survey-critique-deep.pdf
- [ ] [Deep Learning Meets Recommendation Systems](https://nycdatascience.com/blog/student-works/deep-learning-meets-recommendation-systems/)
- [ ] [Using Keras' Pretrained Neural Networks for Visual Similarity Recommendations](https://www.ethanrosenthal.com/2016/12/05/recasketch-keras/)
- [ ] [Recommending music on Spotify with deep learning](http://benanne.github.io/2014/08/05/spotify-cnns.html)
- [ ] https://bdsc.lab.uic.edu/docs/survey-critique-deep.pdf
- [ ] [Deep Learning based Recommender System](https://fardapaper.ir/mohavaha/uploads/2019/09/Fardapaper-Deep-Learning-based-Recommender-System-A-Survey-and-New-Perspectives.pdf)
- [ ] http://www.wikicfp.com/cfp/servlet/event.showcfp?eventid=101417&copyownerid=158713
- [ ] https://786121244.github.io/NeuRec-Workshop/

### Restricted Boltzmann Machines for Collaborative Filtering

Let ${V}$ be a $K\times m$ observed binary indicator matrix with $v_i^k = 1$ if the user rated item ${i}$ as ${k}$ and ${0}$ otherwise.
We also let $h_j$, $j = 1, \dots, F,$ be the binary values of hidden (latent) variables, that can be thought of as representing
stochastic binary features that have different values for different users.

We use a conditional multinomial distribution (a “softmax”) for modeling each column of the observed
"visible" binary rating matrix ${V}$ and a conditional
Bernoulli distribution for modeling "hidden" user features *${h}$*:
$$
p(v_i^k = 1 \mid h) = \frac{\exp(b_i^k + \sum_{j=1}^{F} h_j W_{i,j}^{k})}{\sum_{l=1}^{K}\exp( b_i^k + \sum_{j=1}^{F} h_j W_{i, j}^{l})} \\
p( h_j = 1 \mid V) = \sigma(b_j + \sum_{i=1}^{m}\sum_{k=1}^{K} v_i^k W_{i,j}^k)
$$
where $\sigma(x) = \frac{1}{1 + exp(-x)}$ is the logistic function, $W_{i,j}^{k}$ is is a symmetric interaction parameter between feature
${j}$ and rating ${k}$ of item ${i}$, $b_i^k$ is the bias of rating ${k}$ for item ${i}$, and $b_j$ is the bias of feature $j$.

The marginal distribution over the visible ratings ${V}$ is
$$
p(V) = \sum_{h}\frac{\exp(-E(V,h))}{\sum_{V^{\prime},h^{\prime}} \exp(-E(V^{\prime},h^{\prime}))}
$$
with an "energy" term given by:

$$
E(V,h) = -\sum_{i=1}^{m}\sum_{j=1}^{F}\sum_{k=1}^{K}W_{i,j}^{k} h_j v_i^k - \sum_{i=1}^{m}\sum_{k=1}^{K} v_i^k b_i^k -\sum_{j=1}^{F} h_j b_j.
$$
The items with missing ratings do not make any contribution to the energy function

The parameter updates required to perform gradient ascent in the log-likelihood  over the visible ratings ${V}$ can be obtained
$$
\Delta W_{i,j}^{k} = \epsilon \frac{\partial\log(p(V))}{\partial W_{i,j}^{k}}
$$
where $\epsilon$ is the learning rate.
The authors put a `Contrastive Divergence` to approximate the gradient.

We can also model “hidden” user features $h$ as Gaussian latent variables:
$$
p(v_i^k = 1 | h) = \frac{\exp(b_i^k+\sum_{j=1}^{F}h_j W_{i,j}^{k})}{\sum_{l=1}^{K}\exp(b_i^k+\sum_{j=1}^{F}h_j W_{i,j}^{l})} \\
p( h_j = 1 | V) = \frac{1}{\sqrt{2\pi}\sigma_j} \exp(\frac{(h - b_j -\sigma_j \sum_{i=1}^{m}\sum_{k=1}^{K} v_i^k W_{i,j}^k)^2}{2\sigma_j^2})
$$
where $\sigma_j^2$ is the variance of the hidden unit ${j}$.

<img title = "RBM " src ="https://raw.githubusercontent.com/adityashrm21/adityashrm21.github.io/master/_posts/imgs/book_reco/rbm.png" width="30%" />

* https://www.cnblogs.com/pinard/p/6530523.html
* https://www.cnblogs.com/kemaswill/p/3269138.html
* [Restricted Boltzmann Machines for Collaborative Filtering](https://www.cs.toronto.edu/~rsalakhu/papers/rbmcf.pdf)
* [Building a Book Recommender System using Restricted Boltzmann Machines](https://adityashrm21.github.io/Book-Recommender-System-RBM/)
* [On Contrastive Divergence Learning](http://www.cs.toronto.edu/~fritz/absps/cdmiguel.pdf)
* http://deeplearning.net/tutorial/rbm.html
* [RBM notebook form Microsoft](https://github.com/Microsoft/Recommenders/blob/master/notebooks/00_quick_start/rbm_movielens.ipynb)

### AutoRec for Collaborative Filtering

[AutoRec](http://users.cecs.anu.edu.au/~akmenon/papers/autorec/autorec-paper.pdf) is a novel `autoencoder` framework for collaborative filtering (CF). Empirically, AutoRec’s
compact and efficiently trainable model outperforms state-of-the-art CF techniques (biased matrix factorization, RBMCF and LLORMA) on the Movielens and Netflix datasets.

Formally, the objective function for the Item-based AutoRec (I-AutoRec) model is, for regularization strength $\lambda > 0$,

$$\min_{\theta}\sum_{i=1}^{n} {\|r^{i}-h(r^{i}|\theta)\|}_{O}^2 +\frac{1}{2}({\|W\|}_F^{2}+ {\|V\|}_F^{2})$$

where $\{r^{i}\in\mathbb{R}^{d}, i=1,2,\dots,n\}$ is partially observed vector and ${\| \cdot \|}_{o}^2$ means that we only consider the contribution of observed ratings.
The function $h(r|\theta)$ is  the reconstruction of input $r\in\mathbb{R}^{d}$:

$$h(r|\theta) = f(W\cdot g(Vr+\mu)+b)$$

for for activation functions $f, g$ as described in  dimension reduction. Here $\theta = \{W,V,r,b\}$.

* [AutoRec: Autoencoders Meet Collaborative Filtering》WWW2015 阅读笔记](https://blog.csdn.net/studyless/article/details/70880829)
* [AutoRec: Autoencoders Meet Collaborative Filtering](http://users.cecs.anu.edu.au/~akmenon/papers/autorec/autorec-paper.pdf)


### Deep crossing



<img src="http://www.arvinzyy.cn/2017/10/15/Deep-Crossing-Web-Scale-Modeling-without-Manually-Crafted-Combinatorial-Features/1.png" width="70%"/>

- https://zhuanlan.zhihu.com/p/91057914
- https://www.microsoft.com/en-us/research/people/xingx/
- https://www.pianshen.com/article/31571380403/
- https://www.kdd.org/kdd2016/papers/files/adf0975-shanA.pdf


### Neural collaborative filtering

>  This model leverages the flexibility and `non-linearity of neural networks to replace dot products of matrix factorization`, aiming at enhancing the model expressiveness. 
> In specific, this model is structured with two subnetworks including generalized matrix factorization (GMF) and MLP and models the interactions from two pathways instead of simple inner products. 
> The outputs of these two networks are concatenated for the final prediction scores calculation. 
> Unlike the rating prediction task in AutoRec, this model generates a ranked recommendation list to each user based on the implicit feedback.
>  [We will use the personalized ranking loss introduced in the last section to train this model.](https://d2l.ai/chapter_recommender-systems/neumf.html)

<img src="https://d2l.ai/_images/rec-neumf.svg" width="80%"/>

- [Neural Collaborative Filtering](https://www.comp.nus.edu.sg/~xiangnan/papers/ncf.pdf)
- https://d2l.ai/chapter_recommender-systems/neumf.html
- https://github.com/hexiangnan/neural_collaborative_filtering
- [Neural Collaborative Filtering vs. Matrix Factorization Revisited](https://arxiv.org/abs/2005.09683)
- [Outer Product-based Neural Collaborative Filtering](https://www.ijcai.org/Proceedings/2018/0308.pdf)
  
### Collaborative deep learning for RecSys

[Collaborative filtering (CF) is a successful approach commonly used by many recommender systems. Conventional CF-based methods use the ratings given to items by users as the sole source of information for learning to make recommendation. However, the ratings are often very sparse in many applications, causing CF-based methods to degrade significantly in their recommendation performance. To address this sparsity problem, auxiliary information such as item content information may be utilized. Collaborative topic regression (CTR) is an appealing recent method taking this approach which tightly couples the two components that learn from two different sources of information. Nevertheless, the latent representation learned by CTR may not be very effective when the auxiliary information is very sparse. To address this problem, we generalize recently advances in deep learning from i.i.d. input to non-i.i.d. (CF-based) input and propose in this paper a hierarchical Bayesian model called collaborative deep learning (CDL), which jointly performs deep representation learning for the content information and collaborative filtering for the ratings (feedback) matrix. Extensive experiments on three real-world datasets from different domains show that CDL can significantly advance the state of the art.](http://www.wanghao.in/CDL.htm)

Given part of the ratings in ${R}$ and the content information $X_c$, the problem is to predict the other ratings in ${R}$,
where row ${j}$ of the content information matrix $X_c$ is the bag-of-words vector $Xc;j{\ast}$ for item ${j}$ based on a vocabulary of size ${S}$.

`Stacked denoising autoencoders(SDAE)` is a feedforward neural network for learning
representations (encoding) of the input data by learning to predict the clean input itself in the output.
Using the Bayesian SDAE as a component, the generative
process of CDL is defined as follows:
1. For each layer ${l}$ of the SDAE network,
    * For each column ${n}$ of the weight matrix $W_l$, draw
    $$W_l;{\ast}n \sim \mathcal{N}(0,\lambda_w^{-1} I_{K_l}).$$
    * Draw the bias vector
    $$b_l \sim \mathcal{N}(0,\lambda_w^{-1} I_{K_l}).$$
    * For each row ${j}$ of $X_l$, draw
    $$X_{l;j\ast}\sim \mathcal{N}(\sigma(X_{l-1;j\ast}W_l b_l), \lambda_s^{-1} I_{K_l}).$$

2. For each item ${j}$,
      * Draw a clean input
        $$X_{c;j\ast}\sim \mathcal{N}(X_{L, j\ast}, \lambda_n^{-1} I_{K_l}).$$
      * Draw a latent item offset vector $\epsilon_j \sim \mathcal{N}(0, \lambda_v^{-1} I_{K_l})$ and then set the latent item vector to be:
        $$v_j=\epsilon_j+X^T_{\frac{L}{2}, j\ast}.$$
3. Draw a latent user vector for each user ${i}$:
     $$u_i \sim \mathcal{N}(0, \lambda_u^{-1} I_{K_l}).$$

4. Draw a rating $R_{ij}$ for each user-item pair $(i; j)$:
  $$R_{ij}\sim \mathcal{N}(u_i^T v_j, C_{ij}^{-1}).$$

Here $\lambda_w, \lambda_s, \lambda_n, \lambda_u$and $\lambda_v$ are hyperparameters and $C_{ij}$ is
a confidence parameter similar to that for CTR ($C_{ij} = a$ if $R_{ij} = 1$ and $C_{ij} = b$ otherwise).

And joint log-likelihood of these parameters is
$$L=-\frac{\lambda_u}{2}\sum_{i} {\|u_i\|}_2^2-\frac{\lambda_w}{2}\sum_{l} [{\|W_l\|}_F+{\|b_l\|}_2^2]\\
-\frac{\lambda_v}{2}\sum_{j} {\|v_j - X^T_{\frac{L}{2},j\ast}\|}_2^2-\frac{\lambda_n}{2}\sum_{l} {\|X_{c;j\ast}-X_{L;j\ast}\|}_2^2 \\
-\frac{\lambda_s}{2}\sum_{l}\sum_{j} {\|\sigma(X_{l-1;j\ast}W_l b_l)-X_{l;j}\|}_2^2 -\sum_{ij} {\|R_{ij}-u_i^Tv_j\|}_2^2
$$

It is not easy to prove that it converges.


* http://www.winsty.net/
* http://www.wanghao.in/
* https://www.cse.ust.hk/~dyyeung/
* [Collaborative Deep Learning for Recommender Systems](http://www.wanghao.in/CDL.htm)
* [Deep Learning for Recommender Systems](https://www.inovex.de/fileadmin/files/Vortraege/2017/deep-learning-for-recommender-systems-pycon-10-2017.pdf)
* https://github.com/robi56/Deep-Learning-for-Recommendation-Systems
* [推荐系统中基于深度学习的混合协同过滤模型](http://www.10tiao.com/html/236/201701/2650688117/2.html)
* [CoupledCF: Learning Explicit and Implicit User-item Couplings in Recommendation for Deep Collaborative Filtering](http://203.170.84.89/~idawis33/DataScienceLab/publication/nonIID-RS-final.pdf)

### Wide & Deep Model

The output of this model is
$$
P(Y=1|x) = \sigma(W_{wide}^T[x,\phi(x)] + W_{deep}^T \alpha^{(lf)}+b)
$$
where the `wide` part deal with the categorical features such as user demographics and the `deep` part deal with continuous features.


<img src=https://upload-images.jianshu.io/upload_images/1500965-13fa11d119bb20b7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1000/format/webp width=70%/>
<img src=http://kubicode.me/img/Take-about-CTR-With-Deep-Learning/fnn_pnn_wdl.png width=70%/>

* https://arxiv.org/pdf/1606.07792.pdf
* [Wide & Deep Learning: Better Together with TensorFlow, Wednesday, June 29, 2016](https://ai.googleblog.com/2016/06/wide-deep-learning-better-together-with.html)
* [Wide & Deep](https://www.jianshu.com/p/dbaf2d9d8c94)
* https://www.sohu.com/a/190148302_115128

<img src = http://kubicode.me/img/Take-about-CTR-With-Deep-Learning/dcn_arch.png width=60%/>

--------------

### Deep FM

`DeepFM` ensembles FM and DNN and to learn both second order and higher-order feature interactions:
$$\hat{y}=\sigma(y_{FM} + y_{DNN})$$
where $\sigma$ is the sigmoid function so that $\hat{y}\in[0, 1]$ is the predicted CTR, $y_{FM}$ is the output of
FM component, and $y_{DNN}$ is the output of deep component.

<img src = https://pic3.zhimg.com/v2-c0b871f214bdae6284e98989dc8ac99b_1200x500.jpg width=60%/>

The **FM component** is a factorization machine and the output of FM is the summation of
an `Addition` unit and a number of `Inner Product` units:

$$
\hat{y}
= \left<w, x\right>+\sum_{j_1=1}^{n}\sum_{j_2=i+1}^{n}\left<v_i, v_j\right> x_{j_1} x_{j_2}.
$$

The **deep component** is a `feed-forward neural network`, which is used to learn high-order feature interactions. There is a personal guess that the component function in activation function $e^x$ can expand in the polynomials form $e^x=1+x+\frac{x^2}{2!}+\dots,+\frac{x^n}{n!}+\dots$, which include all the order of interactions.

We would like to point out the two interesting features of this network structure:

1) while the lengths of different input field vectors can be different, their embeddings are of the same size $(k)$;
2) the latent feature vectors $(V)$ in FM now server as network weights which are learned and used to compress the input field vectors to the embedding vectors.

It is worth pointing out that FM component and deep component share the same feature embedding, which brings two important benefits:

1) it learns both low- and high-order feature interactions from raw features;
2) there is no need for expertise feature engineering of the input.

<img src=http://kubicode.me/img/Deep-in-out-Wide-n-Deep-Series/deepfm_arch.png width=80% />

* https://zhuanlan.zhihu.com/p/27999355
* https://zhuanlan.zhihu.com/p/25343518
* https://zhuanlan.zhihu.com/p/32127194
* https://arxiv.org/pdf/1703.04247.pdf
* [CTR预估算法之FM, FFM, DeepFM及实践](https://blog.csdn.net/John_xyz/article/details/78933253#deep-fm)

### Neural Factorization Machines

$$
\hat{y} = w_0 + \left<w, x\right> + f(x)
$$
where the first and second terms are the linear regression part similar to that for FM, which models global bias of data and weight
of features. The third term $f(x)$ is the core component of NFM
for modelling feature interactions, which is a `multi-layered feedforward neural network`.

`B-Interaction Layer` including `Bi-Interaction Pooling` is an innovation in artificial neural network.

<img title="Neu FM" src="https://pic2.zhimg.com/80/v2-c7012d7a76e488643db9911d7588ccbd_hd.jpg" width="70%" />


* http://staff.ustc.edu.cn/~hexn/
* https://github.com/hexiangnan/neural_factorization_machine
* [LibRec 每周算法：NFM (SIGIR'17)](https://www.infosec-wiki.com/?p=394011)

### Attentional Factorization Machines

Attentional Factorization Machine (AFM) learns the importance of each feature interaction from data via a neural attention network.

We employ the attention mechanism on feature interactions by performing a weighted sum on the interacted vectors:

$$\sum_{(i, j)} a_{(i, j)}(V_i \odot V_j) x_i x_j$$

where $a_{i, j}$ is the attention score for feature interaction.

<img src=https://deepctr-doc.readthedocs.io/en/latest/_images/AFM.png width=80% />

* https://www.comp.nus.edu.sg/~xiangnan/papers/ijcai17-afm.pdf
* https://arxiv.org/abs/1708.04617
* http://blog.leanote.com/post/ryan_fan/Attention-FM%EF%BC%88AFM%EF%BC%89
* https://www.cnblogs.com/Lee-yl/p/9643098.html

### xDeepFM

It mainly consists of 3 parts: `Embedding Layer`, `Compressed Interaction Network(CIN)` and `DNN`.

<img title="xDeepFM" src="https://www.msra.cn/wp-content/uploads/2018/08/kdd-2018-xdeepfm-5.png" width="60%" />


<img src="http://kubicode.me/img/eXtreme-Deep-Factorization-Machine/CIN-Network.png" width="80%" />

- [X] [KDD 2018 | 推荐系统特征构建新进展：极深因子分解机模型](https://www.msra.cn/zh-cn/news/features/kdd-2018-xdeepfm)
- [ ] [xDeepFM: Combining Explicit and Implicit Feature Interactions for Recommender Systems](https://arxiv.org/abs/1803.05170)
- [ ] https://arxiv.org/abs/1803.05170
- [ ] [据说有RNN和CNN结合的xDeepFM](http://kubicode.me/2018/09/17/Deep%20Learning/eXtreme-Deep-Factorization-Machine/)
- [ ] [推荐系统遇上深度学习(二十二)--DeepFM升级版XDeepFM模型强势来袭！](https://www.jianshu.com/p/b4128bc79df0)

### RepeatNet



<img title="Repeat Net" src="http://kubicode.me/img/More-Session-Based-Recommendation/repeatnet_arch.png" width="70%"/>

* https://arxiv.org/pdf/1806.08977.pdf
* [RepeatNet: A Repeat Aware Neural Recommendation Machine
for Session-based Recommendation
](https://staff.fnwi.uva.nl/m.derijke/wp-content/papercite-data/pdf/ren-repeatnet-2019.pdf)
* https://github.com/PengjieRen/RepeatNet
* https://github.com/PengjieRen/RepeatNet-pytorch
* https://xamat.github.io/pubs/recsys12-tutorial.pdf

****

* [Deep Knowledge-aware Network for News Recommendation](https://github.com/hwwang55/DKN)
* https://www.csie.ntu.edu.tw/~b97053/paper/Rendle2010FM.pdf
* https://www.cnblogs.com/pinard/p/6370127.html
* https://www.jianshu.com/p/6f1c2643d31b
* https://blog.csdn.net/John_xyz/article/details/78933253
* https://zhuanlan.zhihu.com/p/38613747
* [Recommender Systems with Deep Learning](https://amundtveit.com/2016/11/20/recommender-systems-with-deep-learning/)
* [深度学习在序列化推荐中的应用](http://kubicode.me/2018/10/25/Deep%20Learning/More-Session-Based-Recommendation/)
* [深入浅出 Factorization Machine 系列](http://kubicode.me/2018/02/23/Deep%20Learning/Deep-in-out-Factorization-Machines-Series/)
* [论文快读 - Deep Neural Networks for YouTube Recommendations](http://lipixun.me/2018/02/01/youtube)

### Deep Matrix Factorization

[Matrix Factorization is a widely used collaborative filtering method in recommender systems. However, most of them are under the assumption that the rating data is missing at random (MAR), which may not be very common. For some users, they may only rate those movies they like, so the inferences will be biased in previous models. In this paper, we proposed a deep matrix factorization method based on missing not at random (MNAR) assumption. As far as we know, this model firstly uses deep learning method to address MNAR issue. The model consists of a complete data model (CDM) and a missing data model (MDM), which are both learned by neural networks. The CDM is nonlinearly determined by two factors, the user latent features and item latent features like other matrix factorization methods. And the MDM also use these two factors but taking the rating value as extra information while training. We used variational Bayesian inference to generate the posterior distribution of our proposed model. Through extensive experiments on different kind of datasets, our proposed model produce gains in some widely used metrics, comparing with several state-of-the-art models. We also explore the performance of our model within different experimental settings.](https://iopscience.iop.org/article/10.1088/1742-6596/1060/1/012001)

* [Deep Matrix Factorization Models for Recommender Systems](https://www.ijcai.org/proceedings/2017/0447.pdf)
* [Deep Matrix Factorization for Recommender Systems with Missing Data not at Random](https://iopscience.iop.org/article/10.1088/1742-6596/1060/1/012001)

----------------


### Deep Matching Models for Recommendation

It is essential for the recommender system  to find the item which matches the users' demand. Its difference from web search is that recommender system provides item information even if the users' demands or generally interests are not provided.
It sounds like modern crystal ball to read your mind.

In [A Multi-View Deep Learning Approach for Cross Domain User Modeling in Recommendation Systems](http://sonyis.me/paperpdf/frp1159-songA-www-2015.pdf) the authors propose to extract rich features from user’s browsing
and search histories to model user’s interests. The underlying assumption is that, users’ historical online activities
reflect a lot about user’s background and preference, and
therefore provide a precise insight of what items and topics users might be interested in.


Its training data set and the test data is  $\{(\mathrm{X}_i, y_i, r_i)\mid i =1, 2, \cdots, n\}$ and $(\mathrm{X}_{n+1}, y_{n+1})$, respectively.
Matching Model is trained using the training data set: a class of `matching functions’
$\mathcal F= \{f(x, y)\}$ is defined, while the value of the function $r(\mathrm{X}, y)\in \mathcal F$ is a real number  a set of numbers $R$ and the $r_{n+1}$ is predicted as  $r_{n+1} = r(\mathrm{X}_{n+1}, y_{n+1})$.

The data is assumed to be generated according to the distributions $(x, y) \sim P(X,Y)$, $r \sim P(R \mid X,Y)$ . The goal of
the learning task is to select a matching function $f (x, y)$ from the class $F$ based on the observation of the training data.
The learning task, then, becomes the following optimization problem.
$$\arg\min_{r\in \mathcal F}\sum_{i=1}^{n}L(r_i, r(x_i, y_i))+\Omega(r)$$
where $L(\cdot, \cdot)$ denotes a loss function and $\Omega(\cdot)$ denotes regularization.

In fact, the inputs x and y can be instances (IDs), feature vectors, and structured objects, and thus the task can be carried out at instance level, feature level, and structure level.

And $r(x, y)$ is supposed to be non-negative in some cases.

|Framework of Matching|
|:---:|
|Output: MLP|
|Aggregation: Pooling, Concatenation|
|Interaction: Matrix, Tensor|
|Representation: MLP, CNN, LSTM|
|Input: ID Vectors $\mathrm{X}$, Feature Vectors $y$|


Sometimes, matching model and ranking model are combined and trained together with pairwise loss.
Deep Matching models takes the ID vectors and features together as the input to a deep neural network to train the matching scores including **Deep Matrix Factorization, AutoRec, Collaborative Denoising Auto-Encoder, Deep User and Image Feature, Attentive Collaborative Filtering, Collaborative Knowledge Base Embedding**.

`semantic-based matching models`

<img src="https://www.msra.cn/wp-content/uploads/2018/06/knowledge-graph-in-recommendation-system-i-18.png" width="80%"/>

* https://sites.google.com/site/nkxujun/
* http://sonyis.me/dnn.html
* https://akmenon.github.io/
* https://sigir.org/sigir2018/program/tutorials/
* [Learning  to Match](http://www.hangli-hl.com/uploads/3/4/4/6/34465961/learning_to_match.pdf)
* [Deep Learning for Matching in Search and Recommendation](http://staff.ustc.edu.cn/~hexn/papers/sigir18-tutorial-deep-matching.pdf)
* [Facilitating the design, comparison and sharing of deep text matching models.](https://github.com/NTMC-Community/MatchZoo)
* [Framework and Principles of Matching Technologies](http://www.hangli-hl.com/uploads/3/4/4/6/34465961/wsdm_2019_workshop.pdf)
* [A Multi-View Deep Learning Approach for Cross Domain User Modeling in Recommendation Systems](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/frp1159-songA.pdf)
* [Learning to Match using Local and Distributed Representations of Text for Web Search](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/10/wwwfp0192-mitra.pdf)
* https://github.com/super-zhangchao/learning-to-match
* https://deepctr-doc.readthedocs.io/en/latest/Features.html




## Embedding methods for RecSys

- https://u.osu.edu/cep1/
- https://labs.pinterest.com/publications/embeddings/
- https://theory.cs.northwestern.edu/events/embeddings/
- https://recsys.acm.org/recsys18/tutorials/
- https://dawenl.github.io/publications/LiangACB16-cofactor.pdf
- https://cseweb.ucsd.edu/~jmcauley/pdfs/recsys18c.pdf
- http://diposit.ub.edu/dspace/bitstream/2445/130481/3/memoria.pdf
- https://cseweb.ucsd.edu/~jmcauley/workshops/scmls20/
- https://www.ismll.uni-hildesheim.de/pub/pdfs/Ahmed_RecSys19.pdf
- https://www.cc.gatech.edu/~lsong/papers/rnn_coevolve.pdf
- [Unified Collaborative Filtering over Graph Embeddings](http://yongfeng.me/attach/wang-sigir2019a.pdf)
- [Hyperbolic embedding](https://github.com/LiuChuang0059/hyperbolic_embedding_papers)
- [Item-based Collaborative Filtering with BER](https://www.aclweb.org/anthology/2020.ecnlp-1.8.pdf)
- https://github.com/xiangwang1223/tree_enhanced_embedding_model

### Hyperbolic Recommender Systems

Many well-established recommender systems are based on representation learning in Euclidean space.
In these models, matching functions such as the Euclidean distance or inner product are typically used for computing similarity scores between user and item embeddings.
`Hyperbolic Recommender Systems` investigate the notion of learning user and item representations in hyperbolic space.

Given a user ${u}$ and an item ${v}$ that are both lying in the Poincare ball $B^n$, the distance between two points on *P* is given by
$$d_p(x, y)=cosh^{-1}(1+2\frac{\|(x-y\|^2}{(1-\|x\|^2)(1-\|y\|^2)}).$$

`Hyperbolic Bayesian Personalized
Ranking(HyperBPR)` leverages BPR pairwise learning to minimize the pairwise ranking loss between the positive and negative items.
Given a user ${u}$ and an item ${v}$ that are both lying in Poincare ball $B^n$, we take:
$$\alpha(u, v) = f(d_p(u, v))$$
where $f(\cdot)$ is simply preferred as a linear function $f(x) = \beta x + c$ with $\beta\in\mathbb{R}$ and $c\in\mathbb{R}$ are scalar parameters and learned along with the network.
The objective function is defined as follows:
$$\arg\min_{\Theta} \sum_{i, j, k} -\ln(\sigma\{\alpha(u_i, v_j) - \alpha(u_i, v_k)\}) + \lambda  {\|\Theta\|}_2^2$$

where $(i, j, k)$ is the triplet that belongs to the set ${D}$ that
contains all pairs of positive and negative items for each
user; $\sigma$ is the logistic sigmoid function; $\Theta$ represents the model parameters; and $\lambda$ is the regularization parameter.

The parameters of our model are learned by using [`RSGD`](https://arxiv.org/abs/1111.5280).

* [Stochastic gradient descent on Riemannian manifolds](https://arxiv.org/abs/1111.5280)
* [Hyperbolic Recommender Systems](https://arxiv.org/abs/1809.01703)
* [Scalable Hyperbolic Recommender Systems](https://arxiv.org/abs/1902.08648v1)



### Prod2Vec

 Product embedding
* Based on item-item co-occurrence from transaction sequences
 co-purhased products)
* Uses method of word embedding: low-dimensional, distributed
embeddings of words based on word sequences in text documents

- https://astro.temple.edu/~tuc17157/pdfs/grbovic2015kddB.pdf
- http://www.majumderb.com/prod2vec_initial_report.pdf
- https://dl.acm.org/citation.cfm?id=2959166

### Item2vec

- https://www.cnblogs.com/hellojamest/p/11766401.html
- http://ceur-ws.org/Vol-1688/paper-13.pdf

### Meta-Prod2Vec

`Meta-Prod2ve` is a novel method to compute item similarities for recommendation that leverages existing item metadata. 

- https://arxiv.org/abs/1607.07326
- http://labs.criteo.com/2016/09/meta-prod2vec-product-embeddings-using-side-information-recommendation/

### Graph Embeddings for RecSys

- https://github.com/aarivan/Graph-Embeddings-for-Recommender-Systems

#### proNet


- http://cherry.cs.nccu.edu.tw/~g10018/portfolio/slides/pronet.pdf
- https://github.com/haowei01/proNet-core

#### Modularize Graph Embedding for Recommendation

We can take the recommendation as Link Prediction on Graphs.

1. Efficient retrieval from approximate nearest neighbor (ANN) search methods.
2. Efficient pairwise comparison due to dimensionality reduction (DR)
3. Reduced space complexity due to DR
4. Transfer learning with pertained embeddings 

So graph embedding is GREAT for recommendation :
* Reduces data sparsity and cold start via integrating auxiliary information
* Provides holistic view of REC problem and jointly mines different relations in terms of graph structures
* Trains fast, compares fast, and retrieves fast while taking less space

In order to address the challenges of the graph embedding, we need modularize graph embedding for adaptability.

* Extracts graph structures from dataset while remains type-agnostic to sampled entities, i.e., nodes & edges
* Converts entities into spatial features via embedding stacking operations, e.g, lookup, pooling (average, etc.)
* Preserves entity relatedness as spatial properties with customizable similarity metrics and loss functions


- https://github.com/cnclabs/smore
- https://github.com/chihming/awesome-network-embedding
- http://cherry.cs.nccu.edu.tw/~g10018/recsys19_smore.pdf
- http://staff.ustc.edu.cn/~hexn/papers/sigir19-NGCF.pdf
- https://www.slideshare.net/changecandy/recsys19-smore

## Graph-based RecSys

> Graph is an important structure for System II intelligence, with the universal representation ability to capture the relationship between different variables, and support interpretability, causality, and transferability / inductive generalization. Traditional logic and symbolic reasoning over graphs has relied on methods and tools which are very different from deep learning models, such Prolog language, SMT solvers, constrained optimization and discrete algorithms. Is such a methodology separation between System I and System II intelligence necessary? How to build a flexible, effective and efficient bridge to smoothly connect these two systems, and create higher order artificial intelligence?

> [Graph neural networks](https://logicalreasoninggnn.github.io/), have emerged as the tool of choice for graph representation learning, which has led to impressive progress in many classification and regression problems such as chemical synthesis, 3D-vision, recommender systems and social network analysis. However, prediction and classification tasks can be very different from logic/symbolic reasoning.

[In this tutorial, we revisit the recommendation problem from the perspective of graph learning. ](https://next-nus.github.io/)
Common data sources for recommendation can be organized into graphs, such as user-item interactions (bipartite graphs), social networks, item knowledge graphs (heterogeneous graphs), among others. 
Such a graph-based organization connects the isolated data instances, bringing benefits for exploiting high-order connectivities that encode meaningful patterns for collaborative filtering, content-based filtering, social influence modeling and knowledge-aware reasoning. 
Together with the recent success of graph neural networks (GNNs), graph-based models have exhibited the potential to be the technologies for next generation recommendation systems. 
The tutorial provides a review on graph-based learning methods for recommendation, with special focus on recent developments of GNNs and knowledge graph-enhanced recommendation. 
By introducing this emerging and promising area in the tutorial, we expect the audience can get deep understanding and accurate insight on the spaces, stimulate more ideas and discussions, and promote developments of technologies.

- https://next-nus.github.io/
- https://logicalreasoninggnn.github.io/
- https://arxiv.org/abs/1902.07243
- https://zhuanlan.zhihu.com/p/66521058
- [Graph-search based Recommendation system](https://github.com/chandan-u/graph-based-recommendation-system)
- https://next-nus.github.io/slides/tuto-cikm2019-public.pdf
- [Multi-behavior Recommendation with Graph Convolutional
Networks](http://staff.ustc.edu.cn/~hexn/papers/sigir20-MBGCN.pdf)

### Deep Geometric Matrix Completion

It’s easy to observe how better matrix completions can be achieved by considering the sparse matrix as defined over two different graphs:
a user graph and an item graph. From a signal processing point of view, the matrix ${X}$
can be considered as a bi-dimensional signal defined over two distinct domains.
Instead of recurring to multigraph convolutions realized over the entire matrix ${X}$, two
independent single-graph GCNs (graph convolution networks) can be applied on matrices ${W}$ and ${H}$.

Given the aforementioned multi-graph convolutional layers,
the last step that remains concerns the choice of the architecture to use for reconstructing the missing information.
Every (user, item) pair in the multi-graph approach and every user/item in the separable
one present in this case an independent state, which is updated (at every step) by means of the features produced by
the selected GCN.

* [graph convolution network有什么比较好的应用task？ - superbrother的回答 - 知乎](https://www.zhihu.com/question/305395488/answer/554847680)
* https://arxiv.org/abs/1704.06803
* [Deep Geometric Matrix Completion: a Geometric Deep Learning approach to Recommender Systems](http://www.ipam.ucla.edu/abstract/?tid=14552&pcode=DLT2018)
* [Talk: Deep Geometric Matrix Completion](http://helper.ipam.ucla.edu/publications/dlt2018/dlt2018_14552.pdf)

### PinSage

- http://snap.stanford.edu/graphsage/
- http://cedric.cnam.fr/~thomen/journal_club/19-10-18.pdf
- https://sites.google.com/view/ruining-he/
- https://samsiatrtp.wordpress.com/category/program/computational-advertising/
- https://docs.dgl.ai/en/latest/_modules/dgl/sampling/pinsage.html
- https://www.hotbak.net/key/%E5%9B%BE%E7%A5%9E%E7%BB%8F%E7%BD%91%E7%BB%9C%E7%94%A8%E4%BA%8E%E6%8E%A8%E8%8D%90%E7%B3%BB%E7%BB%9F%E9%97%AE%E9%A2%98PinSage.html

### Spectral Collaborative Filtering

- https://www.cs.uic.edu/~clu/doc/recsys18_spectralCF.pdf



### LightGCN


-  https://github.com/kuandeng/LightGCN
-  https://blog.csdn.net/qq_39388410/article/details/106970194
-  http://staff.ustc.edu.cn/~hexn/

### GraphRec


- https://github.com/wenqifan03/GraphRec-WWW19
- https://daiwk.github.io/posts/dl-graph-recommendations.html


## Feature Interaction Selection in RecSys


[A feature interaction is some way in which a feature or features modify or influence another feature in defining overall system behavior.](http://pamelazave.com/faq.html)

- https://www.tinymind.cn/articles/4233?from=articles_commend
- [HOP-rec: high-order proximity for implicit recommendation](https://dl.acm.org/doi/10.1145/3240323.3240381)
- https://archsummit.infoq.cn/2020/shenzhen/presentation/2330
- [Bayesian Personalized Feature Interaction Selection for Factorization Machines](https://staff.fnwi.uva.nl/m.derijke/wp-content/papercite-data/pdf/chen-2019-bayesian.pdf)

Generally, feature interactions matter in recommender system.


[Attribute interactions are the irreducible dependencies between attributes. Interactions underlie feature relevance and selection, the structure of joint probability and classification models: if and only if the attributes interact, they should be connected. While the issue of 2-way interactions, especially of those between an attribute and the label, has already been addressed, we introduce an operational definition of a generalized n-way interaction by highlighting two models: the reductionistic part-to-whole approximation, where the model of the whole is reconstructed from models of the parts, and the holistic reference model, where the whole is modelled directly. An interaction is deemed significant if these two models are significantly different. Correlation is a special case of attribute interaction.](http://stat.columbia.edu/~jakulin/Int/)

- http://pamelazave.com/fi.html
- https://staff.fnwi.uva.nl/m.derijke/wp-content/papercite-data/pdf/chen-2019-bayesian.pdf
- [Experimentation with fairness-aware recommendation using librec-auto](http://www.that-recsys-lab.net/home/projects/fala-tutorial-2020)
- http://www.inf.unibz.it/~ricci/papers/intro-rec-sys-handbook.pdf
- https://pycaret.org/feature-interaction/
- https://www.cs.cmu.edu/~ckaestne/pdf/icse12.pdf
- https://www.public.asu.edu/~huanliu/papers/ijcai07.pdf
- https://digitalcommons.unl.edu/cgi/viewcontent.cgi?article=1189&context=cseconfwork
- http://stat.columbia.edu/~jakulin/Int/interaction-slides.pdf
- https://iclr.cc/virtual_2020/poster_BkgnhTEtDS.html
- http://stat.columbia.edu/~jakulin/Int/
- https://christophm.github.io/interpretable-ml-book/interaction.html

### AutoCross

By performing beam search in a tree-structured space, AutoCross enables efficient generation of high-order cross features, which is not yet visited by existing works.

<img src="https://cdn-image.aijishu.com/419/674/4196744805-5efef8e60a75b" width="80%"/>

- [AutoCross: Automatic Feature Crossing for Tabular Data in Real-World Applications](https://dl.acm.org/doi/10.1145/3292500.3330679)
- https://aijishu.com/a/1060000000081601

### Product-based Neural Network

> Facing with the extreme sparsity, traditional models may limit their capacity of mining shallow patterns from the data, i.e. low-order feature combinations. Deep models like deep neural networks, on the other hand, cannot be directly applied for the high-dimensional input because of the huge feature space.

- https://arxiv.org/abs/1611.00144
- https://www.kdd.org/kdd2016/papers/files/adf0975-shanA.pdf
- https://dl.acm.org/doi/10.1145/3233770
- https://github.com/Atomu2014/product-nets
- https://app.dimensions.ai/details/publication/pub.1007555309

### Deep Crossing

[The Deep Crossing model  is a deep neural network that automatically combines features to produce superior models. The input of Deep Crossing is a set of individual features that can be either dense or sparse. The important crossing features are discovered implicitly by the networks, which are comprised of an embedding and stacking layer, as well as a cascade of Residual Units.](https://www.kdd.org/kdd2016/subtopic/view/deep-crossing-web-scale-modeling-without-manually-crafted-combinatorial-fea)

- https://www.kdd.org/kdd2016/papers/files/adf0975-shanA.pdf

### AutoGroup


AutoGroup casts the selection of feature interactions as a structural optimization problem. In a nutshell, AutoGroup first automatically groups useful features into a number of feature sets. Then, it generates interactions of any order from these feature sets using a novel interaction function. The main contribution of AutoGroup is that it performs both dimensionality reduction and feature selection which are not seen in previous models.



- [Efficient Sparse Modeling with Automatic Feature Grouping](https://icml.cc/Conferences/2011/papers/9_icmlpaper.pdf)
- [AutoGroup: Automatic Feature Grouping for Modelling Explicit High-Order Feature Interactions in CTR Prediction](https://dl.acm.org/doi/abs/10.1145/3397271.3401082)
- https://zhuanlan.zhihu.com/p/136594025

### AutoFIS

> `AutoFIS` can automatically identify important feature interactions for factorization models with computational cost just equivalent to training the target model to convergence. In the $\color{red}\text{search stage}$, instead of searching over a discrete set of candidate feature interactions, we relax the choices to be continuous by introducing the architecture parameters

- [AutoFIS: Automatic Feature Interaction Selection in Factorization Models for Click-Through Rate PredictionCODE ](https://arxiv.org/abs/2003.11235)
- https://github.com/zhuchenxv/AutoFIS

### AutoFeature

$\mathrm{AutoInt}$ to automatically learn the high-order feature interactions of input features.
[Our proposed algorithm is very general, which can be applied to both numerical and categorical input features.](https://arxiv.org/abs/1810.11921)
Specifically, we map both the numerical and categorical features into the same low-dimensional space. Afterwards, a multi-head self-attentive neural network with residual connections is proposed to explicitly model the feature interactions in the low-dimensional space. With different layers of the multi-head self-attentive neural networks, different orders of feature combinations of input features can be modeled. 

- [AutoFeature: Searching for Feature Interactions and Their Architectures for Click-through Rate Prediction](https://dl.acm.org/doi/abs/10.1145/3340531.3411912)
- https://arxiv.org/abs/1810.11921

### Automated Embedding

`AutoEmb`  can enable various embedding dimensions according to the popularity in an automated and dynamic manner.

- [AutoEmb: Automated Embedding Dimensionality Search in Streaming Recommendations](https://arxiv.org/abs/2002.11252)
- [Automated Embedding Size Search in Deep Recommender Systems](https://dl.acm.org/doi/abs/10.1145/3397271.3401436)
- https://www.cse.msu.edu/~zhaoxi35/
- https://sites.google.com/view/kdd20-marketplace-autorecsys/

## Ensemble Methods for Recommender System

The RecSys can be considered as some regression or classification tasks, so that we can apply the ensemble methods to these methods as  `BellKor's Progamatic Chaos` used the blended solution to win the prize.
In fact, its essence is bagging or blending, which is one sequential ensemble strategy in order to avoid over-fitting or reduce the variance.

In this section, the boosting is the focus, which is to reduce the error and boost the performance from a weaker learner.

There are two common methods to construct a stronger learner from a weaker learner: (1) reweight the samples and learn from the error: AdaBoosting; (2) retrain another learner and learn to approximate the error: Gradient Boosting.

- [General Functional Matrix Factorization Using Gradient Boosting](http://w.hangli-hl.com/uploads/3/1/6/8/3168008/icml_2013.pdf)
- [recsys2019](https://github.com/logicai-io/recsys2019/tree/master/publications)

### BellKor's Progamatic Chaos

Until now, we consider the recommendation task as a regression prediction process, which is really common in machine learning.
The boosting or stacking methods may help us to enhance these methods.

> A key to achieving highly competitive results on the Netflix data is usage of sophisticated blending schemes, which combine the multiple individual predictors into a single final solution. This significant component was managed by our colleagues at the Big Chaos team. Still, we were producing a few blended solutions, which were later incorporated as individual predictors in the final blend. Our blending techniques were applied to three distinct sets of predictors. First is a set of 454 predictors, which represent all predictors of the BellKor’s Pragmatic Chaos team for which we have matching Probe and Qualifying results. Second, is a set of 75 predictors, which the BigChaos team picked out of the 454 predictors by forward selection. 
> Finally, a set of 24 BellKor predictors for which we had matching Probe and Qualifying results. from [Netflix Prize.](https://www.netflixprize.com/assets/GrandPrize2009_BPC_BellKor.pdf)



* https://www.netflixprize.com/community/topic_1537.html
* https://www.netflixprize.com/assets/GrandPrize2009_BPC_BellKor.pdf
* https://www.netflixprize.com/assets/GrandPrize2009_BPC_BigChaos.pdf


### BoostFM

`BoostFM` integrates boosting into factorization models during the process of item ranking.
Specifically, BoostFM is an adaptive boosting framework that linearly combines multiple homogeneous component recommender system,
which are repeatedly constructed on the basis of the individual FM model by a re-weighting scheme.

**BoostFM**

+ _Input_: The observed context-item interactions or Training Data $S =\{(\mathbf{x}_i, y_i)\}$ parameters E and T.
+ _Output_: The strong recommender $g^{T}$.
+ Initialize $Q_{ci}^{(t)}=1/|S|,g^{(0)}=0, \forall (c, i)\in S$.
+ for $t = 1 \to T$ do
  +  1. Create component recommender $\hat{y}^{(t)}$ with $\bf{Q}^{(t)}$ on $\bf S$,$\forall (c,i) \in \bf S$, , i.e., `Component Recommender Learning Algorithm`;
  +  2. Compute the ranking accuracy $E[\hat{r}(c, i, y^{(t)})], \forall (c,i) \in \bf S$;
  +  3. Compute the coefficient $\beta_t$,
 $$ \beta_t = \ln (\frac{\sum_{(c,i) \in \bf S} \bf{Q}^{(t)}_{ci}\{1 + E[\hat{r}(c, i, y^{(t)})]\}}{\sum_{(c,i) \in \bf S} \bf{Q}^{(t)}_{ci}\{1-  E[\hat{r}(c, i, y^{(t)})]\}})^{\frac{1}{2}} ; $$
  +  4. Create the strong recommender $g^{(t)}$,
  $$ g^{(t)} = \sum_{h=1}^{t} \beta_h \hat{y}^{(t)} ;$$
  +  5. Update weight distribution \(\bf{Q}^{t+1}\),
  $$ \bf{Q}^{t+1}_{ci} = \frac{\exp(E[\hat{r}(c, i, y^{(t)})])}{\sum_{(c,i)\in \bf{S}} E[\hat{r}(c, i, y^{(t)})]} ; $$
+ end for


**Component Recommender**

Naturally, it is feasible to exploit the L2R techniques to optimize Factorization Machines
(FM). There are two major approaches in the field of L2R, namely, pairwise and listwise approaches.
In the following, we demonstrate ranking factorization machines with both pairwise and listwise optimization.

`Weighted Pairwise FM (WPFM)`

`Weighted ‘Listwise’ FM (WLFM)`

- [BoostFM: Boosted Factorization Machines for Top-N Feature-based Recommendation](http://wnzhang.net/papers/boostfm.pdf)
- http://wnzhang.net/
- https://fajieyuan.github.io/
- https://www.librec.net/luckymoon.me/
- [The author’s final accepted version.](http://eprints.gla.ac.uk/135914/7/135914.pdf)

### Adaptive Boosting Personalized Ranking (AdaBPR)

`AdaBPR (Adaptive Boosting Personalized Ranking)` is a boosting algorithm for top-N item recommendation using users' implicit feedback.
In this framework, multiple homogeneous component recommenders are linearly combined to achieve more accurate recommendation.
The component recommenders are learned based on a re-weighting strategy that assigns a dynamic weight to each observed user-item interaction.

Here explicit feedback refers to users' ratings to items while implicit feedback is derived
from users' interactions with items, e.g., number of times a user plays a song.

The primary idea of applying boosting for item recommendation is to learn a set of homogeneous component recommenders and then create an ensemble of the component recommenders to predict users' preferences.

Here, we use a linear combination of component recommenders as the final recommendation model
$$f=\sum_{t=1}^{T}{\alpha}_t f_{t}.$$

In the training process, AdaBPR runs for ${T}$ rounds, and the component recommender $f_t$ is created at t-th round by
$$
\arg\min_{f_t\in\mathbb{H}} \sum_{(u,i)\in\mathbb{O}} {\beta}_{u} \exp\{-E(\pi(u,i,\sum_{n=1}^{t}{\alpha}_n f_{n}))\}.
$$

where the notations are listed as follows:

- $\mathbb{H}$ is the set of possible component recommenders such as collaborative ranking algorithms;
- $E(\pi(u,i,f))$ denotes the ranking accuracy associated with each observed interaction pair;
- $\pi(u,i,f)$ is the rank position of item ${i}$ in the ranked item list of ${u}$, resulted by a learned ranking model ${f}$;
- $\mathbb{O}$ is the set of all observed user-item interactions;
- ${\beta}_{u}$ is defined as reciprocal of the number of user $u$'s  historical items  ${\beta}_{u}=\frac{1}{|V_{u}^{+}|}$ ($V_{u}^{+}$ is the historical items of ${u}$).
***
- [A Boosting Algorithm for Item Recommendation with Implicit Feedback](https://www.ijcai.org/Proceedings/15/Papers/255.pdf)
- [The review @Arivin's blog](http://www.arvinzyy.cn/2017/09/23/A-Boosting-Algorithm-for-Item-Recommendation-with-Implicit-Feedback/)


### Gradient Boosting Factorization Machines

`Gradient Boosting Factorization Machine (GBFM)` model is to incorporate feature selection algorithm with Factorization Machines into a unified framework.

**Gradient Boosting Factorization Machine Model**

> + _Input_: Training Data $S =\{(\mathbf{x}_i, y_i)\}$.
> + _Output_: $\hat{y}_S =y_0(x) + {\sum}^S_{s=1}\left<v_{si}, v_{sj}\right>$.
> + Initialize rating prediction function as $\hat{y}_0(x)$
> + for $s = 1 \to S$ do
> +  1. Select interaction feature $C_p$ and $C_q$ from Greedy Feature Selection Algorithm;
> +  2. Estimate latent feature matrices $V_p$ and $V_q$;
> +  3. Update  $\hat{y}_s(\mathrm{x}) = \hat{y}_{s-1}(\mathrm{x}) + {\sum}_{i\in C_p}{\sum}_{j\in C_q} \mathbb{I}[i,j\in \mathrm{x}]\left<V_{p}^{i}, V_{q}^{j}\right>$
> + end for

where s is the iteration step of the learning algorithm. At step s, we greedily select two interaction features $C_p$ and $C_q$
where $\mathbb{I}$ is the indicator function, the value is 1 if the condition holds otherwise 0.

**Greedy Feature Selection Algorithm**

From the view of gradient boosting machine, at each
step s, we would like to search a function ${f}$ in the function
space ${F}$ that minimize the objective function:
$$L=\sum_{i}\ell(\hat{y}_s(\mathrm{x}_i), y_i)+\Omega(f)$$

where $\hat{y}_s(\mathrm{x}) = \hat{y}_{s−1}(\mathrm{x}) + \alpha_s f_s(\mathrm{x})$.

We heuristically assume that the
function ${f}$ has the following form:
$$ f_{\ell}(\mathrm{x})={\prod}_{t=1}^{\ell} q_{C_{i}(t)}(\mathrm{x}) $$
where the function _q_ maps latent feature
vector x to real value domain
$$ q_{C_{i}(t)}(\mathrm{x})=\sum_{j\in C_{i}(t)}\mathbb{I}[j\in \mathrm{x}]w_{t} $$

It is hard for a general convex loss function $\ell$ to search function ${f}$ to optimize the objective function:
$L=\sum_{i}\ell(\hat{y}_s(\mathrm{x}_i), y_i)+\Omega(f)$.

The most common way is to approximate it by least-square
minimization, i.e., $\ell={\| \cdot \|}_2^2$. Like in `xGBoost`, it takes second order Taylor expansion of the loss function $\ell$ and problem isfinalized to find the ${i}$(t)-th feature which:

$$\arg{\min}_{i(t)\in \{0, \dots, m\}} \sum_{i=1}^{n} h_i(\frac{g_i}{h_i}-f_{t-1}(\mathrm{x}_i) q_{C_{i}(t)}(\mathrm{x}_i))^2 + {\|\theta\|}_2^2 $$
where the negativefirst derivative and the second derivative at instance ${i}$ as $g_i$ and $h_i$.

- [Gradient boosting factorization machines](http://tongzhang-ml.org/papers/recsys14-fm.pdf)

#### Gradient Boosted Categorical Embedding and Numerical Trees

`Gradient Boosted Categorical Embedding and Numerical Trees (GB-CSENT)` is to combine Tree-based Models and Matrix-based Embedding Models in order to handle numerical features and large-cardinality categorical features.
A prediction is based on:

* Bias terms from each categorical feature.
* Dot-product of embedding features of two categorical features,e.g., user-side v.s. item-side.
* Per-categorical decision trees based on numerical features ensemble of numerical decision trees where each tree is based on one categorical feature.

In details, it is as following:
$$
\hat{y}(x) = \underbrace{\underbrace{\sum_{i=0}^{k} w_{a_i}}_{bias} + \underbrace{(\sum_{a_i\in U(a)} Q_{a_i})^{T}(\sum_{a_i\in I(a)} Q_{a_i}) }_{factors}}_{CAT-E} + \underbrace{\sum_{i=0}^{k} T_{a_i}(b)}_{CAT-NT}.
$$
And it is decomposed as the following table.
_____
Ingredients| Formulae| Features
---|---|---
Factorization Machines |$\underbrace{\underbrace{\sum_{i=0}^{k} w_{a_i}}_{bias} + \underbrace{(\sum_{a_i\in U(a)} Q_{a_i})^{T}(\sum_{a_i\in I(a)} Q_{a_i}) }_{factors}}_{CAT-E}$ | Categorical Features
GBDT |$\underbrace{\sum_{i=0}^{k} T_{a_i}(b)}_{CAT-NT}$ | Numerical Features
_________
- http://www.hongliangjie.com/talks/GB-CENT_SD_2017-02-22.pdf
- http://www.hongliangjie.com/talks/GB-CENT_SantaClara_2017-03-28.pdf
- http://www.hongliangjie.com/talks/GB-CENT_Lehigh_2017-04-12.pdf
- http://www.hongliangjie.com/talks/GB-CENT_PopUp_2017-06-14.pdf
- http://www.hongliangjie.com/talks/GB-CENT_CAS_2017-06-23.pdf
- http://www.hongliangjie.com/talks/GB-CENT_Boston_2017-09-07.pdf
- [Talk: Gradient Boosted Categorical Embedding and Numerical Trees](http://www.hongliangjie.com/talks/GB-CENT_MLIS_2017-06-06.pdf)
- [Paper: Gradient Boosted Categorical Embedding and Numerical Trees](https://qzhao2018.github.io/zhao/publication/zhao2017www.pdf)
- https://qzhao2018.github.io/

####  Deep Embedding Networks and Gradient Boosting Decision Trees

- http://www.simflow.net/Publications/Papers/Year2018/Baibing.pdf
- https://doogkong.github.io/proposal_2019.html

## Tree-based Deep Model for Recommender Systems

By indexing items in a tree hierarchy and training a user-node preference prediction model satisfying a max-heap like property in the tree, 
[`TDM` provides logarithmic computational complexity w.r.t. the corpus size, enabling the use of arbitrary advanced models in candidate retrieval and recommendation.](https://arxiv.org/abs/1801.02294)

Our purpose, in this paper, is to develop a method to jointly learn the `index structure and user preference prediction model`. 


Recommendation problem is basically `to retrieve a set of most relevant or preferred items for each user request from the entire corpus`. 
In the practice of large-scale recommendation, the algorithm design should strike a balance between accuracy and efficiency.

The above methods include 2 stages/models: (1) find the preference of the users based on history or other information; (2) retrive some items according to the predicted preferences.

TDM uses a tree hierarchy to organize items, and each leaf node in the tree corresponds to an item. Like a max-heap, 
`TDM assumes that each user-node preference is the largest one among the node’s all children’s preferences`.
The main idea is to predict user interests `from coarse to fine by traversing tree nodes in a top-down fashion and making decisions for each user-node pair`. 

Each item in the corpus is firstly assigned to a leaf node of a tree
hierarchy $\mathcal{T}$. 
The non-leaf nodes can be seen as a coarser abstraction of their children. In retrieval, the user information combined with the node to score is firstly vectorized to a user preference representation as the input of a deep neural network $\mathcal{M}$ (e.g. fully connected networks). While retrieving
for the top-k items (leaf nodes), a `top-down beam search strategy`
is carried out level by level.

<img src="https://yqfile.alicdn.com/c8fbcb9f1d76a3d5789aadc5fceb4914eb475c03.png" width="80%" />

TDM uses a tree as index and creatively proposes a max-heap like probability formulation on the tree, where the user preference for each non-leaf node $n$ in level $l$ is derived as:
$$p^{(l)}(u \mid n)=\frac{\max_{n_c\in\{\text{the children of the node $n$ in the $l+1$ level}\}} p^{(l)}(n_c \mid u)}{\alpha^{(l)}}$$

where $p^{(l)}(u \mid n)$ is the ground truth probability that the user $u$ prefers the node $n$. 
The above formulation means that the ground truth user-node probability on a node equals to the maximum user-node probability of its children divided by a normalization term. 
Therefore, the top-k nodes in level $l$ must be contained in the children of top-k nodes in level $l −1$ and the retrieval for top-k leaf items can be restricted to top-k nodes in each layer without losing the accuracy. 
Based on this, `TDM turns the recommendation task into a hierarchical retrieval problem`. 
By a top-down retrieval process, the candidate items are selected gradually from coarse to detailed.

According to the retrieval process, the recommendation accuracy of TDM is determined by the quality of the user preference model
$\mathcal M$ and tree index $\mathcal T$. Given n pairs of positive training data $(u_i, c_i)$, 
which means the user $u_i$ is interested in the target item $c_i$, $\mathcal T$ determines which non-leaf nodes $\mathcal M$ should select to achieve $c_i$ for $u_i$.

Denote $p (\pi(c_i)|u_i; \pi)$ as user u’s preference probability over
leaf node $\pi(c_i)$ given a user-item pair $(u_i, c_i)$, 
where $\pi(·)$ is a projection function that projects an item to a leaf node in $\mathcal T$.
Note that the projection function $\pi(\cdot)$ actually determines the item hierarchy in the tree. 
The model $\mathcal M$ is used to estimate and output the user-node preference $\hat{p} (\pi(c_i)|u_i;\theta \pi)$ given $\theta$ as model parameters.
If the pair $(u_i , c_i)$ is a positive sample, we have the ground truth preference $p (\pi(c_i)|u_i; \pi)=1$. According to the `max-heap property`,
the user preference probability of all $π(c_i)$’s ancestor nodes, i.e.,
$\{p(b_j (\pi(c_i))|u_i; \pi)\}^{l_{max}}_{j=0}$ should also be 1, in which $b_j(\cdot)$ is the projection from a node to its ancestor node in level $j$ and $l_{max}$ is the max level in $\mathcal T$.
To fit such a user-node preference distribution, the
global loss function is formulated as

$$L(\theta, \mathcal T)= -\sum_{i=1}^n \sum_{j=1}^{l_{max}}\log(\hat{p}(b_j (\pi(c_i))|u_i; \pi) )$$

where we sum up the negative logarithm of predicted user-node
preference probability on all the positive training samples and their
ancestor user-node pairs as the global empirical loss.

- https://github.com/DeepGraphLearning/RecommenderSystems
- https://github.com/DeepGraphLearning
- https://jian-tang.com/
- [Learning Tree-based Deep Model for Recommender Systems](https://arxiv.org/abs/1801.02294)
- [Joint Optimization of Tree-based Index and Deep Model for Recommender Systems](https://arxiv.org/pdf/1902.07565.pdf)
- https://developer.aliyun.com/article/720309
- [学习基于树的推荐系统深度模型](https://blog.csdn.net/XindiOntheWay/article/details/85220342)
- [Behavior Sequence Transformer for E-commerce Recommendation in Alibaba](https://arxiv.org/abs/1905.06874)
- [Multi-Interest Network with Dynamic Routing for Recommendation at Tmall](https://arxiv.org/abs/1904.08030v1)
- [AutoInt: Automatic Feature Interaction Learning via Self-Attentive Neural Networks](https://arxiv.org/abs/1810.11921v1)

The core of `TDM` is to regard the recommendation as ranking.

## Context-aware Recommendations

[Context-aware information is widely available in various ways and is becoming more and more important for enhancing retrieval performance and recommendation results. ](http://carr-workshop.org/)
The current main issue to cope with is not only recommending or retrieving the most relevant items and content, but defining them ad hoc. Further relevant issues are personalizing and adapting the information and the way it is displayed to the user’s current situation and interests. 


- https://www.baltrunas.info/context-aware
- https://www.kdd.org/kdd2014/tutorials/KDD-%20The%20RecommenderProblemRevisited-Part2.pdf
- [Workshop on Context-Aware Recommender Systems (CARS-2009)](http://ids.csom.umn.edu/faculty/gedas/cars2009/)
- [Context-aware Recommendation Using Role-based Trust Network](https://www.icst.pku.edu.cn/leizou/docs/2018-11/20181121164540356311.pdf)
- [Context-Aware Recommendations Based on Deep Learning Frameworks](https://dl.acm.org/doi/10.1145/3386243)
- [CARS2: Learning Context-aware Representations for Context-aware Recommendations](https://alexiskz.files.wordpress.com/2016/06/km1212-karatzoglou.pdf)
- http://carr-workshop.org/

### Context-Aware Factorization Machines

- [Fast Context-aware Recommendations with Factorization Machines](https://www.ismll.uni-hildesheim.de/pub/pdfs/Rendle_et_al2011-Context_Aware.pdf)
- [Optimizing Factorization Machines for Top-N Context-Aware Recommendations](https://fajieyuan.github.io/papers/WISE2016.pdf)
- [Factorization Models for Context-/Time-Aware Movie
Recommendations](https://www.ismll.uni-hildesheim.de/pub/pdfs/Gantner_Rendle_2010_CAMRa.pdf)
- [Gaussian Process Factorization Machines for Context-aware  Recommendations](http://www.mscs.mu.edu/~praveen/Research/SocialAnalytics/p63-nguyen.pdf)

## Sequential Recommender Systems

- https://project.inria.fr/sr4sg/home/
- https://jiaxit.github.io/resources/wsdm18caser.pdf
- https://www.ijcai.org/Proceedings/2019/0883.pdf
- [Adaptive-Hierarchical-Translation-Sequential](http://people.tamu.edu/~zhan13679/Paper/Adaptive-Hierarchical-Translation-Sequential.pdf)
- https://www.hongliangjie.com/publications/wsdm2020.pdf
- [Disentangled Self-Supervision in Sequential Recommenders](http://pengcui.thumedialab.com/papers/DisentangledSequentialRecommendation.pdf)

## Top-N recommendation

* http://yongfeng.me/attach/jrl-cikm17.pdf
* [Local Item-Item Models for Top-N Recommendation](http://glaros.dtc.umn.edu/gkhome/node/1192)
* [Improving Top-N Recommendation with Heterogeneous Loss](https://www.ijcai.org/Proceedings/16/Papers/339.pdf)
* https://blog.csdn.net/lthirdonel/article/details/80021282
* [Top-N Recommendations from Implicit Feedback Leveraging Linked Open Data](http://ceur-ws.org/Vol-1127/paper4.pdf)
* [Top-N Recommendations from Implicit Feedback Leveraging Linked Open Data ?](https://core.ac.uk/display/23873231)

## Explainable Recommendations

Explainable recommendation and search attempt to develop models or methods that not only generate high-quality recommendation or search results, 
but also intuitive explanations of the results for users or system designers, 
which can help improve the system transparency, persuasiveness, trustworthiness, and effectiveness, etc.

Providing personalized explanations for recommendations can help users to understand the underlying insight of the recommendation results, 
which is helpful to the effectiveness, transparency, persuasiveness and trustworthiness of recommender systems. 
Current explainable recommendation models mostly generate textual explanations based on pre-defined sentence templates. 
However, the expressiveness power of template-based explanation sentences are limited to the pre-defined expressions, 
and manually defining the expressions require significant human efforts

+ [Explainable Recommendation and Search @ rutgers](https://www.cs.rutgers.edu/content/explainable-recommendation-and-search)
+ [Explainable Recommendation: A Survey and New Perspectives](https://www.groundai.com/project/explainable-recommendation-a-survey-and-new-perspectives/)
+ [Explainable Entity-based Recommendations with Knowledge Graphs](http://www.cs.cmu.edu/~wcohen/postscript/recsys-2017-poster.pdf)
+ [2018 Workshop on Explainable Recommendation and Search (EARS 2018)](https://ears2018.github.io/)
+ [EARS 2019](https://sigir.org/sigir2019/program/workshops/ears/)
+ [Explainable Recommendation and Search (EARS)](http://yongfeng.me/projects/)
+ [TEM: Tree-enhanced Embedding Model for Explainable Recommendation](http://staff.ustc.edu.cn/~hexn/slides/www18-tree-embedding-recsys.pdf)
+ https://ears2019.github.io/
+ [Explainable Recommendation for Self-Regulated Learning](http://www.cogsys.org/papers/ACSvol6/posters/Freed.pdf)
+ [Dynamic Explainable Recommendation based on Neural Attentive Models](http://www.yongfeng.me/attach/dynamic-explainable-recommendation.pdf)
+ https://github.com/fridsamt/Explainable-Recommendation
+ [Explainable Recommendation for Event Sequences: A Visual Analytics Approach by Fan Du](https://talks.cs.umd.edu/talks/2028)
+ https://wise.cs.rutgers.edu/code/
+ http://www.cs.cmu.edu/~rkanjira/thesis/rose_proposal.pdf
+ http://jamesmc.com/publications
+ [FIRST INTERNATIONAL WORKSHOP ON  DEEP MATCHING IN PRACTICAL APPLICATIONS ](https://wsdm2019-dapa.github.io/#section-ketnotes)
+ [Explainable Matrix Factorization for Collaborative Filtering](https://www.researchgate.net/publication/301616080_Explainable_Matrix_Factorization_for_Collaborative_Filtering)




## Social Recommendation

[We present a novel framework for studying recommendation algorithms in terms of the ‘jumps’ that they make to connect people to artifacts. This approach emphasizes reachability via an algorithm within the `implicit graph structure` underlying a recommender dataset and allows us to consider questions relating algorithmic parameters to properties of the datasets.](http://people.cs.vt.edu/~ramakris/papers/receval.pdf)

> [Social Recommender Systems (SRSs)](http://www.comp.hkbu.edu.hk/~lichen/srs2010/) aim to alleviate information overload over social media users by presenting the most attractive and relevant content, often using personalization techniques adapted for the specific user. 
> SRSs also aim at increasing adoption, engagement, and participation of new and existing users of social media sites. In addition to recommending content to consume, new types of recommendations emerge within social media, such as of people and communities to connect to, to follow, or to join.

User-item/user-user interactions are usually in the form of graph/network structure. What is more, the graph is dynamic, and  we need to apply to new nodes without model retraining.


- [ ] [6th International Workshop on Social Recommender Systems (SRS 2015)](http://www.comp.hkbu.edu.hk/~lichen/srs2015/)
- [ ] http://www.comp.hkbu.edu.hk/~lichen/srs2010/
- [ ] http://www.comp.hkbu.edu.hk/~lichen/srs2012/
- [ ] http://www.comp.hkbu.edu.hk/~lichen/srs2011/
- [ ] [1st International Workshop on Adaptation, Personalization and REcommendation in the Social-semantic We 7th Extended Semantic Web Conference (ESWC 2010)](http://ir.ii.uam.es/apresw2010/)
- [ ] [Recommendation and Advertising in Online Social Networks](http://math.unipa.it/readnet2019/)
- [ ] [Fairness and Discrimination in Retrieval and Recommendation](https://fair-ia.ekstrandom.net/)
- [ ] https://fairumap.wordpress.com/
- [ ] [Recommender Systems with Social Regularization](https://www.microsoft.com/en-us/research/wp-content/uploads/2011/01/wsdm10.pdf)
- [ ] [Do Social Explanations Work? Studying and Modeling the Effects of Social Explanations in Recommender Systems](https://arxiv.org/pdf/1304.3405.pdf)
- [ ] [Existing Methods for Including Social Networks until 2015](http://ajbc.io/projects/slides/chaney_recsys2015.pdf)
- [ ] [Social Recommendation With Evolutionary Opinion Dynamics](https://shiruipan.github.io/pdf/TSMC-18-Xiong.pdf)
- [ ] [Workshop on Responsible Recommendation](https://piret.gitlab.io/fatrec/)
- [ ] https://recsys.acm.org/recsys18/fatrec/
- [ ] [A Probabilistic Model for Using Social Networks in Personalized Item Recommendation](http://ajbc.io/projects/papers/Chaney2015.pdf)
- [ ] [Product Recommendation and Rating Prediction based on Multi-modal Social Networks](http://delab.csd.auth.gr/papers/RecSys2011stm.pdf)
- [ ] [Graph Neural Networks for Social Recommendation](https://paperswithcode.com/paper/graph-neural-networks-for-social)
- [ ] [Studying Recommendation Algorithms by Graph Analysis](http://people.cs.vt.edu/~ramakris/papers/receval.pdf)
- [ ] [Low-rank Linear Cold-Start Recommendation from Social Data](https://akmenon.github.io/papers/loco/loco-paper.pdf)
- [ ] [Accurate and scalable social recommendation using mixed-membership stochastic block models](https://www.pnas.org/content/113/50/14207)
- [ ] [Social Choice Theory and Recommender Systems](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/11/social_choice_theory.pdf)
- [ ] https://raweb.inria.fr/rapportsactivite/RA2004/axis/uid26.html

### SocialMF: MF with social trust propagation

Based on the assumption of trust aware recommender
* users have similar tastes with other users they trust
* the transitivity of trust and propagate trust to indirect neighbors in the social network.

- https://github.com/grahamjenson/list_of_recommender_systems
- https://www.librec.net/doc/librec-v1.1/librec/rating/SocialMF.html
- [A matrix factorization technique with trust propagation for recommendation in social networks](https://www.semanticscholar.org/paper/A-matrix-factorization-technique-with-trust-for-in-Jamali-Ester/c73287153c0a50102a40800c1ada626a410c63cc)


### Algorithmic Bias in Search and Recommendation

> Both search and recommendation algorithms provide results based on their relevance for the current user. In order to do so, such a relevance is usually computed by models trained on historical data, which is biased in most cases.
>  Hence, the results produced by these algorithms naturally propagate, and frequently reinforce, biases hidden in the data, consequently strengthening inequalities. Being able to measure, characterize, and mitigate these biases while keeping high effectiveness is a topic of central interest for the information retrieval community. 

- http://bias.disim.univaq.it/
- https://www.mirkomarras.com/publication/bias2020/
- [FAIRNESS, ACCOUNTABILITY AND TRANSPARENCY IN RECOMMENDER SYSTEMS](https://scholarworks.boisestate.edu/fatrec/)
- [On the Need for Fairness in Financial Recommendation Engines](https://berthuang.com/papers/yao-finance18.pdf)
- [What are you optimizing for? Aligning Recommender Systems with Human Values](https://participatoryml.github.io/papers/2020/42.pdf)
- [Algorithms are not neutral: Bias in collaborative filtering](https://www.catherinestinson.ca/Files/Papers/Algorithms_are_not_Neutral.pdf)

## Knowledge Graph and Recommender System

Items usually correspond to entities in many fields, such as books, movies and music, making it possible for transferring information between them.
These information involving in `recommender system and knowledge graph` are complementary revealing the connectivity among items or between users and items.
In terms of models, the two tasks are both to rank candidates for a target according to either implicit or explicit relations.
For example, KG completion is to find correct movies (e.g., Death Becomes Her) for the person Robert Zemeckis given the explicit relation is Director Of.
Item recommendation aims at recommending movies for a target user satisfying some implicit preference.
Therefore, we are to fill in the gap between `item recommendation` and `KG completion` via a joint model, and systematically investigate how the two tasks impact each other.


- [ ] [推荐算法不够精准？让知识图谱来解决](https://www.msra.cn/zh-cn/news/features/embedding-knowledge-graph-in-recommendation-system-i)
- [ ] [如何将知识图谱特征学习应用到推荐系统？](https://www.msra.cn/zh-cn/news/features/embedding-knowledge-graph-in-recommendation-system-ii)
- [ ] [可解释推荐系统：身怀绝技，一招击中用户心理](https://www.msra.cn/zh-cn/news/features/explainable-recommender-system-20170914)
- [ ] [深度学习与知识图谱在美团搜索广告排序中的应用实践](https://tech.meituan.com/2018/06/07/searchads-dnn.html)
- [ ] [Unifying Knowledge Graph Learning and Recommendation: Towards a Better Understanding of User Preferences](http://staff.ustc.edu.cn/~hexn/papers/www19-KGRec.pdf)
- [ ] [Explainable Reasoning over Knowledge Graphs for Recommendation](https://arxiv.org/pdf/1811.04540.pdf)


***********

- https://github.com/BaeSeulki/WhySoMuch
- https://github.com/numb3r3/kgraph-rec


****

- https://www.cs.cmu.edu/~wcohen/postscript/recsys-2016.pdf
- https://ieeexplore.ieee.org/abstract/document/9216015/
- https://github.com/hwwang55/KGNN-LS
- https://github.com/hwwang55/KGCN
- https://xiangwang1223.github.io/papers/KGAT_final.pdf
- https://xiangwang1223.github.io/
- https://arxiv.org/abs/2003.05753
- https://arxiv.org/abs/2102.07057
- https://www.comp.nus.edu.sg/~xiangnan/papers/www19-KGRec.pdf

### RippleNet


- https://arxiv.org/pdf/1803.03467.pdf
- https://github.com/hwwang55/RippleNet
- https://caojiangxia.github.io/RippleNet/

## Reinforcement Learning and Recommender System

Services that introduce stores to users on the Internet are increasing in recent years. 
Each service conducts thorough analyses in order to display stores matching each user's preferences. 
In the field of recommendation, collaborative filtering performs well when there is sufficient click information from users. 
Generally, when building a user-item matrix, data sparseness becomes a problem. It is especially difficult to handle new users. 
When sufficient data cannot be obtained, a multi-armed bandit algorithm is applied. 
Bandit algorithms advance learning by testing each of a variety of options sufficiently and obtaining rewards (i.e. feedback). 
It is practically impossible to learn everything when the number of items to be learned periodically increases. 
The problem of having to collect sufficient data for a new user of a service is the same as the problem that collaborative filtering faces. 
In order to solve this problem, we propose a recommender system based on deep reinforcement learning. 
In deep reinforcement learning, a multilayer neural network is used to update the value function.

* https://www.ashudeepsingh.com/publications/
* http://www.cse.msu.edu/~zhaoxi35/
* https://github.com/Jinjiarui/rl4rs-papers
+ https://recsys.acm.org/recsys19/reveal/
+ https://recsys.acm.org/recsys20/reveal/


___________________________


* [Ieep reinforcement learning for recommender systems](https://ieeexplore.ieee.org/document/8350761)
* [Deep Reinforcement Learning for Page-wise Recommendations](https://pdfs.semanticscholar.org/5956/c34032126185d8ad19695e4a1a191c08b5a1.pdf)
* [A Reinforcement Learning Framework for Explainable Recommendation](https://www.microsoft.com/en-us/research/uploads/prod/2018/08/main.pdf)
* [TPGR: Large-scale Interactive Recommendation with Tree-structured Policy Gradient](http://www.noahlab.com.hk/#/news/new1811_1)
+ [Explore, Exploit, and Explain: Personalizing Explainable Recommendations with Bandits](http://jamesmc.com/blog/2018/10/1/explore-exploit-explain)
+ [Learning from logged bandit feedback](https://drive.google.com/file/d/0B2Rxz7LRWLOMX2dycXpWTGxoUE5lNkRnRWZuaDNZUlVRZ1kw/view)
+ [Improving the Quality of Top-N Recommendation](https://drive.google.com/file/d/0B2Rxz7LRWLOMekRtdExZVVpZQmlXNks0Y2FJTnd6ZG90TXdZ/view)
+ [ParsRec: Meta-Learning Recommendations for Bibliographic Reference Parsing](https://arxiv.org/abs/1808.09036)
+ [强化学习在阿里的技术演进与业务创新 | 免费资料库](https://yq.aliyun.com/articles/708953)
+ [Closing the loop with the real world: reinforcement and robust estimators for recommendation](https://sites.google.com/view/reveal2019/)

_______

|Traditional Approaches | Beyond Traditional Methods|
|---------------------- |--------------------------|
|Collaborative Filtering | Tensor Factorization & Factorization Machines|
|Content-Based Recommendation | Social Recommendations|
|Item-based Recommendation | Learning to rank|
|Hybrid Approaches | MAB Explore/Exploit|


- [ ] https://github.com/wzhe06/Reco-papers
- [ ] https://github.com/hongleizhang/RSPapers
- [ ] https://github.com/hongleizhang/RSAlgorithms
- [ ] https://zhuanlan.zhihu.com/p/26977788
- [ ] https://zhuanlan.zhihu.com/p/45097523
- [ ] https://www.zhihu.com/question/20830906
- [ ] https://www.zhihu.com/question/56806755/answer/150755503


##  Adversarial Learning for  Recommender Systems

+ https://github.com/sisinflab/adversarial-recommender-systems-survey
+ https://github.com/EdisonLeeeee/RS-Adversarial-Learning
+ https://yasdel.github.io/
+ [Adversarial Personalized Ranking for Recommendation](http://bio.duxy.me/papers/sigir18-adversarial-ranking.pdf)
+ [Deep Adversarial Social Recommendation](https://www.ijcai.org/Proceedings/2019/0187.pdf)
+ https://yasdel.github.io/files/RecSys20_tutorial.pdf
+ [Generative Adversarial User Model for Reinforcement Learning BasedRecommendation System](https://icml.cc/media/Slides/icml/2019/201(11-14-00)-11-14-25-4831-generative_adve.pdf)
+ http://tommasodinoia.com/


### Generative Adversarial Networks for Recommender Systems

- [Generative Adversarial User Model for Reinforcement Learning Based Recommendation System](https://arxiv.org/abs/1812.10613)
- [RecGAN: Recurrent Generative Adversarial Networks for Recommendation Systems](https://www.brianlim.net/wordpress/wp-content/uploads/2018/08/recsys2018-recgan-recommender.pdf)
- [Enhancing Social Recommendation with Adversarial Graph Convolutional Networks](https://arxiv.org/abs/2004.02340)

### Adversarial Attacks


- [Adversarial Attacks on an oblivious recommender](https://recsys.acm.org/wp-content/uploads/2019/10/recsys-19-material-adversarial.pdf)
- https://www-users.cs.umn.edu/~baner029/papers/19/adv_attack.pdf

### Adversarial Training

+ [Adversarial Training Towards Robust Multimedia Recommender System](https://github.com/duxy-me/AMR)
- https://espace.library.uq.edu.au/view/UQ:b731966
- [Generating Reliable Friends via Adversarial Training to Improve Social Recommendation](https://ieeexplore.ieee.org/document/8970896)
- https://github.com/laugh12321/adversarial_multi_feedback_ranking

## Health Recommender Systems

Recommendations are becoming evermore important in health settings with the aim being to assist people live healthier lives. 
Three previous workshops on Health Recommender Systems (HRS) have incorporated diverse research fields and problems 
in which recommender systems can improve our awareness, understanding and behaviour regarding our own, and the general public's health. 
At the same time, these application areas bring new challenges into the recommender community. 
Recommendations that influence the health status of a patient need to be legally sound and, 
as such, today, they often involve a human in the loop to make sure the recommendations are appropriate. 
To make the recommender infallible, complex domain-specific user models need to be created, which creates privacy issues.
While trust in a recommendation needs to be explicitly earned through, 
for example, transparency, explanations and empowerment, other systems might [want to persuade users into taking beneficial actions that would not be willingly chosen otherwise.](https://healthrecsys.github.io/2019/)
Multiple and diverse stakeholders in health systems produce further challenges. 

* Taking the patient's perspective, simple interaction and safety against harmful recommendations might be the prioritized concern. 
* For clinicians and experts, on the other hand, what matters is precise and accurate content. 
* Healthcare and insurance providers and clinics all have other priorities. 

This workshop will deepen the discussions started at the three prior workshops and will work towards further development of the research topics in Health Recommender Systems.

- http://132.199.138.79/healthrecsys/papers/index.html
- http://ceur-ws.org/Vol-1953/
- https://recsys.acm.org/recsys18/healthrecsys/
- https://healthrecsys.github.io/2019/
- https://www.vis.uni-konstanz.de/en/members/schaefer/
- https://www.christophtrattner.info/
- [Towards Health (Aware) Recommender Systems](https://www.christophtrattner.info/pubs/DH2017.pdf)
- [HealthRecSys 2018 Health Recommender Systems](http://ceur-ws.org/Vol-2216/)
- [UMUAI: Special Issue on Recommender Systems for Health and Wellbeing](https://healthrecsys.github.io/umuai/)
- [SeWeBMeDa 2019 Semantic Web Solutions for Large-Scale Biomedical Data Analytics](http://ceur-ws.org/Vol-2477/)
- [2019 KDD Workshop on Applied Data Science for Healthcare](https://dshealthkdd.github.io/dshealth-2019/)
- https://dshealthkdd.github.io/dshealth-2019/#papers
- [Health Recommender Systems: Concepts, Requirements, Technical Basics and Challenges](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3968965/)
- [Health Recommender System using Big data analytics](http://ibii-us.org/Journals/JMSBI/V2N2/Publish/V2N2_3.pdf)
- [Health Recommender System in Social Networks: A Case of Facebook](http://www.webology.org/2019/v16n1/a178.pdf)
- [Health Recommender research project](https://healthrecommender.org/)
- [Consumers’ intention to use health recommendation systems to receive personalized nutrition advice](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC3623628/)
- [Visual instance-based recommendation system for medical data mining](https://www.sciencedirect.com/science/article/pii/S1877050917316009)
- [Health Recommender System design in the context of CAREGIVERSPRO-MMD Project](https://caregiversprommd-project.eu/wp-content/uploads/Olive-Felipe-et-al.pdf)
- [Towards Health (Aware) Recommender Systems](https://dl.acm.org/citation.cfm?id=3079499)
- [Personalized Recommendation System for Medical Assistance using Hybrid Filtering](https://www.ijcaonline.org/research/volume128/number9/salunke-2015-ijca-906626.pdf)
- [Designing a Mobile Recommender System for Treatment Adherence Improvement among Hypertensives](https://fruct.org/publications/fruct22/files/Zav.pdf)
- https://caregiversprommd-project.eu/
- https://wiki.aalto.fi/display/~llahti@aalto.fi/Lauri+Lahti
- https://fruct.org/
- [A Systematic Literature Review on Health Recommender Systems](https://www.researchgate.net/publication/261488604_A_systematic_literature_review_on_Health_Recommender_Systems)
- http://people.dbmi.columbia.edu/noemie/
- [MACHINE LEARNING FOR HEALTHCARE (MLHC)](http://www.mucmd.org/)
- [Microsoft’s focus on transforming healthcare: Intelligent health through AI and the cloud](https://blogs.microsoft.com/blog/2018/02/28/microsofts-focus-transforming-healthcare-intelligent-health-ai-cloud/)
- https://www.cs.ubc.ca/~rng/
- http://homepages.inf.ed.ac.uk/ckiw/
- http://groups.csail.mit.edu/medg/people/psz/home/Pete_MEDG_site/Home.html
- [MIT CSAIL Clinical Decision Making Group](http://groups.csail.mit.edu/medg/)


### Recommdender System for Doctor 

[Finding a primary care doctor is simpler than it used to be, thanks to on-demand services like ZocDoc, SimplyBook, and Doodle. 
But matching up with a clinician who’s compatible with your (or your family’s) personality is another story.](https://venturebeat.com/2018/08/14/researchers-use-ai-to-match-patients-with-primary-care-doctors/)


* [Which Doctor to Trust: A Recommender System for Identifying the Right Doctors](https://www.ncbi.nlm.nih.gov/pmc/articles/PMC4956912/?report=printable)
* [Recommendation of Doctors and Medicines Using Review Mining](https://www.leadingindia.ai/downloads/projects/HC/hc_10.pdf)
* [Which Doctor to Trust: A Recommender System for Identifying the Right Doctors](https://www.researchgate.net/publication/305036152_Which_Doctor_to_Trust_A_Recommender_System_for_Identifying_the_Right_Doctors)

___


The recommender system is the core component of the social network named HealthNet (HN).
The recommendation algorithm first computes similarities among patients, and then generates a ranked list of doctors and hospitals suitable for a given patient profile, by exploiting health data shared by the community. 
Accordingly, the HN user can find her most similar patients, look how they cured their diseases, and receive suggestions for solving her problem.

HN is implemented as a standard social network where users are `patients`. 
The first interaction with the system is the registration step. 
Then, the patient can enter `personal health data`: conditions, treatments (e.g., drugs, dosages, side effects, surgeries), health indicators (e.g., blood pressure, body weight, laboratory analysis, etc.), consulted doctors, hospitalizations.
In this way, HN centralizes individual health data and allows a simple and organized `access` to them.

The Recommender System is the core component of HN. 
It exploits patient profiles for suggesting other `similar` patients, doctors,hospitals (the list of suggested, patients, doctors and hospitals can be further filtered by position and disease). 
The similarity between two patients $p,p^{\prime}$ is computed in terms of conditions and treatments. 
The `semantic matching` between the conditions exploits the [HN disease hierarchy](http://www.www2015.it/documents/proceedings/companion/p81.pdf).
More formally, the similarity score between two
patients is computed as follows:
$$s(p, p^{\prime}) =
\alpha\frac{\sum_{i=1}^{k}\sum_{j=1}^{n}s_c(p_{c_i}, p^{\prime}_{c_j})}{kn}\\
+ (1-\alpha)\frac{\sum_{i=1}^{z}\sum_{j=1}^{r}s_t(p_{t_i}, p^{\prime}_{t_j})}{zr}
$$
where $k$ (respectively $n$) is the number of conditions $p$ (respectively $p^{\prime}$) is affected by, 
$p_c$ is a condition of the patient $p$,
$z$ (respectively $r$) is the number of treatments for $p$ (respectively $p^{\prime}$), 
$p_t$ is a treatment for the patient $p$.
They are computed as follows:
$$s_c(p_{c_i}, p^{\prime}_{c_j}) =
\begin{cases}
\log\frac{p_{c_i}}{p^{\prime}_{c_j}}, &\text{if $c_i=c_j$}\\
\frac{1}{sp(c_i, c_j)}, &\text{otherwise}
\end{cases},
s_t(p_{t_i}, p^{\prime}_{t_j}) =
\begin{cases}
1, &\text{if $t_i=t_j$}\\
0, &\text{otherwise}
\end{cases}.
$$

* [A Recommender System for Connecting Patients to the Right Doctors in the HealthNet Social Network](http://www.www2015.it/documents/proceedings/companion/p81.pdf)

#### Patient-Doctor Matchmaking

There are different perspectives of patient-doctor matchmaking system:

- From patients’ perspectives, such systems should provide `explainable` recommendations and safeguard against poor recommendations in order to be
trustworthy. 
- From the perspective of healthcare professionals, these systems need to provide suitable recommendations based on their `domain knowledge and experience`. 
- More generally, insurance companies and healthcare institutes are interested in improving recommendation rates through research and reaping the potential benefits of these recommendation systems.

The features include demographic data, behevioral data, ICD-9, interaction, the number of visits to the doctor.


[A Hybrid Recommender System for Patient-Doctor Matchmaking in Primary Care](https://arxiv.org/abs/1808.03265) perform `hybrid matrix
factorization (MF)` and recommend each patient a list of family doctors according to the level of information available about them.
We achieve this by learning `latent representations` for patients and doctors from their interactions and metadata


Given the different level of information available to us about different patients,  five use cases are proposed to make doctor recommendations in different scenarios.

The patient-doctor interaction matrix $Y \in \mathbb{R}^{M\times N}$ is defined as:
$$y_{ij} =
\begin{cases}
1, &\text{if interaction (patient i, doctor j) exists}\\
0, &\text{otherwise}
\end{cases}
$$

MF learns $\mathbf{p}_i$ and $\mathbf{q}_j$, such that the predicted score for
unobserved entries $\hat{y}_{ij}$ is given by the `inner product` of latent
patient and doctor representations:
$$\hat{y}_{ij}=g(i,j\mid \mathbf{p}_i, \mathbf{q}_j)=g(\mathbf{p}_i\cdot \mathbf{q}_j)=\frac{1}{1+\exp(\left<\mathbf{p}_i,\mathbf{q}_j)\right>}.$$

Then formulate a learning-to-rank task by using `Weighted Approximate-Rank Pairwise (WARP) loss`.
For each observed interaction $\hat{y}_{ij}$, WARP samples a negative doctor $d$ and computes the difference between predicted $\hat{y}_{ij}$ and $\hat{y}_{id}$, 
and performs a gradient update to rank the positive doctor higher if the difference is negative,
i.e., a rank violation is found.
Otherwise, it continues sampling negative doctors until it identifies a violating example. 
Thus, the rank of doctor j for patient i is minimized when taking a large number of sampled doctors d that need to be considered
before finding a violating example.

We can model the trust $T_{ij} (t)$ between a patient $i$ and a family doctor $j$ at time $t$, given both the frequency and recency of their consultation
history as:
$$T_{ij} (t)=\sum_{t}\sum_{k}\frac{C_{ij}(t)e^{-\lambda t}}{C_{ik}(t)}$$
where $\lambda$ is annualized discount rate for the exponential
decay function and treated as hyper-parameter during the
model training, $C_{ij}(t)$ is the number of consultations between
patient $i$ and doctor $j$ until year $t$, which is normalized by
the total number of her consultations with $k$ doctors $C_{ik} (t)$
thus far. 

- [Collaborative Filtering for Implicit Feedback Datasets](http://yifanhu.net/PUB/cf.pdf)
* [AI Researchers use AI to match patients with primary care doctors](https://venturebeat.com/2018/08/14/researchers-use-ai-to-match-patients-with-primary-care-doctors/)
* [A Hybrid Recommender System for Patient-Doctor Matchmaking in Primary Care](https://arxiv.org/abs/1808.03265)
* http://www.suggestadoctor.com/
* https://www.researchgate.net/profile/Bo_Jin16
* https://orcid.org/0000-0002-4209-4637
* https://nyulangone.org/doctors
* https://destrin.smalldata.io/
* https://smalldata.io/
* http://www.www2015.it/industrial-track/
* http://www.itu.dk/~bardram/pmwiki/
* http://www.bardram.net/
* http://www.cachet.dk/
* https://www.researchgate.net/profile/Jakob_Bardram
* https://wp.cs.ucl.ac.uk/acm-digitalhealth-2015/alberto-sanna/
* https://www.acm-digitalhealth.org/2018/committee/alberto-sanna/index.html
* https://research.hsr.it/en/index.html

### DeepReco

- [DeepReco: Deep Learning Based Health Recommender System Using Collaborative Filtering](https://www.mdpi.com/2079-3197/7/2/25/htm)
- https://utd-ir.tdl.org/handle/10735.1/7542

## Resource on RecSys


- http://www.cs.ucr.edu/~cshelton/
- http://hst.mit.edu/users/rgmarkmitedu
- http://erichorvitz.com/
- https://www.hms.harvard.edu/dms/neuroscience/fac/Kohane.php
- https://www.khoury.northeastern.edu/people/carla-brodley/
- https://mquad.github.io/
- https://www.aau.at/en/ainf/research-groups/infsys/team/dietmar-jannach/
- https://xamat.github.io/
- http://presnick.people.si.umich.edu/
- https://www.stern.nyu.edu/faculty/bio/alexander-tuzhilin
- http://people.stern.nyu.edu/atuzhili/
- https://www.researchgate.net/profile/Markus_Zanker
- https://cseweb.ucsd.edu/~jmcauley/datasets.html
* https://zhuanlan.zhihu.com/p/87293483
* https://www.zhihu.com/question/336304380/answer/784976195
* [最新！五大顶会2019必读的深度推荐系统与CTR预估相关的论文 - 深度传送门的文章 - 知乎](https://zhuanlan.zhihu.com/p/69050253)
* [深度学习在搜索和推荐系统中的应用](https://blog.csdn.net/malefactor/article/details/52040228)
* [CSE 258: Web Mining and Recommender Systems](http://cseweb.ucsd.edu/classes/fa18/cse258-a/)
* [CSE 291: Trends in Recommender Systems and Human Behavioral Modeling](https://cseweb.ucsd.edu/classes/fa17/cse291-b/)
* [THE AAAI-19 WORKSHOP ON RECOMMENDER SYSTEMS AND NATURAL LANGUAGE PROCESSING (RECNLP)](https://recnlp2019.github.io/)
* [Information Recommendation for Online Scientific Communities, Purdue University, Luo Si, Gerhard Klimeck and Michael McLennan](https://www.cs.purdue.edu/homes/lsi/CI_Recom/CI_Recom.html)
* [Recommendations for all : solving thousands of recommendation problems a day](https://ai.google/research/pubs/pub46822)
* http://staff.ustc.edu.cn/~hexn/
* [Learning Item-Interaction Embeddings for User Recommendations](https://arxiv.org/abs/1812.04407)
* [Summary of RecSys](https://github.com/fuxuemingzhu/Summary-of-Recommender-System-Papers)
* [How Netflix’s Recommendations System Works](https://help.netflix.com/en/node/100639)
* [个性化推荐系统，必须关注的五大研究热点](https://www.msra.cn/zh-cn/news/executivebylines/tech-bylines-personalized-recommendation-system)
* [How Does Spotify Know You So Well?](https://medium.com/s/story/spotifys-discover-weekly-how-machine-learning-finds-your-new-music-19a41ab76efe)
* [推荐系统论文集合](https://daiwk.github.io/posts/links-navigation-recommender-system.html)
* http://csse.szu.edu.cn/staff/panwk/recommendation/
* https://hong.xmu.edu.cn/Services___fw/Recommender_System.htm
* https://blog.statsbot.co/recommendation-system-algorithms-ba67f39ac9a3
* https://buildingrecommenders.wordpress.com/
* https://homepages.dcc.ufmg.br/~rodrygo/recsys-2019-1/
* https://developers.google.com/machine-learning/recommendation/
* https://sites.google.com/view/lianghu/home/tutorials/ijcai2019
* https://acmrecsys.github.io/rsss2019/
* https://github.com/alibaba/x-deeplearning/wiki
* https://apple.github.io/turicreate/docs/userguide/recommender/

### Labs

- http://www.christophtrattner.com/
- http://elizabethchurchill.com/presentations/
- http://www.that-recsys-lab.net/
- https://www.christophtrattner.info/publications.html
- https://www.ludovicoboratto.com/publications/
- https://www.ucsm.info/publications
- http://recsys.deib.polimi.it/
- https://www.know-center.tugraz.at/en/publications/publications/
- https://qcri.academia.edu/LuisLuque
- http://www.martijnwillemsen.nl/recommenderlab/
- https://cseweb.ucsd.edu/~jmcauley/
- https://github.com/mJackie/RecSys
- https://piret.gitlab.io/fatrec/
- https://ailab.criteo.com/publications/
- https://layer6.ai/
- https://cseweb.ucsd.edu/~jmcauley/career.html
- [Recommender Systems](http://csse.szu.edu.cn/csse.szu.edu.cn/staff/panwk/recommendation/index.html)
- https://libraries.io/github/computational-class
- http://www.52caml.com/
- http://www-scf.usc.edu/~kuanl/
- http://www.yjzheng.com/

### Workshop 

+ [DLRS 2018 : 3rd Workshop on Deep Learning for Recommender Systems](http://www.wikicfp.com/cfp/servlet/event.showcfp?eventid=76328&copyownerid=87252)
+ [Deep Learning based Recommender System: A Survey and New Perspectives](https://arxiv.org/pdf/1707.07435.pdf)
+ [$5^{th}$ International Workshop on Machine Learning Methods for Recommender Systems](https://doogkong.github.io/2019/)
+ [MoST-Rec 2019: Workshop on Model Selection and Parameter Tuning in Recommender Systems](http://most-rec.gt-arc.com/)
+ [2018 Personalization, Recommendation and Search (PRS) Workshop](https://prs2018.splashthat.com/)
+ [WIDE & DEEP RECOMMENDER SYSTEMS AT PAPI](https://www.papis.io/recommender-systems)
+ [Interdisciplinary Workshop on Recommender Systems](http://www.digitaluses-congress.univ-paris8.fr/Interdisciplinary-Workshop-on-Recommender-Systems)
+ [2nd FATREC Workshop: Responsible Recommendation](https://piret.gitlab.io/fatrec2018/)
- [ ] [Social Media Mining: An Introduction](http://dmml.asu.edu/smm/slides/)
- [ ] [The 2nd International Workshop on ExplainAble Recommendation and Search (EARS 2019)](https://ears2019.github.io/)
- [ ] [NLP meets RecSys](https://recnlp2019.github.io/)
- [ ] http://dmml.asu.edu/smm/slide/SMM-Slides-ch9.pdf
- [ ] [PRS 2019](https://prs2018.splashthat.com/)
- [ ] https://dlp-kdd.github.io/
- [ ] https://recsys.acm.org/blog/

### Implementation


- [ ] [Surprise: a Python scikit building and analyzing recommender systems](http://surpriselib.com/)
- [ ] [Orange3-Recommendation: a Python library that extends Orange3 to include support for recommender systems.](https://orange3-recommendation.readthedocs.io/en/latest/)
- [ ] [MyMediaLite: a recommender system library for the Common Language Runtime](http://www.mymedialite.net/index.html)
- [ ] http://www.mymediaproject.org/
- [Workshop: Building Recommender Systems with Apache Spark 2.x](https://qcon.ai/qconai2019/workshop/building-recommender-systems-w-apache-spark-2x)
- [A Leading Java Library for Recommender Systems](https://www.librec.net/)
- [lenskit: Python Tools for Recommender Experiments](https://lenskit.org/)
- [Samantha - A generic recommender and predictor server](https://grouplens.github.io/samantha/)
* http://libfm.org/
* https://github.com/srendle/libfm
* https://www.csie.ntu.edu.tw/~cjlin/libffm/
* https://github.com/srendle
* https://github.com/lyst/lightfm
* https://github.com/guoguibing/librec
* https://recbole.io/index.html

********************

* [TensorFlow implementation of an arbitrary order Factorization Machine](https://github.com/geffy/tffm)
* https://github.com/tensorflow/recommenders
* https://github.com/fuhailin/DeePray
- [ ] https://github.com/gasevi/pyreclab
- [ ] https://github.com/cheungdaven/DeepRec
- [ ] https://github.com/cyhong549/DeepFM-Keras
- [ ] https://github.com/grahamjenson/list_of_recommender_systems
- [ ] https://github.com/maciejkula/spotlight
- [ ] https://github.com/Microsoft/Recommenders
- [ ] https://github.com/alibaba/euler
- [ ] https://github.com/alibaba/x-deeplearning/wiki/
- [ ] https://github.com/lyst/lightfm


# Preference Learning


> [Roughly speaking,](http://www.ke.tu-darmstadt.de/events/PL-10/) preference learning is about methods for learning preference models from explicit or implicit preference information, typically used for predicting the preferences of an individual or a group of individuals. Approaches relevant to this area range from learning special types of preference models, such as lexicographic orders, over "learning to rank" for information retrieval to collaborative filtering techniques for recommender systems.

- http://www.ke.tu-darmstadt.de/events/PL-10/
- http://www.preference-learning.org/
- [Preference Learning: Problems and Applications in AI (PL-12) ECAI-12 Workshop, Montpellier](http://www.ke.tu-darmstadt.de/events/PL-12/workshop.html)
- [From Multiple Criteria Decision Aid to Preference Learning](https://event.unitn.it/da2pl2020/)
- [Research Workshop on AI for Preference Learning: Sentiment, Comparison, and Recommendation](https://scis.smu.edu.sg/newsletter/31391)
- [PREFERENCE LEARNING   WHAT DEFINES AN OPTIMAL SHIFT SCHEDULE?](https://essay.utwente.nl/80170/1/van%20Weersel_MA_BMS.pdf)
- [Preference Learning: A Tutorial Introduction](http://www.preference-learning.org/PL-Tutorial-DS-11.pdf)
- [Preference Learning: An Introduction](http://www.ke.tu-darmstadt.de/publications/papers/PLBook-Introduction.pdf)
- http://plt.institutedigitalgames.com/
- http://www.gatsby.ucl.ac.uk/~chuwei/

## Pairwise Preference Learning and Ranking

- [Pairwise Preference Learning and Ranking](http://www.ofai.at/cgi-bin/get-tr?paper=oefai-tr-2003-14.pdf)
- [Preference Learning and Ranking by Pairwise Comparison](http://www.ke.tu-darmstadt.de/publications/papers/PLBook-Pairwise.pdf)
- [Preference Uncertainty, Preference Learning, and Paired Comparison Experiments ](https://www.fs.fed.us/rm/value/docs/preference_uncertainty_learning_paired_comparison.pdf)
- [Learning Mallows Models with Pairwise Preferences](https://icml.cc/2011/papers/135_icmlpaper.pdf)

## Collaborative Preference Learning



- [Collaborative Gaussian Processes for Preference Learning](https://papers.nips.cc/paper/2012/hash/afdec7005cc9f14302cd0474fd0f3c96-Abstract.html)
- [Poster Collaborative Gaussian Processes for Preference Learning](https://jmhldotorg.files.wordpress.com/2013/11/posternipscollaborativegaussianprocesses2012.pdf)
- [Scalable Collaborative Bayesian Preference Learning](http://proceedings.mlr.press/v33/khan14.pdf)
- [Collaborative Preference Learning: A Case Study](https://ieeexplore.ieee.org/document/9255131)
- [Collaborative Context-aware Preference Learning](http://users.cecs.anu.edu.au/~sguo/cmpl2011_submission_4.pdf)
- [Neural Collaborative Preference Learning with Pairwise Comparisons](https://ieeexplore.ieee.org/document/9141200)


## Preference Learning and Gaussian Processes

- [Multi-Task Preference Learning with Gaussian Processes](https://www.elen.ucl.ac.be/Proceedings/esann/esannpdf/es2009-122.pdf)
- [Gaussian Process Preference Elicitation](http://users.cecs.anu.edu.au/~ssanner/Papers/gppe_final.pdf)
- [Extensions of Gaussian Processes for Ranking: Semi-supervised and Active Learning](http://www.gatsby.ucl.ac.uk/~chuwei/paper/gprl.pdf)
- [Preference Learning with Gaussian Processes](https://icml.cc/Conferences/2005/proceedings/papers/018_Preference_ChuGhahramani.pdf)
- https://github.com/neilhoulsby/pref_learning
- [Fast Active Exploration for Link-Based Preference Learning using Gaussian Processes](https://www.cs.cornell.edu/people/tj/publications/xu_etal_10a.pdf)

## Preference Learning and Choice Model


Preference learning has been studied for several decades and has drawn increasing attention in recent years due to its importance in web applications, such as ad serving, search, and electronic commerce. In all of these applications, we observe (often discrete) choices that reflect relative preferences among several items, e.g. products, songs, web pages or documents. Moreover, observations are in many cases censored. Hence, the goal is to reconstruct the overall model of preferences by, for example, learning a general ordering function based on the partially observed decisions.
Choice models try to predict the specific choices individuals (or groups of individuals) make when offered a possibly very large number of alternatives. Traditionally, they are concerned with the decision process of individuals and have been studied independently in machine learning, data and web mining, econometrics, and psychology. However, these diverse communities have had few interactions in the past. One goal of this workshop is to foster interdisciplinary exchange, by encouraging abstraction of the underlying problem (and solution) characteristics.


- [Choice Models and Preference Learning Workshop](https://www.k4all.org/event/choice-models-and-preference-learning-workshop/)
- [The 12th International Conference on Modeling Decisions for Artificial Intelligence](http://www.mdai.cat/mdai2015/)
- [Choice Models and Preference Learning: NIPS workshop, 17 December 2011, Sierra Nevada, Spain](https://sites.google.com/site/cmplnips11/)
- [Active Preference Learning with Discrete Choice Data](https://www.cs.ubc.ca/~nando/papers/interface.pdf)
- [A rational model of preference learning and choice prediction by children](https://cocosci.princeton.edu/tom/papers/preferences1.pdf)
- [Modeling preference evolution in discrete choice models: A Bayesian state-space approach](https://www8.gsb.columbia.edu/researcharchive/articles/2372)




### Modeling Users’ Preferences


> The ever-growing nature of user generated data in online systems poses obvious challenges on how we process such data. Typically, this issue is regarded as a scalability problem and has been mainly addressed with distributed algorithms able to train on massive amounts of data in short time windows. However, data is inevitably adding up at high speeds. Eventually one needs to discard or archive some of it. Moreover, the dynamic nature of data in user modeling and recommender systems, such as change of user preferences, and the continuous introduction of new users and items make it increasingly difficult to maintain up-to-date, accurate recommendation models.

- [Workshop on Online Recommender Systems and User Modeling](https://recsys.acm.org/recsys19/orsum/)
- [Modeling Users’ Preferences and Social Links in Social Networking Services: A Joint-Evolving Perspective](http://staff.ustc.edu.cn/~cheneh/paper_pdf/2016/Le-Wu-AAAI.pdf)
- [Modeling and Learning User Preferences Over Sets](https://www.seas.upenn.edu/~eeaton/papers/Wagstaff2010Modeling.pdf)
- [Modeling the Dynamics of User Preferences in Coupled Tensor Factorization](http://delab.csd.auth.gr/papers/RecSys2014rn.pdf)
- [Modeling Users’ Mobile App Privacy Preferences: Restoring Usability in a Sea of Permission Settings](https://www.usenix.org/system/files/conference/soups2014/soups14-paper-lin.pdf)
- [Adaptive User Modeling with Long and Short-Term Preferences for Personalized Recommendation](https://www.ijcai.org/Proceedings/2019/0585.pdf)
- [bbbbbbbbbbbbbbbbbb](http://ceur-ws.org/Vol-2711/paper40.pdf)
- https://fangyuan1st.github.io/paper/ECML16_SEQ_slides.pdf
- [Deep Modeling of the Evolution of User Preferences and Item Attributes in Dynamic Social Networks](https://dl.acm.org/doi/10.1145/3184558.3186956)

# Computational Advertising

`Advertising, recommendation and search` is 3 fundation stone of e-economics.

- https://www.ecommercefoundation.org/reports

Online advertising has grown over the past decade to over 26 billion dollars in recorded revenue in 2010. 
The revenues generated are based on different pricing models that can be fundamentally grouped into two types: 
cost per (thousand) impressions (CPM) and cost per action (CPA), 
where an action can be a click, signing up with the advertiser, a sale, or any other measurable outcome. 
A web publisher generating revenues by selling advertising space on its site can offer either a CPM or CPA contract. 
We analyze the conditions under which the two parties agree on each contract type, accounting for the relative risk experienced by each party.

The information technology industry relies heavily on the on-line advertising such as [Google，Facebook or Alibaba].
Advertising is nothing except information, which is not usually accepted gladly. 
In fact, it is more difficult than recommendation because it is less known of the context where the advertisement is placed.


[Hongliang Jie](http://www.hongliangjie.com/talks/Etsy_ML.pdf) shares 3 challenges of computational advertising in Etsy,
which will be the titles of the following subsections.

<img title="ad" src="https://gokulchittaranjan.files.wordpress.com/2016/06/blog-on-advertising-figures-e1466486030771.png" width="70%" />

* [广告为什么要计算](https://zhuanlan.zhihu.com/p/72092504)
* [计算广告资料汇总](https://www.jianshu.com/p/8c591feb9fc4)
* [ONLINE VIDEO ADVERTISING: All you need to know in 2019](https://strategico.io/video-advertising/)
* [计算广告](https://dirtysalt.github.io/html/computational-advertising.html)
* [计算广告和机器学习](http://www.52caml.com/)
* https://headerbidding.co/category/adops/
* [Deep Learning Based Modeling in Computational Advertising: A Winning Formula](https://www.omicsonline.org/open-access/deep-learning-based-modeling-in-computational-advertising-a-winning-formula-2169-0316-1000266.pdf)
* [Computational Marketing](https://www.marketing-schools.org/types-of-marketing/computational-marketing.html)
* [Data Science and Analytics in Computational Advertising](https://gokulchittaranjan.wordpress.com/2016/06/22/datascienceinadvertising/)
* [Counterfactual Reasoning and Learning Systems: The Example of Computational Advertising](https://www.microsoft.com/en-us/research/wp-content/uploads/2013/11/bottou13a.pdf)
* [Text Mining in Computational Advertising](https://www.valassisdigital.com/us/wp-content/uploads/sites/7/2017/01/Whitepaper_TextMining.pdf)
* https://stat.duke.edu/people/david-l-banks
* http://wnzhang.net/teaching/ee448/
* https://recsys.acm.org/recsys08/keynotes/
* https://www.researchgate.net/profile/Andrei_Broder

## Click-Through Rate Modeling


**GBRT+LR**

When the feature vector ${x}$ are given, the tree split the features by GBRT then we transform and input the features to the logistic regression.

[Practical Lessons from Predicting Clicks on Ads at Facebook](https://www.jianshu.com/p/96173f2c2fb4) or the [blog](https://zhuanlan.zhihu.com/p/25043821) 
use the GBRT to select proper features and LR to map these features into the interval $[0,1]$ as a ratio.
Once we have the right features and the right model (decisions trees plus logistic regression), 
other factors play small roles (though even small improvements are important at scale).

<img src="https://pic4.zhimg.com/80/v2-fcb223ba88c456ce34c9d912af170e97_hd.png" width = "40%" />

* [Learning Piece-wise Linear Models from Large Scale Data for Ad Click Prediction](https://arxiv.org/abs/1704.05194)
* [聊聊CTR预估的中的深度学习](http://kubicode.me/2018/03/19/Deep%20Learning/Talk-About-CTR-With-Deep-Learning/)
* [Deep Models at DeepCTR](https://deepctr.readthedocs.io/en/latest/models/DeepModels.html)
* [镶嵌在互联网技术上的明珠：漫谈深度学习时代点击率预估技术进展](https://zhuanlan.zhihu.com/p/54822778)
* [CTR预估算法之FM, FFM, DeepFM及实践](https://blog.csdn.net/john_xyz/article/details/78933253)
* [Turning Clicks into Purchases](https://www.hongliangjie.com/talks/SF_2018-05-09.pdf)
* https://github.com/shenweichen/DeepCTR
* https://github.com/wzhe06/CTRmodel
* https://github.com/cnkuangshi/LightCTR
* https://github.com/evah/CTR_Prediction
* http://2016.qconshanghai.com/track/3025/
* https://blog.csdn.net/u011747443/article/details/68928447

## Conversion Rate Modeling

+ [ ] [Post-Click Conversion Modeling and Analysis for Non-Guaranteed Delivery Display Advertising](http://people.csail.mit.edu/romer/papers/NGDAdvertisingWSDM12.pdf)
+ [ ] [Estimating Conversion Rate in Display Advertising from Past Performance Data](http://wnzhang.net/share/rtb-papers/cvr-est.pdf)
+ [ ] [https://www.optimizesmart.com/](https://www.optimizesmart.com/introduction-machine-learning-conversion-optimization/)

## Bid Optimization

+ [A collection of research and survey papers of real-time bidding (RTB) based display advertising techniques.](https://github.com/wnzhang/rtb-papers)

****


* http://yelp.github.io/MOE/
* http://www.hongliangjie.com/talks/AICon2018.pdf
* https://sites.google.com/view/tsmo2018/invited-talks
* https://matinathomaidou.github.io/research/
* https://www.usermind.com/
______________________________________________________

## User Engagement

[User engagement measures whether users find value in a product or service. Engagement can be measured by a variety or combination of activities such as downloads, clicks, shares, and more. Highly engaged users are generally more profitable, provided that their activities are tied to valuable outcomes such as purchases, signups, subscriptions, or clicks.](https://mixpanel.com/topics/what-is-user-engagement/)

* [WHAT IS USER ENGAGEMENT?](https://mixpanel.com/topics/what-is-user-engagement/)
* [What is Customer Engagement, and Why is it Important?](https://blog.smile.io/what-is-customer-engagement-and-why-is-it-important)
* [What is user engagement? A conceptual framework for defining user engagement with technology](https://open.library.ubc.ca/cIRcle/collections/facultyresearchandpublications/52383/items/1.0107445)
* [How to apply AI for customer engagement](https://www.pega.com/artificial-intelligence-applications)
* [The future of customer engagement](https://dma.org.uk/event/the-future-of-customer-engagement)
* [Second Uber Science Symposium: Exploring Advances in Behavioral Science](https://eng.uber.com/second-uber-science-symposium-behavioral-science)
* [Measuring User Engagement](https://mounia-lalmas.blog/2013/04/29/measuring-user-engagement/)
* https://uberbehavioralsciencesymposium.splashthat.com/
* https://inlabdigital.com/
* https://www.futurelab.net/
* http://www.ueo-workshop.com/
- [The User Engagement Optimization Workshop2](http://www.ueo-workshop.com/)
- [The User Engagement Optimization Workshop1](http://www.ueo-workshop.com/previous-editions/ueo-2013-at-cikm-2013/)
- [EVALUATION OF USER EXPERIENCE IN MOBILE ADVERTISI](http://galjot.si/research)
- [WWW 2019 Tutorial on Online User Engagement](https://onlineuserengagement.github.io/)
- http://www.ueo-workshop.com/
- http://www.ueo-workshop.com/program/
- https://www.nngroup.com/
- https://labtomarket.eu/
- http://research.google.com/pubs/AmrAhmed.html
- https://home.ubalt.edu/ntsbarsh/business-stat/opre504.htm
- https://www.nersc.gov/about/nersc-staff/user-engagement/
- https://www.microsoft.com/en-us/research/people/eladyt/
- http://yom-tov.info/

## User Modeling

[User models are used to generate or adapt user interfaces at runtime, to address particular user needs and preferences. User models are also known as user profiles, personas or archetypes. They can be used by designers and developers for personalisation purposes and to increase the usability and accessibility of products and services.](https://www.w3.org/WAI/RD/wiki/User_modeling)

- https://www.um.org/
- https://www.um.org/umap2020/
- https://www.um.org/awards/best-paper-awards
- https://www.w3.org/WAI/RD/wiki/User_modeling
- https://www2018.thewebconf.org/program/user-modeling/
- http://kdd2018tutorial-behavior.datasciences.org/
- https://www2019.thewebconf.org/research-track/user-modeling-personalization-and-experience
- [User Modeling: Recent Work, Prospects and Hazards1](https://www.ics.uci.edu/~kobsa/papers/1993-aui-kobsa.pdf)
- [Research on the Use, Characteristics, and Impact of e-Commerce Product Recommendation Agents: A Review and Update for 2007–2012](https://link.springer.com/chapter/10.1007%2F978-3-642-39747-9_18)
- [Beyond Bags of Words: Modeling Implicit User Preferences in Information Retrieval](http://ciir.cs.umass.edu/pubfiles/ir-491.pdf)
- [Modeling User Exposure in Recommendation](http://www.cs.columbia.edu/~blei/papers/LiangCharlinMcInerneyBlei2016.pdf)
- [E-Commerce Product Recommendation Agents: Use, Characteristics, and Impact](https://misq.org/catalog/product/view/id/222)
- [Modeling User Preferences and Mediating Agents in Electronic Commerce](http://ii.tudelft.nl/~catholijn/publications/sites/default/files/Dastani_Modeling%20user%20preferences%202001.pdf)
- http://www.humanize-workshop.org/
- http://iwum.org/


## Resource

### Labs

- http://www.thuir.cn/group/~mzhang/
- http://www.shichuan.org/
- [洪亮劼，博士 – Etsy工程总监](https://www.hongliangjie.com/)
- [Data Mining Machine Learning @The University of Texas at Austin](http://www.ideal.ece.utexas.edu/)
- [Center for Big Data Analytics @The University of Texas at Austin](https://bigdata.oden.utexas.edu/)
- [Multimedia Computing Group@tudelft.nl](https://www.tudelft.nl/ewi/over-de-faculteit/afdelingen/intelligent-systems/multimedia-computing/)
- [knowledge Lab@Uchicago](https://www.knowledgelab.org/)
- [DIGITAL TECHNOLOGY CENTER@UMN](https://www.dtc.umn.edu/)
- [The Innovation Center for Artificial Intelligence (ICAI)](https://icai.ai/)
- [Data Mining and Machine Learning lab (DMML)@ASU](http://dmml.asu.edu/)
- [Next Generation Personalization Technologies](http://ids.csom.umn.edu/faculty/gedas/NSFcareer/)
- [Recommender systems & ranking](https://sites.google.com/view/chohsieh-research/recommender-systems)
- [Secure Personalization: Building Trustworthy Recommender Systems](https://www.nsf.gov/awardsearch/showAward?AWD_ID=0430303)
- [Similar grants of  Next Generation Personalization Technologies](https://app.dimensions.ai/details/grant/grant.3063812)
- [Big Data and Social Computing Lab @UIC](https://bdsc.lab.uic.edu/)
- [Web Intelligence and Social Computing](https://www.cse.cuhk.edu.hk/irwin.king/wisc_lab/home)
- [Welcome to the family, Zalando AdTech Lab Hamburg!](https://jobs.zalando.com/tech/blog/zalando-adtech-lab-hamburg/)
- [Data and Marketing Associat](https://dma.org.uk/)
- [Web search and data mining(WSDM) 2019](http://www.wsdm-conference.org/2019/)
- [Web Intelligent Systems and Economics(WISE) lab @Rutgers](https://wise.cs.rutgers.edu/)
- [Ishizuka Lab. was closed. (2013.3) ](http://www.miv.t.u-tokyo.ac.jp/HomePageEng.html)
- [Online Marketing Congress 2017](https://gorrion.io/blog/online-marketing-congress-2017)
- [course-materials of Sys for ML/AI](https://pooyanjamshidi.github.io/mls/course-materials/)
- https://sigopt.com/blog/
- [Web Understanding, Modeling, and Evaluation Lab](http://wume.cse.lehigh.edu/)
- https://knightlab.northwestern.edu/
- https://bdsc.lab.uic.edu/

### Courese

* [Papers on Computational Advertising](https://github.com/wzhe06/Ad-papers)
* [CAP 6807: Computational Advertising and Real-Time Data Analytics](http://www.cse.fau.edu/~xqzhu/courses/cap6807.html)
* [Computational Advertising Contract Preferences for Display Advertising](https://www.soe.ucsc.edu/departments/technology-management/research/computational-advertising)
* [Machine Learning for Computational Advertising, UC Santa Cruz, April 22, 2009, Alex Smola, Yahoo Labs, Santa Clara, CA](http://alex.smola.org/teaching/ucsc2009/)
* [Computational Advertising and Recommendation](https://people.eecs.berkeley.edu/~jfc/DataMining/SP12/lecs/lec12.pdf)
* [Practical Lessons from Predicting Clicks on Ads at Facebook](http://quinonero.net/Publications/predicting-clicks-facebook.pdf)
* [advertising](https://web.njit.edu/~ychen/advertising.html)
* http://people.stern.nyu.edu/ja1517/
* [CS7792 - Counterfactual Machine Learning, Special Topics in Machine Learning](http://www.cs.cornell.edu/courses/cs7792/2018fa/)
* https://github.com/computational-class/computational-advertising-2015
* [Computational Advertising: Techniques for Targeting Relevant Ads](https://www.nowpublishers.com/article/Details/INR-045)
* http://catalog.illinois.edu/courses-of-instruction/adv/
* http://people.csail.mit.edu/morteza/
* [CAP 6807: Computational Advertising and Real-Time Data Analytics](http://www.cse.fau.edu/~xqzhu/courses/cap6807.html)
* [Tutorial: Information Retrieval Challenges in Computational Advertising](http://www.cikm2011.org/tutorials/PM3.html)