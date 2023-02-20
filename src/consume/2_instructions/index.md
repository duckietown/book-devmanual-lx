# Step 2: Using the `dts code` workflow

```{tableofcontents}
```

The `dts code` workflow is a set of simple but powerful Duckietown shell commands that you can use to edit, test, 
and run Duckietown Learning Experiences (LX). This includes tools to spin up a development environment, run new robot
behaviors in the simulator and on a Duckiebot, and submit your results to Duckietown challenges.

The commands are presented here in 
the order you will want to use them. Take a 
look at the full list below to get an overview of your tool kit, then the following pages will walk you through how and 
where to run each one.  You can find example LX packages in the [Duckietown Learning Experiences repository](https://github.com/duckietown/duckietown-lx) if you don't have a specific one to begin working through.

## `dts code` commands

`dts code build`

Builds a learning experience into an image that can be run

`dts code edit`

Spins up a browser based development environment that can be used to work through the learning experience using 
VSCode

`dts code workbench`

Creates a virtual environment with Desktop icons that will allow you to easily run activities, simulate a 
Duckiebot directed through a virtual world by your control algorithms, or execute a demo on your real world Duckiebot - 
all with debugging and visualization tools to help you along the way

`dts code evaluate`

Evaluates your solutions to the learning experience activities on your local machine to quickly inform you of your 
progress

`dts code submit`

Submits your work to the Duckietown challenges server so that you can monitor your results and 
view the work of other developers around the world

```{tip}
Remember that in addition to the `dts code` workflow, you also have the complete set of Duckietown development tools 
at your disposal for building and running the projects within each learning experience.  Check out the [Duckiebot](opsmanual-duckiebot:TODO) and [Duckietown Simulator](opsmanual-duckiebot:TODO) development pages for more helpful 
Duckietown shell commands.
```