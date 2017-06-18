# CarND-Controls-PID
Self-Driving Car Engineer Nanodegree Program

---

## Reflections and description of the process of parameters tuning.

"P controller" proportionately responds to the CTE. The higher the value of P, the stronger the car reacts to the error.

I gradually increased the value of "P", until I got a car movement with a level of oscillation sufficient to get to the first turn (corner).

The "D controller" reacts proportionally to the change in the CTE and smoothing the final result of the controller's operation as a whole.

After that, I began to increase the value of D, reducing the level of oscillation, until the car started to go more or less straight.

After that, I increased the value of P until the car began to fit into more steep turns after the bridge. It led to an increase in the oscillation when moving along a straight line.

To mitigate the increased oscillation of the car when driving in a straight line, I began to increase the value of D until I achieved a more or less decent result.
But the car still passes steep turns (after the bridge) not by one turn movement, but a series of short but strong turn movements (if you can tell how to fix it, I will be very grateful).

As I understand it, the simulator does not have a drift. But there is a strange place at the end of the bridge, where the car make a move and it looks like a drift. I could not find the value of I that somehow changed the behavior of the car in this place, so I returned the value of I to zero.

---

## Dependencies

* cmake >= 3.5
 * All OSes: [click here for installation instructions](https://cmake.org/install/)
* make >= 4.1
  * Linux: make is installed by default on most Linux distros
  * Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
  * Windows: [Click here for installation instructions](http://gnuwin32.sourceforge.net/packages/make.htm)
* gcc/g++ >= 5.4
  * Linux: gcc / g++ is installed by default on most Linux distros
  * Mac: same deal as make - [install Xcode command line tools]((https://developer.apple.com/xcode/features/)
  * Windows: recommend using [MinGW](http://www.mingw.org/)
* [uWebSockets](https://github.com/uWebSockets/uWebSockets)
  * Run either `./install-mac.sh` or `./install-ubuntu.sh`.
  * If you install from source, checkout to commit `e94b6e1`, i.e.
    ```
    git clone https://github.com/uWebSockets/uWebSockets 
    cd uWebSockets
    git checkout e94b6e1
    ```
    Some function signatures have changed in v0.14.x. See [this PR](https://github.com/udacity/CarND-MPC-Project/pull/3) for more details.
* Simulator. You can download these from the [project intro page](https://github.com/udacity/self-driving-car-sim/releases) in the classroom.

There's an experimental patch for windows in this [PR](https://github.com/udacity/CarND-PID-Control-Project/pull/3)

## Basic Build Instructions

1. Clone this repo.
2. Make a build directory: `mkdir build && cd build`
3. Compile: `cmake .. && make`
4. Run it: `./pid`. 

## Editor Settings

We've purposefully kept editor configuration files out of this repo in order to
keep it as simple and environment agnostic as possible. However, we recommend
using the following settings:

* indent using spaces
* set tab width to 2 spaces (keeps the matrices in source code aligned)

