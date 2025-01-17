
# awesome-neural-ode
A collection of resources regarding the interplay between differential equations, dynamical systems, deep learning, control and scientific machine learning.

**NOTE:** Feel free to suggest additions via `Issues` or `Pull Requests`.

# Table of Contents

* **Differential Equations in Deep Learning**

	* [General Architectures](#general-architectures)
	
	* [Neural ODEs](#neural-odes)
	
		* [Training of Neural ODEs](#training-of-neural-odes)
		
		* [Speeding up continuous models](#speeding-up-continuous-models)
		
		* [Control with Neural ODEs](#control-with-neural-odes)
		
	* [Neural SDEs](#neural-sdes)
	
	* [Neural CDEs](#neural-cdes)
	
	* [Normalizing Flows](#normalizing-flows)
	
	* [Applications](#applications)
	
* **Deep Learning Methods for Differential Equations (Scientific ML)**

	* [Solving Differential Equations](#solving-differential-equations)
	
	* [Learning PDEs](#learning-pdes)
	
	* [Model Discovery](#model-discovery)
		
* **Dynamical System View of Deep Learning**

	* [Recurrent Neural Networks](#recurrent-neural-networks)
	
	* [Theory and Perspectives](#theory-and-perspectives)
	
	* [Optimization](#optimization)
	
* [Software and Libraries](#software-and-libraries)

* [Websites and Blogs](#websites-and-blogs)

## Differential Equations in Deep Learning

### General Architectures

* Recurrent Neural Networks for Multivariate Time Series with Missing Values: [Scientific Reports18](https://arxiv.org/abs/1606.01865)

> Multivariate time series data in practical applications, such as health care, geoscience, and biology, are characterized by a variety of missing values. We propose a GRU-based model called GRU-D, in which a decay mechanism is designed for the input variables and the hidden states to capture the aforementioned properties. We introduce decay rates in the model to control the decay mechanism by considering the following important factors.

* Learning unknown ODE models with Gaussian processes: [arXiv18](https://arxiv.org/abs/1803.04303), [code](https://github.com/cagatayyildiz/npde/)

> However, for many complex systems it is practically impossible to determine the equations or
interactions governing the underlying dynamics. In these settings, parametric ODE model cannot be formulated. Here, we overcome this issue by introducing a novel paradigm of nonparametric ODE modeling that can learn the underlying dynamics of arbitrary continuous-time systems without prior knowledge. We propose to learn non-linear, unknown differential functions from state observations using Gaussian process vector fields within the exact ODE formalism.

* Deep Equilibrium Models: [NeurIPS19](https://arxiv.org/abs/1909.01377)

> We present a new approach to modeling sequential data: the deep equilibrium model (DEQ). Motivated by an observation that the hidden layers of many existing deep sequence models converge towards some fixed point, we propose the DEQ approach that directly finds these equilibrium points via root-finding.

* Fast and Deep Graph Neural Networks: [AAAI20](https://arxiv.org/pdf/1911.08941.pdf)

* Hamiltonian Neural Networks: [NeurIPS19](https://arxiv.org/abs/1906.01563)

* Deep Lagrangian Networks: Using Physics as Model Prior for Deep Learning: [ICLR19](https://arxiv.org/abs/1907.04490)

* Lagrangian Neural Networks: [ICLR20 DeepDiffEq](https://arxiv.org/abs/2003.04630)

* Simplifying Hamiltonian and Lagrangian Neural Networks via Explicit Constraints: [NeurIPS20](https://arxiv.org/abs/2010.13581), [code](https://github.com/mfinzi/constrained-hamiltonian-neural-networks)

> Reasoning about the physical world requires models that are endowed with the right inductive biases to learn the underlying dynamics. Recent works improve generalization for predicting trajectories by learning the Hamiltonian or Lagrangian of a system rather than the differential equations directly. While these methods encode the constraints of the systems using generalized coordinates, we show that embedding the system into Cartesian coordinates and enforcing the constraints explicitly with Lagrange multipliers dramatically simplifies the learning problem.

### Neural ODEs

* Neural Ordinary Differential Equations (best paper award): [NeurIPS18](https://arxiv.org/pdf/1806.07366.pdf)

> We introduce a new family of deep neural network models. Instead of specifying a discrete sequence of hidden layers, we parameterize the derivative of the hidden state using a neural network. We also construct continuous normalizing flows, a generative model that can train by maximum likelihood, without partitioning or ordering the data dimensions

* Dissecting Neural ODEs (oral): [NeurIPS20](https://arxiv.org/abs/2002.08071)

> In this work, we “open the box” and offer a system–theoretic perspective with the aim of clarifying the influence of several design choices on the underlying dynamics. We formulate and solve the infinite–dimensional problem linked to the true deep limit formulation of Neural ODE. We provide numerical approximations to the infinite–dimensional problem, leading to novel model variants, such as Galerkin and piecewise–constant Neural ODEs. Augmentation is developed beyond existing approaches to include input–layer and higher–order augmentation strategies. Finally, the novel paradigms of data–control (vector field conditioning) and depth–adaptation are introduced.

* Augmented Neural ODEs: [NeurIPS19](https://arxiv.org/abs/1904.01681)

> We show that Neural Ordinary Differential Equations (ODEs) learn representations that preserve the topology of the input space and prove that this implies the existence of functions Neural ODEs cannot represent. To address these limitations, we introduce Augmented Neural ODEs which, in addition to being more expressive models, are empirically more stable, generalize better and have a lower computational cost than Neural ODEs.

* Graph Neural Ordinary Differential Equations: [arXiv19](https://arxiv.org/abs/1911.07532)

> We introduce the framework of continuous–depth graph neural networks (GNNs). Neural graph ordinary differential equations (Neural GDEs) are formalized as the counterpart to GNNs where the input–output relationship is determined by a continuum of GNN layers, blending discrete topological structures and differential equations. We further introduce general Hybrid Neural GDE models as a hybrid dynamical systems. 

* Latent ODEs for Irregularly-Sampled Time Series: [NeurIPS19](https://arxiv.org/abs/1907.03907)

* ODE2VAE: Deep generative second order ODEs with Bayesian neural networks: [NeurIPS19](https://arxiv.org/pdf/1905.10994.pdf)

* Symplectic ODE-Net: Learning Hamiltonian Dynamics with Control: [arXiv19](https://arxiv.org/abs/1909.12077)

* Stable Neural Flows: [arXiv20](https://arxiv.org/abs/2003.08063)

* On Second Order Behaviour in Augmented Neural ODEs [NeurIPS20](https://arxiv.org/abs/2006.07220)

#### Training of Neural ODEs

* Accelerating Neural ODEs with Spectral Elements: [arXiv19](https://arxiv.org/abs/1906.07038)

* Adaptive Checkpoint Adjoint Method for Gradient Estimation in Neural ODE: [ICML20](https://arxiv.org/abs/2006.02493)

#### Speeding up continuous models

* How to Train you Neural ODE: [ICML20](https://arxiv.org/abs/2002.02798)

* Hypersolvers: Toward Fast Continuous-Depth Models: [NeurIPS20](https://arxiv.org/abs/2007.096018)

* Hey, that's not an ODE": Faster ODE Adjoints with 12 Lines of Code: [arXiV20](https://arxiv.org/pdf/2009.09457.pdf)

> Neural differential equations may be trained by backpropagating gradients via the adjoint method. Here, we demonstrate that the particular structure of the adjoint equations makes the usual choices of norm (such as L2) unnecessarily stringent. By replacing it with a more appropriate (semi)norm, fewer steps are unnecessarily rejected and the backpropagation is made faster.

* Interpolation Technique to Speed Up Gradients Propagation in Neural ODEs: [NeurIPS20](https://papers.nips.cc/paper/2020/file/c24c65259d90ed4a19ab37b6fd6fe716-Paper.pdf)

> We propose a simple interpolation-based method for the efficient approximation of gradients in neural ODE models. We compare it with the reverse dynamic method (known in the literature as “adjoint method”) to train neural ODEs on classification, density estimation, and inference approximation tasks.

#### Control with Neural ODEs

* Model-based Reinforcement Learning for Semi-Markov Decision Processes with Neural ODEs: [NeurIPS20](https://arxiv.org/pdf/2006.16210.pdf)

> In this paper, we take a model-based approach to continuous-time RL, modeling the dynamics via neural ordinary differential equations (ODEs). Not only is this more sample efficient than model-free approaches, but it allows us to efficiently adapt policies learned using one schedule of interactions with the environment for another.

### Neural SDEs

* Neural SDE: Stabilizing Neural ODE Networks with Stochastic Noise: [arXiv19](https://arxiv.org/abs/1906.02355)

* Neural Jump Stochastic Differential Equations: [arXiv19](https://arxiv.org/abs/1905.10403)

* Towards Robust and Stable Deep Learning Algorithms for Forward Backward Stochastic Differential Equations: [arXiv19](https://arxiv.org/abs/1910.11623)

* Scalable Gradients and Variational Inference for Stochastic Differential Equations: [AISTATS20](https://arxiv.org/abs/2001.01328)

### Neural CDEs

* Neural Controlled Differential Equations for Irregular Time Series (spotlight): [NeurIPS20](https://arxiv.org/abs/2005.08926)

* Neural CDEs for Long Time Series via the Log-ODE Method: [arXiv20](https://arxiv.org/abs/2009.08295)

### Normalizing Flows

* Monge-Ampère Flow for Generative Modeling: [arXiv18](https://arxiv.org/pdf/1809.10188.pdf)

* FFJORD: Free-form Continuous Dynamics for Scalable Reversible Generative Models: [ICLR19](https://arxiv.org/abs/1810.01367)

* Equivariant Flows: sampling configurations for multi-body systems with symmetric energies: [arXiv18](https://arxiv.org/pdf/1910.00753.pdf)

* Flows for simultaneous manifold learning and density estimation: [NeurIPS20](https://arxiv.org/abs/2003.13913)

> We introduce manifold-learning flows (M-flows), a new class of generative models that simultaneously learn the data manifold as well as a tractable probability density on that manifold. We argue why such models should not be trained by maximum likelihood alone and present a new training algorithm that separates manifold and density updates.

* TrajectoryNet: A Dynamic Optimal Transport Network for Modeling Cellular Dynamics [arXiv20](https://arxiv.org/pdf/2002.04461.pdf)

* Convex Potential Flows: Universal Probability Distributions with Optimal Transport and Convex Optimization: [arXiv20](https://arxiv.org/pdf/2012.05942.pdf)

> CP-Flows are the gradient map of a strongly convex neural potential function. The convexity implies invertibility and allows us to resort to convex optimization to solve the convex conjugate for efficient inversion.

### Applications 

* Learning Dynamics of Attention: Human Prior for Interpretable Machine Reasoning: [NeurIPS19](https://arxiv.org/abs/1905.11666)

## Deep Learning Methods for Differential Equations

### Solving Differential Equations

### Learning PDEs

* PDE-Net: Learning PDEs From Data: [ICML18](https://arxiv.org/abs/1710.09668)

### Model Discovery

* Universal Differential Equations for Scientific Machine Learning: [arXiv20](https://arxiv.org/abs/2001.04385)

## Dynamical System View of Deep Learning

### Recurrent Neural Networks

* A Comprehensive Review of Stability Analysis of Continuous-Time Recurrent Neural Networks: [IEEE Transactions on Neural Networks 2006](https://ieeexplore.ieee.org/abstract/document/6814892)

* AntysimmetricRNN: A Dynamical System View on Recurrent Neural Networks: [ICLR19](https://openreview.net/pdf?id=ryxepo0cFX)

* Recurrent Neural Networks in the Eye of Differential Equations: [arXiv19](https://arxiv.org/pdf/1904.12933.pdf)

* Visualizing memorization in RNNs: [distill19](https://distill.pub/2019/memorization-in-rnns/)

* One step back, two steps forward: interference and learning in recurrent neural networks: [arXiv18](https://arxiv.org/abs/1805.09603)

* Reverse engineering recurrent networks for sentiment classification reveals line attractor dynamics: [arXiv19](https://arxiv.org/pdf/1906.10720.pdf)

* System Identification with Time-Aware Neural Sequence Models: [AAAI20](https://arxiv.org/abs/1911.09431)

* Universality and Individuality in recurrent networks: [NeurIPS19](https://arxiv.org/abs/1907.08549)

### Theory and Perspectives

* A Proposal on Machine Learning via Dynamical Systems: [Communications in Mathematics and Statistics 2017](https://link.springer.com/content/pdf/10.1007/s40304-017-0103-z.pdf)

* Deep Learning Theory Review: An Optimal Control and Dynamical Systems Perspective: [arXiv19](https://arxiv.org/abs/1908.10920)

* Stable Architectures for Deep Neural Networks: [IP17](https://arxiv.org/pdf/1705.03341.pdf)

* Beyond Finite Layer Neural Network: Bridging Deep Architects and Numerical Differential Equations: [ICML18](https://arxiv.org/abs/1710.10121)

* Review: Ordinary Differential Equations For Deep Learning: [arXiv19](https://arxiv.org/abs/1911.00502)

### Optimization

* Gradient and Hamiltonian Dynamics Applied to Learning in Neural Networks: [NIPS96](https://papers.nips.cc/paper/1033-gradient-and-hamiltonian-dynamics-applied-to-learning-in-neural-networks.pdf)

* Maximum Principle Based Algorithms for Deep Learning: [JMLR17](https://arxiv.org/abs/1710.09513)

* Hamiltonian Descent Methods: [arXiv18](https://arxiv.org/pdf/1809.05042.pdf)

* Port-Hamiltonian Approach to Neural Network Training: [CDC19](https://arxiv.org/abs/1909.02702), [code](https://github.com/Zymrael/PortHamiltonianNN)

* An Optimal Control Approach to Deep Learning and Applications to Discrete-Weight Neural Networks: [arXiv19](https://arxiv.org/abs/1803.01299)

* Optimizing Millions of Hyperparameters by Implicit Differentiation: [arXiv19](https://arxiv.org/abs/1911.02590)

* Shadowing Properties of Optimization Algorithms: [NeurIPS19](https://papers.nips.cc/paper/9431-shadowing-properties-of-optimization-algorithms)

## Software and Libraries

### Python

* **torchdyn**: PyTorch library for all things neural differential equations. [repo](https://github.com/diffeqml/torchdyn), [docs](https://torchdyn.readthedocs.io/)

* **torchdiffeq**: Differentiable ODE solvers with full GPU support and O(1)-memory backpropagation: [repo](https://github.com/rtqichen/torchdiffeq)

* **torchsde**: Stochastic differential equation (SDE) solvers with GPU support and efficient sensitivity analysis: [repo](https://github.com/google-research/torchsde)

* **torchcde**: GPU-capable solvers for controlled differential equations (CDEs): [repo](https://github.com/patrick-kidger/torchcde)

* **torchSODE**: PyTorch Block-Diagonal ODE solver: [repo](https://github.com/Zymrael/torchSODE)

### Julia

* **DiffEqFlux**: [repo](https://github.com/JuliaDiffEq/DiffEqFlux.jl)

> Neural differential equation solvers with O(1) backprop, GPUs, and stiff+non-stiff DE solvers. Supports stiff and non-stiff neural ordinary differential equations (neural ODEs), neural stochastic differential equations (neural SDEs), neural delay differential equations (neural DDEs), neural partial differential equations (neural PDEs), and neural jump stochastic differential equations (neural jump diffusions). All of these can be solved with high order methods with adaptive time-stepping and automatic stiffness detection to switch between methods. 
  
* **NeuralNetDiffEq**: Implementations of ODE, SDE, and PDE solvers via deep neural networks: [repo](https://github.com/JuliaDiffEq/NeuralNetDiffEq.jl)

## Websites and Blogs

* Scientific ML Blog (Chris Rackauckas and SciML): [link](http://www.stochasticlifestyle.com/)
