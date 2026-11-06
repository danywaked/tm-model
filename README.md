# Traffic Manager Block Implementation and Testing

In network switch devices, the traffic manager ("TM") is the component that handles packet buffers and distributes packet processing tasks among the hardware resources available in the data plane. Specifically, in the context of P4-programmable data planes, the TM is located between the ingress and egress stages of data plane processing. The ingress stage sets egress port (unicast), or multicast group (multicast) for a packet, and the TM must then choose which egress resources to use, and how to prioritize traffic.

This is a list of requirements for a model of a TM:
- Packet buffering
Including basic QoS such as prioritization and robust resource allocation
- Multicast support
Including source port pruning and multicast groups configurable from the control plane
-	Support for implementing LACP
LACP (Link Aggregation Control Protocol) is a protocol for bundling multiple physical links into a single logical link
-	Support for implementing ECMP
ECMP (Equal-Cost Multi-Path) is a technique for distributing traffic over multiple routes to the same destination

The TM is modeled in a suitable high-level language and a test suite designed to validate the functionality. For LACP and ECMP, either existing control plane implementation may be used or a stand-in may be designed for this project. For this level of ambition, the focus will be on the testing and validation, which ideally should be portable to other TM implementations.
