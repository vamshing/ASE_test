[<img width=900 src="https://raw.githubusercontent.com/txt/mase/master/img/banner1.png">](https://github.com/txt/mase/blob/master/README.md)   
[At a glance...](https://github.com/txt/mase/blob/master/OVERVIEW.md) |
[Syllabus](https://github.com/txt/mase/blob/master/SYLLABUS.md) |
[Models](https://github.com/txt/mase/blob/master/MODELS.md) |
[Code](https://github.com/txt/mase/tree/master/src) |
[Lecturer](http://menzies.us) 


### Simulated Annealing

  1. In a few lines, define ordered and unordered search. In what way are they different?
  - Orderd search is for the problems which have inherant ordering like maze,soduku etc. The solution spreads out evenly.'
  - Unordered search has randomly generated candidates which are evaluated for optimality. the are fiddled/mutated to give
    optimal solutions.
  - difference between them: ordered search is useful for problems where _current decisions_ affect the future choices. Whereas,
    unordered search would produce M<=N solutions to N inputs where rest of them are filled at random and is applied for 
    problems where ordering does not matter
  2. In a few lines, compare and contrast: (1) Greedy search; (2) Local Search; and (3) Stochastic search. What, if any, are the trade-offs in using a Stochastic search?
  - Greedy search looks of locally optimal solutions for jumping to nearby candidates. Local search changes the part of the 
    current solution which improves the score. Stochastic search tinkers with the current solution randomly.
    Trade-offs in using Stochastic search: Exploits the CPU speed to randomly search for the optimal solution. Downside  is that
    it may not guarentee a global extrema always.
  3. In about 10 lines, write down the pseudo-code for SA. Number each line.
  ```python
  1.s=s0;e=e0; #initialze s to default
  2.sb=s;eb=e  #initialize best to default
  3.kmax = 1000.0;k=1
  4.while k < kmax and e > emax:
  5.sn = neighbour(s,radius);en=Energy(s) #radius for the sphere to look at
  6.if en < e:
      e = en; s = sn #make a jump to the neighbour
  7.elif en < eb:
      eb = en;sb = sn
  8.if P(e,en,k/kmax) < random.random():
      s = sn;e = en #make a crazy jump
  9. k = k+1
  10.return sb  # returns the best solution seen so far
  ```
  4. In the pseudo-code for SA, you used a neighbourhood function `Neighbour()`. Write down an expression for this.
  ```python 
  def neighbout(x,radius):
    return random.uniform(max(range.low,x-radius),min(x+radius,range.high))
  ```
  5. 4. In the pseudo-code for SA, you used a probability function `P(e_new, e_old, t)`. What would be a valid mathematical expression for this?
  ```
  return math.e**((e_new-e_old)/t) < rand()
  or
  return t < rand()
  t = k/kmax....which would tend to 1 as cooling is reached....-> crazy jumps are reduced
  ```
  6. With respect to function `P(e_new, e_old, t)`, justify the following statements:
      * Initially, SA is like a drunk, then it sobers up: as the P is near 0 -> crazy jumps happen...as P is near 1...jumps do
        are less likely to happen
      * SA consumes lower memory.: Since it stores only three solutions: current,best,and the worst/neighbour
  7. How would you terminate a stochastic algorithms such as SA sooner? (*HINT: Look at variances of epochs*)
    - after each era, 1) consider the median values. if within epsilon of some goal, stop 
      2) compare this era to the last. if no improvement, consider stopping 
      (implementation detail: in my code, i give my optimizers 5 lives.  
      if no improvement, they lose one life. otherwise, they they five more lives. 
      and i stop early if i run out of lives. but not that "5" is just a magic number i set by "engineering judgement")
  8. When finding a solution, you can either mutate towards ''Heaven'' (A better spot) or you can choose to mutate away from "Hell" (A worse spot). Why would you choose one over the other? (*HINT: One of them has a better diversity of search.*)
    - Away from hell would expose to more number of points,hence better coverage of pareto frontier.
      Hence diversity of search.

_________

<img align=right src="https://raw.githubusercontent.com/txt/mase/master/img/pd-icon.png">Copyright © 2015 [Tim Menzies](http://menzies.us).
This is free and unencumbered software released into the public domain.   
For more details, see the [license](https://github.com/txt/mase/blob/master/LICENSE.md).

