*~ based on Chapter 3, Deep Learning by Ian Goodfellow et. al.*

This note provides a quick glance to probability and information theory in their relations to deep learning. In particular, their theoretical roles, some common concepts and definitions as well as pointer to some futher readings.

**Probability theory** defines a set of rules for deriving uncertain statements and reason in presence of uncertainty.  In the context of machine learning, its laws instruct how the AI systems should reason and behave. Thus, probability theory provides a theoretical framework for designing and reasoning about AI systems.

**Information theory**, on the other hand, allows us to quantify the amount of uncertainty in a probability distribution. **TODO:** ?Measure informative? Generalization?

## 1 Probability theory
Motivations

- represent simple but uncertain rules which are better than a complex but certain one e.g. "Most birds fly" vs. "Birds ﬂy, except for very young birds that have not yet learned toﬂy, sick or injured birds that have lost the ability to ﬂy..."

- represent and reason about qualitative levels of certainty (degree of belief)

- extend logic to deal with uncertainty

### 1.1 Definitions
**Probability Mass Function (PMF)** describes a probability distribution over discrete random variables {% raw %} $X$ {% endraw %}, denoted {% raw %} $P(X)$ {% endraw %}.

- domain of {% raw %} $P$ {% endraw %} is set of all possible states of {% raw %} $X$ {% endraw %}

- {% raw %} $\forall x \in X, 0 \leq P(x) \leq 1$ {% endraw %}

- {% raw %} $\sum_{x \in X} P(x) = 1$ {% endraw %}

**Probability Density Function (PDF)** describes a probability distribution over continuous random variables {% raw %} $X$ {% endraw %}, denoted {% raw %} $p(X)$ {% endraw %}.

- domain of {% raw %} $p$ {% endraw %} is set of all possible states of {% raw %} $X$ {% endraw %}

- {% raw %} $\forall x \in X, p(x) \geq 0$ {% endraw %}

- {% raw %} $\int p(x) dx = 1$ {% endraw %}

**Marginal probability** is the probability distribution over the subset of random variables e.g. given the joint distribution {% raw %} $P(x, y)$ {% endraw %}, we usually interest in the marginal probability {% raw %} $P(x)$ {% endraw %}

- sum rule {% raw %} $\forall x \in X, P(X=x) = \sum_{y} P(X=x, Y=y)$ {% endraw %}

**Conditional probability** is the probability of some event, given that some other event has happened

- {% raw %} $P(Y=y \mid X=x) = \frac{P(Y=y, X=x)}{P(X=x)}$ {% endraw %}

**Chain rule of conditional probabilities**

- {% raw %} $P(x^{(1)},...,x^{(n)}) = P(x^{(1)}) \prod_{i=2}^{n} P(x^{(i)} \mid x^{(1)},...,x^{(i-1)})$ {% endraw %}

**Expectation (expected value)** is the average or mean value that {% raw %} $f$ {% endraw %} takes on when {% raw %} $x$ {% endraw %} is drawn from {% raw %} $P$ {% endraw %}

- {% raw %} $ \mathbb{E}_{x \sim P}[f(x)] = \sum_x P(x)f(x) $ {% endraw %}

**Variance** measures how much the values of {% raw %} $f(x)$ {% endraw %} vary as we sample diﬀerent values of {% raw %} $x$ {% endraw %} from P

- {% raw %} $Var(f(x)) = \mathbb{E}[(f(x) - \mathbb{E}[f(x)])^{2}]$ {% endraw %}

**Covariance** describes how much two values are linearly related to each other

- {% raw %} $Cov(f(x), g(y)) = \mathbb{E}[(f(x) - \mathbb{E}[f(x)])(g(y) - \mathbb{E}[g(y)])]$ {% endraw %}

## Further reading

- [Probability theory](http://www.med.mcgill.ca/epidemiology/hanley/bios601/GaussianModel/JaynesProbabilityTheory.pdf)

- [Frequentist and Bayesian probability](https://core.ac.uk/download/pdf/7048428.pdf)