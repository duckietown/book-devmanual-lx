# What is a Duckietown LX?

```{admonition} Definition
A learning experience is a stand-alone block of activities that is self-contained and ideally can plug and play into a 
full course of materials.
```

**Learners** can complete activities from the Duckietown LX library. This will allow you to dive into the fundamental topics of robotics and then immediately implement behaviors on your Duckiebot using your new skills. See [How To - Progress Through an LX](env-setup) to jump right in.

**Instructors** can create additional custom learning experiences using the Duckietown development tools to present course content as interactive notebooks. To cement topics in practice, you can seamlessly integrate additional robot activities and simulated challenges in a preconfigured environment. 
This prevents students from getting lost in debugging before their project even begins by eliminating extra setup steps and smoothing over complex implementation details.  You can see all available features on the [following page](lx-features) and the LX creation tutorial in [How To - Progress Through an LX](how-to-create-lx).

## Outcomes

Outcomes after completing a learning experience should generally be actionable skills to demonstrate new knowledge.  

These skills are verified through the culminating a demo activity in each LX that can be run on a simulated or real world Duckiebot 
and evaluated in a challenge.

## Learning Goals

LX developers should answer the following questions in the LX description contained in each README. Anyone 
working through an LX should use this information to direct their efforts as they choose and work through LX: 

```{list-table}
:header-rows: 1
:name: learning-goals-tab
* - Question
  - Example
* - What will the LX learner gain from this experience? 
  - Learners will be able to describe and implement a PID controller for a differential drive robot.
* - What are the output activities of the experience?
  - Learners will tune and test their PID controller on a Simulated Duckiebot to achieve a distance traveled goal.
* - What is the prerequisite knowledge and where can learners find it?
  - This LX depends on students having completed the Duckietown ROS LX for the fundamentals of using ROS messages.
```