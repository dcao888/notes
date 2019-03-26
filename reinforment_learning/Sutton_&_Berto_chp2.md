# Chapter 2: Multi-armed Bandits

We begin by studying the various aspects of reinforcement learning through a simplified toy example: the $k$-armed bandit. This is a *nonassociative* model in the sense that there is no association between actions and states; rather each trial can be seen as an $i.i.d.$ event.

## 2.1 &ensp; A $k$-armed Bandit Problem

> *$k$-armed Bandit:*
Consider a slot machine with $k$ levers, each with payout that is randomly drawn from a respective $\NN (\mu_i, 1)$ distribution for $i =1,...,k$. The objective is to maximize the expected total return over some time period, say $n=1000$ trials.

If the values of $\mu_i$ were known, the optimal solution is trivial by the *Strong Law of Large Numbers*: simply pick the lever with the largest expected payout (reward)

$$ q_*(a) = \E(R_t | A_t = a). $$

Without this knowledge a-priori, we would have to try each lever multiple times (exploration) and before being able to confidently commit to an action (exploitation). This tradeoff between immediate capitalization and delayed gratification is known as the *exploration vs. exploitation* tradeoff.

## 2.2 &ensp; Action-value Methods

*Action-value methods* are used to first estimate the value of an action, (e.g. $q_*(a))$,  and then select an action based on this value. 

The simplest selection criterion is the *greedy method*: ${n \choose k} $

$$ \argmax_{n \in \N}{n \choose k} $$