


Here are the "Ready-to-Write" exam notes for questions 1(a) and 1(b) from your question paper, followed by crystal-clear Neplish explanations to help you memorize them easily.

---

### **1. a) What is Artificial Intelligence? Mention the advantages of Artificial Intelligence. [8 Marks]**

**[Exam Ready Note]**

**Definition of Artificial Intelligence (AI):**
Artificial Intelligence (AI) is a prominent branch of computer science dedicated to creating intelligent systems capable of performing tasks that typically require human intelligence. These tasks include learning from experience, reasoning, problem-solving, understanding natural language, and perceiving the environment. 
According to Russell and Norvig, AI can be defined through four distinct approaches:
1. Thinking Humanly (Cognitive modeling)
2. Acting Humanly (Turing test approach)
3. Thinking Rationally (Laws of thought)
4. Acting Rationally (Rational agent approach - maximizing expected performance).

**Advantages of Artificial Intelligence:**
1. **Automation of Repetitive Tasks:** AI excels at performing monotonous, repetitive tasks without fatigue, freeing up humans to focus on creative and complex problem-solving.
2. **24/7 Availability:** Unlike humans who require rest, AI systems and machines can operate continuously 24 hours a day, 7 days a week, increasing overall productivity.
3. **Reduction of Human Error:** AI models, when programmed properly, can process vast amounts of data with high precision and accuracy, significantly reducing "human error" in fields like data entry and complex calculations.
4. **Handling Hazardous Tasks (Risk Mitigation):** AI-driven robots can be deployed in environments dangerous to humans, such as bomb disposal, space exploration, deep-ocean mining, or handling radioactive materials.
5. **Faster Decision Making:** AI can analyze massive datasets (Big Data) and extract patterns much faster than a human, enabling rapid decision-making in critical areas like algorithmic stock trading or medical diagnosis.
6. **Digital Assistance:** AI powers virtual assistants (like Siri, Alexa, or Chatbots) that provide highly personalized experiences and immediate customer support.

***

**💡 Nepali Core Concept Summary (Neplish):**
*   **AI bhanya k ho?** AI bhaneko computer science ko tyo branch ho jasle machine lai manxe jastai sochne, bujhne ra decision line banauna madat garcha. Exam ma definition lekhda 'Learning, Reasoning, ra Problem-solving' vanne words chutaunai hudaina. Russell ra Norvig ko 4 wota approach (Thinking/Acting Humanly/Rationally) lekhdyo bhane marks full aauxa!
*   **Faida (Advantages) k k hun ta?** 
    1. *Boring kaam aafai garne* (Automation). 
    2. *Thakai nalagne* (24/7 kaam garna sakne). 
    3. *Galti nagarne* (High accuracy, human error nahune). 
    4. *Danger thau ma pathauna milne* (Jastai bomb disarm garna robot pathaune). 
    5. *Chhito decision line* (Thulo data lai second mai process garne).

---

### **1. b) What are the criteria for the evaluation of search algorithms? Compare DFS and BFS.[7 Marks]**

**[Exam Ready Note]**

**Criteria for the Evaluation of Search Algorithms:**
To evaluate and compare the performance of different search algorithms, we use the following four standard criteria:
1. **Completeness:** Is the algorithm guaranteed to find a solution if at least one solution exists?
2. **Optimality:** If there are multiple solutions, is the algorithm guaranteed to find the best (optimal/lowest cost) solution?
3. **Time Complexity:** How long does it take for the algorithm to find a solution? (Usually measured by the number of nodes generated).
4. **Space Complexity:** How much memory (RAM) is required to perform the search? (Usually measured by the maximum number of nodes stored in memory at any point).

**Comparison Between DFS and BFS:**

| Feature | Breadth-First Search (BFS) | Depth-First Search (DFS) |
| :--- | :--- | :--- |
| **Basic Approach** | Explores the search tree level-by-level (shallowest nodes first). | Explores the search tree by diving deep down one path to the bottom before backtracking. |
| **Data Structure Used** | Uses a **Queue** (FIFO - First In, First Out). | Uses a **Stack** (LIFO - Last In, First Out). |
| **Completeness** | **Yes** (Complete if the branching factor is finite). | **No** (It can get stuck in infinite loops or infinitely deep paths). |
| **Optimality** | **Yes** (Optimal if all step costs are equal). | **No** (It might find a longer, sub-optimal path first). |
| **Time Complexity** | $O(b^d)$ (where $b$ is branching factor, $d$ is depth of shallowest solution). | $O(b^m)$ (where $m$ is the maximum depth of the search tree). |
| **Space Complexity** | $O(b^d)$ - **Very High**. It must store all nodes of a level in memory. | $O(bm)$ - **Very Low/Linear**. It only stores a single path from root to leaf node. |

