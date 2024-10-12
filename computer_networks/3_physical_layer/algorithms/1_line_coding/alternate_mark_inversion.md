# Alternate Mark Inversion

## Overview

Alternate Mark Inversion (AMI) is a line coding scheme used in digital data transmission, especially in telecommunications. It's often used to encode binary data into a form suitable for transmission over a physical medium, where it can effectively reduce or eliminate some common issues that arise in data transmission, such as synchronization loss and direct current (DC) offset. Let's go over the concept and gradually increase the complexity of the explanation.

### 1\. Basic Concept of AMI

AMI is a bipolar encoding scheme that represents binary `1` and `0` in a specific way:

* **Binary 0:** Encoded as no voltage (0 level).
* **Binary 1:** Encoded as alternating positive and negative voltages (+V and -V) with each occurrence.

The key feature of AMI is that it alternates the polarity of the signal representing `1`. This means that if the first `1` is transmitted as +V, the next `1` will be -V, the third `1` will be +V, and so on.

### 2\. Why Use AMI?

The AMI scheme has a few advantages:

* **DC Balance:** Since the `1`s alternate in polarity, the average voltage over time is zero. This helps in eliminating DC bias, which can cause issues with certain transmission media.
* **Error Detection:** In AMI, if a `1` is detected without alternating polarity, it indicates an error.
* **Synchronization:** Alternating the `1`s in a predictable way helps maintain synchronization between the transmitter and receiver. However, long sequences of `0`s can disrupt this, which is why additional coding techniques like Bipolar with 8-Zeros Substitution (B8ZS) or High-Density Bipolar 3 (HDB3) are often used in practice.

### 3\. How AMI Works

To understand how AMI operates, let’s look at a binary data sequence: For example: **1 0 0 1 0 1 1 0 0 1**

1. **Starting with +V**: The first `1` is encoded as +V.
2. **Next 1 alternates**: The next `1` is -V, and so on.
3. **Zeroes are 0 level**: All `0`s are encoded as zero voltage.

This sequence would be encoded as:

* +V 0 0 -V 0 +V -V 0 0 +V

### 4\. Detailed Encoding Rules for AMI

The AMI encoding scheme follows these rules:

* If the bit is `0`, output `0V` (no signal).
* If the bit is `1`, output a signal that alternates in polarity from the previous `1`.

## Examples

Now that we’ve established the basic encoding process, let’s go through some examples to solidify our understanding.

### Example 1

**Binary Data:** `1 0 1`

* Start with +V for the first `1`.
* `0` remains `0`.
* Alternate polarity for the next `1`.

**Encoding:** +V 0 -V

### Example 2

**Binary Data:** `1 1 0 0 1`

* First `1` is +V.
* Second `1` is -V.
* Two `0`s are `0`.
* Next `1` is +V.

**Encoding:** +V -V 0 0 +V

### Example 3

**Binary Data:** `1 0 1 1 0 1`

* First `1` is +V.
* `0` remains 0.
* Second `1` alternates to -V.
* Third `1` alternates back to +V.
* `0` remains 0.
* Fourth `1` alternates to -V.

**Encoding:** +V 0 -V +V 0 -V

### Example 4

**Binary Data:** `1 0 0 0 1 0 1 0`

* First `1` is +V.
* Three `0`s remain 0.
* Second `1` alternates to -V.
* Next `0` remains 0.
* Third `1` alternates back to +V.
* Last `0` remains 0.

**Encoding:** +V 0 0 0 -V 0 +V 0

### Example 5

**Binary Data:** `1 1 1 0 1`

* First `1` is +V.
* Second `1` alternates to -V.
* Third `1` alternates back to +V.
* `0` remains 0.
* Fourth `1` alternates to -V.

**Encoding:** +V -V +V 0 -V

### Example 6

**Binary Data:** `1 0 1 0 1 1 0 1 0 1`

* First `1` is +V.
* `0` remains 0.
* Second `1` alternates to -V.
* `0` remains 0.
* Third `1` alternates back to +V.
* Fourth `1` alternates to -V.
* `0` remains 0.
* Fifth `1` alternates back to +V.
* `0` remains 0.
* Sixth `1` alternates to -V.

**Encoding:** +V 0 -V 0 +V -V 0 +V 0 -V

### Example 7

**Binary Data:** `1 0 1 0 1 1 1 0 1 0 0 1`

* First `1` is +V.
* `0` remains 0.
* Second `1` alternates to -V.
* `0` remains 0.
* Third `1` alternates back to +V.
* Fourth `1` alternates to -V.
* Fifth `1` alternates back to +V.
* `0` remains 0.
* Sixth `1` alternates to -V.
* Two `0`s remain 0.
* Seventh `1` alternates back to +V.

**Encoding:** +V 0 -V 0 +V -V +V 0 -V 0 0 +V

### Recap

AMI is an effective way to encode binary data for transmission over a medium that cannot carry DC signals. By alternating the polarity of `1`s, it maintains a balanced signal without long sequences of `1`s or `0`s causing synchronization or DC drift issues. Through these examples, we’ve illustrated the basic mechanism and rules behind AMI encoding, progressing through various levels of complexity in binary data patterns.
