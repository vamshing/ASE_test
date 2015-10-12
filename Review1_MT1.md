[<img width=900 src="https://raw.githubusercontent.com/txt/mase/master/img/banner1.png">](https://github.com/txt/mase/blob/master/README.md)   
[At a glance...](https://github.com/txt/mase/blob/master/OVERVIEW.md) |
[Syllabus](https://github.com/txt/mase/blob/master/SYLLABUS.md) |
[Models](https://github.com/txt/mase/blob/master/MODELS.md) |
[Code](https://github.com/txt/mase/tree/master/src) |
[Lecturer](http://menzies.us) 


# Review1: Week of Aug 25

## Theory

Can you define the following?

1. Evolutionary algorithms
   1. Genetic algorithms
   - Genetic algos make use of selection,recombination(crossover) and mutation to find solutions to the problem.They work
     over a population of candidate solutions. Initially, the population is created at random. Later, the generations 
     makes use of selection,recombination and mutation to to select promising solutions,mix them in certain way and 
     adjust them slightly(mutate) adjust them. GA is used in test case generation for SBSE.
     :initial random population -> evaluate(fitness of individual) -> selection(to improve overall fitness) -> crossover(new      individuals) -> mutation(add randomness to individual) -> repeat
   1. Genetic programming
   - GP is a way to find computer programs to perform a user-defined task. It is a ML technique which is used to optimize
     a population of programs according to a fitness landscape determined by a programs ability to perform a task. They are 
     represented in memory by tree structures. Every node has an opertor and the terminal node an operand. The main o
     operations in GP are crossover and mutation. Assuming tree structure,
     Crossover: is replacing a node of an individual's tree with a node of another individuals tree(ex. mating)
     Mutations: is applied on the individual's tree by replacing whole node or replacing the node information.
     Difference b/w GA and GP is the representation of solution. GA represents the candidate solns by encoding/string of 	     numbers. GP creates programs.
1. Evolutionary programs 101
   1. Mutation
      1. Can u give examples of GA mutation? of GP mutation? 
      	 - GA Mutation: construct a list of operations using (0-9,+,-,*,/) such that the sequence give the result as 42.
      	 - GP Mutation: A program to fire a gun to hit the moving target. objective is to find the off target distance  	           of the bullet to the target. Several variables like windspeed,distance of target,gun speed etc, are to be 
      	   mutated to find the best program.
  1. Crossover
	  1. Can u give examples of GA crossover? of GP crossover
	  - Identical parents in GP crossover can yield differnt offspring whereas identical parents in GA would yield
	    identical offspring.
	  - GA Crossover: The picture (http://www.abrandao.com/wp-content/uploads/2015/01/gene_crossover.gif) 
	  - GP Crossover: The picture (http://images.slideplayer.com/3/778832/slides/slide_51.jpg)
  1. Selection
    1. Binary domination
       - The method of selection the mating pool where two members are selected at random to compete with the only member
         progressing to the next round of the tournament. When tournament is over, the relative fitness of the member is 
	 decided according to the level of the tournament reached. The more successful the chromosome is in the competetion,
 	 the more often it is expected to appear in the mating pool
    1. Pareto frontier (hint a diagram is good here)
      1. spread
      	- The spread is the spacing of solutions in the approximate set amongst each other.
      1. hypervolume
      	- It measures the area of the solution set dominated by pareto-optimal solutions. The hypervolume represents
      	  the dominance of sets.
	- Hypervolume: If solutions are considered as point in an N-Dimensional space (where N=no. of objectives), then the 		  hypervolume is the N-Dimensional space contained by that solution. Thus, if we were solving for 2 solutions,              then 	we have a 2-D space, the hypervolume will just be the area of the solutions (refer Rahul Krishnas mail           which has the pictures)(https://lh3.googleusercontent.com/-o2OD5VALxfc/Vhr_1xYDBMI/AAAAAAAABkw/Yt6LQ98lZB4/s1600/Bu		  siness%2BCards_4.jpg)(https://lh3.googleusercontent.com/-fZng26GIlO0/Vhr954w4X8I/AAAAAAAABkg/0N4daQYkE5g/s1600/B		  usiness%2BCards_2.jpg)
____

1. Optimizing optimizers <img align=right width=400 src="http://snag.gy/Cdatd.jpg">
   (not examinable)	  
   1. Writing models: understanding and representing a domain. Very slow
   1. Enabling models: getting them running. Not fast
   1. Running them
      1. _M:_ Mutation cost: making  _M_ mutants
      2. _E_: Evaluating _M_ mutants
	     1. If any random variables in the model, then _E*20_ to _E*100*_
	  3. _S_: Selecting cost: worst case _S=M<sup>2</sup>_ comparisons
	  4. _G_: Generations: _G_ times: mutate, select, crossover, repeat
   1. Verification cost:
      1. 20 (say) repeated runs, for many models,  for many optimizers
   1. Techniques (using data mining!)
      1. _M_ cost is low. just do it,
         1. Then feed into some incremental clustering algorithm ([mini-batch k-means](http://goo.gl/V8BQs),
	        [Genic](http://papers.rgrossman.com/proc-079.pdf): [code](https://github.com/ai-se/timm/blob/ffc7071f133521014e69fc91c99aa9432510ffdb/genic.py#L5))
		 1. <img align=right src="http://snag.gy/41kWD.jpg" width=400>	Then only keep (say) a few examples per cluster, selected randomly,
		    
	   1. _E_ reductions:
	     1. In each cluster, find a handful of most different examples and just evaluate those  	 
	   1. _S_ reduction:
	     1. YOur _M_ reductions have also reduced your 	  _S=M<sup>2</sup>_ effort
	   1. _G_ remains. consider "near enough is good enough"<br clear=all>

____

1. Simulated annealing
   1. When to use SA
      - SA is used as an Unordered search.It is used where greedy methods fail especially when there are a lot of local
        extremas in the function. SA uses the stochastic search to find the global maxima/minima by trying to escape 
	the local extrema by making use of the cooling function. Used when there are a lot of local extremas. Also used 
	when we have enough space for holding 3 solutions in RAM.
   1. Why random jumps?
      - Random jumps helps the optimizer escape local extrema. Its done to jump to a worse solution when the 
        temperature is less than a random probability.Whenever, the temperature is cooled, which is gets closer to one,
	the random jumps are reduced.
   2. What is the cooling schedule?
      1. Why slow cooling? (when you jump less and less)
   1. When to stop
   1. Aggregation functions
      1. brittle aggregation functions

## Practice

For each of the following, can you offer a 3 line code snippet to demo
the idea?

1. Classes
```
class employee:
	def __init__(self,name,age):
		self.name = name 
		self.age = age
	def __repr__(name,age):
		return '%s is %g years old' %(self.name,self.age)
```
1. Functions
 - ```def fn(x,y) : return x+y```
1. Decorators
 - ``` @timer def f(x,y): return x + y ```
1. Static variables, functions
 - Variables declared inside the class not the methods are called static variables. 
 ```class myopia:
    i = 2
myopia.i```
 - Static function It does not receive an implicit first argument
```class MyClass(object):
    @staticmethod
    def the_static_method(x):
        print x
MyClass.the_static_method(2)```
1. Scope
  1. nested scope
  - ```
def foo():
    x='Outer String'
    def bar():
        print x
    return bar
test = foo()
test()```

1. functions
  1. default params
  1. variable lists args
  1. variable dictionary args
  1. lambda bodies
1. list comprehensions
 - ```a = [x for x in range(10)]```
1. decorators


_________

<img align=right src="https://raw.githubusercontent.com/txt/mase/master/img/pd-icon.png">Copyright © 2015 [Tim Menzies](http://menzies.us).
This is free and unencumbered software released into the public domain.   
For more details, see the [license](https://github.com/txt/mase/blob/master/LICENSE.md).

