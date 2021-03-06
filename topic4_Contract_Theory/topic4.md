## Topic 4: Contract Theory
### 4.A Job contract problem
Boss's profit is dependent on Tom's effort:
* Tom's effort: $e \in \{H,L\}$.
* Profit to boss: $\pi \sim F_e \ on \ [0,1]$
* $F_H$ first order stochastically dominates (FOSD) $F_L$.
  * $Pr(\pi \geq x | H) \geq Pr(\pi \geq x | L)$ for any $x \in [0,1]$.
  * High effort is more likely to generate high profit.


Game: 
* Boss makes the job offer. The job contract  will specify:
  1. Effort level $e$ that Tom has to exert.
  2. Wage $w(\pi)$ that Tom will receive given $\pi \in [0,1]$ ($w(\pi:[0,1] \to \mathbb{R}_+)$).
* Tom decides whether to accept or not.

Payoffs:
* Boss's payoff: $\pi - w$
  * Boss is risk neutral.
  * Boss cares about the profit $\pi$, not the effort $e$.
* Tom's payoff: $v(w) - g(e)$
  * Tom is risk averse: $v(w)$ is increasing and concave, which means the marginal utility is decreasing as the wage increases.
  * $g(e)$ is increasing, meaning higher effort is more exhausting.
  * Tom cares about the wage $w$, not the profit $\pi$ for Boss.

Contract theory:
* Principal: party wants a job done but cannot do it by himself
* Agent: party that can do the job
* Contract: terms **determined by the principal** about the agent doing the job
* Optimal contract: incentivize the agent to do the job in **the best interest of the principal**

Optimal strategy:
* Contract will let the Boss gets the highest expected payoff.
* Tom will accept such offer only if his expected payoff is at least $\bar{u}$ ($\bar{u}$: opportunity cost, the value of outside option).
* Solution $(e^*,w^*)$ to the best contract:
$$max_{e,w} \int_0^1 [\pi-w(\pi)]f_e(\pi)d\pi$$
$$s.t. \int_0^1 [v(w(\pi))-g(e)]f_e(\pi)d\pi \geq \bar{u}$$
* Equivalent to:
$$max_{e,w} \ E[\pi|e]-E[w(\pi)|e]$$
$$s.t. \ E[v(w(\pi))|e]-g(e) \geq \bar{u}$$

### 4.B SBE
**Obs. 1: Optimal wage $w^*$ is almost everywhere constant.**