***

**💡 Nepali Core Concept Summary (Neplish):**
*   **Evaluation Criteria:** Kunai pani search algorithm (bato khojne tarika) ramro cha ki nai vanera 4 wota kura ma test garincha:
    1. *Completeness:* Answer fix bhetaucha ki bhetaudaina?
    2. *Optimality:* Bhetayeko answer sabai bhanda best (chhoto bato) ho ki haina?
    3. *Time Complexity:* Kati time lagcha?
    4. *Space Complexity:* Kati memory/RAM khancha?
*   **BFS vs DFS Compare:** 
    *   **BFS (Breadth-First Search):** Yesle line-by-line (level wise) check garcha. **Queue** use garcha. Answer fix bhetcha (Complete) ra best answer bhetcha (Optimal). Tara sabai level ko data save garna parne vayekole **Memory ekdum dherai khancha** ($O(b^d)$).
    *   **DFS (Depth-First Search):** Yesle euta bato samatepachi tesko chheu sammai pugcha. **Stack** use garcha. Memory ekdum **kam khancha** ($O(bm)$). Tara yo baango-tingo bato ma fasna sakcha (Not complete) ra bhetayeko answer sabai bhanda best nahuna pani sakcha (Not optimal).


### **A* Search Algorithm (Short & Exam-Ready)**

**[Exam Ready Note]**

**Concept:** 
A* (A-star) is the most popular **Informed Search Algorithm**. It finds the shortest path by combining the actual cost taken so far with the estimated cost to reach the goal. 
It uses the evaluation function: **$f(n) = g(n) + h(n)$**
*   **$g(n)$**: Actual cost from the start node to the current node $n$.
*   **$h(n)$**: Heuristic (estimated) cost from the current node $n$ to the goal.
*   **$f(n)$**: Total estimated cost of the path through node $n$.

**Algorithm Steps:**
1.  **Initialize** two lists: 
    *   `OPEN` (Priority Queue to store unvisited nodes, sorted by lowest $f(n)$).
    *   `CLOSED` (List to store already visited nodes).
2.  Put the **Start Node** into the `OPEN` list.
3.  **Loop** while the `OPEN` list is not empty:
    *   **Pick** the node $n$ with the lowest $f(n)$ from `OPEN`.
    *   If $n$ is the **Goal Node**, return SUCCESS and trace back the path.
    *   Otherwise, remove $n$ from `OPEN` and put it in `CLOSED`.
    *   **Expand** node $n$ (generate its neighbors/successors).
    *   For each neighbor:
        *   Calculate its $f(n) = g(n) + h(n)$.
        *   If it is neither in `OPEN` nor `CLOSED`, add it to `OPEN`.
        *   If it is already in `OPEN` but with a higher cost, **update** it with this new lower cost.
4.  If `OPEN` becomes empty and the goal is not reached, return FAILURE.

***

**💡 Nepali Core Concept Summary (Neplish):**
*   **A* (A-star) Algorithm** sabai vanda best search technique ho. Yesle andha vayera bato khojdaina, formula lagaucha: **$f(n) = g(n) + h(n)$**.
*   **$g(n)$** bhaneko start point bata ahile ko thau samma aaudako actual kharcha (Past cost) ho. 
*   **$h(n)$** bhaneko ahile ko thau bata goal samma pugna kati lagla vanera guess gareko kharcha (Future cost/Heuristic) ho.
*   **Algorithm ko idea:** Duita list banaune (OPEN ra CLOSED). Suruma Start node lai OPEN ma halne. Tespachi OPEN list bata sabai vanda kam $f(n)$ (sasto bato) vako node nikalne. Yadi tyo goal ho vane sakkiyo! Haina vane tesko chhimeki (neighbors) haru ko $f(n)$ nikalne ra OPEN list ma halne. Yo process goal navetesamma repeat garirakhne.


### **How to Optimize the A* Algorithm (Exam-Ready Note)**

**[Exam Ready Note]**

While A* is optimally efficient for any given heuristic, its main drawback is its **Space Complexity** (it runs out of memory quickly because it keeps all generated nodes in memory). To optimize the A* algorithm in terms of speed and memory, we can use the following techniques:

