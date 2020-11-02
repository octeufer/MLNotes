# [Correlation and Causation](https://medium.com/causal-data-science/if-correlation-doesnt-imply-causation-then-what-does-c74f20d26438)

### Questions marks

- Why we need causation? What correlation cannot and causation can do.
- How to represent causation? What tools to use.
- What questions can causation help to answer more easier?
- What can we do to answer those question causally?

### Why we need causation?

Assumptions, Context, Action: 
Anytime you decide to take an action, in a business context or otherwise, you’re making some assumptions about how the world operates. That is, you’re making assumptions about the causal effects of possible actions.

Causation can help us to answer the `what if` questions, estimate under the change of the system.

### How to represent causation?

Simple, rough assumptions about causal relations:
Our model just needs to include the most common, large effects on our trip to work. If we omit a large number of small, independent effects, we can just treat them as “noise”.

Dependence relations roots in the structure:
There is no correlation without causation. If neither A nor B causes the other, and the two are correlated, there must be some common cause of the two.

### What questions can causation help to answer more easier?

The question of “What would have happened if things were different?” is an essentially causal question. 

If you only observe how the system normally operates, you’ll generally get the wrong answer.
Because you are misled by the correlation, which dose not reflect how system will reflect with some changes.

### What can we do to answer those question causally?

All of these questions are extremely hard to answer experimentally, and can’t necessarily be answered from statistical data (even with large dataset).

If we have a good causal model of how the system operates, to go with our statistical data, and possibly supplemented by the few experiments within the system that we’re able to do.