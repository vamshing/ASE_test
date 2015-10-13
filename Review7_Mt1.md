[<img width=900 src="https://raw.githubusercontent.com/txt/mase/master/img/banner1.png">](https://github.com/txt/mase/blob/master/README.md)   
[At a glance...](https://github.com/txt/mase/blob/master/OVERVIEW.md) |
[Syllabus](https://github.com/txt/mase/blob/master/SYLLABUS.md) |
[Models](https://github.com/txt/mase/blob/master/MODELS.md) |
[Code](https://github.com/txt/mase/tree/master/src) |
[Lecturer](http://menzies.us) 


# Review 7: Differential Evolution

- Explain: DE's build new examples by extrapolating between known ones.
  - New = X + f* (Y-Z) ; f  =extrapolation over factor
- Explain the following DE constants:
- What is np and how is it used?
 - np is the number of candidates to be generated over the frontier
- What is cf and how is it used?
 - is the prob of cross over....checked against random probability rand() < cf, then we cross over the parents.
- What is f and how is it used?
 - f is the extrapolation factor. its is used in the crossover for ex, new = New = X + f* (Y-Z)
- Write down, in 10 lines or less, pseudo-code for DE.
  1.take np and generate random candidates
  2.when rand() < cf then mix and match.
  3.mix them by an extrapolation factor. X + f* (Y-Z)
  4.the child replaces the parents in the pareto frontier by checking the fitness against parents
  5.compute the average fitness of all the points on pareto frontier
  6.stop when the average fitness reaches some epsilon value.
- Distinguish between the following two kinds of DE algorithms:
    + DE/rand/1
     - rand1 + 1-factor * (rand2-rand3)
    + DE/best/2
     - best + 1-factor * (rand1 + rand2  + - ....)

_________

<img align=right src="https://raw.githubusercontent.com/txt/mase/master/img/pd-icon.png">Copyright © 2015 [Tim Menzies](http://menzies.us).
This is free and unencumbered software released into the public domain.   
For more details, see the [license](https://github.com/txt/mase/blob/master/LICENSE.md).

