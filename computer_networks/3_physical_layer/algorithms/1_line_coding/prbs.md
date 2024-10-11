### **Pseudo-Random Binary Sequence (PRBS) Algorithm**

A **Pseudo-Random Binary Sequence (PRBS)** is a sequence of binary numbers (0s and 1s) that appears random but is actually generated deterministically using an algorithm. This sequence is widely used in communication systems, particularly in testing and simulating noise in the physical layer of computer networks.

#### 1\. **Basic Idea of PRBS:**

* The sequence is **pseudo-random**, meaning it mimics a random sequence but is generated using a defined method.
* PRBS is periodic, meaning the sequence eventually repeats after a certain number of bits.
* The goal of PRBS is to simulate random noise to test the robustness of communication systems without actually introducing random noise.

#### 2\. **Linear Feedback Shift Register (LFSR):**

The most common method of generating a PRBS is using a **Linear Feedback Shift Register (LFSR)**. An LFSR is a shift register that generates a sequence of bits based on its previous state. Each bit is determined using a **linear feedback function** that is applied to some of the bits in the register.

* The LFSR consists of a shift register (a series of flip-flops) and a feedback loop.
* The feedback is a **linear combination** (XOR operation) of the current bits in the register.

#### 3\. **Generating PRBS Using LFSR:**

* **Initial State**: The register starts with a non-zero seed or initial state (otherwise, the sequence would consist of only 0s).
* **Feedback**: At each clock cycle, the register shifts all bits to the right, and a new bit is introduced at the leftmost position. This new bit is computed as a feedback function of certain bits in the register.
* **Taps**: The feedback function uses specific bits in the register, called "taps". The selection of these taps determines the length and properties of the PRBS.

#### 4\. **Maximal Length PRBS:**

A PRBS is said to be **maximal length** if it produces the longest possible sequence before repeating. For an LFSR with nnn flip-flops, the maximum possible length of a PRBS is 2n−12^n - 12n−1, because an all-zero state is excluded.

#### Example: A 3-bit LFSR with taps at positions 1 and 3 will generate a sequence of length 23−1\=72^3 - 1 = 723−1\=7

* * *

### **7 Examples of PRBS Generation with Increasing Complexity**

#### **Example 1: Simple 2-bit LFSR**

* **Initial state**: \[1,0\]\[1, 0\]\[1,0\]

* **Taps**: Tap the first bit (feedback XOR from the leftmost bit to the new input).

* **Feedback**: New bit = XOR of first bit.

* **Output Sequence**: \[1,0\],\[0,1\],\[1,1\],\[1,0\],…\[1, 0\], \[0, 1\], \[1, 1\], \[1, 0\], \\dots\[1,0\],\[0,1\],\[1,1\],\[1,0\],…

* **Solution**:

  * State: \[1, 0\], Feedback (XOR of bit 1) = 1 → Next state = \[0, 1\]
  * State: \[0, 1\], Feedback (XOR of bit 1) = 0 → Next state = \[1, 0\]
  * This sequence will repeat every 3 bits.

#### **Example 2: 3-bit LFSR**

* **Initial state**: \[1,0,0\]\[1, 0, 0\]\[1,0,0\]

* **Taps**: XOR feedback from bit 1 and bit 3.

* **Output Sequence**: \[1,0,0\],\[0,1,0\],\[0,0,1\],\[1,0,1\],\[1,1,0\],\[0,1,1\],\[1,1,1\]\[1, 0, 0\], \[0, 1, 0\], \[0, 0, 1\], \[1, 0, 1\], \[1, 1, 0\], \[0, 1, 1\], \[1, 1, 1\]\[1,0,0\],\[0,1,0\],\[0,0,1\],\[1,0,1\],\[1,1,0\],\[0,1,1\],\[1,1,1\]

* **Solution**:

  * State: \[1, 0, 0\] → XOR bits 1 and 3 = 1 → Next state = \[0, 1, 0\]
  * State: \[0, 1, 0\] → XOR bits 1 and 3 = 0 → Next state = \[0, 0, 1\]
  * Continues until sequence repeats.

#### **Example 3: 4-bit LFSR (Maximal Length)**

