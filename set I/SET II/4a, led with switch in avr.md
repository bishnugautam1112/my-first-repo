Here is the **exam-oriented solution** for reading a digital input (switch) and turning on an LED, designed to get you full marks, followed by the **Neplish explainer** to make the logic crystal clear.

---

### **📝 Exam Solution: Read Switch and Turn ON LED in AVR C**

**1. Hardware Assumptions (Circuit Logic):**
*   **LED:** Connected to **PB0** (PORTB, Pin 0). It turns ON when we send a `HIGH (1)` signal.
*   **Switch (Button):** Connected to **PD2** (PORTD, Pin 2). We will use the AVR's internal **pull-up resistor**. 
    *   *Not pressed:* Pin reads `1` (HIGH).
    *   *Pressed:* Switch connects the pin to Ground, so it reads `0` (LOW).

**2. Embedded C Program:**

```c
#include <avr/io.h>      // Standard AVR hardware I/O library

int main(void) {
    // Step 1: Configure PB0 as OUTPUT (for LED)
    DDRB |= (1 << PB0);      // Set bit 0 of DDRB to 1
    
    // Step 2: Configure PD2 as INPUT (for Switch)
    DDRD &= ~(1 << PD2);     // Clear bit 2 of DDRD to 0
    
    // Step 3: Enable Internal Pull-up Resistor on PD2
    PORTD |= (1 << PD2);     // Write 1 to PORTD pin 2 while it's an input
    
    // Step 4: Infinite loop to continuously monitor the switch
    while (1) {
        
        // Read the state of the switch from PIND register
        // (PIND & (1<<PD2)) isolates the PD2 bit. 
        // We use '!' because pressing the button makes the pin read 0 (LOW).
        if (!(PIND & (1 << PD2))) {
            
            // Switch is pressed -> Turn ON the LED
            PORTB |= (1 << PB0);
            
        } else {
            
            // Switch is NOT pressed -> Turn OFF the LED
            PORTB &= ~(1 << PB0);
            
        }
    }
    
    return 0;
}
```

**3. Key Registers Explained:**
*   `DDRx` (Data Direction Register): Decides if a pin is an Input (`0`) or Output (`1`).
*   `PORTx` (Data Register): For an output pin, it sets the voltage HIGH/LOW. For an input pin, writing a `1` activates the internal pull-up resistor.
*   `PINx` (Port Input Pins): This is the register we **read** to find out the actual physical voltage level (HIGH or LOW) on an input pin.

---

### **💡 Neplish Explainer (Core Concept Bujhne Tarika)**

**Concept:** 
Euta switch (button) thichda LED balne ra xodda nibhne program lekhna pareko ho. Yesma main kura bhaneko **Input kasari padhne** bhanne ho.

**Kasari Samjhine? (Point-by-Point):**

1.  **Input/Output Set garne (DDR ko kaam):**
    *   LED balna current pathaunu parxa, so Output (`DDRB = 1`).
    *   Switch thicheko xa ki nai vanera data linu parxa, so Input (`DDRD = 0`).

2.  **Pull-up Resistor (Exam ma yo lekhda pro dekhinxa!):**
    *   Switch khulla huda microontroller confuse hunxa (voltage 0 ho ki 5V ho tha hunna, yeslai floating state vanxa). 
    *   Tesaile hamile bhitra kai euta resistor use garera pin lai default ma HIGH (1) banauxau: `PORTD |= (1 << PD2);`. 
    *   Aba switch thichda current ground ma janxa ra reading LOW (0) aauxa.

3.  **Button state padhne (PIND ko magic):**
    *   Input padhna kahile pani `PORT` use hudaina, **`PIN`** register use hunxa. (e.g., `PIND`).
    *   `PIND & (1 << PD2)` le k garxa? Baki sabai pin lai ignore garera thakkai 2-number pin ma k xa vanera check garxa.
    *   Agadi `!` (NOT) kin rakhyo? Kina bhane hamro pull-up resistor le garda button **thichda 0 aauxa**. `!0` vayo vane condition `True` hunxa ani bhitra gayera LED balxa (`PORTB |= 1`).

**Exam Tips:** 
*   Output dinu parda `PORT` use garne, Input padhnu parda `PIN` use garne.
*   Yeti code ra logic yaad garayou vane 7 or 8 marks direct aauxa! 🚀