# design process
# L5.1 Logic: Basics needed for Software Testing
_we are going to be looking at  software testing and test case design focusing more on the relational and logical expressions that come as a part of decision statements in the code_


# L5.2 logic coverage criteria
_in the last lecture we had an introduction to logic, discussed predicate logic, propositional logic_
In this lecture we are going to use logic to define coverage criteria, and in the next few lectures we'll learn how to do source code testing
- defining predicates and clauses
	- ![[Pasted image 20231121170323.png]]
	- the predicate is the whole equation, whole the clause is the subparts of the eqn
		- here x>y is the first clause, C is the next clause and f(z) is the last clasue
	- ![[Pasted image 20231121165822.png]]
	- there are a set of predicates P and put all the clauses in those predicates to make a set C
- predicate coverage
	- ![[Pasted image 20231121170724.png]]
	- for each predicate you have collected, the test requirement TR, contains 2 things
	- let the entire predicate evaluate to true once
	- let the entire predicate evaluate to false once. 
	we have to assign values like this.
- so lets say this predicate was a label at an if condition in the code, when it evaluates to true, it will cover the if part, and wen it evaluates to false, it will cover the else part.
	- comparing this to the graph coverage criteria in the previious weeks, this is ntng but the edge coverage criteria
	- but our focus is to not view it as a control flow graph,but to consider the predicate that labels the statement and evaluate it to tur once and false once
- Clause coverage
	- ![[Pasted image 20231121171714.png]]
	- predicate coverage can be achieved by not exercising each clause to be true once and false once, but we might miss certain errors.
		- to overcome this draw back, we introduce a new coverage criteria, called clause coverage criteria
		- clause coverage criteria = for each clause that you collect from all the predicates in your software artifact, your test requirement contains two.
			- let it evaluate to true
			- let it evaluate to false
- clause coverage vs predicate coverage
	- ![[Pasted image 20231121174440.png]]
	- but the clause coverage need not make the predicate true once and false once i.e **it need not subsume predicate coverage**
	- so in the above example, clause coverage can be achieved but considering only 2,3
		- (a=T,b=F) and (a=F,b=T) these are enough for clause coverage but not predicate coverage as we are getting only (T,T) for both.
		- do the predicate never becomes false although we have covered the clauses.
		- _so clause coverage need not subsume predicate coverage_
	- we wernt covering the clauses with predicate coverage, we intriduced clause coverage, and now we are not covering all the predicates, so the solution is conbinatorial coverage.
- combinatorial coverage
	- ![[Pasted image 20231121175148.png]]
	- so instead of doing clauses separately and predicates separately,consider all the combiantions of T,F values.
	- so your TR contains all the clause in that predicate to evaluate each possible combimnation of true, falsse valuse
	- but this is very difficult to scale.
- clause determining a predicte
	- ![[Pasted image 20231122171337.png]]
	- we focus on once clause, it is called the major clause, the rest of the clauses are called minor clauses
		- we say that the major clause determines the predicate P
			- if the minor clauses takes true/false values such that, if i change the true/falsity of the major clause, then the truth/falsity of the predicate also changes along with that.
- Active clause coverage
	- ![[Pasted image 20231122172523.png]]
	- [[https://youtu.be/whiScMBb9uU?t=1103 | active clause coverage]] #meet1
- GACC and CACC
	- gacc and acc are one and the same thing
	- the predicates value may or maynot change, it is not necessary that it must evaluate to true once and false once(like whenever we change the major clause ig)
		- so it does not subsume predicate coverage
		- but this is a condition we are imposing in CACC
		- *The values chosen for the minor clauses $c_j$ must cause p to be true for one value of the major clause $c_i$ and false for the other*
			- so cacc subsumes predicate coverage
			- ![[Pasted image 20231129131159.png]] #smoldoubt did not understand the example:
				- #wius we need only 2 TRs (TT,FF) for gacc as it is making (a,b) T once and F once, but for cass we need extra TRs:
					- wen a is maj clause(TT,FT) : so a is becoming ToFo and predicate is also becoming ToFo
					- wen b is maj clause(TT,TF): so b is becoming ToFo and predicate is also becoming ToFo?
					- so my doubt is for gacc, so we not check like this(major clause becoming ToFo)?
		- note that this is not same as determination
			- determination are the conditions that are necessary for a clause to determine a predicate
	- here minor values can take anything
- RACC:
	- same as correlated, but the value for minor clauses must remain the same
	- for eg, if we have a set of values for the minor clauses where it is making the predicate True, then you must keep the values for the minor clauses similar to the predicate()
	- ![[Pasted image 20231129133923.png]]
		- wen a is T the predicate is T, when a is F, the predicate is F, but values for the minor clauses remain the same(when a is maj clause)



# L5.3 p2
_previous on st,_ 
- we learnt that the predicate which is extracted from a conditional expression can have several clauses; 
- a clause is an individual atomic entity of the predicate that is free of any logical operator;
- the simplest criteria of the logic is to cover the predicate
	- TR says make the whole prediacte tru once and false once
- we realized that this could be inadequate, as we need to test each clause also
	- so came clause coverage, where in each clause seperately has to be true once and false once
	- but we realized that, this in the preocess need not make the prediacte itself true/false, i.e it need not imply predicate coverage
	- which is inadequate again
- so we said test for all possible combinations of true/false values of clauses across the entire truth table of the predicate
	- but if there are n clauses for the predicate, we realized that there cud be 2^n combinations of t/f values
	- which gets expensive for large predicates
	- so ideally we want a mid way b/w predicate coverage and clause coverage, and also all combinations
- se we started looking at active clause coverage
	- it is basically a way if considering one clause at a time to be active/major clause, and lets the minor clauses take values such that we explore the possibility of the major clause determining the predicate
	- i.e if i change the value of the major clause frm true to false, that also changes the value of the predicate (from true to false) or (from flase to true).
- so we take once active clause for the predicate at a time and check if we can achieve active clause coverage for the particular clause against the predicate. 
- based on the values that the minor clauses can take, there are 3 subcategories of active clause coverage,
	- generalized: where there are no restrictions on what the minor clauses could take
		- we realized that this isnt good, because it will again not satisfy predicate coverage
	- correlated: where minor clauses together take values such that, the major clause for sure influences the predicate
		- i.e flipping the value of the major clause from t to f, thus ends up flipping truth/falsity of the predicate
	- restricted: where we restrict and say that the major clause will determine the predicate, possibly, and in this case the minor clauses take the same value as when the major clause becomes true, and as when the major clause become false.

- Icc

- extensions of icc
	- general
	- restricted

- Infeasibility of logic coverage criteria
- example 
- dealing with infeasibility
- subsumption
	- ![[Pasted image 20231123161423.png]]


# L5.4
_we will look at how to automate the process of determining when the clause will determine the predicate_
