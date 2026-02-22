Here is the **perfectly balanced, high-yield exam solution** for the VHDL Modeling Styles and Structural Full Adder question. 

---

### **📝 Exam Solution: VHDL Modeling Styles & Structural Full Adder [8 Marks]**

#### **1. Different VHDL Modeling Styles**
VHDL allows designing hardware in three distinct styles depending on the level of abstraction:

1.  **Dataflow Modeling:**
    *   Describes the flow of data through boolean equations.
    *   Uses concurrent signal assignment statements (`<=`).
    *   *Example:* `Sum <= A XOR B; Carry <= A AND B;`
2.  **Behavioral Modeling:**
    *   Describes *what* the circuit does (algorithm/behavior) without worrying about the hardware logic gates.
    *   Uses sequential statements inside a `PROCESS` block (e.g., `if-else`, `case`).
3.  **Structural Modeling:**
    *   Describes *how* the circuit is physically built by connecting smaller pre-designed components together (like drawing a schematic or connecting Legos).
    *   Uses `COMPONENT` declarations and `PORT MAP` to wire them up using `SIGNAL`s.

---

#### **2. Full Adder using Structural Modeling**
A Full Adder can be constructed structurally using **two Half Adders (HA)** and **one OR Gate**.
*   **Internal Signals (Wires):** We need internal wires (`S1`, `C1`, `C2`) to connect the components.

**VHDL Code:**
```vhdl
library ieee;
use ieee.std_logic_1164.all;

-- 1. Main Entity
entity Full_Adder is
    port ( A, B, Cin : in std_logic; 
           Sum, Cout : out std_logic );
end Full_Adder;

architecture Structural of Full_Adder is

    -- 2. Declare Components to be used
    component Half_Adder
        port ( X, Y : in std_logic; S, C : out std_logic );
    end component;

    component OR_Gate
        port ( X, Y : in std_logic; Z : out std_logic );
    end component;

    -- 3. Declare Internal Signals (Wires)
    signal S1, C1, C2 : std_logic;

begin
    -- 4. Instantiate and Connect Components (Port Mapping)
    
    -- First Half Adder: Inputs A, B -> Outputs S1, C1
    HA1: Half_Adder port map (X => A, Y => B, S => S1, C => C1);
    
    -- Second Half Adder: Inputs S1, Cin -> Outputs Sum, C2
    HA2: Half_Adder port map (X => S1, Y => Cin, S => Sum, C => C2);
    
    -- OR Gate: Inputs C1, C2 -> Output Cout
    OG1: OR_Gate port map (X => C1, Y => C2, Z => Cout);

end Structural;
```

---

#### **3. Verification by Drawing Waveform**
*(Draw this simple timing diagram in your exam. It is essentially the Truth Table drawn as high/low signals).*

```text
Time (ns):   0       10      20      30      40
             |       |       |       |       |
A      :  ___|_______|_______|¯¯¯¯¯¯¯|¯¯¯¯¯¯¯|   (0, 0, 0, 1, 1)
B      :  ___|_______|¯¯¯¯¯¯¯|___    |¯¯¯¯¯¯¯|   (0, 0, 1, 0, 1)
Cin    :  ___|¯¯¯¯¯¯¯|¯¯¯¯¯¯¯|¯¯¯¯¯¯¯|¯¯¯¯¯¯¯|   (0, 1, 1, 1, 1)
----------------------------------------------
Sum    :  ___|¯¯¯¯¯¯¯|___    |___    |¯¯¯¯¯¯¯|   (0, 1, 0, 0, 1)
Cout   :  ___|_______|¯¯¯¯¯¯¯|¯¯¯¯¯¯¯|¯¯¯¯¯¯¯|   (0, 0, 1, 1, 1)
```

---

### **💡 Neplish Explainer (Exam ko lagi Perfect Concept)**

**Concept:**
Yo question le VHDL ma code lekhne 3 wota tarika (styles) ra "Structural style" use garera Full Adder banauna sodheko ho.

**Kasari Samjhine? (Point-by-Point):**

1.  **3 Styles of VHDL:**
    *   **Dataflow:** Direct math ko formula lekhne. (e.g., `Y = A + B`).
    *   **Behavioral:** If-Else use garera software jastai logic lekhne. (`PROCESS` keyword use hunxa).
    *   **Structural:** Hardware component haru lai wire le jodne. (Breadboard ma IC jode jastai).

2.  **Structural Full Adder Logic (Lego Jastai):**
    *   Full adder banauna **2 wota Half Adder** ra **1 wota OR Gate** chainxa.
    *   **HA1 (Pahilo block):** A ra B input dinxa. Yesle bich ko Sum (`S1`) ra bich ko Carry (`C1`) nikalxa.
    *   **HA2 (Dosro block):** Tyo `S1` ra bahira bata aako `Cin` lai joder final `Sum` nikalxa. Ani arko carry (`C2`) nikalxa.
    *   **OR Gate:** Duita carry (`C1` ra `C2`) lai OR gate ma pathayepachi final `Cout` niskinxa.
    *   *Code samjhine trick:* Paila `component` declare garne (Saman kinera lyako), ani `signal` declare garne (Taar lyako), ani last ma `port map` garne (Saman ma taar jodeko).

3.  **Waveform:**
    *   Ghabrauna pardaina, yo just **Truth Table lai chitra ma banako ho**.
    *   `___` vanya `0` (Low) ho.
    *   `¯¯¯` vanya `1` (High) ho.
    *   Exam ma A, B, Cin ko kunai 4 wota condition line (jastai 000, 001, 011, 111) ani teskai aadhar ma Sum ra Carry ko line mathi-tala garne. 

Yeti code ra chitra banaidiyou vane **8 ma 8 full marks** kasailay katna sakdaina! 🚀