```{seo}
:description: Learn how to build a Duckietown Learning Experience (LX) and structure activities using the official development tools.
:keywords: Duckietown, learning experience, build LX, robotics education, curriculum design
```

(dts-code-build)=
# `dts code build`

## Purpose

The `dts code build` command builds the learning experience package into a Docker image that will be 
used by each of the other commands in the workflow.

The first step to working through any learning experience is to build it.

```{hint}
Begin each work session with a fresh build of the LX to avoid continuing development over previous errors.
```

## Prerequisites

Ensure the system is up-to-date before starting a new learning experience. 
If the Duckietown shell has not been installed and the development environment configured, 
return to the [](env-setup) before continuing.

- Update the shell commands:

      dts update

- Update your laptop/desktop: 

      dts desktop update

- Update your Duckiebot: 

      dts duckiebot update [ROBOT_NAME]


## Run the learning experience

Navigate to the root directory of the learning experience (e.g., `lx-ros-basics`).

```{important}
All `dts code` commands should be executed inside the root directory of the learning experience.
```

Run the build:

    dts code build -R [ROBOT_NAME]

Successful build output example:

```
INFO Project packaged successfully!


==============================
Docker Build Analyzer
Version: 1.1.0
==============================

Final image name: docker.io/<namespace>/ros-basics:ente-amd64
-------------------------
Time: 29 seconds
Documentation: Skipped
====================================================================================
```

For additional logs, run with `--debug`:

    dts --debug code build

## Troubleshooting

If you run into any issues while building the image, you can search the troubleshooting symptoms below or 
reference the [](how-to-get-help) section of this manual.

```{trouble}

`dts :  The path '/home/myuser/not_an_lx_directory' does not appear to be a Duckietown project. 
     :  The metadata file '.dtproject' is missing.`

---
You need to be in the root directory of the LX in order to run the `dts code` commands.
```

## What's Next?

Now that the **ros-basics** learning experience has been built, continue on to the next page to 
open the editor and complete your first notebook activities.

## Extra Options

```{warning}
First-time users may skip the following section and proceed to the next page to open the first LX activity.
```

Once you are comfortable with the `dts code` workflow, you may want to use some additional control provided 
over each command. This section documents each of the flags available to extend the `dts code build` command.

<!-- You can also explore the [Behind the Scenes - dts code build](behind-the-scenes-code-build) chapter 
for more details on what happens in the background when you run the `dts code build` command. -->

### Command options

```bash
usage: main.py [-h] [-C WORKDIR] [-H MACHINE] [-R ROBOT] [--local]
               [-u USERNAME] [--no-pull] [--no-cache] [--push]
               [--recipe RECIPE] [--recipe-version RECIPE_VERSION]
               [--registry REGISTRY] [-L LAUNCHER] [-b BASE_TAG] [-v]
               [--quiet]

options:
  -h, --help            show this help message and exit
  -C WORKDIR, --workdir WORKDIR
                        Directory containing the project to be built
  -H MACHINE, --machine MACHINE
                        Docker socket or robot name to build the agent on
  -R ROBOT, --robot ROBOT
                        Name of the robot we want to build the code on
  --local               should we build the image on the local machine instead
                        of the robot
  -u USERNAME, --username USERNAME
                        The docker registry username to use
  --no-pull             Skip updating the base image from the registry
  --no-cache            Ignore the Docker cache
  --push                Push the resulting Docker image to the registry
  --recipe RECIPE       Path to use if specifying a custom local recipe path
  --recipe-version RECIPE_VERSION
                        Branch to use if specifying a test branch of the
                        recipes repository
  --registry REGISTRY   Docker registry to use
  -L LAUNCHER, --launcher LAUNCHER
                        The launcher to use as entrypoint to the built
                        container
  -b BASE_TAG, --base-tag BASE_TAG
                        Docker tag for the base image. Use when the base image
                        is also a development version
  -v, --verbose         Be verbose
  --quiet               Be quiet
```