**1. Improving the Heuristic Function ($h(n)$)**
*   **Concept:** The performance of A* depends heavily on the accuracy of the heuristic. If we design a heuristic $h_2(n)$ that is strictly greater than or equal to another heuristic $h_1(n)$ (but remains admissible, i.e., never overestimates), we say **$h_2$ dominates $h_1$**.
*   **Result:** A dominating heuristic will always expand fewer nodes, drastically optimizing the search time and memory usage.

**2. Weighted A* (Trading Optimality for Speed)**
*   **Concept:** If finding the *perfectly optimal* path is not strictly necessary, we can speed up the search by multiplying the heuristic by a weight $W > 1$.
*   **Formula:** **$f(n) = g(n) + W \times h(n)$**
*   **Result:** This biases the search to focus much more heavily on the goal rather than exploring past costs. It explores significantly fewer nodes and is incredibly fast, though the final path might be slightly longer than the absolute best path.

**3. Using Memory-Bounded Variations**
To solve A*'s massive memory consumption ($O(b^d)$), we can use optimized variants of A* that limit memory usage:
*   **IDA* (Iterative Deepening A*):** Combines the low memory usage of DFS with the optimality of A*. Instead of using a depth limit, it uses an $f$-cost limit. It only requires linear memory ($O(bd)$).
*   **SMA* (Simplified Memory-bounded A*):** It proceeds like A* until memory is full. Then, it drops the least promising node (highest $f$-cost) to make room for new ones.

**4. Data Structure Optimization**
*   **Concept:** The `OPEN` list requires frequent extraction of the node with the lowest $f(n)$. 
*   **Result:** Instead of using a simple array or list (which takes $O(N)$ time to search), implementing the `OPEN` list as a **Min-Heap** or **Priority Queue** reduces the time to find the best node to $O(\log N)$, making the algorithm run much faster.

***

**💡 Nepali Core Concept Summary (Neplish):**
A* Algorithm ekdum ramro ho tara yesko eutei thulo problem cha: **Memory (RAM) dherai khancha** kina vane yesle sabai node lai save garera rakhcha. Yeslai optimize (fast ra better) garna 4 wota tarika chan:

1.  **Heuristic Ramro Banaune:** Goal samma pugne distance ko exact guess (Dominant heuristic) garna sakyo bhane useless bato haru check garna pardaina.
2.  **Weighted A\*:** $h(n)$ lai kunai number (Weight $W$) le multiply gardine. Yesle algorithm lai ekdum fast banauncha tara aayeko answer 100% best (optimal) chai nahuna sakcha. Fast answer chaiyeko bela yo use huncha.
3.  **Memory-Bounded A\* (IDA\*):** RAM full hune problem solve garna IDA* (Iterative Deepening A*) use garne. Yesle DFS ko jasto trick lagayera memory ekdum kam khancha ($O(bd)$).
4.  **Min-Heap Data Structure:** OPEN list bata sabai vanda sasto $f(n)$ vako node khojna time lagcha. Yadi list ko sato 'Min-Heap' data structure use garyo vane, sasto node khojne kaam ekdum fast ($O(\log N)$) huncha.


Here are the "Ready-to-Write" exam notes and solutions for questions 3(a) and 3(b), complete with Neplish explanations.

---

### **3. a) Represent following statements into predicate logic. [8 Marks]**

**[Exam Ready Note]**

**i) All Hindu are either loyal to Krishna or Shiva.**
*   *Predicates:* $Hindu(x)$, $LoyalTo(x, y)$. *Constants:* $Krishna, Shiva$.
*   **FOL:** $\forall x (Hindu(x) \rightarrow LoyalTo(x, Krishna) \lor LoyalTo(x, Shiva))$

**ii) Every gardener like sun.**
*   *Predicates:* $Gardener(x)$, $Likes(x, y)$. *Constant:* $Sun$.
*   **FOL:** $\forall x (Gardener(x) \rightarrow Likes(x, Sun))$

**iii) There is exactly two red mushrooms.**
*   *Predicates:* $Mushroom(x)$, $Red(x)$.
*   *(Logic Concept: We must state that there exist two distinct red mushrooms, $x$ and $y$, and if any other object $z$ is a red mushroom, it must be either $x$ or $y$.)*
*   **FOL:** $\exists x \exists y (\; Mushroom(x) \land Red(x) \land Mushroom(y) \land Red(y) \land (x \neq y) \;\land\; \forall z (Mushroom(z) \land Red(z) \rightarrow (z = x \lor z = y)) \;)$