* **Initial state**: \[1,0,0,0\]\[1, 0, 0, 0\]\[1,0,0,0\]

* **Taps**: XOR feedback from bit 1 and bit 4.

* **Output Sequence**: \[1,0,0,0\],\[0,1,0,0\],\[0,0,1,0\],\[0,0,0,1\],\[1,0,0,1\],\[1,1,0,0\],\[0,1,1,0\],\[0,0,1,1\],\[1,0,1,1\],\[1,1,0,1\],\[1,1,1,0\],\[0,1,1,1\],\[1,1,1,1\],\[0,0,1,1\],\[1,0,0,1\]\[1, 0, 0, 0\], \[0, 1, 0, 0\], \[0, 0, 1, 0\], \[0, 0, 0, 1\], \[1, 0, 0, 1\], \[1, 1, 0, 0\], \[0, 1, 1, 0\], \[0, 0, 1, 1\], \[1, 0, 1, 1\], \[1, 1, 0, 1\], \[1, 1, 1, 0\], \[0, 1, 1, 1\], \[1, 1, 1, 1\], \[0, 0, 1, 1\], \[1, 0, 0, 1\]\[1,0,0,0\],\[0,1,0,0\],\[0,0,1,0\],\[0,0,0,1\],\[1,0,0,1\],\[1,1,0,0\],\[0,1,1,0\],\[0,0,1,1\],\[1,0,1,1\],\[1,1,0,1\],\[1,1,1,0\],\[0,1,1,1\],\[1,1,1,1\],\[0,0,1,1\],\[1,0,0,1\]

* **Solution**:

  * State: \[1, 0, 0, 0\] → XOR bits 1 and 4 = 1 → Next state = \[0, 1, 0, 0\]
  * Repeat process until sequence reaches maximum length of 15.

#### **Example 4: 5-bit LFSR**

* **Initial state**: \[1,0,0,0,0\]\[1, 0, 0, 0, 0\]\[1,0,0,0,0\]

* **Taps**: XOR feedback from bit 2 and bit 5.

* **Output Sequence**: \[1,0,0,0,0\],\[0,1,0,0,0\],\[0,0,1,0,0\],…\[1, 0, 0, 0, 0\], \[0, 1, 0, 0, 0\], \[0, 0, 1, 0, 0\], \\dots\[1,0,0,0,0\],\[0,1,0,0,0\],\[0,0,1,0,0\],…

* **Solution**:

  * State: \[1, 0, 0, 0, 0\] → XOR bits 2 and 5 = 0 → Next state = \[0, 1, 0, 0, 0\]
  * Sequence length is 25−1\=312^5 - 1 = 3125−1\=31.

#### **Example 5: 6-bit LFSR (with taps on more than two positions)**

* **Initial state**: \[1,1,0,0,0,1\]\[1, 1, 0, 0, 0, 1\]\[1,1,0,0,0,1\]

* **Taps**: XOR feedback from bits 1, 2, and 6.

* **Output Sequence**: Generate a sequence with length 63.

* **Solution**:

  * State: \[1, 1, 0, 0, 0, 1\] → XOR bits 1, 2, and 6 → Continue until sequence repeats at 63.

#### **Example 6: 7-bit LFSR**

* **Initial state**: \[1,0,0,0,0,0,1\]\[1, 0, 0, 0, 0, 0, 1\]\[1,0,0,0,0,0,1\]

* **Taps**: XOR feedback from bit 1 and bit 7.

* **Output Sequence**: Sequence of length 27−1\=1272^7 - 1 = 12727−1\=127.

* **Solution**:

  * Feedback from bit 1 and 7 → New sequence state is generated for every clock cycle until the 127-bit sequence repeats.

#### **Example 7: 8-bit LFSR**

* **Initial state**: \[1,0,0,0,0,0,0,1\]\[1, 0, 0, 0, 0, 0, 0, 1\]\[1,0,0,0,0,0,0,1\]

* **Taps**: XOR feedback from bit 1, bit 2, bit 7, and bit 8.

* **Output Sequence**: Generates sequence with length 28−1\=2552^8 - 1 = 25528−1\=255.

* **Solution**:

  * For each clock cycle, feedback is taken from bits 1, 2, 7, and 8.
