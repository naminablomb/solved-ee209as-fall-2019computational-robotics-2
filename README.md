Download Link: https://assignmentchef.com/product/solved-ee209as-fall-2019computational-robotics-2
<br>



<strong>Objectives</strong>

The goal of this lab is to explore build autonomy into a simple two-wheeled non-holonomic robot. You will develop an RRT-based planner designed to get your robot to a desired goal state.

<h1>Preliminaries</h1>

0(a). What is the link to your (fully commented) github repo for this pset?

0(b). Who did you collaborate with?

0(c). What other resources did you use?

0(d). What was the aggregate % contributions of each team member?

<h1>1        Robot model</h1>

You will consider a two-wheeled robot similar to the one shown in Fig. 1. It has two wheels of radius <em>r </em>= 25<em>mm</em>, separated by a distance <em>w </em>= 90<em>mm</em>. It drags a tail for stability, at a distance <em>l </em>= 75<em>mm </em>behind the centerpoint of the wheels. The position of this robot in the environment is defined relative to the centerpoint of the wheels.

Each wheel is powered independently by a continuous rotation servo, with the angular velocity of the wheel controlled by a PWM signal from the microcontroller. Assume each input prescribes the respective angular speed of the wheel, from -60 to +60 RPM. This allows the robot to drive forwards or backwards at variable speed, or turn with any turning radius.

1(a). What is the dimensionality of the input (action) space, robot state (configuration) space, and operational space?

1(b). Define the (continuous space) system model. Assume a fully observable system, i.e. the state itself is directly accessible with no sensor model.

1

Figure 1: Two wheeled tank-drive robot, with dimensions as specified

<h1>2        Trajectory planning</h1>

The robot must move through a cluttered rectangular environment representing a parking lot, ultimately achieving a prescribed goal, i.e. attaining a state within a desired region in C-space. You will consider geometric obstacles defined by rectangles specified within the operational space. For an additional challenge, you may also include “one-way” regions in the space that only permit motion in one direction.

Implement an RRT based algorithm to take the robot from a given initial state to the desired goal state while avoiding obstacles, and use that to simulate a planner / controller specifying the inputs to the actuators as a function of time.

2(a). Given a set of points <em>V </em>in C-space and a single target point <em>x<sub>t</sub></em>, define and justify a metric that can be used to determine which of the points in <em>V </em>is closest to <em>x<sub>r</sub></em>.

2(b). Given arbitrary initial robot state <em>x<sub>i </sub></em>and target robot state <em>x<sub>t </sub></em>(in C-space), generate a smooth achievable trajectory (that matches the metric you defined above) from the <em>x<sub>i </sub></em>towards <em>x<sub>t </sub></em>lasting 1 second. What are the control inputs for this trajectory?

2(c). Given a smooth robot trajectory in C-space and obstacles defined in operational space, determine whether this trajectory is collision free.

2(d). Combine the above to implement an RRT planner generating a trajectory from a specified initial state to a desired goal region. Visualize the evolution of the RRT.

<h1>3        Evaluation and Extensions</h1>

3(a). Run some examples that demonstrate the performance (in terms of computational efficiency, trajectory efficiency, and obstacle avoidance) of your planner as your robot tries to achieve various goals (such as head-in parking and parallel parking between other such parked vehicles). Clearly describe the experiments that were run, the data that was gathered, and the process by which you use that data to characterize the performance of your planner. Include figures; you may also refer to animations uploaded to your git repo.

3(b). How much relative computational cost is associated with the various operations of the RRT planner?

3(c). Improve on your planner using the RRT* algorithm, and compare to your original RRT planner using the above metrics.

3(d). Qualitatively describe some conclusions about the effectiveness of your planner for potential tasks your robot may encounter. For example, what happens to your planner in the presence of process noise, i.e. a stochastic system model? How might you modify your algorithm to better handle noise?


