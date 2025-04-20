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
#### DVR Implementation:
- Used Bellman-Ford algorithm for its simplicity in distributed environments
- Chose to update all nodes simultaneously in each iteration (simulating parallel updates)
- Maintained separate distance and nextHop tables for clarity
