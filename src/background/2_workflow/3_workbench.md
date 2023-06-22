(behind-the-scenes-code-workbench)=
# `dts code workbench`

This command allows us to run the learning experience code on either a simulated or a real Duckiebot.

## No flags

When no flags are given, only a ROS container is run and the VNC allows us to have a virtual desktop to connect to it.
```{figure} ../../_images/background/workbench-no-flag.drawio.png

Containers running on the Duckiebot and base station with the `--local` flag
```

## `--sim`

<!-- [`ex-modcon-experiment-manager`, `ex-modcon-simulator`, `ex-modcon-ros`, `ex-modcon-vnc`, `ex-modcon-agent`] -->
With the `--sim` flag, the code is executed on the local machine and communicates with a simulator of the Duckiebot.

```{figure} ../../_images/background/workbench-sim-scheme.drawio.png

Containers running on the Duckiebot and base station
```

## `--duckiebot`

With the `--duckiebot` flag we execute the agent code on the real Duckiebot.
The communication between the FIFO bridge and the ROS stack of the real Duckiebot enables the agent to control the Duckiebot.

```{figure} ../../_images/background/workbench-duckiebot-scheme.png

Containers running on the Duckiebot and base station
```

## `--local`

When the `--local` flag is passed, the agent, the FIFO bridge and the other ROS container are executed on the local machine.
The communication between the FIFO bridge and the ROS stack of the real Duckiebot enables the agent to control the Duckiebot.

```{figure} ../../_images/background/workbench-duckiebot-scheme-local.drawio.png

Containers running on the Duckiebot and base station with the `--local` flag
```
