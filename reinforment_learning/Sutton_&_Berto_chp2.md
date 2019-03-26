# Chapter 2: Multi-armed Bandits

We begin by studying the various aspects of reinforment learning through a simplified toy example: the k-armed bandit. This is *nonassociative* in the sense that there is no association between actions and states; rather each trial can be seen as an i.i.d. event.

## 2.1 &ensp; A k-armed Bandit Problem

> *K-armed Bandit:* 
Consider a slot machine with k levers, each with a payout that is randomly drawn from a normal distribution (with variance 1 and unknown mean). The objective is to maximize the expected total return over some time period, say n=1000 trials. 

If we knew the values of $\mu_i$, this would be a trivial exercise by the Strong Law of Large Numbers: simply pick the lever with the largest expected payout (reward) 

\[ \q_*(a) = \E(R_t | A_t = a). \]

Without this knowledge a-priori, we have to try several levers multiple times (exploration) and then stick to a lever once confident it has the highest reward (exploit). This tradeoff between immediate vs long-term reward is known as the *exploration vs. exploitation* tradeoff. 

The *Gamma function* satisfying $\Gamma(n) = (n-1)!\quad\forall n\in\mathbb N$ is via the Euler integral

$$
\Gamma(z) = \int_0^\infty t^{z-1}e^{-t}dt\,.
$$
