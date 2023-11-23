# 2.1
- Types of users
	- primary
	- secondary
	- teritiary
- Analysis of requirement
	1. Anomaly
	2. Inconsistency
	3. Incompleteness
	4. Ambiguous

# 2.2
How to identify requirements?
	1. questionaire
	2. Interviews
	3. Focus Groups
	4. Documentations
	5. NAturalistic observations

How to identify Users? (i think or give it another heading)
	1. Structured Interview
	2. Semistructured Interview
	3. Unstructured Interview
	4. Questionaires


# 2.3
Functional and Non functional requriements
- Funtional:
	1. these are similar to a mathematical function where a function transforms an element in the input domain 'i' to value in the output 'o'.
	2. so a functional requirement of the system should clearly describe each functionality that the system would support along with the input and the output data set
	3. eg taken in lec is that a person shud be able to add/edit/delete a catalogue

- Non functional:
	1. eg in the lec: the product shud appear in the catalogue within 5 seconds 
	2. cannot be expressed as functions with an input and an output
	3. they tell how the system should behave and not what the system should do
	- **a few types of non fun req**
		1. Reliability: we want the system to behave the same way over time and not crash often 
		2. Robustness: ability to handle unexpected situations like when the user gives a garbage input, or large numbers or high traffic
		3. performance
		4. portability
		5. security

# 2.4
we have identified and gathered all the requirements now the question is how do we <mark style="background: #FFF3A3A6;">organize</mark> all these requirements to analyze them?
- In the first week, we looked at two prominent software assessment models, the <mark style="background: #FFF3A3A6;">Plan and the Document model</mark> and the <mark style="background: #FFF3A3A6;">agile model</mark>
	- Plan and document
		- first the system analyst gathers al the information by consulting the other members of the software team
		- after the analyst has gathered all the requirements, they organize the requirements in a <mark style="background: #FFF3A3A6;">Software Requirements Specification(SRS) documents</mark>
		- and this doc contains alll the user requriemetns in a specific form 
		- Some of the imp sections of the srs docuement:
			-  Section 1 and 2:
				- describe the broad outline and description of the software system
				- might contain the purpose, scope, acronyms, abbreviations used in the software
				- aswell as perspective functions, assumptions, dependencies, etc
			- Section 3:
				- contains the functional and non functional requirements of the system
				- section 3.1: external interface requirements 
					- ![[Pasted image 20231003164943.png]]
						- eg for ui: what are the sample screen images, gui standards, screen layouts etc
						- eg for hardware interface: in an atm system we need to specify the interface between the atm system, atm card, and the atm software
						- eg for software interface: what is the database, operating system.
							- more like software interaction with other software components
							- eg: amazon seller portal should be able to communicate with the amazon buyer portal
						- communication interfaces: like sending an email, sms, etc
				- section 3.2:
					- it outlines a broad high level function called the system feature and the corresponding functional requirements for each of these system features
					- ![[Pasted image 20231003165541.png]]
					- and for each of these system features, we add additional functional features
				- section 3.3 to 3.6
					- contains the details of non functional requirements like performance, security etc
		- Advantages of an SRS document:

# 2.5

