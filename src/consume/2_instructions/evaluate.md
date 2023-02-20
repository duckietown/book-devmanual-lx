# `dts code evaluate`

### What does it do?

The `dts code evaluate` command runs your code to implement a robot agent at the end of each LX and evaluates it 
against some set of performance metrics for the Duckiebot. This might be distance travelled in an obstacle avoidance 
challenge, intersections successful and lawfully handled in the Duckietown city, or any other hurdle that the LX 
creator may have defined for you.  

Details of the evaluation metrics will be outlined in the LX `README` file.

### How do I run it?

We suggest you evaluate your work locally before submitting your solution.
You can do so by running the following command,

    dts code evaluate

This should take a few minutes.

Wait for a URL to appear on the terminal, then click on it or copy-paste it in the address bar
of your browser to access the visualization of your evaluation simulation and statistics.

If you run into any issues using this command, you can search the troubleshooting symptoms below or 
reference the **How to get help** section of the [What's Next?](../3_next/index) page in this development manual.

```{trouble}

`dts :  The path '/home/kathryn-duckietown/duckietown/daffy-stage/docs' does not appear to be a Duckietown project. 
     :  The metadata file '.dtproject' is missing.`

---
You need to be in the root directory of the LX in order to run the `dts code` commands.
```

### Behind the scenes ...

**TODO: This info may go here or in an LX**

### Expert Mode Options

```{warning}
If this is your first time using the `dts code workflow`, don't worry about the following section just yet. Continue 
on to the next page to submit the soliution to your first LX activity.
```

Once you are comfortable with the `dts code` workflow, you may want to use some of the additional control provided 
over each command.  This section documents each of the flags available to extend the `dts code evaluate` command.

```
usage: dts [-h] [-C WORKDIR] [-H MACHINE] [-a ARCH] [-u USERNAME] [--recipe RECIPE] [--no-pull] [--no-cache] [--impersonate IMPERSONATE]
           [-c CHALLENGE] [-L LAUNCHER] [-v]

optional arguments:
  -h, --help            show this help message and exit
  -C WORKDIR, --workdir WORKDIR
                        Directory containing the project to submit
  -H MACHINE, --machine MACHINE
                        Docker socket or hostname where to build the image
  -a ARCH, --arch ARCH  Target architecture for the image to build
  -u USERNAME, --username USERNAME
                        The docker registry username to use
  --recipe RECIPE       Path to use if specifying a custom recipe
  --no-pull             Skip pulling the base image from the registry (useful when you have a local BASE image)
  --no-cache            Ignore the Docker cache
  --impersonate IMPERSONATE
                        Duckietown UID of the user to impersonate
  -c CHALLENGE, --challenge CHALLENGE
                        Challenge to evaluate against
  -L LAUNCHER, --launcher LAUNCHER
                        The launcher to use as entrypoint to the submission container
  -v, --verbose         Be verbose
```