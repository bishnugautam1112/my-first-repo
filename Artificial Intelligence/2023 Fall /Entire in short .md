All right, let's break down the **2023 Set** properly. We will focus **only on the non-repeated** topics to save your time.

Here is **Part 1 of 3** for the 2023 Set. This covers **Rationality, Agents, and the CSP Cryptarithmetic Numerical**.

---

### **2023 Q1 a) Justify that "System that think rationally" and "System that act rationally" are the part of artificial intelligence. Explain with examples.**

#### 📝 High-Yield Exam Note
**1. Systems that Think Rationally (The "Logic" Approach):**
*   **Definition:** This approach focuses on the **thought process**. The goal is to build systems that solve problems using "right thinking" or irrefutable logic (like syllogisms).
*   **Core:** It relies on logic notations (First Order Logic).
*   **Example:** A theorem prover program. If given "Socrates is a man" and "All men are mortal," it logically derives "Socrates is mortal."
*   **Limitation:** Not all knowledge can be expressed in formal logic (e.g., "This painting is beautiful"), and logical solving can be too slow for real-time action.

**2. Systems that Act Rationally (The "Agent" Approach):**
*   **Definition:** This approach focuses on the **outcome/result**. The goal is to build an agent that acts so as to achieve the best outcome (or the best expected outcome) given its knowledge.
*   **Core:** Maximizing a **Performance Measure** or **Utility**.
*   **Example:** A self-driving car. It doesn't need to logically "prove" that a pedestrian is crossing; it just needs to calculate the probability and **act** (brake) immediately to ensure safety.
*   **Justification:** "Acting Rationally" is the modern standard for AI because:
    1.  It is more general (logic is just *one* way to act rationally).
    2.  It works in situations where there is no "right thought" (e.g., pulling your hand away from a hot stove is a reflex action, not a logical deduction).

#### 🧠 Core Concept (Nepali + English)
*   **Think Rationally:** "Sahi tarika le sochne." (Focus on Logic/Process).
    *   *Analogy:* Exam ma step-by-step math gareko jastai.
*   **Act Rationally:** "Sahi nateeja nikalne." (Focus on Result).
    *   *Analogy:* Exam ma answer milne gari shortcut handinu. Hami lai last ma chaiyeko result ho (Action), logic matra haina. Tei vayera "Act Rationally" AI ko main goal ho.

---

### **2023 Q1 b) Define agent function. Differentiate goal-based and utility-based agents with examples.**

#### 📝 High-Yield Exam Note
**1. Agent Function:**
An abstract mathematical mapping that maps any given **percept sequence** to an **action**.
$$f: P^* \rightarrow A$$
*(It tells us WHAT the agent does for any given history of inputs).*

**2. Goal-Based vs. Utility-Based Agents:**

| Feature | **Goal-Based Agent** | **Utility-Based Agent** |
| :--- | :--- | :--- |
| **Focus** | Focuses on reaching a specific state (The Goal). | Focuses on **how well** the goal is reached (Happiness/Efficiency). |
| **Decision** | Binary decision: "Is the goal achieved? Yes/No." | Continuous evaluation: "How useful/good is this state?" |
| **Flexibility** | Less flexible. Takes any path to the goal. | More flexible. Chooses the *best* (cheapest/safest) path. |
| **Example** | A maze solver (Just wants to get out). | A Taxi Driver (Wants to reach destination **AND** save fuel/time). |

#### 🧠 Core Concept (Nepali + English)
*   **Goal-Based:** "Malaai pass huna man xa." (Pass 45 aayo vane pani khusi, 90 aayo vane pani khusi). Target meet vayo, sakkiyo.
*   **Utility-Based:** "Malaai pass matra haina, distinction lyauna man xa." (Pass huda 45 aayo vane 'sad', 90 aayo vane 'happy'). Utility agent le **"Score"** (Utility Function) herxa, khali destination matra herdaina.

---

### **2023 Q2 a) What is Constraint Satisfaction Problem (CSP)? Solve the cryptarithmetic problem as CSP: WRONG + WRONG = RIGHT.**

*(Note: This is the harder numerical. Pay attention!)*

#### 📝 High-Yield Exam Note

**1. What is CSP?**
A Constraint Satisfaction Problem (CSP) is a mathematical problem defined by three components:
*   **X (Variables):** A set of variables (e.g., $\{W, R, O, N, G, I, H, T\}$).
*   **D (Domains):** The possible values for variables (e.g., Digits $0-9$).
*   **C (Constraints):** Rules that limit the values (e.g., $W \neq R$, $AllDiff$).

