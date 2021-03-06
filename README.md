Genetic Algorithm PID Controller Tuner
================================

Overview
--------

Genetic-algorithm-pid-controller-tuner is an example of using a genetic algorithm to tune a PID controller.

A PID controller is any controller that uses a combination of integral, proportional, and derivative parameters (I, P, D) to
follow some target value. We integrate, derive, and multiply the distance from our target by certain constants. Call them (ki, kp kd)

So our "velocity towards the target value" is the function f(x) = ki*I(x) + kp*P(x) + kd*D(x) where "x" is the current distance
from the target location.

In our example, we have a robot following a theoretical line. The line randomly walks about the origin "0" at each timestep. We use
a genetic algorithm to find how fit our robot is to follow the line.

The application outputs some pretty cool graphs that show how the values of (a, b, c) evolve over time

News
----

*09/14/2013 : I've completed the basic code refactoring and got the simulation running, without visuals. The next step is to abstract
    out the controller a little more to increase the size of the data we can work with without getting numeric overflows (increasing the
    simulation length creates numeric overflows during some arithmetic operations). Of course I also need to get the visual system hooked back
    up and I'll probably create a library module for it. I'll probably stop working on this project until further notice because I have a lot
    of other, more pertinent projects I'm working on and I don't see a huge future for this one.

*08/31/2013 : I'm currently overhauling the project and moving it to a new architecture. The application will consist of four main modules:
    - Algorithm, which will house the genetic algorithm logic
    - Map, which creates or loads a map over which the robot runs
    - Chromosome, which defines the chromosome (a, b, c), which are also known as (Ki, Kp, Kd)
    - Simulation, which contains methods for running the simulation.

*04/20/2011 : Original completion of this project as a class project for Introduction to Robotics at University of Central Florida

Possible Future Improvements
----------------------------

* Reduce premature convergence on local minima.
* Add parallel populations who independently evolve and then merge
* Improve Line Generation algorithm to make it change smoothly in one direction or the other.


Resources
---------
* The code is self documented
* An introduction to genetic algorithms can be found here: http://www.obitko.com/tutorials/genetic-algorithms/


Dependencies
------------

* Python 2.7
* Numpy 1.5
* Matplotlib
