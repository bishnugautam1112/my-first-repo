Here is the **highly condensed, high-yield exam solution** for Question 3(b). This structure directly answers every part of the 8-mark question for maximum points.

---

### **📝 Exam Solution: 3(b) Task Synchronization, Deadlock & Priority Inversion [8 Marks]**

#### **1. Task Synchronization Mechanisms in RTOS**
Task synchronization ensures that multiple tasks share resources or communicate without data corruption. Key mechanisms include:
*   **Mutex (Mutual Exclusion):** A locking mechanism (like a key). Only one task can acquire the mutex to access a shared resource. The task that locks it *must* unlock it (Ownership).
*   **Semaphores:** A signaling mechanism. 
    *   *Binary Semaphore:* Used for signaling between tasks or interrupts (0 or 1).
    *   *Counting Semaphore:* Used to manage a pool of identical resources (e.g., 3 printers).
*   **Message Queues:** Used to safely pass data/messages between multiple tasks.

#### **2. Handling Deadlock in RTOS**
**Deadlock** occurs when two or more tasks are stuck waiting indefinitely for resources held by each other.
*   **How it is handled:**
    *   **Timeouts:** Instead of waiting forever, tasks wait for a resource for a specified maximum time (e.g., `xSemaphoreTake(mutex, 100ms)`). If it times out, the task aborts and releases its held resources.
    *   **Resource Ordering:** Tasks must request multiple resources in a strict, globally defined order (e.g., always request Mutex A before Mutex B).

#### **3. Priority Inversion & Example**
**Priority Inversion** is a scheduling flaw where a High-priority task is forced to wait for a lower-priority task, effectively "inverting" their priorities.

*   **Example (The Classic 3-Task Scenario):**
    1.  **Task L (Low Priority)** acquires a shared resource (Mutex).
    2.  **Task H (High Priority)** needs the same resource, so it gets blocked waiting for Task L to release it.
    3.  **Task M (Medium Priority)**, which doesn't need the resource, becomes ready and preempts Task L (since M > L).
    *   *The Problem:* Task M runs indefinitely. Task L cannot run to release the Mutex. Task H is blocked waiting for L. **Result:** Task M has indirectly delayed Task H! *(This caused the Mars Pathfinder rover to crash in 1997).*

#### **4. Techniques to Overcome Priority Inversion**
RTOS uses two main protocols to solve this problem:
*   **Priority Inheritance Protocol (PIP):**
    *   *How it works:* The Low-priority task (L) temporarily "inherits" the priority of the High-priority task (H) that is waiting for the resource.
    *   Now, Task L runs at High priority, so Task M cannot preempt it. Once L releases the resource, its priority drops back to Low, and H takes over.
*   **Priority Ceiling Protocol (PCP):**
    *   *How it works:* Every resource is assigned a "Ceiling Priority" (the priority of the highest task that will ever use it). As soon as a task acquires the resource, its priority is immediately bumped up to the ceiling priority.

---

### **💡 Neplish Explainer (2-Minute Ninja Revision)**

**Concept:** 
Yo question le RTOS ma task haru kasari milera kaam garxan ra k k problem aauxa (Deadlock, Priority Inversion) vanera sodheko ho.

**Kasari Samjhine? (Real-Life Examples):**

1.  **Synchronization (Milera kaam garne):**
    *   **Mutex:** Euta Toilet (Resource) ra euta Chabi (Mutex). Jasle chabi linxa usle matra toilet use garxa. Arko manxe bahira wait garxa.
    *   **Semaphore:** Traffic light jastai, signal dine kaam garxa (Go or Stop).

2.  **Deadlock (Fasne awastha):**
    *   Sano bato ma duita gadi opposite bata aayo. Dubai le bato xodna mandaina. Dubai sadhai ko lagi fasyo! 
    *   *Solution:* Euta le 2 minute wait garxa (Timeout), bato payena vane back garxa.

3.  **Priority Inversion (Sabai vanda important for exam!):**
    *   **VIP (High), Normal (Medium), ra Garib (Low)**.
    *   Garib toilet bhitra xa (Mutex locked). VIP aayera line ma basyo kinsaki toilet pack xa. 
    *   Teti belai Normal manxe aayo ra Garib lai baato ma rokkera guff garna lagyo (Preempted).
    *   Aba socha ta: VIP wait gariraxa. Normal manxe le Garib lai toilet jana deko xaina. **Indirectly, Normal manxe le VIP lai hold ma rakhdiyo!** Yeslai nai *Priority Inversion* vanxa.

4.  **Solutions (Overcome garne tarika):**
    *   **Priority Inheritance:** Garib lai temporary "VIP Pass" (Inheritance) didine jabasamma usle toilet ko kaam sakdaina. Tyo vayo vane Normal manxe le uslai roknu sakdaina. Kaam sakiyesi pass firta linxa. 

Yeti kura yaad vayo vane exam ma own words ma lekhda pani **8/8 fixed!** Bold words haru chai chutaunai nahune keywords hun.