**iv) Every parents are older than their childs.**
*   *Predicates:* $Parent(x, y)$ (x is parent of y), $Older(x, y)$ (x is older than y).
*   **FOL:** $\forall x \forall y (Parent(x, y) \rightarrow Older(x, y))$

***

**💡 Nepali Core Concept Summary (Neplish):**
*   **i)** "All" aayeko le $\forall x$ ra $\rightarrow$ use garne. "Either OR" ko lagi $\lor$ (OR) sign use garne.
*   **ii)** "Every" aayeko le $\forall x$ ra $\rightarrow$ use garne. Sun lai constant maneyra $Likes(x, Sun)$ lekhne.
*   **iii)** Yo exam ko sabai vanda tricky question ho! "Exactly two" (thakkai dui wota) dekhauna ko lagi: Paila $x$ ra $y$ duitai Red Mushroom ho ra ti dube farak hun ($x \neq y$) vanne. Tespachi $\forall z$ lagayera yadi kunai tesro object ($z$) pani Red Mushroom ho bhane, tyo ki ta $x$ huna parcha ki ta $y$ huna parcha ($z = x \lor z = y$) vanera fix gardine.
*   **iv)** "Every" cha so $\forall x \forall y$ use garne. Relation lai $Parent(x,y)$ manney, jasai meaning $x$ chai $y$ ko parent ho. Implies ($\rightarrow$) pachi $Older(x,y)$ lekhdine.

---

### **3. b) Define Bayes rule for probabilistic problem. [...] Calculate probability using Bayes theorem. [7 Marks]**

**[Exam Ready Note]**

**1. Definition of Bayes' Rule:**
Bayes' theorem is a mathematical formula used in probability and artificial intelligence to calculate the **posterior probability** of an event based on prior knowledge of conditions that might be related to the event. It updates our belief in a hypothesis (cause) after observing new evidence (effect).

The formula is:
$$P(A|B) = \frac{P(B|A) \times P(A)}{P(B)}$$
*Where:*
*   $P(A|B)$ = Posterior probability (Probability of Cause A given Effect B).
*   $P(B|A)$ = Likelihood (Probability of Effect B given Cause A).
*   $P(A)$ = Prior probability of Cause A.
*   $P(B)$ = Marginal probability of Effect B.

---
**2. Solution to the Numerical Problem:**

**Given Data:**
*   Probability of Symptoms (Effect), $P(S) = \frac{1}{20} = 0.05$
*   Probability of Disease (Cause), $P(D) = \frac{1}{45000}$
*   Probability of Symptoms given Disease (Likelihood), $P(S|D) = 50\% = \frac{1}{2} = 0.50$

**To Find:**
*   Probability of Disease given Symptoms (Posterior), $P(D|S) = ?$

**Applying Bayes' Theorem:**
$$P(D|S) = \frac{P(S|D) \times P(D)}{P(S)}$$

*Putting the values into the formula:*
$$P(D|S) = \frac{0.50 \times \left(\frac{1}{45000}\right)}{\left(\frac{1}{20}\right)}$$

$$P(D|S) = \frac{\left(\frac{1}{2}\right) \times \left(\frac{1}{45000}\right)}{\left(\frac{1}{20}\right)}$$

$$P(D|S) = \frac{\left(\frac{1}{90000}\right)}{\left(\frac{1}{20}\right)}$$

$$P(D|S) = \frac{1}{90000} \times \frac{20}{1}$$

$$P(D|S) = \frac{20}{90000} = \frac{2}{9000} = \frac{1}{4500}$$

$$P(D|S) \approx 0.000222 \text{ (or } 0.0222\%)$$

**Answer:** The probability of having the disease given the symptoms is **1/4500** (approx 0.0222%).

***

**💡 Nepali Core Concept Summary (Neplish):**
*   **Bayes Rule ko Definition:** Kunai pani event vaisakepachi (jastai symptom dekhiepachi), tesko main kaaran (disease) k ho vanera purano data use garera probability nikalne formula lai Bayes Theorem vaninxa. $P(Cause | Effect)$ nikalne kaam yesle garcha.
*   **Numerical Trick:** Question maa value haru words ma ghumaera diyeko cha, tesaile paila carefully value tipne. 
    *   $P(Symptoms)$ = $1/20$
    *   $P(Disease)$ = $1/45000$
    *   $P(Symptoms | Disease)$ = "probability of symptoms condition to disease" vanna leketko cha, yo $50\%$ wa $1/2$ ho.
    *   Hamilai "Probability of disease condition to symptoms" nikalna vaneko cha, matlab $P(Disease | Symptoms)$.
