Aspect-Oriented Programming provides a way for us to inject code into existing functions or objects, without modifying the target logic.

There are various common good examples of aspects like 
 - logging
 - auditing 
 - declarative transactions
 - security
 - caching, etc. 
The key unit of modularity in OOP is the class, whereas in AOP the unit of modularity is the aspect.

Good example of implementation are different types of interceptors in frameworks like NestJS.


**The main problem with AOP**

Their main problem with it is that its main benefit is actually hiding logic and complexity,
potentially causing side effects without being too clear about it.