*Proof*: 
* Denote $(e^*,w^*)$ as the optimal solution. If it is not, then denote it as $w'=E[w^*(\pi)|e^*]$, such that it is now a non-constant function of $\pi$.
* Since $v$ is a concave function, from Jensen's inequality ($E[y(x)] < y(E[x])$), $E[v(w^*(\pi))|e^*] < v(w')$.
* Hence, there is a gap $\epsilon$, where $E[v(w^*(\pi))|e^*] = v(w'-\epsilon)$.
* By offering wage $w'-\epsilon$, Tom gets the same expected payoff while Boss pays less, which contrasts the optimal condition.
* $w^*$ must be constant.
* **Wage uncertainty incurs a risk premium for Tom but comes with no benefit to risk neutral Boss.**

**Obs. 2: Tom's expected payoff under the optimal contract is $\bar{u}$.**

*Proof:*
* If the payoff is strictly above $\bar{u}$, the Principal can always deviate to a less pay. There has been deviation until the Tom's payoff is exactly $\bar{u}$.
* Tom is indifferent between taking or rejecting the offer.
* No surplus value for the Agent.

**Optimal contract:**
* Require high effort $H$: $v(w_H)-g(H)=\bar{u} \Rightarrow w_H=v^{-1}(\bar{u}+g(H))$
* Require low effort $L$: $v(w_L)-g(L)=\bar{u} \Rightarrow w_L=v^{-1}(\bar{u}+g(L))$
* Optimal contract: if $E[\pi|H]-w_H > E[\pi|L]-w_L$, the optimal contract is $(H,w_H)$; the reverse also holds.
* Incentivizing high effort may not be optimal, since the cost can be also high.

### 4.C A more flexible contract
* A more flexible contract allows Tom to choose the effort level by himself.
* The wage scheme is $w(e,\pi)$.
* Game changes for Tom: after accepting, he can choose $e \in \{H,L\}$, and he will choose to maximizing his expected payoff:
$$max_{e\in\{L,H\}}E[v(w(\pi,e))|e]-g(e) \geq \bar{u}$$

**Obs. 1: No harm for the Boss. The optimal flexible contract is no worse than the optimal inflexible contract.**

*Proof:*
* Always be able to construct a flexible contract yielding the same payoff as if it was a inflexible contract. 
* Denote $(e^*,w^*)$ as the optimal inflexible contract. Consider a flexible contract wage scheme $w(e,\pi)$ where $w(e^*,\pi)=w^*$ and $w(e,\pi)=\bar{u}-\epsilon$ for $e \neq e^*$ and $\epsilon > 0$. In this way, Tom will choose $e^*$ to maximize his utility and Boss gets the same payoff.
* No way for Boss to choose a wage scheme that yields a lower utility for him.

**Obs. 2: No help for the Boss. The optimal flexible contract is no better than the optimal inflexible contract.**

*Proof:*
* Optimal choices under flexible contract are always available under inflexible games.
* Suppose $(e^*,w^*)$ is the optimal solution under the flexible game for Tom. Then, under inflexible game, $(e,w)=(e^*,w^*)$ will be also accepted by Tom, and yield the same return for Boss.

### 4.D Incontractable effort
* Effort is incontractable when 
  * Effort is unobservable to Boss and Court. - Hidden actions.
  * Effort is unobservable to court. - Unenforceable.
  * Effort cannot be legally used as a contingency. - Gender, race, etc.
* Contract can only specify wage scheme depend on profit: $w(\pi)$.
* Given $w(\pi)$, Tom will choose $e^*(w)$ to maximize his payoff.
$$e^*(w):=argmax_{e\in\{H,L\}}\int_0^1[v(w(\pi))-g(e)]f_e(\pi)d\pi$$
* Optimal problem:
$$max_{w} \int_0^1 [\pi-w(\pi)]f_{e^*(w)}(\pi)d\pi$$
$$s.t. \int_0^1 [v(w(\pi))-g(e^*(w))]f_{e^*(w)}(\pi)d\pi \geq \bar{u}$$
, where
$$e^*(w):=argmax_{e\in\{H,L\}}\int_0^1[v(w(\pi))-g(e)]f_e(\pi)d\pi$$
* To find a solution:
  * Find $w_L$ that makes Tom choose $L$.
  * Find $w_H$ that makes Tom choose $H$.
  * Compare $w_L$ and $w_H$.

**Obs. 1: $w_L$ is constant and is equal to $v^{-1}(\bar{u}+g(L))$.**

*Proof:*
* Agent needs to accept the offer: individual rationality (IR), $v(w_L)-g(L)=\bar{u} \Rightarrow w_L=v^{-1}(\bar{u}+g(L))$.
* Tom is incentivized to choose $L$: incentive compatibility (IC), $v(w_L)-g(L) \geq v(w_H)-g(H)$ is auto satisfied since $g$ is increasing.

**Obs. 2: For $w_H$, IR is binding. Individual rationality: $\int_0^1[v(w(\pi))-g(H)]f_H(\pi)d\pi \geq \bar{u}$**

*Proof:*
* By contradiction, if IR is not binding, there exist $\epsilon > 0$, such that $\int_0^1 [v(w(\pi))-g(H)]f_H(\pi)d\pi + \epsilon = \bar{u}$.
* Construct $w'(\pi)$, such that $v(w(\pi)) - \epsilon = v(w'(\pi))$, meaning under $w'(\pi)$, Tom always get $\epsilon$ regardless of his effort. Hence, IC still holds.
* $w'(\pi)$ yields Boss a higher return, hence a un-binding $w(\pi)$ cannot be optimal to Boss.
* Boss will make a binding offer under the optimization condition.

<img src="IR_binding.png" alt="drawing" height="300"/>

**Obs. 3: For $w_H$, IC is binding. Incentive compatibility: $\int_0^1[v(w(\pi))-g(H)]f_H(\pi)d\pi \geq \int_0^1[v(w(\pi))-g(L)]f_L(\pi)d\pi$**

