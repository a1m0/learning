### Pulse Amplitude Modulation (PAM) Overview

**Pulse Amplitude Modulation (PAM)** is a modulation technique used to encode information into the amplitude of pulses. In this method, each pulse in a signal has a specific amplitude that represents a particular bit or symbol. PAM is widely used in various communication systems, including digital telephony and data communication over copper cables.

In general, PAM can be classified into two types:

1.  **Analog PAM:** The amplitude of the pulses varies in a continuous manner, representing analog signals.
2.  **Digital PAM:** The amplitude of the pulses takes on discrete values, representing digital signals.

Digital PAM is further divided into:

*   **2-PAM (Binary PAM):** Encodes 1 bit per pulse.
*   **4-PAM:** Encodes 2 bits per pulse.
*   **8-PAM:** Encodes 3 bits per pulse, and so on.

The main idea is that the amplitude level of each pulse corresponds to a specific data value. The higher the number of amplitude levels, the more bits each pulse can carry.

### Step-by-Step Explanation of the PAM Algorithm

Let's walk through the algorithm for a Digital PAM system with increasing complexity:

#### 1\. Basic Binary PAM (2-PAM)

*   **Step 1:** Define two amplitude levels: one for binary '0' and one for binary '1'.
*   **Step 2:** Map each bit to one of these two levels.
*   **Example:** 0 → -1V and 1 → +1V
*   **Transmission:** Send a pulse for each bit with the corresponding amplitude.

#### 2\. Multi-Level PAM (4-PAM)

*   **Step 1:** Define four distinct amplitude levels.
*   **Step 2:** Each pulse represents 2 bits, so we have four combinations (00, 01, 10, 11).
*   **Step 3:** Map each of these combinations to a specific amplitude level.
*   **Example:**
    *   00 → -3V
    *   01 → -1V
    *   10 → +1V
    *   11 → +3V
*   **Transmission:** Send a pulse for each two-bit symbol with the corresponding amplitude.

#### 3\. Higher-Level PAM (8-PAM)

*   **Step 1:** Define eight amplitude levels.
*   **Step 2:** Each pulse represents 3 bits.
*   **Step 3:** Map the 3-bit combinations to amplitude levels.
*   **Example:**
    *   000 → -7V
    *   001 → -5V
    *   010 → -3V
    *   011 → -1V
    *   100 → +1V
    *   101 → +3V
    *   110 → +5V
    *   111 → +7V
*   **Transmission:** Send a pulse for each three-bit symbol with the corresponding amplitude.

### Examples with Solutions

Here are examples with increasing complexity to demonstrate how PAM works.

* * *

#### **Example 1: 2-PAM**

*   **Given:** A binary sequence: `1011`
*   **Solution:**
    *   Assign amplitudes: 0 → -1V, 1 → +1V.
    *   Transmit pulses for each bit:
        *   `1` → +1V
        *   `0` → -1V
        *   `1` → +1V
        *   `1` → +1V
    *   **Output Signal:** +1V, -1V, +1V, +1V

* * *

#### **Example 2: 2-PAM with Different Levels**

*   **Given:** A binary sequence: `1100`
*   **Solution:**
    *   Assign amplitudes: 0 → -2V, 1 → +2V.
    *   Transmit pulses for each bit:
        *   `1` → +2V
        *   `1` → +2V
        *   `0` → -2V
        *   `0` → -2V
    *   **Output Signal:** +2V, +2V, -2V, -2V

* * *

#### **Example 3: 4-PAM**

*   **Given:** A bit sequence: `110100`
*   **Solution:**
    *   Group bits in sets of 2: `11`, `01`, `00`
    *   Assign amplitudes: 00 → -3V, 01 → -1V, 10 → +1V, 11 → +3V.
    *   Transmit pulses for each pair:
        *   `11` → +3V
        *   `01` → -1V
        *   `00` → -3V
    *   **Output Signal:** +3V, -1V, -3V

* * *

#### **Example 4: 4-PAM with Unequal Levels**

*   **Given:** A bit sequence: `100110`
*   **Solution:**
    *   Group bits in sets of 2: `10`, `01`, `10`
    *   Assign amplitudes: 00 → -2V, 01 → 0V, 10 → +2V, 11 → +4V.
    *   Transmit pulses for each pair:
        *   `10` → +2V
        *   `01` → 0V
        *   `10` → +2V
    *   **Output Signal:** +2V, 0V, +2V

* * *

#### **Example 5: 8-PAM**

*   **Given:** A bit sequence: `110101001`
*   **Solution:**
    *   Group bits in sets of 3: `110`, `101`, `001`
    *   Assign amplitudes:
        *   000 → -7V
        *   001 → -5V
        *   010 → -3V
        *   011 → -1V
        *   100 → +1V
        *   101 → +3V
        *   110 → +5V
        *   111 → +7V
    *   Transmit pulses for each triplet:
        *   `110` → +5V
        *   `101` → +3V
        *   `001` → -5V
    *   **Output Signal:** +5V, +3V, -5V

* * *

#### **Example 6: 8-PAM with Non-Uniform Steps**

*   **Given:** A bit sequence: `011010111`
*   **Solution:**
    *   Group bits in sets of 3: `011`, `010`, `111`
    *   Assign amplitudes:
        *   000 → -8V
        *   001 → -4V
        *   010 → -2V
        *   011 → 0V
        *   100 → +2V
        *   101 → +4V
        *   110 → +6V
        *   111 → +8V
    *   Transmit pulses for each triplet:
        *   `011` → 0V
        *   `010` → -2V
        *   `111` → +8V
    *   **Output Signal:** 0V, -2V, +8V

* * *

#### **Example 7: 16-PAM**

*   **Given:** A bit sequence: `1001100100011011`
*   **Solution:**
    *   Group bits in sets of 4: `1001`, `1001`, `0001`, `1011`
    *   Assign amplitudes from -15V to +15V for 16 different levels.
    *   Transmit pulses for each 4-bit sequence:
        *   Map each 4-bit sequence to a specific amplitude, for instance:
            *   `0000` → -15V
            *   `0001` → -13V
            *   `0010` → -11V
            *   `1001` → -1V
            *   `1011` → +3V
        *   Transmit: -1V, -1V, -13V, +3V
    *   **Output Signal:** -1V, -1V, -13V, +3V

This process shows how increasing the levels of PAM allows more data to be encoded per pulse by using more distinct amplitude values.