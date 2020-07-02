# ProbabilityCircuit

## Contents:

- Expressiveness v.s. tractability.
- Probabilistic circuits.
- Learning circuits.
- Representation and theory.

## Why tractable inference?

- Tractable probabilistic inference.
    + queries (inference) $$\mathcal{Q}$$, probabilistic models M.
    + **exactly** computing q(m) runs in time O(poly(|m|)).
    + Learning: learn the model m.
    + Inference: query a quantity with m.
- Different query nodes.
    + terminate node --> prediction --> P_m(Y|X), x->y.
    + an ancestor of the evidence --> diagnosis --> P_m(X|Y), x->y.
- Several models.
    + GANs: $$min_{\theta}max_{\phi} E_{x \sim P_{data}(x)}[logD_{\phi}(x)] + E_{z \sim P(z)}[log(1 - D_{\phi}(G_{\theta}(z)))]$$
        * no likelihood, no tractable evidence.
        * sample quality needs a lot of samples for learning.
        * unstable, mode collapse.
    + VAE: $$logP_{\theta} >= E_{z \sim Q_{\phi}(z|x)}[logP_{\theta}(x|z)] - KL(Q_{\phi}(z|x)||P(z))$$.
        * explicit likelihood.
        * infinite and uncountable mixture for the computation of $$logP_{\theta(X)}$$ --> intractable.
        * reparameterizing trick for optimizing ELBO
    + Autoregressive models: $$P_{\theta}(x) = \prod_i P_{\theta}(x_i|x_1, \cdots, x_{i-1})$$
        * explicit likelihood.
        * product of factors --> tractable evidence.
        * tractable query for some fixed ordering.
    + Normalizing flows:
        * explicit likelihood --> tractable evidence.
        * computing Jacobian determinant --> marginal query is generally intractable.
    + Probabilistic Graphical Models (PGMS):
        * Nodes (variables), Edges (dependencies).
        * Inference: conditioning, elimination, message passing.
        * Treewidth --> tree-decomposition of model m.
        * tractable with bounded Treewidth.
- Expressiveness
    + Mixtures: convex combination of k (simpler) PGMs: $$P(x) = w_1 P_1(x) + w_2 P_2(x)$$.
    + Stack mixtures like in deep generative models.
- Advanced queries
    + "What is the probability of seeing more traffic jams in Uptown than Midtown?" --> counts and group comparison.
    + expected predictions, (khosravi2019expect).
    + expected classification agreements (oztok2016solving; choi2017optimal; choi2018robust).

## Probabilistic circuits

A probabilistic circuit $$\mathcal{C}$$ is a computational graph encoding a probability distribution P(X) over variables X.

Nodes: unit of computations.
Edges: orders of executions.

- tractable --> constraining the graph.
- A single node encodes a distribution.
- tractable queries:
    + evidence: P(X).
    + marginal query: probability or density.
    + maximum a priori: output the mode.
- expressiveness:
    + recursive semantics.
    + mixtures.
- inference:
    + feedforward pass. --> From marginals to joints.
    + backward pass.
- smoothness + decomposability = tractable marginal queries.
    + smoothness: integrals are pushed down to children. --> due to same parents.
    + decomposability: integrals decompose into easier ones. --> due to different parents.
- an arbitrary conditional query: $$p(q|e) = p(q,e) / p(e)$$.
    + once feedforward pass: $$p(q,e)$$.
    + once feedforward pass: $$p(e)$$.

## Learning probabilistic circuits

A probabilistic circuit $$\mathcal{C}$$ is a computational graph encoding a probability distribution P(X) over variables X, parametrized by $$\Omgea$$.

- Learning PC means learning the **graph structure** and **parameters**.
    + parameters: MLE, EM, VI, Deterministic Circuit, MCMC.
    + structures: sub-graph, ensemble.
    + for DAGs --> jaini2018prometheus; Dennis2015.
    + for heterogeneous data --> Molina2017b.
    + approximating independence tests --> di2018sum.

