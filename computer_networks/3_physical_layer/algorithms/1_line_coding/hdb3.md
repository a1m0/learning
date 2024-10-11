### High-Density Bipolar 3 (HDB3) Algorithm – Detailed Description

HDB3 (High-Density Bipolar 3) is a line coding scheme used in digital transmission systems, specifically for T-carrier and E-carrier systems, which is designed to encode data into a format that is suitable for transmission over a physical medium. HDB3 is an extension of the Bipolar AMI (Alternate Mark Inversion) encoding scheme, and it aims to solve the problem of long sequences of zeros in the transmitted data.

#### 1\. **Basics of Bipolar AMI**

In **AMI (Alternate Mark Inversion)** coding:

* The binary value "1" is represented by alternating polarities (positive and negative voltages), i.e., successive ones are sent as `+V`, `-V`, `+V`, `-V`, and so on.
* The binary value "0" is represented by no voltage (0V), creating a gap in the signal.

However, AMI has a limitation: **it cannot handle long sequences of zeros**, which can cause synchronization problems because the receiver may lose track of signal transitions.

#### 2\. **Why HDB3?**

**HDB3** solves the problem of synchronization loss caused by long strings of zeros in AMI by replacing these long zero sequences with a pattern containing intentional violations of the bipolar rule. These violations ensure that the receiver can maintain synchronization by detecting these violations.

In HDB3:

* A sequence of four consecutive zeros (`0000`) is replaced by a special "violation pattern" that introduces either a positive or negative voltage pulse to break the long string of zeros. These violations are alternated in such a way that the overall bipolar rule is maintained.

#### 3\. **Violation Pattern in HDB3**

The replacement of consecutive zeros in HDB3 depends on the polarity of the previous pulse and the number of ones (1s) that have been transmitted between zero runs.

The key idea is:

* **If there are 4 consecutive zeros (0000)**, they are replaced based on the following rule:
  * If the number of 1s since the last violation is **odd**, the sequence `0000` is replaced by **`B00V`**, where:
    * `B` is a pulse with the same polarity as the last pulse (no change in polarity),
    * `V` is a violation pulse that breaks the AMI rule by repeating the previous polarity.
  * If the number of 1s since the last violation is **even**, the sequence `0000` is replaced by **`000V`**, where:
    * `V` is the violation pulse that breaks the AMI rule.These rules ensure the signal's polarity balance over time is preserved while allowing synchronization recovery in the event of long zero sequences.

### Examples with Increasing Complexity

#### Example 1: Simple Case (No zero sequence exceeding 3 zeros)

**Input Data:** `1011`

* AMI encoding without zero violations: `+V 0 -V +V`
* Since there are no long zero sequences, HDB3 encoding remains: `+V 0 -V +V`
* **Solution:** `+V 0 -V +V`

#### Example 2: One Sequence of Four Zeros

**Input Data:** `100001`

* AMI encoding without zero violations: `+V 0 0 0 0 -V`
* There are four consecutive zeros, so we replace `0000` with `B00V`. Since there has been one "1" before the zero sequence, the count is **odd**.
  * `100001` becomes `+V 0 -V 0 0 +V`
* **Solution:** `+V 0 -V 0 0 +V`

#### Example 3: Two Sequences of Four Zeros

**Input Data:** `100000001`

* AMI encoding without zero violations: `+V 0 0 0 0 0 0 0 0 +V`
* The first four zeros are replaced by `B00V` (since there’s one "1", the count is odd): `+V 0 -V 0 0 +V`
* The next four zeros are also replaced by `000V`: `+V 0 -V 0 0 +V 0 0 -V`
* **Solution:** `+V 0 -V 0 0 +V 0 0 -V`

#### Example 4: More Complex Case (Multiple Zero Sequences)

**Input Data:** `10000000001`

* AMI encoding: `+V 0 0 0 0 0 0 0 0 0 -V`
* First four zeros replaced with `B00V` (odd count): `+V 0 -V 0 0 +V`
* Second four zeros replaced with `000V` (even count): `+V 0 -V 0 0 +V 0 0 -V`
* Last sequence is valid: `+V 0 -V 0 0 +V 0 0 -V 0 -V`
* **Solution:** `+V 0 -V 0 0 +V 0 0 -V 0 -V`

#### Example 5: Complex Zero Sequence Pattern with Odd Count of 1s

**Input Data:** `10010000001`

* AMI encoding: `+V 0 -V 0 +V 0 0 0 0 0 -V`
* First four zeros replaced with `B00V` (odd count): `+V 0 -V 0 +V 0 0 +V`
* Final sequence remains as is: `+V 0 -V 0 +V 0 0 +V -V`
* **Solution:** `+V 0 -V 0 +V 0 0 +V -V`

#### Example 6: Longer Sequence with Multiple Zero Runs

**Input Data:** `1001000000000001`

* AMI encoding: `+V 0 -V 0 +V 0 0 0 0 0 0 0 0 0 +V`
* First four zeros replaced with `B00V` (odd count): `+V 0 -V 0 +V 0 0 +V`
* Next four zeros replaced with `000V`: `+V 0 -V 0 +V 0 0 +V 0 0 -V`
* **Solution:** `+V 0 -V 0 +V 0 0 +V 0 0 -V`

#### Example 7: Realistic Data Stream

**Input Data:** `1100000001000001`

* AMI encoding: `+V -V 0 0 0 0 0 0 0 0 +V 0 0 0 0 -V`
* First four zeros replaced with `B00V` (odd count): `+V -V 0 0 +V 0 0 -V`
* Second four zeros replaced with `000V` (even count): `+V -V 0 0 +V 0 0 -V 0 0 +V`
* **Solution:** `+V -V 0 0 +V 0 0 -V 0 0 +V`

### Summary of HDB3 Rules

* Replace sequences of four zeros with either `B00V` or `000V` depending on the parity of the 1s preceding the zero sequence.
* Ensure alternating polarities for "1s" to maintain synchronization.
