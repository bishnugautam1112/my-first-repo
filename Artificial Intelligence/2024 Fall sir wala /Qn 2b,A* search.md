


Here is the **"Slay" Material for 2024 Q2b**. This is a guaranteed 8-mark numerical. If you master this, you have practically passed the exam!

---

### **2024 Q2 b) What is A* search? Apply A* search to determine the optimal path from Node S to Node G.**
![alt text](image-1.png)
#### 📝 High-Yield Exam Note (Write this to get full marks)

**1. What is A* Search?**
A* (A-star) search is an advanced, informed "Best-First Search" algorithm. It finds the shortest path from a start node to a goal node by combining actual costs and estimated costs.
It uses the evaluation function: 
$$f(n) = g(n) + h(n)$$
Where:
*   $g(n)$ = Exact path cost from the Start node to Node $n$.
*   $h(n)$ = Heuristic estimated cost from Node $n$ to the Goal node.
*   *Note:* A* is complete and optimal if the heuristic $h(n)$ is admissible (never overestimates the real cost).

**2. Applying A* Search (Step-by-Step Solution):**
*Start at Node S. Always expand the node with the lowest $f(n)$.*

*   **Step 1: Start Node**
    *   $S \rightarrow f(S) = g(S) + h(S) = 0 + 7 = 7$
    *   *Open List:* `[S(7)]`

*   **Step 2: Expand S** (Calculate for its neighbors A, B, C)
    *   Path `S -> A`: $f(A) = 3 + 6 = \mathbf{9}$
    *   Path `S -> B`: $f(B) = 4 + 4 = \mathbf{8}$  *(Lowest, will expand next)*
    *   Path `S -> C`: $f(C) = 7 + 5 = 12$
    *   *Open List:* `[B(8), A(9), C(12)]`

*   **Step 3: Expand B** (Neighbor is E)
    *   Path `S -> B -> E`: $g(E) = (4+4)=8$. $f(E) = 8 + 2 = \mathbf{10}$
    *   *Open List:* `[A(9), E(10), C(12)]` *(Notice A has 9, so we expand A next!)*

*   **Step 4: Expand A** (Neighbors are D, E)
    *   Path `S -> A -> D`: $g(D) = (3+4)=7$. $f(D) = 7 + 2 = \mathbf{9}$ *(Lowest)*
    *   Path `S -> A -> E`: $g(E) = (3+7)=10$. $f(E) = 10 + 2 = 12$
    *   *Open List:* `[D(9), E(10), C(12), E-via-A(12)]`

*   **Step 5: Expand D** (Neighbor is E)
    *   Path `S -> A -> D -> E`: $g(E) = (7+5)=12$. $f(E) = 12 + 2 = 14$
    *   *Open List:* `[E(10), C(12), E-via-A(12), E-via-D(14)]`

*   **Step 6: Expand E (with lowest cost 10)** (Neighbor is G)
    *   Path `S -> B -> E -> G`: $g(G) = (8+3)=11$. $f(G) = 11 + 0 = \mathbf{11}$
    *   *Open List:* `[G(11), C(12), E(12), E(14)]`

*   **Step 7: Expand G**
    *   Goal Reached!

**Final Answer:**
*   **Optimal Path:** **S $\rightarrow$ B $\rightarrow$ E $\rightarrow$ G**
*   **Optimal Cost:** **11**

---

### 🧠 Core Concept Guide (Romanized Nepali + English)

**Numerical bigrina nadine "Exam Hacks":**
*   **The Biggest Mistake Students Make:** $g(n)$ nikalda naya edge ko value matra jodne haina! Start dekhi ko sabai bato ko cost jod-dai lyaune ho. (Example: Node E samma pugda `S->B ko 4` ra `B->E ko 4` jodera balla $g=8$ vako ho).
*   **Queue/List Rule:** Jaba euta node expand garxau, sabai open nodes bata **sab vanda sano $f(n)$ vako** lai matra chunne. 
    *   *Step 3 paxi hera ta:* Hami le B bata E nikalem ($f=10$). Tara purano A ko f-value ta 9 thiyo ni! Tei vayera E bata sidhai G ma najani, paxi farkera A lai expand gareko ho. A* ko "Magic" nai yehi ho!
*   **Presentation trick:** Exam ma dherai sentence lekhnu pardaina. Mathi ko jastai **"Path -> f(n) calculation -> Open List"** format ma lekhdeu, sir le step herne bittikai 8 ma 8 thopkidinxa.

---

**Status:** 2024 Q2(b) ✅ Slayed! 

We are making great time. Ready for **2024 Q3a (Mini-Max & Alpha-Beta Pruning)**? This is another easy numerical from Game Trees! Type "Let's prune" to continue!