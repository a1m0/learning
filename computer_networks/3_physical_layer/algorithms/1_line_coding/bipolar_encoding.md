### **Bipolar Encoding Overview**

Bipolar encoding, also known as _Alternate Mark Inversion (AMI)_, is a line coding scheme used to encode binary data for transmission over a medium, such as a physical cable. Unlike unipolar and polar encoding, bipolar encoding uses three voltage levels: **positive (+), zero (0), and negative (-)**.

In Bipolar encoding:

* A binary `0` is represented by a **0 voltage level**.
* A binary `1` is represented by alternating **+V** and **\-V** voltages.

The "alternating" feature is a crucial aspect of bipolar encoding. Every time a binary `1` appears, the voltage alternates between +V and -V from the previous binary `1`. This property is essential because it prevents a DC component (the mean voltage over time remains zero), which is important for some transmission mediums.

### **How Bipolar Encoding Works:**

1. **Encoding Rules:**

    * **Binary 0**: Represented by a **zero voltage**.
    * **Binary 1**: Represented by a **non-zero voltage**, which alternates in polarity (i.e., if the last `1` was positive, the next `1` will be negative, and vice versa).
2. **Algorithm Steps:**

    * Initialize the voltage state as **0** at the start of transmission.
    * For each bit in the data stream:
        * If the bit is `0`, set the output to **0** (no change in voltage).
        * If the bit is `1`, check the previous non-zero voltage level:
            * If it was **positive (+V)**, change it to **negative (-V)**.
            * If it was **negative (-V)**, change it to **positive (+V)**.
        * Alternate the voltage levels for each consecutive `1`.
    * Continue this for the entire bit sequence.
3. **Benefits of Bipolar Encoding:**

    * **DC balance:** The average voltage level remains zero due to the alternation between +V and -V.
    * **Error Detection**: Two consecutive `1`s of the same polarity indicate an error (as they violate the alternating rule).
    * **Low Spectral Density at Low Frequencies**: Helps to avoid problems with transformer-coupled and capacitor-coupled systems.

### **Examples with Solutions:**

Let’s go through examples of increasing complexity to demonstrate the bipolar encoding.

* * *

### **Example 1: Simple Sequence**

**Bit Sequence:** `101`

**Solution:**

* **1** → `+V`
* **0** → `0`
* **1** → `-V`

**Encoded Signal:** `+V 0 -V`

* * *

### **Example 2: Adding More Bits**

**Bit Sequence:** `1101`

**Solution:**

* **1** → `+V`
* **1** → `-V`
* **0** → `0`
* **1** → `+V`

**Encoded Signal:** `+V -V 0 +V`

* * *

### **Example 3: Alternating 1s and 0s**

**Bit Sequence:** `101010`

**Solution:**

* **1** → `+V`
* **0** → `0`
* **1** → `-V`
* **0** → `0`
* **1** → `+V`
* **0** → `0`

**Encoded Signal:** `+V 0 -V 0 +V 0`

* * *

### **Example 4: Long Consecutive Zeros**

**Bit Sequence:** `100001`

**Solution:**

* **1** → `+V`
* **0** → `0`
* **0** → `0`
* **0** → `0`
* **0** → `0`
* **1** → `-V`

**Encoded Signal:** `+V 0 0 0 0 -V`

* * *

### **Example 5: Sequence with Consecutive Ones**

**Bit Sequence:** `11100011`

**Solution:**

* **1** → `+V`
* **1** → `-V`
* **1** → `+V`
* **0** → `0`
* **0** → `0`
* **0** → `0`
* **1** → `-V`
* **1** → `+V`

**Encoded Signal:** `+V -V +V 0 0 0 -V +V`

* * *

### **Example 6: Longer Sequence with Patterns**

**Bit Sequence:** `101101010`

**Solution:**

* **1** → `+V`
* **0** → `0`
* **1** → `-V`
* **1** → `+V`
* **0** → `0`
* **1** → `-V`
* **0** → `0`
* **1** → `+V`
* **0** → `0`

**Encoded Signal:** `+V 0 -V +V 0 -V 0 +V 0`

* * *

### **Example 7: Complex Sequence with Interleaved Patterns**

**Bit Sequence:** `1110101110`

**Solution:**

* **1** → `+V`
* **1** → `-V`
* **1** → `+V`
* **0** → `0`
* **1** → `-V`
* **0** → `0`
* **1** → `+V`
* **1** → `-V`
* **1** → `+V`
* **0** → `0`

**Encoded Signal:** `+V -V +V 0 -V 0 +V -V +V 0`

* * *

### **Summary of Example Solutions**

By applying the bipolar encoding algorithm, each `1` in the sequence alternates between +V and -V, while each `0` is represented as a 0 voltage level. This alternating property helps maintain a zero-average voltage level and supports error detection, making bipolar encoding an effective and efficient choice for various transmission systems.
