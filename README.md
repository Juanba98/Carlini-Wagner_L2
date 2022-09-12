# Carlini-Wagner attack (http://arxiv.org/abs/1608.04644)

## L2 attack
To ensure the modifitacions yields to a valid image, we use the third method of box contraints at the paper and we define  $\delta$ as:

$$\delta_{i} = \frac{1}{2}(tanh(w_{i}) + 1) - x_{i} $$

and we optimize over the variable $w$



### Attack

Given x, and choosing a target class $t$  ( $t \neq C^{\*}(x)$, beeing $C^{\*}(x)$  the correct label of x we search for a $w$ that solves)



$$minimize \ ||\delta||^{2}_{2} + c \cdot f(x + \delta)$$ 



with $f$ defined as

$$f(x') = max(max\{Z(x')_i :  i \neq t\} - Z(x')_t, -\kappa)$$

To control the confidence with which missclasifation ocurrs we adjust κ but we wil set it to 0 for out attack

### L2 formula

$$||x||_{2} = \sqrt{\sum_{i=1}^{n} x^{2}_{i}} $$

## Referential implementation:
- https://github.com/carlini/nn_robust_attacks.git
- https://github.com/kkew3/pytorch-cw2/blob/master/cw.py
