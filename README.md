# dv-ls-routing-protocols

We will implement and compare two important types of routing protocols: the distance-vector (DV) protocol and the link-state (LS) protocol. 

Motivation:

Why do we need routing protocols? In a network, nodes are not fully connected and there's a need for multi-hop communication. Routing protocols help nodes identify neighbor (next hop) in the optimal path to a destination. They also nodes forward packets hop-by-hop from the source to the destination, where the data packet contains the destination node in the header and a node receives a data packet and forwards it to the preferred neighbor in the optimal path to the destination.

Challenges:

Mobile hosts can move, mobile hosts can be dynamically added or removed from the network, wireless links often have intermittent conenctivity, and the network connectivity changes dynamically. Mobile nodes often have stringent energy and memory constaints. Wireless links have limited bandwidth, and time-varying link error probability. Additionally, some apps require real-time data delivery and others require robust data delivery.

Design goals:

Routing protocol needs to be fully distributed (no centralized control, adaptivity to network topology changes, loop-free paths, fast route discovery (for real-time applications), low control overhead (for bandwidth-/energy-constrained apps), fault-tolerance (for security/emergency applications.

Classification of routing protocols:

1) Link-State
2) Distance-Vector 
   - Proactive
   - Reactive 
   - Hybrid


