# `dts code build`

### What does it do?

The `dts code build` command builds the learning experience package into a software image that will be used by each of 
the other commands in the workflow.  

The first step to working 
through any LX is to build it and confirm that you have no initial errors.

```{hint}
Strengthen your iterative development habits by beginning every work session with a fresh build of your LX. This 
will help ensure that you don't continue development on top of any previous errors.
```

### Prerequisites

Always make sure that your system is up to date before starting a new learning experience. If you haven't yet installed the 
  Duckietown shell and configured your development environment, return to the [Environment Setup page](../1_setup/index) before continuing.

- 💻 Update the shell commands:

      dts update

- 💻 Update your laptop/desktop: 

      dts desktop update

- 🚙 Update your Duckiebot: 

      dts duckiebot update <your_robot_name>

### How do I run it?

First, navigate into the directory containing the learning experience you would like to progress through. 
For example, if you have the following collection of learning experiences and would like to work through the 
`object-detection` LX, all `dts code` commands should be executed inside of the`object-detection` directory.

```{figure} ../../_images/consume/lx-directory.png
:name: lx-directory

List of LX directories with the object-detection directory highlighted.
```

Then run

    dts code build

You will see the following message once your LX has built successfully

```{figure} ../../_images/consume/build-success.png
:name: build-success

Success message that indicates a successful LX build.
```

For more information about what is happening during your build process, you can run any `dts code` command in debug 
mode using the `--debug` flag.

    dts --debug code build

If you run into any issues while building the image, you can search the troubleshooting symptoms below or 
reference the **How to get help** section of the [What's Next?](../3_next/index) page in this development manual.

```{trouble}

`dts :  The path '/home/kathryn-duckietown/duckietown/daffy-stage/docs' does not appear to be a Duckietown project. 
     :  The metadata file '.dtproject' is missing.`

---
You need to be in the root directory of the LX in order to run the `dts code` commands.
```

### Extra Options

```{warning}
If this is your first time using the `dts code workflow`, don't worry about the following section just yet. Continue 
on to the next page to open you first LX activity.
```

Once you are comfortable with the `dts code` workflow, you may want to use some of the additional control provided 
over each command.  This section documents each of the flags available to extend the `dts code build` command.

You can also explore the **Behind the Scenes** chapter for more details on what is happening in the background when you run the `dts code build` command.

**Command options:**

```
usage: dts [-h] [-C WORKDIR] [-H MACHINE] [-u USERNAME] [--no-pull] [--no-cache] [--push] [--recipe RECIPE] [--registry REGISTRY] [-L LAUNCHER] [-b BASE_TAG] [-v] [--quiet]

optional arguments:
  -h, --help            show this help message and exit
  -C WORKDIR, --workdir WORKDIR
                        Directory containing the project to be built
  -H MACHINE, --machine MACHINE
                        Docker socket or hostname to use
  -u USERNAME, --username USERNAME
                        The docker registry username to use
  --no-pull             Skip updating the base image from the registry
  --no-cache            Ignore the Docker cache
  --push                Push the resulting Docker image to the registry
  --recipe RECIPE       Path to use if specifying a custom recipe
  --registry REGISTRY   Docker registry to use
  -L LAUNCHER, --launcher LAUNCHER
                        The launcher to use as entrypoint to the built container
  -b BASE_TAG, --base-tag BASE_TAG
                        Docker tag for the base image. Use when the base image is also a development version
  -v, --verbose         Be verbose
  --quiet               Be quiet
```