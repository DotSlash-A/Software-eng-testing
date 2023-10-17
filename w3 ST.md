
# 3.4 : data flow coverage criteria
we have seen :
- structural coverage criteria
- dataflow coverage criteria
now we will see data flow coverage criteria

previously on ST lecture, 
- we took control flow graphs, 
- we augmented the data definitions and data uses
- then understood how the data flow criteria can be used to test code
	- data flow criteria basically ensures that every variable that is defined reaches its use in the right way that it is meant to be used
- Recap on Def-use paths:
	- ![[Pasted image 20231015163236.png]]
	- du path wrt to v is a simple path that begins with the definition of v and reaches the use of v, such that along the way, v is definition clear 
		- i.e there are no more redefinitions of v from the def of v to the use of v
		- there cud be intervening uses along the path
	- see what du(ni,nj,v) represent
	- and what du(ni,v) represnrt (we let go of the uses here)
- Recap on data flow criteria
	- ![[Pasted image 20231015163705.png]]
	- all defs covereage: each definition reaches atleast one use, so it doesnt go waste
	- all uses coverage: ensures that every definition reaches all possible uses
		- we write a set of test cases to check for every defintion reaching all possible uses 
	- all du paths coverage: this test requirement demands that for every definition, we consider all possible uses though all possible different paths from the definition to the uses
- then i didnt pay attention cause my vid was at 2x and she was speakign too fast _cri_


# 3.5 summary
- we modeled the code as a graph and looked at covereage criteria of the graph
- we looked at structural coverage criteria, purely based on control flow graphs
- then we added data definitions and uses and looked at data flow coverage criteria

The level at which we are at unit testing of the code i.e we have one particular function and we need to unit test this entity
	One way we learned to do it was to abstract out the paths of the methods and model parts of it as graphs and then use the stucture of the graphs + the data availabel inm the methods to be able to unit test it
	