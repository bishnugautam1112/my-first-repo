Based on the image provided, here is the complete, step-by-step solution.

**Problem Statement Summary:**
*   An urn contains **7 red** balls and **4 white** balls.
*   Total number of balls in the urn = $7 + 4 = \mathbf{11}$ balls.
*   **3 balls** are drawn at random.
*   We need to find the **probability distribution, mathematical expectation, and variance** for the number of white balls drawn.

Let the random variable $X$ denote the number of white balls drawn.
Since 3 balls are drawn, the possible number of white balls ($X$) can be $0, 1, 2, \text{ or } 3$.

To find the probabilities, we will use the concept of combinations $\binom{n}{r}$, which represents choosing $r$ items from $n$ items.

*   **Total number of ways to draw 3 balls out of 11:**
    $$n(S) = \binom{11}{3} = \frac{11 \times 10 \times 9}{3 \times 2 \times 1} = \mathbf{165}$$

---

### **1. Probability Distribution**

Let's calculate the probability for each possible value of $X$.
The formula for hypergeometric probability is: $P(X=x) = \frac{\binom{\text{White}}{x} \times \binom{\text{Red}}{3-x}}{\binom{\text{Total}}{3}}$

*   **Case $X = 0$ (Drawing 0 white balls, which means 3 red balls):**
    Number of ways to choose 0 white from 4 = $\binom{4}{0} = 1$
    Number of ways to choose 3 red from 7 = $\binom{7}{3} = \frac{7 \times 6 \times 5}{3 \times 2 \times 1} = 35$
    $$P(X=0) = \frac{1 \times 35}{165} = \mathbf{\frac{35}{165}}$$

*   **Case $X = 1$ (Drawing 1 white ball, which means 2 red balls):**
    Number of ways to choose 1 white from 4 = $\binom{4}{1} = 4$
    Number of ways to choose 2 red from 7 = $\binom{7}{2} = \frac{7 \times 6}{2 \times 1} = 21$
    $$P(X=1) = \frac{4 \times 21}{165} = \mathbf{\frac{84}{165}}$$

*   **Case $X = 2$ (Drawing 2 white balls, which means 1 red ball):**
    Number of ways to choose 2 white from 4 = $\binom{4}{2} = \frac{4 \times 3}{2 \times 1} = 6$
    Number of ways to choose 1 red from 7 = $\binom{7}{1} = 7$
    $$P(X=2) = \frac{6 \times 7}{165} = \mathbf{\frac{42}{165}}$$

*   **Case $X = 3$ (Drawing 3 white balls, which means 0 red balls):**
    Number of ways to choose 3 white from 4 = $\binom{4}{3} = 4$
    Number of ways to choose 0 red from 7 = $\binom{7}{0} = 1$
    $$P(X=3) = \frac{4 \times 1}{165} = \mathbf{\frac{4}{165}}$$

*(Verification check: $\frac{35}{165} + \frac{84}{165} + \frac{42}{165} + \frac{4}{165} = \frac{165}{165} = 1$)*

**Probability Distribution Table:**
To make calculations easier later, we will use fractions with the common denominator of 165, but we can also show simplified fractions.

| $X$ (No. of white balls) | $0$ | $1$ | $2$ | $3$ |
| :---: | :---: | :---: | :---: | :---: |
| **$P(X=x)$** | $\frac{35}{165}$ | $\frac{84}{165}$ | $\frac{42}{165}$ | $\frac{4}{165}$ |
| *Simplified $P(X)$* | *$\frac{7}{33}$* | *$\frac{28}{55}$* | *$\frac{14}{55}$* | *$\frac{4}{165}$* |

---

### **2. Mathematical Expectation, $E(X)$**

The mathematical expectation (or mean) is calculated using the formula:
$$E(X) = \sum [x \cdot P(x)]$$

Let's compute using the unsimplified fractions for easier addition:
$$E(X) = \left(0 \times \frac{35}{165}\right) + \left(1 \times \frac{84}{165}\right) + \left(2 \times \frac{42}{165}\right) + \left(3 \times \frac{4}{165}\right)$$
$$E(X) = 0 + \frac{84}{165} + \frac{84}{165} + \frac{12}{165}$$
$$E(X) = \frac{180}{165}$$

Simplify the fraction by dividing numerator and denominator by 15:
$$E(X) = \mathbf{\frac{12}{11}} \approx \mathbf{1.09}$$

---

### **3. Variance, $Var(X)$**

The variance is calculated using the formula:
$$Var(X) = E(X^2) - [E(X)]^2$$

**Step A: Calculate $E(X^2)$**
$$E(X^2) = \sum [x^2 \cdot P(x)]$$
$$E(X^2) = \left(0^2 \times \frac{35}{165}\right) + \left(1^2 \times \frac{84}{165}\right) + \left(2^2 \times \frac{42}{165}\right) + \left(3^2 \times \frac{4}{165}\right)$$
$$E(X^2) = 0 + \left(1 \times \frac{84}{165}\right) + \left(4 \times \frac{42}{165}\right) + \left(9 \times \frac{4}{165}\right)$$
$$E(X^2) = \frac{84}{165} + \frac{168}{165} + \frac{36}{165}$$
$$E(X^2) = \frac{288}{165}$$
Simplify by dividing by 3: $E(X^2) = \frac{96}{55}$

**Step B: Apply Variance Formula**
$$Var(X) = \frac{96}{55} - \left(\frac{12}{11}\right)^2$$
$$Var(X) = \frac{96}{55} - \frac{144}{121}$$

Find a common denominator ($55 \times 11 = 605$):
$$Var(X) = \left(\frac{96 \times 11}{55 \times 11}\right) - \left(\frac{144 \times 5}{121 \times 5}\right)$$
$$Var(X) = \frac{1056}{605} - \frac{720}{605}$$
$$Var(X) = \mathbf{\frac{336}{605}} \approx \mathbf{0.555}$$