```{seo}
:description: Explore the Duckietown LX Editor Interface and understand how learners interact with notebooks and solution code.
:keywords: Duckietown, LX editor, learning experience, robotics education, notebooks
```

(dts-code-editor)=
# `dts code editor`

## Purpose

The `dts code editor` command provides a local code editor used to work through learning 
experience notebooks and to develop agents that run on a Duckiebot, in the browser.

## Run the editor

Open the code editor by running the following command:

```
dts code editor
```

Wait for a URL to appear on the terminal, then open it in a web browser to access the `VSCode`-powered code editor.

```{note}
On supported operating systems, the page opens automatically in a new browser tab as soon as it is ready.
```

```{figure} ../_images/consume/editor-url.png
:name: editor_url_1
:alt: URL to access the VSCode editor in the browser.
:align: center
:width: 90%

Access link for the VSCode editor in the browser.
```

The initial view displays the README document, which contains the learning objectives for the LX.

```{figure} ../_images/consume/code-editor.png
:name: code_editor_2
:alt: Duckietown VSCode Learning Experience editor.
:align: center
:width: 90%

VSCode Learning Experience editor.
```

After reviewing the learning experience goals in the README, open the `notebooks` directory using the file navigator on the left. Notebook activities contain the primary guidance and content of a learning experience.

When required, modify the code in a cell and run it using the Run Cell arrow on the left side of the cell.

If no code changes are required, run the cell and observe the outcome.

```{figure} ../_images/consume/run-cell.png
:name: run-cell
:alt: Duckietown run cell
:align: center
:width: 90%
```

Complete notebooks in sequence.

```{note}
A suitable starting learning experience is ROS Basics. Complete the following notebooks in the `lx-ros-basics/notebooks` directory:
```

* 01_navigating_file_system.ipynb
* 02_catkin_workspaces.ipynb
* 03_catkin_packages.ipynb
* 04_ros_nodes.ipynb
* 05_ros_topics.ipynb
* 06_ros_messages.ipynb
* 07_duckietown_ros.ipynb

After completing the notebooks, finalize the experience by completing the TODO task in the joystick demo node under `packages/src/dt-joystick-demo`. Reference implementation file: [dt-joystick-demo-node.py](https://github.com/duckietown/lx-ros-basics/blob/ente/packages/src/dt-joystick-demo/src/dt-joystick-demo-node.py).

```{important}
Not all learning experiences follow the same format. Always follow the instructions provided within each notebook.
```

Continue to the `dts code workbench` command.

```{hint}

Use the Testing interface in `VSCode` to run the provided unit tests for each function implemented in an LX. 
This confirms expected behavior before running in simulation or on a Duckiebot. The beaker icon to open the Testing interface may not appear in the sidebar until after a Python file in the `packages` directory has been opened.

```{figure} ../_images/consume/test-interface.png
:name: test_interface_4
:alt: Duckietown LX example test interface
:align: center
:width: 90%
```

```


## Troubleshooting

If issues arise, consult the troubleshooting symptoms below or reference the [](how-to-get-help) section of this manual.

```{trouble}

`dts :  The path '/home/myuser/not_an_lx_directory' does not appear to be a Duckietown project. 
     :  The metadata file '.dtproject' is missing.`

---
Run within the root directory of the LX to execute `dts code` commands.
```

## Extra Options

```{warning}
First-time users may skip the following section and proceed to the next page to run the first LX activity.
```

Once you are comfortable with the `dts code` workflow, you may want to use some additional control provided 
over each command. This section documents each of the flags available to extend the `dts code editor` command.

You can also explore the [Behind the Scenes - dts code editor](behind-the-scenes-code-editor) chapter 
for more details on what happens in the background when you run the `dts code editor` command.

### Command options

```
usage: main.py [-h] [-C WORKDIR] [-u USERNAME] [--distro DISTRO] [--bind BIND]
               [--no-build] [--build-only] [--recipe RECIPE]
               [--recipe-version RECIPE_VERSION] [--image IMAGE] [--plain]
               [--no-pull] [--keep] [--impersonate IMPERSONATE] [-v]

options:
  -h, --help            show this help message and exit
  -C WORKDIR, --workdir WORKDIR
                        Directory containing the project to open the editor on
  -u USERNAME, --username USERNAME
                        The docker registry username to use
  --distro DISTRO       Custom distribution to use VSCode from
  --bind BIND           Address to bind to
  --no-build            Whether to skip building VSCode for this project,
                        reuse last build instead
  --build-only          Whether to build VSCode for this project without
                        running it
  --recipe RECIPE       Path to use if specifying a custom local recipe path
  --recipe-version RECIPE_VERSION
                        Branch to use if specifying a test branch of the
                        recipes repository
  --image IMAGE         Docker image to use as editor (advanced use only)
  --plain               Whether to skip building VSCode for this project, use
                        plain VSCode instead
  --no-pull             Whether to skip updating the base VSCode image from
                        the registry
  --keep                Whether to keep the VSCode once done (useful for
                        debugging)
  --impersonate IMPERSONATE
                        Username or UID of the user to impersonate inside
                        VSCode
  -v, --verbose         Be verbose
```