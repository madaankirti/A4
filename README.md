# Assignment 4: Distance Vector and Link State Routing Simulation
**Group Members:**  
- Amandeep Upadhyay (210114)  
- Kirti (210522)  
- Mohammad Suhail Ilyas (210617)
## Assignment Features
### Features Implemented
- Complete **Distance Vector Routing (DVR)** algorithm using **Bellman-Ford**
- Complete **Link State Routing (LSR)** algorithm using **Dijkstra's algorithm**
- Graph input from external file in **adjacency matrix** format
- **Iterative DVR table display** to show convergence process
- Final routing tables for both DVR and LSR algorithms
- Proper handling of **unreachable nodes** using `INF = 9999`
### Features Not Implemented
- Graphical visualization of the network
- Support for dynamic topology changes
- Use of advanced or additional routing metrics
## Design Decisions  
### Algorithm Implementation Choices:
#### 1. DVR Implementation:
- Used Bellman-Ford algorithm for its simplicity in distributed environments
- Chose to update all nodes simultaneously in each iteration (simulating parallel updates)
- Maintained separate distance and nextHop tables for clarity
#### 2. LSR Implementation:
- Implemented Dijkstra's algorithm using priority queue (O(E + V log V) for efficiency
- Used a trace-back method to determine next hops from predecessor array
- Processed each node as source sequentially (rather than simulating flooding)
### Data Structure Choices:
- Used vectors for adjacency matrix storage (simple, cache-friendly)
- Used priority queue for Dijkstra's to efficiently get minimum distance nodes
- Maintained separate tables for distances and next hops for clarity
## Implementation
### High-Level Function Overview
#### `simulateDVR()`
- Initializes **distance** and **nextHop** tables for each node.
- Iteratively updates tables using the **Bellman-Ford equation**
- Continues updating until no more changes occur (**convergence** reached).
- Prints DVR tables after each iteration for clarity.
#### `simulateLSR()`
- For **each node as a source**:
- Runs **Dijkstra's algorithm** with a **priority queue** for efficiency.
- Maintains `distance[]` and `predecessor[]` arrays.
- Uses trace-back from predecessors to determine **next hops**.
- Prints **final routing tables** once completed.
### Helper Functions
####  `printDVRTable()`
- Formats and displays the **Distance Vector Routing (DVR)** table for each node.
- Shows both **cost** and **next hop** information.
#### `printLSRTable()`
- Formats and displays the **Link State Routing (LSR)** table.
- Shows the **shortest path cost** and **corresponding next hop** for each destination.
#### `readGraphFromFile()`
- Reads the **adjacency matrix** from an external `.txt` file.
- Parses the file into a 2D `vector<vector<int>>` used for graph representation.
### Code Flow Diagram
1. Read input graph from file
2. Run DVR simulation:
 --Initialize tables → Iterative updates → Convergence check → Print results
3. Run LSR simulation:
 -- For each node as source: Dijkstra's → Path tracing → Print table
## Contribution of Each Member
| Member | Contribution (%) | Tasks Handled |
|--------|------------------|----------------|
| Amandeep | 33%              | Designed DVR & LSR simulation logic |
| Kirti | 33%              | Handled file I/O, DVR table display |
| Suhail | 33%              | Testing, documentation, and cleanup |
## Testing
### Correctness Testing
- Verified against hand-calculated examples from networking textbooks.
- Tested with various network topologies (fully connected, star, linear).
- Confirmed correct handling of unreachable nodes (`INF = 9999`).
- Checked proper convergence behavior in DVR.
- Ensured shortest paths in LSR matched Dijkstra’s expected results.
### Stress Testing
- Successfully tested with larger graphs (up to 100 nodes).
- Verified performance across different graph densities.
- Checked memory usage for large adjacency matrices.
##  Restrictions
-  Maximum network size limited by system memory (practically up to 1000 nodes).
-  All link costs must be **non-negative integers**.
-  Input file must be **properly formatted** (adjacency matrix).
-  No dynamic topology changes supported during simulation.
## Challenges
### DVR Convergence
- Initially faced issues detecting convergence correctly.
- Resolved by tracking update flags across all nodes after each iteration.
### LSR Next Hop Calculation
- Tricky part: Determining immediate next hop from Dijkstra’s predecessor array.
- Solved by implementing a trace-back method from each destination to the source.
### Input Handling
- Required robust error handling for malformed input files.
- Implemented proper error checking for file I/O operations.
## Sources Referred
- _Computer Networking: A Top-Down Approach_ by Kurose & Ross
- [Dijkstra’s Algorithm – Wikipedia](https://en.wikipedia.org/wiki/Dijkstra%27s_algorithm)
- [Bellman-Ford Algorithm – GeeksforGeeks](https://www.geeksforgeeks.org/bellman-ford-algorithm-dp-23/)
- C++ STL documentation for `priority_queue`
## Declaration
> We declare that this assignment represents our own work and we have not engaged in any form of plagiarism.  
> All code and documentation was written by us except where explicitly cited.
