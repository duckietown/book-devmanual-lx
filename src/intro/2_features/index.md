(lx-features)=
# LX Features and Activities

Let's start by understanding each of the learning experience activities available and how they might be used.

The `duckietown-lx` repository on GitHub contains the learning experiences developed by the Duckietown team - we'll 
break down the [Object Detection](https://github.com/duckietown/duckietown-lx/tree/mooc2022/object-detection) LX as the main example here.

```{note}
Learning Experiences are run using the `dts code` workflow as described in [How To - Progress Through an LX](env-setup). This command set gives students a streamlined environment and powerful tools to complete activities.
```

The following activity types can be implemented with the Duckietown Learning Experience infrastructure:

* [Notebook](notebooks-intro)
* [Workbench Tool](workbench-intro)
* [Simulated Agent](simulator-intro)
* [Duckiebot Agent](agents-intro)
* [Evaluation](evaluation-intro)

---

(notebooks-intro)=
## Activity: Notebooks

Learners are immediately presented with the goals and workflow instructions for a learning experience when they use `dts code editor` to spin up the preconfigured VSCode editor.  Installing a local editor is not necessary, and everyone begins with a uniform environment to complete the learning experience.  The `notebooks` directory will always contain the first activity.

```{figure} ../../_images/intro/obj-det-editor.png
:name: editor-activity-intro
```

A _Notebook Activity_ introduces key concepts within a Jupyter notebook that learners can work through to cement, visualize, and implement their understanding.  Tab through the gallery of notebooks below for a few examples of notebook features.

`````{tab-set}
````{tab-item} Image Filtering
```{figure} ../../_images/intro/vislane-notebook.png
:name: notebook-gallery-2
```
````

````{tab-item} Object Detection
```{figure} ../../_images/intro/obj-det-notebook.png
:name: notebook-gallery-3
```
````

````{tab-item} Hello World
```{figure} ../../_images/intro/hello-world-notebook.png
:name: notebook-gallery-1
```
````
`````

Learners may also be directed to implement long-form solutions in the provided `solution` package. This code can be imported to notebooks for visualization and testing or used by an agent node on the Duckiebot.

```{figure} ../../_images/intro/obj-det-solution.png
:name: notebook-solution
```

### Providing Guidance

Students should be given instruction within the notebooks on how to progress through the LX activities in order. 
Every learning experience should also revolve around a main _Learning Goal_ (or set of learning goals), documented at the beginning of the 
`README` file.

```{admonition} Example Learning Goal
The Object Detection learning experience will take you through the process of collecting data from the Duckietown simulator and formatting it to be used to train a neural network to perform object detection using the robot's camera image. We will use one of the most popular object detection neural networks, called YOLO (v5). Finally you will integrate this trained model into the autonomy stack to create a Duckiebot agent that stops whenever an object (duckie) is detected in the road.
```

---

(workbench-intro)=
## Activity: Workbench Tool

A _Workbench Activity_ provides a VNC that is used for running tool, simulation, and agent based activities. This is a fully functional Desktop environment with the Duckietown and ROS dependencies installed and can be started by simply running `dts code workbench`.  Instructors can develop custom tools or incorporate any standard ROS tool into the LX activity.

The Object Detection LX uses the workbench environment to run a dataset augmentation tool for learners.

```{figure} ../../_images/intro/obj-det-workbench.png
:name: workbench-activity-intro
```

It can also be used to display the Object Detection model results as applied to an image stream from the Duckiebot for visual analysis.

```{figure} ../../_images/intro/workbench-detector.jpeg
:name: workbench-activity-detector
```

---

(simulator-intro)=
## Activity: Simulated Agent

The _Workbench_ can also run simulated Duckiebot agents, allowing learners to test their robot behaviors in a virtual environment.

```{figure} ../../_images/intro/workbench-sim-view.png
:name: sim-activity-intro
```

---

(agents-intro)=
## Activity: Duckiebot Agent

Once their solution works in simulation, learners may wish to run their solution on a real-world Duckiebot in a Duckietown environment like the one shown below.


```{figure} ../../_images/intro/duckiebot-env.jpg
:name: duckiebot-env
```

The _Workbench_ can interface with the Duckiebot using the ROS network and run connected tools such as keyboard control or `rviz`. Tab through the gallery below to see examples of a variety of tools for interacting with Duckiebot agents.


`````{tab-set}
````{tab-item} Image Streams
```{figure} ../../_images/intro/obj-det-duckiebot.png
:name: workbench-gallery-1
```
````

````{tab-item} Rviz and Custom Tools
```{figure} ../../_images/intro/workbench-rviz.png
:name: workbench-gallery-2
```
````

````{tab-item} Keyboard Control
```{figure} ../../_images/intro/workbench-joystick.png
:name: workbench-gallery-3
```
````
`````

---

(evaluation-intro)=
## Activity: Evaluation

Learners can _evaluate_ their solutions to Learning Experience challenges locally and submit them to the uploads your agent to the 
[Duckietown Challenges Server](https://challenges.duckietown.org) for evaluation on the cloud.

```{figure} ../../_images/intro/obj-det-eval.png
:name: evaluation-activity-intro
```
