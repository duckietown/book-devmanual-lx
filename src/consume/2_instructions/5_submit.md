# `dts code submit`

### What does it do?

The `dts code submit` command is very similar to the `dts code evaluate` command, but instead of evaluating your 
agent's performance on your local machine, it sends it to the [Duckietown challenges server](https://challenges.duckietown.org).

```{figure} ../../_images/consume/challenges-server.png
:name: challenges-server

The Duckietown challenges server displaying results for submission simulations.
```

### How do I run it?

When you are ready to submit your solution to the challenge for your LX, use the following command,

    dts code submit

This will package all of your code and send it to the Duckietown servers for evaluation. The command will output a 
URL that you can use to follow your submission and compare your agent with other developers' solutions from around 
the world.

If you run into any issues using this command, you can search the troubleshooting symptoms below or 
reference the **How to get help** section of the [What's Next?](../3_next/index) page in this development manual.

### Troubleshooting

```{trouble}

`dts :  The path '/home/myuser/not_an_lx_directory' does not appear to be a Duckietown project. 
     :  The metadata file '.dtproject' is missing.`

---
You need to be in the root directory of the LX in order to run the `dts code` commands.
```

### Extra Options

```{warning}
If this is your first time using the `dts code workflow`, don't worry about the following section just yet. You now 
have all the tools to complete your first learning experience - go for it!
```

Once you are comfortable with the `dts code` workflow, you may want to use some of the additional control provided 
over each command.  This section documents each of the flags available to extend the `dts code evaluate` command.

You can also explore the **Behind the Scenes** chapter for more details on what is happening in the background when you run the `dts code submit` command.

**Command options:**

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
````