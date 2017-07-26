# Distance Vector and Link State Routing Protocols

We will implement and compare two important types of routing protocols: the distance-vector (DV) protocol and the link-state (LS) protocol along with examples of Dijsksta (for LS) and Bellman Ford algorithms (for DV). Here are some notes regarding the motivation, challenges, design goals, classification, etc. of routing protocols for future reference.

**Motivation**:

Why do we need routing protocols? In a network, nodes are not fully connected and there's a need for multi-hop communication. Routing protocols help nodes identify neighbor (next hop) in the optimal path to a destination. They also nodes forward packets hop-by-hop from the source to the destination, where the data packet contains the destination node in the header and a node receives a data packet and forwards it to the preferred neighbor in the optimal path to the destination.

**Challenges**:

Mobile hosts can move, mobile hosts can be dynamically added or removed from the network, wireless links often have intermittent conenctivity, and the network connectivity changes dynamically. Mobile nodes often have stringent energy and memory constaints. Wireless links have limited bandwidth, and time-varying link error probability. Additionally, some apps require real-time data delivery and others require robust data delivery.

**Design goals**:

Routing protocol needs to be fully distributed (no centralized control, adaptivity to network topology changes, loop-free paths, fast route discovery (for real-time applications), low control overhead (for bandwidth-/energy-constrained apps), fault-tolerance (for security/emergency applications.

**Classification of routing protocols**:

1) Link-State
2) Distance-Vector 
   * Proactive
   * Reactive 
   * Hybrid
   
**Link-state vs. distance-vector**

In link-state protocols, each node: 
* has a complete view of the network topology
* propogates the costs to its outgoing links to all other nodes
* use Dijkstra's algorithm to find the optimal path to other nodes

In distance-vector protocols, each node i:
* maintains for each destination _x_ a set of distances (costs) _di-j-...-x_ of path from _i_ to _x_ through node _j_
* selects to forward a data packet through neighbor k such that _di-k-...x = minj {di-j-...x}_
* propogrates to neighbors current estimates of optimal distance _di-k-...-x_ to each destination _x_
* uses the distributed Bellman Ford algorithm to update local estimates of optimal distances, based on those of its neighbors

**Dijksta's algorithm by example**
https://www.cs.usfca.edu/~galles/visualization/Dijkstra.html

**Distributed Bellman-Ford by example**
 - Routing loops, 

**Distance-vector protocols**
* **proactive protocols** 
  - identify optimal paths to destination nodes in advance, so taht they are already there whenever needed (e.g. DSDV)
* **reactive protocols**
  - identify optimal paths to destination nodes on-demand (when needed) (e.g. AODV)
* **hybrid protocols**
  - use the proactive approach to find paths to nodes within a nearby zone, and the reactive approach to find paths to nodes beyond this zone. (e.g. ZRP)

DSDV and AODV use an enhanced version of the distributed Bellman Ford algorithm, in which route information is annotated with an indication of its freshness to prevent/quickly resolve loops.

To be continued.

