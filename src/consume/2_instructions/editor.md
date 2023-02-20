# `dts code editor`

### What does it do?

The `dts code editor` command provides a local code editor that you will use to work through learning 
experience notebooks and develop agents to run on your Duckiebot - right in your browser.

### How do I run it?

Open the code editor by running the following command

```
dts code editor
```

Wait for a URL to appear on the terminal, then click on it or copy-paste it in the address bar
of your browser to access the VSCode powered code editor. 

The first thing you will see is
the README document for the LX, which should contain an overview of all the commands we will cover in this book as a 
helpful reference.

```{figure} ../../_images/consume/editor-url.png
:name: editor-url

Url to access your VSCode editor in the browser.
```

```{figure} ../../_images/consume/code-editor.png
:name: code-editor

The VSCode LX editor.
```

Now follow the instructions in each of the activities in the `notebooks` directory in sequence to complete the 
learning experience.

```{hint}

Strengthen your test-driven development (TDD) habits by using the Testing interface in the VSCode editor to run the 
provided unit tests for each function you complete in an LX. This will confirm that your solution performs as 
expected before you run it in simulation or on your Duckiebot. Note that the beaker symbol to open the Testing interface may not appear in the sidebar until after you've opened 
one of the Python files in the `packages` directory.
```{image} ../../_images/consume/unit-tests.png
```
%```

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
on to the next page to run your first LX activity.
```

Once you are comfortable with the `dts code` workflow, you may want to use some of the additional control provided 
over each command.  This section documents each of the flags available to extend the `dts code editor` command.

```
usage: dts [-h] [-C WORKDIR] [-u USERNAME] [--distro DISTRO] [--bind BIND] [--no-build] [--build-only] [--recipe RECIPE] [--image IMAGE] [--plain] [--no-pull] [--keep] [--impersonate IMPERSONATE] [-v]

optional arguments:
  -h, --help            show this help message and exit
  -C WORKDIR, --workdir WORKDIR
                        Directory containing the project to open the editor on
  -u USERNAME, --username USERNAME
                        The docker registry username to use
  --distro DISTRO       Custom distribution to use VSCode from
  --bind BIND           Address to bind to
  --no-build            Whether to skip building VSCode for this project, reuse last build instead
  --build-only          Whether to build VSCode for this project without running it
  --recipe RECIPE       Path to a custom recipe to use
  --image IMAGE         Docker image to use as editor (advanced use only)
  --plain               Whether to skip building VSCode for this project, use plain VSCode instead
  --no-pull             Whether to skip updating the base VSCode image from the registry
  --keep                Whether to keep the VSCode once done (useful for debugging)
  --impersonate IMPERSONATE
                        Username or UID of the user to impersonate inside VSCode
  -v, --verbose         Be verbose
```