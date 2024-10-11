The Non-Return to Zero (NRZ) algorithm is a line coding scheme used in digital communication systems for encoding binary data (0s and 1s) into electrical signals for transmission over physical media, such as cables or optical fibers. It is commonly used in the physical layer of the OSI model, where the primary goal is to reliably transmit bits from one device to another.

In NRZ encoding, a binary 1 and a binary 0 are represented by two distinct voltage levels. Unlike other line coding schemes, NRZ does not use any signal transitions between bits, making it more efficient in terms of bandwidth usage. There are two primary forms of NRZ: Non-Return to Zero-Level (NRZ-L) and Non-Return to Zero-Inverted (NRZ-I).

### Detailed Breakdown of the Algorithm

1. **NRZ-L Algorithm:**
    * Choose the `1` and `0` voltage representations. For example positive for `1` and negative for `0`.
    * Start with an initial voltage level.
    * For each bit in the data stream:
        * If the bit is 1, transmit a positive voltage level.
        * If the bit is 0, transmit a negative voltage level.
    * No transition occurs between bits unless the bit value changes.
2. **NRZ-I Algorithm:**
    * Start with an initial voltage level.
    * For each bit in the data stream:
        * If the bit is 1, invert the voltage level.
        * If the bit is 0, maintain the current voltage level.
    * Transitions occur only when there is a 1 in the bitstream.

### Error Detection

**Non-Return to Zero-Level (NRZ-L)**:
The NRZ-L scheme is straightforward but suffers from a major drawback: when there is a long string of consecutive 1s or 0s, there is no voltage change, which can lead to synchronization issues.

**Non-Return to Zero-Inverted (NRZ-I)**:
In NRZ-I, the transition occurs only when a 1 is encountered in the data stream. This helps to reduce synchronization issues because there will be a transition for every 1, even if there is a long string of 0s.

### Examples with Increasing Complexity

#### Example 1: NRZ-L, Simple Sequence

**Bitstream**: `1010`

**Solution**:

1. `1` → Positive Voltage
2. `0` → Negative Voltage
3. `1` → Positive Voltage
4. `0` → Negative Voltage

**NRZ-L Signal**: <sup>___</sup> <sub>___ </sub> <sup> ___</sup> <sub>___ </sub>

#### Example 2: NRZ-I, Simple Sequence

**Bitstream**: `1010`

**Solution**:

1. Start with a baseline (assume positive voltage).
2. `1` → Invert → Negative Voltage
3. `0` → No Change → Negative Voltage
4. `1` → Invert → Positive Voltage
5. `0` → No Change → Positive Voltage

**NRZ-I Signal**: <sub> ______ </sub> <sup> ______</sup>

#### Example 3: NRZ-L, Consecutive Bits

**Bitstream**: `1100`

**Solution**:

1. `1` → Positive Voltage
2. `1` → Positive Voltage (no change)
3. `0` → Negative Voltage
4. `0` → Negative Voltage (no change)

**NRZ-L Signal**: <sup> ______</sup> <sub> ______ </sub>

#### Example 4: NRZ-I, Consecutive Bits

**Bitstream**: `1100`

**Solution**:

1. Start with a baseline (assume positive voltage).
2. `1` → Invert → Negative Voltage
3. `1` → Invert → Positive Voltage
4. `0` → No Change → Positive Voltage
5. `0` → No Change → Positive Voltage

**NRZ-I Signal**: <sub> ___</sub> <sup>___ ______ </Ssup>

#### Example 5: NRZ-L, Alternating Bits

**Bitstream**: `101010`

**Solution**:

1. `1` → Positive Voltage
2. `0` → Negative Voltage
3. `1` → Positive Voltage
4. `0` → Negative Voltage
5. `1` → Positive Voltage
6. `0` → Negative Voltage

**NRZ-L Signal**: <sup>___</sup> <sub>___ </sub> <sup> ___</sup> <sub>___ </sub> <sup> ___</sup> <sub>___ </sub>

#### Example 6: NRZ-I, Alternating Bits

**Bitstream**: `101010`

**Solution**:

1. Start with a baseline (assume positive voltage).
2. `1` → Invert → Negative Voltage
3. `0` → No Change → Negative Voltage
4. `1` → Invert → Positive Voltage
5. `0` → No Change → Positive Voltage
6. `1` → Invert → Negative Voltage
7. `0` → No Change → Negative Voltage

**NRZ-I Signal**: <sub> ______ </sub> <sup> ______ </sup> <sub> ______ </sub>

#### Example 7: NRZ-L and NRZ-I Combined Scenario

**Bitstream**: `11010011`

**Solution (NRZ-L)**:

1. `1` → Positive Voltage
2. `1` → Positive Voltage
3. `0` → Negative Voltage
4. `1` → Positive Voltage
5. `0` → Negative Voltage
6. `0` → Negative Voltage
7. `1` → Positive Voltage
8. `1` → Positive Voltage

**NRZ-L Signal**: <sup> ______ </sup> <sub> ___</sub> <sup>___ </sup> <sub> ______ </sub> <sup> ______ </sup>

**Solution (NRZ-I)**:

1. Start with a baseline (assume positive voltage).
2. `1` → Invert → Negative Voltage
3. `1` → Invert → Positive Voltage
4. `0` → No Change → Positive Voltage
5. `1` → Invert → Negative Voltage
6. `0` → No Change → Negative Voltage
7. `0` → No Change → Negative Voltage
8. `1` → Invert → Positive Voltage
9. `1` → Invert → Negative Voltage

**NRZ-I Signal**: <sub> ___</sub> <sup>___ ___</sup> <sub>___ ______ </sub> <sup> ___</sup> <sub>___ </sub>

These examples illustrate how both NRZ-L and NRZ-I encode bitstreams, demonstrating their behavior across simple, moderate, and complex bit patterns.
