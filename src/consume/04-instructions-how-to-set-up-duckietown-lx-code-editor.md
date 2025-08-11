```{seo}
:description: Explore the Duckietown LX Editor Interface and understand how learners interact with notebooks and solution code.
:keywords: Duckietown, LX editor, learning experience, robotics education, notebooks
```

(dts-code-editor)=
# `dts code editor`

## What does it do?

The `dts code editor` command provides a local code editor used to work through learning 
experience notebooks and to develop agents that run on a Duckiebot, in the browser.

## How do I run it?

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
:alt: Url to access your VSCode editor in the browser.
:align: center
:width: 90%

Url to access your VSCode editor in the browser.
```

The initial view displays the README document, which contains the learning objectives for the LX.

```{figure} ../_images/consume/code-editor.png
:name: code_editor_2
:alt: The Duckietown VSCode Learning Experience editor.
:align: center
:width: 90%

The VSCode Learning Experience editor.
```

After reviewing the learning experience goals in the README document, open the `notebooks` directory using the file navigation on the left side of the editor. The activities in the `notebooks` directory contain the main guidance and content of a learning experience.

To complete a cell modify the code inside when required and run the cell by pressing the arrow on the right hand side of the cell.

If there is no code to modify, simply just run the cell and observe the outcome.

```{figure} ../_images/consume/run-cell.png
:name: run-cell
:alt: Duckietown run cell
:align: center
:width: 90%
```

Complete each notebook in sequence. For the **Braitenberg** LX, complete the following notebooks to create an image filter and implement braitenberg controls:

* 01-Image-Manipulation
* 02-Image-Filtering
* 03-Braitenberg

Then return to this page and continue to the `dts code workbench` command.

```{hint}

Use the Testing interface in `VSCode` to run the provided unit tests for each function completed in an LX. 
This confirms expected behavior before running in simulation or on a Duckiebot. The beaker icon to open the Testing interface may not appear in the sidebar until after a Python file in the `packages` directory has been opened.

``{figure} ../_images/consume/test-interface.png
:name: test_interface_4
:alt: Duckietown LX example test interface
:align: center
:width: 90%
``

```


## Troubleshooting

If you run into any issues using this command, you can search the troubleshooting symptoms below or 
reference the [](how-to-get-help) section of this manual.

```{trouble}

`dts :  The path '/home/myuser/not_an_lx_directory' does not appear to be a Duckietown project. 
     :  The metadata file '.dtproject' is missing.`

---
You need to be in the root directory of the LX in order to run the `dts code` commands.
```

## Extra Options

```{warning}
If this is your first time using the `dts code` workflow, do not worry about the following section just yet. 
Continue on to the next page to run your first LX activity.
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