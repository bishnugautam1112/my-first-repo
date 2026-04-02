Based on your request, here is a detailed, step-by-step solution designed to secure full marks (8/8) in a university exam setting.

**Problem Statement:**
Find the Z-Transform of the given signal: $x[n] = a^n \sin(w_c n) u[n]$

---

### **Detailed Solution**

To find the Z-transform from first principles, we will use the standard definition and Euler's formula.

#### **Step 1: Write down the definition of the Z-Transform**
The two-sided Z-transform of a discrete-time signal $x[n]$ is defined as:
$$X(z) = \sum_{n=-\infty}^{\infty} x[n] z^{-n}$$

#### **Step 2: Substitute the given signal into the formula**
Given $x[n] = a^n \sin(w_c n) u[n]$
$$X(z) = \sum_{n=-\infty}^{\infty} [a^n \sin(w_c n) u[n]] z^{-n}$$

Because of the unit step function $u[n]$, which is defined as:
*   $u[n] = 1$ for $n \ge 0$
*   $u[n] = 0$ for $n < 0$

The limits of our summation change from $-\infty$ to $\infty$ to just $0$ to $\infty$:
$$X(z) = \sum_{n=0}^{\infty} a^n \sin(w_c n) z^{-n}$$

#### **Step 3: Express the sine function using Euler's Identity**
Recall Euler's identity for sine:
$$\sin(\theta) = \frac{e^{j\theta} - e^{-j\theta}}{2j}$$
Substituting $\theta = w_c n$, we get:
$$\sin(w_c n) = \frac{e^{j w_c n} - e^{-j w_c n}}{2j}$$

Now, substitute this back into our $X(z)$ equation:
$$X(z) = \sum_{n=0}^{\infty} a^n \left[ \frac{e^{j w_c n} - e^{-j w_c n}}{2j} \right] z^{-n}$$

#### **Step 4: Expand and separate into two summations**
We can pull out the constant $1/2j$ and split the sum into two separate geometric series:
$$X(z) = \frac{1}{2j} \left[ \sum_{n=0}^{\infty} a^n e^{j w_c n} z^{-n} - \sum_{n=0}^{\infty} a^n e^{-j w_c n} z^{-n} \right]$$

Group the terms with power $n$ together:
$$X(z) = \frac{1}{2j} \left[ \sum_{n=0}^{\infty} (a e^{j w_c} z^{-1})^n - \sum_{n=0}^{\infty} (a e^{-j w_c} z^{-1})^n \right]$$

#### **Step 5: Evaluate the infinite geometric series and find the ROC**
Recall the formula for the sum of an infinite geometric series:
$\sum_{n=0}^{\infty} r^n = \frac{1}{1 - r}$, provided the Region of Convergence (ROC) is $|r| < 1$.

Applying this to our two sums:
1.  **First sum:** $r_1 = a e^{j w_c} z^{-1}$
    Sum = $\frac{1}{1 - a e^{j w_c} z^{-1}}$
    Convergence condition: $|a e^{j w_c} z^{-1}| < 1 \implies |a| \cdot |e^{j w_c}| \cdot |z^{-1}| < 1 \implies |a| \cdot 1 \cdot \frac{1}{|z|} < 1 \implies |z| > |a|$

2.  **Second sum:** $r_2 = a e^{-j w_c} z^{-1}$
    Sum = $\frac{1}{1 - a e^{-j w_c} z^{-1}}$
    Convergence condition: $|a e^{-j w_c} z^{-1}| < 1 \implies |a| \cdot |e^{-j w_c}| \cdot |z^{-1}| < 1 \implies |a| \cdot 1 \cdot \frac{1}{|z|} < 1 \implies |z| > |a|$

The overall **Region of Convergence (ROC)** is the intersection of the two conditions, which is **$|z| > |a|$**.

Now, substitute the evaluated sums back into $X(z)$:
$$X(z) = \frac{1}{2j} \left[ \frac{1}{1 - a e^{j w_c} z^{-1}} - \frac{1}{1 - a e^{-j w_c} z^{-1}} \right]$$

#### **Step 6: Algebraic Simplification**
Find a common denominator to combine the terms:
$$X(z) = \frac{1}{2j} \left[ \frac{(1 - a e^{-j w_c} z^{-1}) - (1 - a e^{j w_c} z^{-1})}{(1 - a e^{j w_c} z^{-1})(1 - a e^{-j w_c} z^{-1})} \right]$$

**Simplify the numerator:**
$= 1 - a e^{-j w_c} z^{-1} - 1 + a e^{j w_c} z^{-1}$
$= a e^{j w_c} z^{-1} - a e^{-j w_c} z^{-1}$
$= a z^{-1} (e^{j w_c} - e^{-j w_c})$

**Simplify the denominator:**
$= 1 - a e^{-j w_c} z^{-1} - a e^{j w_c} z^{-1} + a^2 e^{j w_c} e^{-j w_c} z^{-2}$
$= 1 - a z^{-1} (e^{j w_c} + e^{-j w_c}) + a^2 (1) z^{-2}$

Put it all together:
$$X(z) = \frac{1}{2j} \left[ \frac{a z^{-1} (e^{j w_c} - e^{-j w_c})}{1 - a z^{-1} (e^{j w_c} + e^{-j w_c}) + a^2 z^{-2}} \right]$$

Rearrange to bring the $2j$ into the numerator expression:
$$X(z) = \frac{a z^{-1} \left[ \frac{e^{j w_c} - e^{-j w_c}}{2j} \right]}{1 - a z^{-1} (e^{j w_c} + e^{-j w_c}) + a^2 z^{-2}}$$

#### **Step 7: Final Conversion back to Trigonometric forms**
We know that:
*   $\frac{e^{j w_c} - e^{-j w_c}}{2j} = \sin(w_c)$
*   $e^{j w_c} + e^{-j w_c} = 2\cos(w_c)$

Substituting these back yields:
$$X(z) = \frac{a z^{-1} \sin(w_c)}{1 - 2 a z^{-1} \cos(w_c) + a^2 z^{-2}}$$

To express the result in positive powers of $z$, multiply the numerator and denominator by $z^2$:
$$X(z) = \frac{a z^{-1} \sin(w_c) \cdot z^2}{(1 - 2 a z^{-1} \cos(w_c) + a^2 z^{-2}) \cdot z^2}$$
$$X(z) = \frac{a z \sin(w_c)}{z^2 - 2az \cos(w_c) + a^2}$$

---

### **Final Answer**

**$X(z) = \frac{az \sin(w_c)}{z^2 - 2az \cos(w_c) + a^2}$**
**ROC: $|z| > |a|$**

*(Note: Providing the full derivation above along with the explicit ROC is what typically earns the full 8 marks in a university examination).*