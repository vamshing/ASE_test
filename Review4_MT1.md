[<img width=900 src="https://raw.githubusercontent.com/txt/mase/master/img/banner1.png">](https://github.com/txt/mase/blob/master/README.md)   
[At a glance...](https://github.com/txt/mase/blob/master/OVERVIEW.md) |
[Syllabus](https://github.com/txt/mase/blob/master/SYLLABUS.md) |
[Models](https://github.com/txt/mase/blob/master/MODELS.md) |
[Code](https://github.com/txt/mase/tree/master/src) |
[Lecturer](http://menzies.us) 


What is the problem with local maxima?

1. In the following diagram, each square has the same x,y,z axis. What might the names of those x,y,z values?
![](https://github.com/timm/sbse14/wiki/etc/img/landscape/WrightFitness.jpg)

x,y - attribute of the hare
z - prob of winning fight

2. Explain the following, using the above diagram:

 * Holes : Minimas or the points where there is local minia
 * Poles : Local maxima or hills 
 * Saddles: Flat surface between hills and poles 
 * Local minima: Value less than its neighbours 
 * Flat:  a flat surface with no local minima or maxima
 * Brittle: a bumpy surface with lots of local minima/maxima.Brittleness are solutions that are not robust, 
            meaning that any perturbations to your solution space will result in much worse solutions.

3. Explain the following term and describe how it handles the problem of flat: Retries. Retries mean that we start with 
   a clean slate so as to not remain within the locally stable solutions. Good solutions are few and far apart, so its 
   a good idea to start affresh. If no progress is possible locally, no point in crawl, start afresh.

4. How does the following techniques avoid the problems of local maxima?

  Simulated annealing: crazy jumps
    - Retries: switch to another part of landscape with prob p.
    - Momentum (make sure you explain momentum): When local extrema is reached, momentum pushes to bar to nearby to see any
      fitter solutions exist. Momentum : constant added to mutators of local search.
  
5. Local search can be characterized as follows

   + Jump all around the hills
   + Sometimes, sitting still while rolling marbles left and right
   + Then taking one step along the direction where the marbles roll the furthest.
   + Go to 1.

In the following code snippet, explain where you'd find 5.
```
FOR i = 1 to max-tries DO
  solution = random assignment //jump around all the hills
  FOR j =1 to max-changes DO
    IF  score(solution) > threshold
        THEN  RETURN solution
    FI
    c = random part of solution 
    IF    p < random()
    THEN  change a random setting in c //Sometimes, sitting still while rolling marbles left and right
    ELSE  change setting in c that maximizes score(solution)  //Then taking one step along the direction where the marbles roll the furthest.
    FI
RETURN failure, best solution found
```


_________

<img align=right src="https://raw.githubusercontent.com/txt/mase/master/img/pd-icon.png">Copyright © 2015 [Tim Menzies](http://menzies.us).
This is free and unencumbered software released into the public domain.   
For more details, see the [license](https://github.com/txt/mase/blob/master/LICENSE.md).

