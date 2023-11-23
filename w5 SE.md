# design process
# L5.1 Logic: Basics needed for Software Testing
_we are going to be looking at  software testing and test case design focusing more ont he realtional and logical expressions that come as a part of decision statements in the code_


# L5.2 login coverage criteria
_in the last lecture we had an introduction to logic, discussed predicate logic, propositional logic_
- this lecture we are going to use logic to define coverage criteria, and in the next few lecutures we'll learn how to do source code testing
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
	- 