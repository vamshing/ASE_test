# ASE_test

eading gadgets.py:

1) find one part of the code you understand . write down what it does
(in less than four lines)

```
class Schaffer(Candidate):
lines(46-56)
```
What it does:
The method evaluates the candidate's single decision value at the two functions. This decs stores the legal/allowable values
for the decision variable. Later, the ```objs``` stores the functions to minimize the scores which are called by 
```Less```. To call and store the values minimized into ```objs```, the ```maker()``` method is used.


2) find one part of the code you do not understand, write down the line number.

```
 133:         i.also + x
```
Why is the also being auto-incremented?

3a)  "Recursive factories I";  . in the process of filling in
decisions on line 256, the code recurses somewhere else and asks
another object to fill in one value. What other object?

patience

3b)  "Recursive factories II";  . in the process of filling in
objectives on line 265, the code recurses somewhere else and asks
another object to fill in one value. What other object?



4) on lines 292 to 303 , we are mutating during simulated annealling
- what is "sn"
- what is "can"
- what is "decs"
- what is "can.decs"? What class of objects are stored there?
- what is "i.about.decs"? What class of objects are stored there?
- what us "log.decs"? What class of objects are stored there?
- what is happening on line 302? can't we just delete it?
- why is mutate creation inside a loop (for sn in i.aFewBlanks():)?

5) pick a line and imagine that it is commented out. what would happen
to the code? to find your line to delete:

let one,two,three =   the first 3 letters of your name
let prod = one * two * three (multiply their ascii values)
let line = prod mod 460