*   Aba sidhai formula ma fraction halera solve garne. $0.5$ lai $1/2$ banayera solve garda calculation ekdum fast ra mistake nabhai garna sakincha! Result $1/4500$ aauxa.


Here is a detailed check of your handwritten First-Order Logic (FOL) statements. You have a good grasp of the concepts, but there are a few syntax and scoping errors that could cost you marks in an exam. 

Let's review them one by one:

### **General Exam Tip First:**
You are using a colon (`:`) after your quantifiers (like `∀x :`). While some professors might understand it, **it is non-standard in formal logic**. You should use brackets to define the scope. 
*   *Don't write:* `∀x : P(x) -> Q(x)`
*   *Write:* `∀x ( P(x) -> Q(x) )`

---

### **i) All Hindu are either loyal to Krishna or Shiva.**
*   **Your Answer:** `∀x : Hindu(x) -> loyalto(x, krishna) V loyalto(x, shiva)`
*   **Review:** **Conceptually Correct, Syntax needs minor fix.**
    The logic is absolutely right. However, to avoid ambiguity with the OR (`V`) operator, you should wrap the entire "Then" part in brackets, and wrap the whole statement in brackets.
*   **Corrected Format:** 
    `∀x ( Hindu(x) -> (loyalto(x, Krishna) ∨ loyalto(x, Shiva)) )`

### **ii) Every gardener like sun.**
*   **Your Answer:** `∀x : gardener(x) -> like(x, sun)`
*   **Review:** **Conceptually Correct, Syntax needs minor fix.**
    Again, the logic is perfect. Just replace the colon with brackets for standard notation.
*   **Corrected Format:** 
    `∀x ( gardener(x) -> like(x, Sun) )`

### **iii) There is exactly two read mushroom.** 
*(Note: Assuming 'red mushroom' based on standard questions)*
*   **Your Answer:** `∃x ∃y : readmushroom(x) ∧ readmushroom(y) ∧ x ≠ y ∧ ∀z (Read_mushroom(z)) -> (z = x V z = y))`
*   **Review:** **Concept is 90% there, but MAJOR BRACKET ERROR.**
    You successfully remembered the logic for "exactly two" (exist x, exist y, they are different, and if any z exists, it must be x or y). **Brilliant!** 
    *However*, your bracket placement on the `∀z` part is wrong. You closed the bracket right after `Read_mushroom(z)`, which breaks the implication. The Implies (`->`) must be *inside* the `∀z` scope.
*   *Your mistake:* `... ∀z (Read_mushroom(z)) -> ...` ❌
*   *Correct scope:* `... ∀z (Read_mushroom(z) -> (z = x ∨ z = y)) ` ✅
*   **Corrected Format:**
    `∃x ∃y ( RedMushroom(x) ∧ RedMushroom(y) ∧ (x ≠ y) ∧ ∀z (RedMushroom(z) -> (z = x ∨ z = y)) )`

### **iv) Every parents is older than child.**
*   **Your Answer:** `∀x : parent(x, y) -> older(x, y)`
*   **Review:** **INCORRECT (Free Variable Error).**
    You introduced the variable `y` in `parent(x, y)` and `older(x, y)`, but you completely forgot to declare `y` at the beginning! In FOL, every variable must be bound to a quantifier. Because `y` doesn't have a `∀` or `∃` in front of it, it is a "free variable," making the formula mathematically invalid.
    The statement means: "For ALL x, and for ALL y, if x is the parent of y, then x is older than y."
*   **Corrected Format:** 
    `∀x ∀y ( parent(x, y) -> older(x, y) )`

***

### 💡 **Nepali Core Concept Summary (Exam Tips):**
1.  **Colon (:) use nagarne!** Quantifier pachi sidhai bracket `(` start garne ra last ma `)` close garne. (e.g., `∀x ( ... )`).
2.  **Free Variable galti:** Question number 4 ma timile `y` use garyau tara agadi `∀y` lekhnau. Yesto garda exam ma sidhai 0 marks aauxa! Variable use garne bittikai tesko aagadi $\forall$ wa $\exists$ hunei parcha.
3.  **Exactly Two ko Bracket:** Question 3 ma timile logic ekdum sahi liyeka thiyau, just bracket bigryo. `∀z (Condition -> Conclusion)` format ma hunuparcha. Bracket lekhda dhyaan dine.