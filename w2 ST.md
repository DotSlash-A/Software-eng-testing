# L 2.1
- edges
- degree (undirected graphs), in degree and out degree (directed graphs)
- initial nodes and final nodes
- we will learn about graphs in testing and there are different kinds of them like
	- control flow graphs
	- data flow graphs
	- call graphs
	- design elements modelled as finite state machines and statecharts
	- use case diagrams
	- activity diagrams
- we construct a CFG for a basic if loop with an else statement and without and else part
- Paths in graphs:
	- length of a path: number of edges in the path
	- subpath of a path: subsequencre of vertices that occur in the path (vertices an repeat in a subpath)
- **Reachability**
	- ![[Pasted image 20231017113944.png]]
	- DFS and BFS are widely used for reachability in graphs and most of the reachability problems can be solved with their variations
Observability: coming from the initial vertex to a particular vertex
Controllability: from that particular vertex, going to a final vertex
**touring and visiting**
	touring and visiting are one and the same, but for vertices and edges
**Tests and test paths**
	testpath executed by t: when a test case executes a path t
	![[Pasted image 20231010162644.png]]
	the test path starts at u and ends at x, and the path it takes depends on the condition

**Reachability and test paths**
- we use observability and controllability to check if out testpath can reach a vertex or not
	![[Pasted image 20231010163415.png]]

- **graphs in testing**
	- we will take a requirements document and make a graph out of that and those graphs can have several other parameters
	- ![[Pasted image 20231010163537.png]]
	- and then we work with reachability algorithms for testing of these graphs


# 2.2 : fundamental graph algorithms

**Representation of graphs**
- can use adjacency matrix and adjacency list to represent the graphs
- adjacency list
	- for every vertex, take the list of all the vertices that are adjacent to that vertex
	- memory:[[ https://youtu.be/ukbL29rIvGs?t=392 | 6:32]] #rewatch 
	- ![[Pasted image 20231010170346.png]]
- adjacency matrix
	- for unweighted: 0,1 matrix, if there is an edge for those vertices, its a 1,e lse 0
	- for weigther: we fill the cell with the weight if there is an edge between those two vertices
	- memory: [[https://youtu.be/ukbL29rIvGs?t=544 | memory]] #rewatch 

 - **graph algorithms**
	we cover: ![[Pasted image 20231010170723.png]]
	 - **Breadth First search:** [[BFS pdsa | maybe revise the pdsa part here? ]]
		 It starts at some vertex, then it looks at the adjacency list of that vertex fully, then goes to the first vertex in the adjacency list that is populated, and goes on ...
		 In that process it computes the smallest path between any two vertices in the graph.
		 It also can produce a tree that can be used to traverse from one vertex tot he other, called as breadth first tree, and it will contain all the vertices that are reachable from the vertex s.
		 ![[Pasted image 20231021124541.png]]
		- the algorthm maintains a queue
- Bfs give give the shortest path between the source vertex and the other vertex
- DFS gives the the discovery and finish times, it also help us with the strongly connected components, which are like maximally connected loops in the graphs


# 2.4
- we take these software code modelled as graphs, and the requirements and generate test cases to meet those test requirements.
- Test requirements can be of two type:
	- Structural coverage criteria : just the structure
	- Data Flow coverage criteria: to augment the nodes of the graph with information like variables and then consider the flow of the value of the variables
**Structural coverage criteria**
- _node coverage_: requires the test cases visit the each node atleast once
	- how do the test cases look like? they are just test paths that visit every node atleast once
- _edge coverage_ : means that it shud each every edge atleast once, so instead of saying like that, we say that TR has each reachable path upto 1
	- why do we say upto 1?
		- for resons we like in testing, we would like edge coverage to always subsume node coverage