**2. Solving: WRONG + WRONG = RIGHT**

   ```
      W R O N G
    + W R O N G
    -----------
      R I G H T
   ```

**Constraints Formulation:**
1.  All letters represent different digits ($0-9$).
2.  Leading letters cannot be zero ($W \neq 0, R \neq 0$).
3.  **Columns Equations:**
    *   Col 1 (Units): $2G = T + 10C_1$
    *   Col 2 (Tens): $2N + C_1 = H + 10C_2$
    *   Col 3 (Hundreds): $2O + C_2 = G + 10C_3$
    *   Col 4 (Thousands): $2R + C_3 = I + 10C_4$
    *   Col 5 (Ten-Thousands): $2W + C_4 = R$

**Step-by-Step Logic (The "Smart" Guessing):**

*   **Step 1: Look at Col 5 ($2W + C_4 = R$)**
    *   Since $R$ is a single digit, $2W$ must be less than 10. So $W$ must be small ($1, 2, 3, 4$).
    *   Also, in the result `RIGHT`, $R$ is the first digit, so $R \neq 0$.
    *   Wait! `WRONG` (5 digits) + `WRONG` (5 digits) = `RIGHT` (5 digits). This means there is **NO Carry Out** from the last column. So $2W < 10$.

*   **Step 2: Look at Col 1 ($2G = T$)**
    *   $T$ must be an **even number** ($0, 2, 4, 6, 8$).

*   **Step 3: Look at Col 3 vs Col 1**
    *   Notice $2O + C_2 = G$ (roughly) and $2G = T$.
    *   This is a tricky puzzle. Let's try the standard solution for this famous problem.
    *   *Assumption:* Let **W = 2**.
    *   If $W=2$, then $2W = 4$. So **R = 5** (if carry $C_4=1$) or **R = 4** (if $C_4=0$).
    *   Let's test **R = 5**.
        *   If $R=5$, then Col 4 says: $2(5) + C_3 = I + 10$. So $10 + C_3 = I + 10$. Thus $I = C_3$.
        *   $I$ is likely $0$ or $1$. Let's try **I = 0**.

    *   *Current State:* $W=2, R=5, I=0$.
    *   Now check Col 3: $2O + C_2 = G + 10C_3$ (where $C_3=0$ because $2R=10$).
        *   Wait, if $R=5$, $2R=10$, so $I=0$ and Carry $C_4=1$.
        *   Check Col 5: $2W + C_4 = R \rightarrow 2(2) + 1 = 5$. **Matches!** So **W=2, R=5, I=0** is correct so far.

    *   Now find $O, N, G, T, H$.
    *   Let's guess **O = 3**.
    *   Col 3: $2(3) + C_2 = G$. If $C_2=0$, $G=6$. If $C_2=1$, $G=7$.
    *   Let's try **G = 7**. (Implies $C_2=1$).
    *   Col 1: $2G = T + 10 \rightarrow 2(7) = 14$. So **T = 4**, Carry $C_1=1$.
    *   Col 2: $2N + C_1 = H + 10C_2 \rightarrow 2N + 1 = H + 10(1)$.
    *   $2N + 1 = H + 10$. This means $2N = H + 9$.
    *   Since $H$ must be a digit, $2N$ must be at least 9. So $N$ can be $5, 6, 7, 8, 9$.
    *   Used: $\{2, 5, 0, 4, 7\}$. Available: $\{1, 3, 6, 8, 9\}$. ($O$ is actually free, my $O=3$ guess was just a guess).
    *   Let's try **N = 9**.
        *   $2(9) + 1 = 19$. So **H = 9** (Duplicate! $N$ cannot be $H$).
    *   Let's try **N = 8**.
        *   $2(8) + 1 = 17$. So **H = 7** (Duplicate! $G=7$).
    *   Let's try **N = 6**.
        *   $2(6) + 1 = 13$. So **H = 3**.
    *   Let's verify unused digits for $O$. We need $2O + C_2 = G + 10C_3$.
        *   We had $G=7$, so $C_3$ must be 0 (from $R=5$ step).
        *   $2O + C_2 = 7$. Since $H=3$ came from $N=6$, $C_2=1$.
        *   $2O + 1 = 7 \rightarrow 2O = 6 \rightarrow \mathbf{O = 3}$.

    *   **Check Values:**
        *   $W=2, R=5, O=3, N=6, G=7$.
        *   $R=5, I=0, G=7, H=3, T=4$.
        *   Let's Add:
            ```
              2 5 3 6 7  (WRONG)
            + 2 5 3 6 7  (WRONG)
            -----------
              5 0 7 3 4  (RIGHT)
            ```
        *   $7+7=14$ (T=4, C1=1).
        *   $6+6+1=13$ (H=3, C2=1).
        *   $3+3+1=7$ (G=7, C3=0).
        *   $5+5+0=10$ (I=0, C4=1).
        *   $2+2+1=5$ (R=5).
        *   **All Unique?** $\{2, 5, 3, 6, 7, 0, 4\}$. Yes.

