Timile sodheko "Blink LED wala" question actually **Model Question Set – 1 ko Question 2(b)** ma chha hai ta ("Write a simple Embedded C program to blink an LED connected to PORTB pin 0 of an AVR microcontroller. [7]"). 

Here is the **exam-oriented solution** designed to get you full 7 marks, followed by the **Neplish explainer** to make the bitwise logic clear!

---

### **📝 Exam Solution: Question 2(b) - Blink an LED on PORTB Pin 0 [7 Marks]**

**1. Circuit Connection (Optional but highly recommended for full marks):**
*   **Anode (Positive):** Connected to **PB0** (Pin 0 of PORTB) of the AVR microcontroller through a $330 \Omega$ current-limiting resistor.
*   **Cathode (Negative):** Connected to Ground (GND).

**2. Embedded C Program for AVR (ATmega16/32):**

```c
#define F_CPU 8000000UL      // Define CPU clock frequency as 8 MHz for delay function
#include <avr/io.h>          // Standard AVR input/output library
#include <util/delay.h>      // Library to use _delay_ms() function

int main(void) {
    // Step 1: Configure PB0 as an OUTPUT pin
    // DDRB is the Data Direction Register for PORTB. 
    // Setting bit 0 to '1' makes it an output.
    DDRB |= (1 << PB0);      
    
    // Step 2: Infinite loop to keep blinking forever
    while (1) {
        
        // Turn ON the LED: Set PB0 to HIGH (1)
        PORTB |= (1 << PB0);
        
        // Wait for 1000 milliseconds (1 second)
        _delay_ms(1000);
        
        // Turn OFF the LED: Clear PB0 to LOW (0)
        PORTB &= ~(1 << PB0);
        
        // Wait for 1000 milliseconds (1 second)
        _delay_ms(1000);
        
        /* 
         * Alternative shorter logic inside while(1):
         * PORTB ^= (1 << PB0);  // Toggle the LED state using XOR
         * _delay_ms(1000);
         */
    }
    
    return 0;
}
```

**3. Explanation of the Registers Used:**
*   `DDRB` (Data Direction Register B): Controls whether the pins on PORTB are inputs or outputs. Writing a `1` to a specific bit makes that pin an Output.
*   `PORTB` (Port B Data Register): When configured as an output, writing a `1` to `PORTB` outputs a HIGH voltage (5V, turning the LED ON), and writing a `0` outputs a LOW voltage (0V, turning the LED OFF).
*   `_delay_ms()`: A built-in function that halts the microcontroller execution for the specified number of milliseconds.

---

### **💡 Neplish Explainer (Core Concept Bujhne Tarika)**

**Concept:** 
Euta LED lai microontroller ko PB0 (PORTB ko 0 number pin) ma jodera 1-1 second ko farak ma balne ra nibhaune (Blink) garne program lekhna pareko ho.

**Kasari Samjhine? (Point-by-Point):**

1.  **DDRB (Direction set garne):**
    *   Microcontroller ko pin bata line (Input) ki dine (Output)? Paila tyo set garna parcha.
    *   `DDR` vaneko "Data Direction Register" ho. **`1` lekhe Output, `0` lekhe Input**.
    *   LED balna ta current pathaunu parcha (Output). Tesaile `DDRB` ko 0th bit lai `1` banako: `DDRB |= (1 << PB0);`

2.  **Bitwise Operators (Yo `<<` ra `|` k ho?):**
    *   `1 << PB0` ko matlab ho `1` lai PB0 (0th position) ma shift garne $\rightarrow$ `00000001`.
    *   `|=` (OR) le aaru pin lai disturb nagari bit lai `1` (HIGH/ON) banaucha.
    *   `&= ~` (AND with NOT) le aaru pin lai disturb nagari bit lai `0` (LOW/OFF) banaucha. 
    *   *Exam ma ghabrayou bhane directly `DDRB = 0x01;` ra `PORTB = 0x01;` lekhda pani marks aauxa, tara bitwise lekhda professional dekhincha ra full marks fix huncha!*

3.  **Code ko Logic (Blink garne tarika):**
    *   `while(1)`: Yo vaneko infinite loop ho. Microontroller lai jindagi var yahi kaam gari-rakh vaneko.
    *   Paila LED lai batti balne: `PORTB |= (1 << PB0);` (High garne).
    *   Ani `_delay_ms(1000);` le 1 second wait garne (natra yati fast nibcha ki hami dekhdai dekhdau).
    *   Ani LED nibhaune: `PORTB &= ~(1 << PB0);` (Low garne).
    *   Pheri 1 second wait garne.
    *   Mathi code ma maile "Toggle (`^=`)" garne line pani comment ma haldiekho chu. XOR `^` operator le 0 lai 1 ra 1 lai 0 banaidincha, jasle garda 4 line ko code 2 line mai sakincha!

Yeti lekhyou bhane **7 ma 7 aauxa**. Ekdam simple tara exam ko lagi VIP question ho! 🚀