*Proof:*
* $w$ is not everywhere constant; otherwise Tom will exerts $L$ for best payoff.
* There exists 2 Lebesgue measure-$\delta > 0$ sets $\Pi, \Pi' \subset [0,1]$, s.t. $w(\pi) \geq w(\pi')+2\epsilon$ for some $\epsilon > 0$ for every $\pi \in \Pi$ and $\pi' \in \Pi'$.
* If IC is not binding, Boss can lower $w(\pi)$ by $\epsilon$ such that gives Boss a higher return; Boss can increase $w(\pi')$ by $\epsilon$ such that gives Tom a higher return. The unbinding region will result in above 2 cases; however, when Boss needs to incentive Tom to choose high level and maximize his own utility, $\epsilon \to 0$, indicating IC binding.


<img src="IC_binding.png" alt="drawing" height="400"/>

**Optimal solution to incentivize high effort:**
$$
L(w)=\int_0^1 [\pi-w(\pi)]f_{H(w)}(\pi)d\pi + \\
\gamma (\int_0^1[v(w(\pi))-g(H)]f_H(\pi)d\pi \geq \bar{u}) + \\
\mu (\int_0^1[v(w(\pi))-g(H)]f_H(\pi)d\pi \geq \int_0^1[v(w(\pi))-g(L)]f_L(\pi)d\pi)
$$

By FOC ($\frac{L(w)}{w}=0$):
$$
-f_H(\pi) + \gamma v'(w)f_H(\pi) + \mu v'(w)(f_H(\pi)+f_L(\pi))=0
$$
$$
\Rightarrow \ w(\pi)=(v')^{-1}(k(\pi)), \ where \\
k(\pi)=\frac{1}{\gamma+\mu(1-f_{L}(\pi)/f_H(\pi))}
$$
Since 2 constraints are binding, $\gamma,\mu > 0$.
$v'$ is decreasing (Tom is risk adverse), then $v'^{-1}$ is increasing in $k(\pi)$. Hence, $w(\pi)$ has the same trend as $k(\pi)$.

**Optimal wage: $w^*$ is not necessarily monotone in $\pi$, as $k$ is not necessarily monotone in $\pi$.**
* $w$ is monotone iff $f_H(\pi)/f_L(\pi)$ is increasing in $\pi$. [**"monotone likelihood ratio property"** or **"likelihood ratio dominance"**]
* This means it is possible that higher profit leads to lower wage. Wage increases with profit when high effort does lead to higher possibility of profit increase.
* "Likelihood ratio dominance" is sufficient but not necessary for FOSD(First order stochastic dominance?).

**Optimal wage: $w^*$ is not constant.**
* Comparing with inflexible contract $(H,w_H)$,
$$
E[v(w_H)]=\bar{u}+g(H)=E[v(w^*)]
$$
* $E[w^*] > E[w_H]$ since $v$ is concave. Payment is higher with risks when Boss are signing for a flexible contract, such that expected payoff to Tom is indifferent.

**Efficiency:**
* Boss is worse off if he wants to incentivize $H$ and if effort is incontractible. Tom is indifferent.
* In contrast, to incentivize $L$, whether effort is contractible does not matter.
* Efficiency loss (due to “moral hazard”):
  * If if Boss chooses to incentivize high effort, the risk put in the wage scheme is pure waste.
  * When effort is incontractible, the additional cost to incentivize high effort may make Boss compromise on low effort, which he otherwise would not if effort were contractible.

### 4.E Questions

Consider a moral hazard model where a worker chooses an effort level $e \in [0,1]$; and as a result, either a high or a low output $y \in \{y_l,y_h\}$ is realized with $0 = y_l < y_h < 1$: Denote the probability that $y = y_h$ for effort level $e$ is given by $p(e) = e$: The employer's payoff is $y - w$; where $w$ denotes the wage paid to the worker. The workers payoff is $w - e^2$ if she accepts the contract, and 0 if she rejects the contract.

---
**Q1: Characterize the optimal contract in which the principal maximizes his net utility in the case where the wage $w$ can depend on $e$ (because $e$ is observable).**

*Sol:*
* The principle wants to maximize his utility:
  $$U^p=E[y(e)]-w$$
  , subject to $w \geq e^2$.
* Constraints are binding, since for an observable $e$, employer wants to give a lowest possible wage to maximize his utility.
* $$
  U^p=ey_h+(1-e)y_l-e^2 \\
  \to e^*=\frac{y_h-y_l}{2}=\frac{y_l}{2}, \ w^*=(\frac{y_l}{2})^2
  $$
* Off-EQ path: for $e \neq \frac{1}{2}y_h$, set $w(e)=-K$ for a large $K$.
  
---

---
**Q2: Characterize the optimal contract, maximizing the principals net utility, when only $y$ is observable and variable.**

*Sol:*
* Suppose $e^*$ is the EQ effort level, $e^* \in argmax_e(e(w_h-e^2)+(1-e)(w_l-e^2))$:
  $$e^* = \frac{w_h-w_l}{2}$$
* Among all $e^*$, the principle wants to maximize his expected payoff:
  $$U^p = e(y_h-w_h)+(1-e)(y_l-w_l) \to \\
  U^p = y_l-w_l+(y_h-y_l)\frac{w_h-w_l}{2}-\frac{(w_h-w_l)^2}{2}$$
  $$e^* = y_h/2=(w_h-w_l)^*/2$$
  $$U^p = -w_l$$
* From $U^A \geq 0$,
  $$y_h^2/4 + w_l \geq 0$$
  
* $w_l^* = -y_h^2/4$, $w_h^* = y_h - y_h^2/4$
  $\to w^* = y - y_h^2/4$

---

---
**Q3: Suppose now that the contract requires limited liability in the sense that $w(y) \geq 0$ for all $y$. Does your solution change from Question 2 and if it does, compute the newly optimal contract and effort level under limited liability.**

*Sol:*
* $w_l^*=0, w_h^*=y_h/2$

---