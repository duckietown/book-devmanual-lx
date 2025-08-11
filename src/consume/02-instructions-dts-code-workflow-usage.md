```{seo}
:description: Learn about the `dts code` workflow in Duckietown and how to use it to develop and test Duckietown Learning Experiences (LX).
:keywords: Duckietown, learning experience, LX, dts code, development workflow, Duckiebot, simulator, Docker, VSCode, workbench
```


(devmanual-lx-dts-code-workflow)=
# Step 2: Using the `dts code` workflow

The `dts code` workflow is a set of Duckietown shell commands to edit, test, and run Duckietown Learning Experiences (LX). These tools can:
* Spin up a browser-based development environment
* Build learnings into container images
* Run robot behaviors in the simulator and on a Duckiebot

This section demonstrates the workflow using the Braitenberg experience from the [lx-braitenberg](https://github.com/duckietown/lx-braitenberg) repository as an example. Instructions on how to fork and clone this repository are located in [](env-setup).

## Getting started

Complete the following steps to begin working with the `dts code` workflow:

### ✅ Step 1

Open a terminal and navigate to the `lx-braitenberg` directory.

### ✅ Step 2

Review [](devmanual-lx-dts-code-command-set) for a preview of the toolkit.

### ✅ Step 3

Proceed to the next page, [](dts-code-build), to start the first learning experience.

(devmanual-lx-dts-code-command-set)=
## The `dts code` commands set


### `dts code build`

Builds the learning experience into a Docker image that can then be run with a specified robot.

```bash
dts code build -R <ROBOT_NAME>
```

### `dts code editor`

Starts a browser-based development environment (VS Code) for the learning experience (LX).

### `dts code workbench`

Runs the agent against a robot (real or virtual), with integrated visualization and debugging tools. Add `-m` or `--matrix` to launch the agent and attach to the matrix.

```{important}
Start the Duckiematrix before running `dts code workbench` with a virtual robot. See [`dts code start_matrix`](dts-code-start-matrix).
```

```bash
dts code workbench -R <ROBOT_NAME>
```

If using a virtual robot within the duckiematrix
```bash
dts code workbench -m -R <VIRTUAL_ROBOT_NAME>
```

Expected output:
```bash
2025-08-10 15:26:07 dan-Nitro-AN715-51 dts[129448] INFO Running an image for amd64 on x86_64.
2025-08-10 15:26:07 dan-Nitro-AN715-51 dts[129448] INFO Running an image for amd64 on x86_64. Multiarch not needed!
2025-08-10 15:26:07 dan-Nitro-AN715-51 dts[129448] INFO Syncing code with <ROBOT_NAME>...
duckie@<ROBOT_NAME>.local's password: 
```

```{note}
When connecting to a new robot, the default password is `quackquack`.
```

<!-- ### `dts code evaluate`

Evaluates your solutions to the learning experience activities on your local machine to quickly inform you of your progress.

### `dts code submit`

Submits your work to the 
[Duckietown Challenges Server](https://challenges.duckietown.org) so that you can monitor your results and view the work of other developers around the world. -->

<!--
```{todo}
Update the URL to the challenges server once we move to `duckietown.com`.
```
-->

(dts-code-start-matrix)=
### `dts code start_matrix`

Starts the Duckiematrix simulator.
A virtual robot can be created and managed with `dts duckiebot virtual` commands.

```bash
dts code start_matrix
```

### `dts code vnc`

Opens a noVNC session for the current LX, useful for sending commands and viewing GUI tools.

```bash
dts code vnc -R <ROBOT_NAME>
```

````{tip}
In addition to the `dts code` workflow, the complete set of Duckietown development tools is available for building and running projects within each learning experience.  

Refer to the [Duckiebot](book-opmanual-duckiebot:ops-tools) and [DTProject](book-devmanual-software:dtproject) development pages for additional Duckietown shell commands.
````
