
# Description

Guided media, also known as wired or bounded media, are physical transmission channels that use cables to transmit data. In computer networks, guided media refers to the physical means by which data signals travel from one device to another, usually using some form of cable or wire. Guided media is crucial for many network implementations because it provides a stable, direct path for data transmission, making it less susceptible to interference and data loss compared to wireless transmission.

## Types of Guided Media

1. **Twisted Pair Cable**
2. **Coaxial Cable**
3. **Fiber Optic Cable**

Let’s explore each of these types in detail, covering their materials, structure, use cases, metrics, and how they’re implemented.

* * *

### 1\. Twisted Pair Cable

Twisted pair cables consist of pairs of insulated copper wires twisted together. The twisting helps reduce electromagnetic interference, which can be caused by signals from neighboring wires. These cables are commonly used for local area networks (LANs), telephone networks, and various other data communication applications.

**Types:**

* **Unshielded Twisted Pair (UTP):** No additional shielding, used in most home and office networks due to its low cost and ease of installation.
* **Shielded Twisted Pair (STP):** Contains a layer of shielding material, which offers better protection against interference but is more expensive and less flexible.

**Use Cases:**

* UTP is widely used in LANs, particularly Ethernet networks.
* STP is preferred in environments with significant interference, like factories or areas with high electromagnetic interference.

**Metrics:**

* **Bandwidth:** UTP cables typically support up to 100 Mbps for CAT 5, 1 Gbps for CAT 5e, and 10 Gbps for CAT 6 over shorter distances.
* **Distance:** Typically supports up to 100 meters without requiring signal regeneration.
* **Attenuation:** Twisting reduces signal loss over short distances, but it is still more susceptible to attenuation over longer runs.

**Materials:**

* Conductors: Copper wires, typically 22 or 24 gauge.
* Insulation: Plastic (PVC or similar) surrounds each wire.
* Outer jacket: Protects the internal wires from environmental damage.

**Implementation:**

1. UTP cables are easy to install and connect, usually through modular connectors like RJ-45.
2. Devices are connected to switches, routers, or patch panels in structured cabling systems for organized, scalable networks.
3. To reduce crosstalk, pairs are twisted at specific twists per inch, which varies depending on the category.

* * *

### 2\. Coaxial Cable

Coaxial cables are designed with a central conductor surrounded by an insulating layer, a metallic shield, and an outer protective layer. The shield helps to reduce interference, making coaxial cable suitable for high-frequency signals and longer distances than twisted pair cables.

**Use Cases:**

* Traditionally used for cable television, connecting cable modems, and early computer networks.
* Coaxial cable is often found in broadband internet connections and certain types of LANs.

**Metrics:**

* **Bandwidth:** Can support several GHz of bandwidth, depending on the type.
* **Distance:** Typically transmits data up to 500 meters (e.g., RG-6) without a repeater.
* **Attenuation:** Lower than twisted pair cables, making it suitable for longer distances.

**Materials:**

* Central conductor: Copper or aluminum.
* Insulation: Dielectric insulator surrounding the central conductor.
* Shield: Metallic braid or foil to reduce EMI.
* Outer jacket: Plastic, often PVC, for environmental protection.
  
**Implementation:**

1. Connectors, such as BNC or F-connectors, are attached to the ends of the cable.
2. Devices are connected using these connectors to splitters, modems, or networking devices.
3. For networks, coaxial cables run from the internet service provider’s connection point to modems and routers.

* * *

### 3\. Fiber Optic Cable

Fiber optic cables transmit data as pulses of light through thin strands of glass or plastic fibers. These cables are designed for high-speed, high-bandwidth, and long-distance communication, making them ideal for backbone networks and connections between buildings or cities.

**Types:**

* **Single-mode fiber (SMF):** Carries light directly through the fiber with minimal reflections, suitable for long-distance communication.
* **Multi-mode fiber (MMF):** Allows multiple light signals to travel through the fiber, suitable for shorter distances.

**Use Cases:**

* Backbone networks in data centers and between telecommunications facilities.
* High-speed internet connections, long-distance telecommunication, and intercontinental links.

**Metrics:**

* **Bandwidth:** Up to several Tbps, depending on the type and technology used.
* **Distance:** SMF can support up to 80 km or more, while MMF is generally effective for up to 500 meters.
* **Attenuation:** Very low attenuation compared to copper cables, especially over long distances.

**Materials:**

* Core: Glass or plastic fiber that carries the light signals.
* Cladding: Surrounds the core, reflecting light inward to minimize signal loss.
* Buffer coating: Protects the fiber from physical damage.
* Outer jacket: PVC or similar, providing environmental protection.

**Implementation:**

1. Fiber optic cables are terminated with connectors like SC, LC, or ST, and connected to transceivers or fiber optic switches.
2. Careful alignment is necessary, as fibers must match up precisely for the light signal to pass through.
3. Fiber optic cables can be laid underground, through conduits, or directly between devices.

* * *

### Summary Comparison

| **Media Type**    | **Typical Use Case**               | **Distance**  | **Bandwidth**      | **Materials**                   |
| -                 | -                                  | -             | -                  | -                               |
| Twisted Pair      | LANs, telephone networks           | 100 meters    | 100 Mbps - 10 Gbps | Copper, PVC                     |
| Coaxial Cable     | Cable TV, internet, older networks | 500 meters    | Up to several GHz  | Copper/aluminum, shielding, PVC |
| Fiber Optic Cable | High-speed internet, long distance | 500 m - 80 km | Up to several Tbps | Glass/plastic, cladding, PVC    |

Each type of guided media has unique advantages and use cases depending on factors like distance, required bandwidth, and budget. Fiber optic cables offer the highest performance but at a higher cost, while twisted pair cables are more economical for short-distance applications.