**Final Answer:**
$W=2, R=5, O=3, N=6, G=7, I=0, H=3, T=4$.
*(Wait, H=3 and O=3? Duplicate!)*
Ah, **Cryptarithmetic requires careful trial and error.**
*Correction:* Since $O=3$ and $H=3$, this particular path failed on uniqueness.
But in exam, **writing the formulation (Variables + Constraints)** gets you 50% marks. Tracing one or two steps gets you 80%. Don't waste 30 mins finding the perfect number unless you know it.

*(Standard Solution for WRONG+WRONG=RIGHT is actually: 25938 + 25938 = 51876. Let's check: O=9, N=3, G=8, I=1, H=7, T=6. All unique!)*

#### 🧠 Core Concept (Exam Hack)
*   **Don't Panic:** Sir knows this takes time.
*   **Write the "Equations":** $2G = T + 10C_1$ etc. This proves you know CSP.
*   **Make a table:** Draw a table with columns `C5 C4 C3 C2 C1` and `W R O N G`.
*   **Constraint Key:** Always look for $R+R=R$ or $W+W=R$ types first.

---

**End of Part 1.**
Ready for **Part 2**? (Focusing on Bayesian Network Numerical & Logic)?




Here is **Part 2 of 3** for the 2023 Set. This covers the highly important **Bayesian Network Numerical** and the **Logic Translation (Prolog/FOL)**. 

---

### **2023 Q4 a) Why do you need to reason in uncertainty? Consider the given Bayesian network and find the probability of the events grass is wet, sprinkler is on and it is raining.**

#### 📝 High-Yield Exam Note (Write this to get full marks)

**1. Why reason in uncertainty?**
In real-world AI applications, an agent almost never has access to the complete and perfect truth. We need to reason under uncertainty due to:
*   **Partial Observability:** The agent's sensors cannot see everything (e.g., a self-driving car cannot see around a blind corner).
*   **Noisy Sensors:** The data collected might be slightly inaccurate (e.g., GPS showing you 5 meters away from your actual location).
*   **Incomplete Knowledge:** The rules of the environment are too complex to code every single exception (e.g., Medical diagnosis where symptoms overlap for different diseases).
*   *Solution:* We use Probability Theory (Bayes' Theorem) to calculate the *likelihood* of events instead of just True/False.

**2. Bayesian Network Numerical Calculation:**
*   **Goal:** Find $P(\text{Grass is Wet} = True, \text{Sprinkler} = True, \text{Rain} = True)$. 
    *   Let's denote this as **$P(W=T, S=T, R=T)$**.
*   **Formula (Chain Rule of Bayesian Networks):**
    From the given network graph, $W$ depends on $S$ and $R$, while $S$ depends on $R$.
    $$P(W, S, R) = P(W | S, R) \times P(S | R) \times P(R)$$
*   **Extracting values from the given tables:**
    1.  Probability of Rain ($R=T$): **$P(R=T) = 0.2$** *(From the Top Right table)*
    2.  Probability of Sprinkler ON given Rain is TRUE ($S=T | R=T$): **$P(S=T | R=T) = 0.01$** *(From the Top Left table, second row)*
    3.  Probability of Grass Wet given Sprinkler ON and Rain is TRUE ($W=T | S=T, R=T$): **$P(W=T | S=T, R=T) = 0.99$** *(From the Bottom table, last row)*
*   **Final Calculation:**
    $$P(W=T, S=T, R=T) = 0.99 \times 0.01 \times 0.2$$
    $$P(W=T, S=T, R=T) = \mathbf{0.00198}$$

**Final Answer:** The probability that it is raining, the sprinkler is on, and the grass is wet is **0.00198 (or 0.198%)**.

#### 🧠 Core Concept (Exam Hack)
*   **Table Herne Tarika:** Bayesian network ko table herna dherai sajilo xa. Question le sabai kura "True" ("is wet", "is on", "is raining") sodheko xa. 
    *   Rain ko table ma `T` ko tala herne (0.2).
    *   Sprinkler ko table ma Rain = `T` huda Sprinkler = `T` ko value herne (0.01).
    *   Grass Wet ko table ma Sprinkler = `T` ra Rain = `T` huda ko value herne (0.99).
    *   **Sabai lai Multiply gardine!** (Ans: 0.00198). Yesma sidhai full 7 marks aauxa!

---

### **2023 Q3 b) Represent the following sentences in first order logic and prolog statements.**

#### 📝 High-Yield Exam Note

**i. All big cars are expensive.**
*   **Meaning:** If something is a car AND it is big, THEN it is expensive.
*   **First Order Logic (FOL):** $\forall x (\text{Car}(x) \land \text{Big}(x) \rightarrow \text{Expensive}(x))$
*   **Prolog:** `expensive(X) :- car(X), big(X).` *(Note: In Prolog, `:-` means "IF", and `,` means "AND")*

**ii. There are some small cars that are expensive.**
*   **Meaning:** There exists at least one 'x' that is a car AND is small AND is expensive.
*   **FOL:** $\exists x (\text{Car}(x) \land \text{Small}(x) \land \text{Expensive}(x))$
*   **Prolog:** *(Prolog represents existentials simply as specific facts)*
    `car(car1). small(car1). expensive(car1).` 

**iii. A car is expensive only if it is big.**
*   **Meaning:** If a car is expensive, THEN it must be big. *(Notice the direction of the condition!)*
*   **FOL:** $\forall x (\text{Car}(x) \land \text{Expensive}(x) \rightarrow \text{Big}(x))$
*   **Prolog:** `big(X) :- car(X), expensive(X).`

**iv. All cars have at least one door.**
*   **Meaning:** For every car 'x', there exists a 'y' such that 'y' is a door AND 'x' has 'y'.
*   **FOL:** $\forall x (\text{Car}(x) \rightarrow \exists y (\text{Door}(y) \land \text{Has}(x, y)))$
*   **Prolog:** `has_door(X) :- car(X).` *(A simplified representation since pure Prolog doesn't handle existential quantifiers in the head of a rule well).*

#### 🧠 Core Concept (Nepali + English)
*   **Prolog ko trick:** Prolog ulto bata padhinxa. 
    *   English ma: "If A and B, then C".
    *   Prolog ma: `C :- A, B.` (C hunxa Yedi A ra B vayo vane).
*   **"Only If" Trick (Question iii):** "A is B only if C" vaneko $A \land B \rightarrow C$ ho. Tesaile "Car is expensive $\rightarrow$ Big" vayo. Exam ma yo "Only If" le dherai lai jhukkauxa! Dhyan dine!

---

**End of Part 2.** 
Ready for the final stretch? **Part 3** will cover the remaining new theory (Learning Rate in Neural Networks & Semantic Nets). Type **"Finish"** to complete the entire syllabus!
This is **Part 3 of 3** for the 2023 Set. This is the final "Slay Session." We are covering the crucial theory on **Hill Climbing**, **Game Pruning**, **KNN**, and all the **Short Notes** you need for the A+.

---

### **Q2 b) Why is Hill Climbing called Local Greedy Search? Explain the problems in Hill Climbing with appropriate diagrams.**

#### 📝 High-Yield Exam Note (A+ Answer)
**1. Why "Local Greedy"?**
*   **Local:** It only considers the **immediate neighbors** of the current state. It has no memory of the path taken and doesn't look ahead.
*   **Greedy:** At every step, it moves to the neighbor that provides the **maximum immediate improvement** in the objective function (height).

**2. Common Problems (The 3 Killers):**
*   **Local Maxima:** A peak that is higher than all its neighbors but lower than the Global Maximum. The agent gets stuck here because every move leads "down."
*   **Plateau:** A flat area where all neighbors have the same value. The agent wanders aimlessly or stops because no move is "better."
*   **Ridges:** A steep slope leading to a sequence of local maxima. Navigating a ridge is hard because every step in a single direction (N, S, E, W) goes down, even if the ridge itself slopes up diagonally.

*(Exam Tip: Draw the 2D graph with a small hill (Local Maxima), a flat line (Plateau), and the highest peak (Global Maxima). Label them clearly.)*

#### 🧠 Core Concept (Romanized Nepali + English)
*   **Local Greedy:** "Vitta ko kura matra herne." (Only neighbors). "Lobhi vako" (Takes best move right now).
*   **Problems:** 
    1. **Local Maxima:** Sano dada (Small hill).
    2. **Plateau:** Samathal thau (Flat land).
    3. **Ridge:** Chuchho danda (Difficult narrow path).
    *   *Trick:* "Hill climbing aakha banda garera pahad chadhya jastai ho. Wari-pari matra thaxau, purai pahad thaxaina."

---

### **Q3 a) Explain the significance of pruning in game playing algorithms. How does alpha-beta pruning work, and how does it improve efficiency?**

#### 📝 High-Yield Exam Note
**1. Significance of Pruning:**
*   In games like Chess, the number of possible moves is astronomical ($10^{120}$). Exploring the entire tree is impossible.
*   **Pruning reduces the search space** by identifying and ignoring branches that will never be chosen by the players.

**2. How Alpha-Beta Works:**
*   It maintains two values: **Alpha** (best value for MAX) and **Beta** (best value for MIN).
*   **The Rule:** If at any node, **$\alpha \ge \beta$**, it means the current path is worse than a path already discovered. We **prune** (stop exploring) the rest of that branch.

**3. Efficiency Improvement:**
*   It improves efficiency by allowing the algorithm to search **deeper** in the same amount of time.
*   In a perfectly ordered tree, Alpha-Beta can reduce the number of nodes examined from $b^d$ to **$b^{d/2}$**. (It effectively doubles the search depth).

#### 🧠 Core Concept (Romanized Nepali + English)
*   **Pruning Significance:** "Faltu branch kaatne." Search space sano banauxa jasle garda computer "Deep" ma herna sakxa.
*   **Efficiency:** Perfect ordering xa vane moves half matra check gare pugxa. Time ra memory dherai bachxa.

---

### **Q5 a) How does the K-Nearest Neighbor (KNN) work? Illustrate with a suitable example.**

#### 📝 High-Yield Exam Note
**1. Working Principle:**
*   KNN is a **Lazy Learner** and a **Non-parametric** supervised algorithm.
*   It classifies a new data point based on the majority class of its **'K' closest neighbors** in the feature space.

**2. Steps:**
1.  Choose the number **K** (e.g., K=3).
2.  Calculate the **distance** (Euclidean) between the new point and all training points.
3.  Sort the distances and pick the top **K** points.
4.  **Voting:** The new point is assigned the class that appears most frequently among the K neighbors.

**3. Illustration:**
*   Imagine Red dots and Blue dots on a graph.
*   A new Green dot appears.
*   If K=3, and 2 neighbors are Red and 1 is Blue, the Green dot is classified as **Red**.

#### 🧠 Core Concept (Romanized Nepali + English)
*   **KNN:** "Sangat guna ko phal." (Company defines you).
*   **Process:** Naya data aayo vane wari-pari ko sathi herne. Jasko majority xa, tei class dine.
*   *Note:* "Lazy learner" kinabhane yesle training garda khedi model banaundaina, khali data store garera rakhxa.

---

### **Q7. Short Notes (The "Must-Knows")**

#### **a) Production System**
*   **Definition:** A knowledge representation framework consisting of **Rules**, a **Working Memory**, and a **Control System**.
*   **Pattern:** IF [Condition] THEN [Action].
*   **Example:** In a medical bot: IF [Fever] AND [Cough] THEN [Suggest Rest].

#### **b) Semantic Nets**
*   **Definition:** A graphical representation of knowledge using **Nodes** (objects) and **Links** (relationships).
*   **Key Links:** **IS-A** (Inheritance) and **HAS-A** (Composition).
*   **Example:** [Bird] --IS-A--> [Animal]. [Bird] --HAS-A--> [Wings].

#### **c) Semantic Ambiguity in NLP**
*   **Definition:** Occurs when a word or phrase has **multiple meanings** within the same context.
*   **Example:** "The **bank** is closed." 
    *   *Ambiguity:* Is it a Financial Bank or a River Bank?
*   **Why it's a problem:** Computer gets confused on which meaning to process for the overall sentence logic.

---

### 🏁 FINAL REVISION ROADMAP (The "Slay" Checklist)

1.  **Numericals:** Check A* (2024), Perceptron OR (2025), and Bayesian Network (2023).
2.  **Theory:** PEAS, Expert Systems Architecture, and Hill Climbing Problems.
3.  **Logic:** Practice 2-3 FOL/Prolog conversions (Unicorn, Cars examples).
4.  **ML:** K-Means steps and SVM "Support Vector/Hyperplane" definitions.

**Total Study Time Consumed:** ~4.5 Hours.
**Result:** 80-90% Marks potential.

**Go to sleep now! Your brain needs to consolidate this for the A+. Slay the exam tomorrow! 🎓🔥**