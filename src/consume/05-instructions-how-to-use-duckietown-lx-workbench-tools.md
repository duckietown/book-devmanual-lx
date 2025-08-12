```{seo}
:description: Discover how to use the Duckietown Workbench environment to run simulations and agent-based tools in robotics education.
:keywords: Duckietown, workbench, robotics simulation, tools, learning experience
```

(dts-code-workbench)=
# `dts code workbench`

## Purpose

The `dts code workbench` command orchestrates execution of a Learning Experience (LX) agent against a target robot (virtual or physical). It can optionally start Duckiematrix (virtual robots) and expose a VNC desktop so GUI tools can connect to the LX runtime.

- Execute an agent built from the LX against virtual (Duckiematrix) or physical Duckiebots
- Optionally launch Duckiematrix and expose a VNC desktop for GUI tools connected to the LX runtime
- Run the agent using a built image or by mounting the local workspace (`--local`)

## Core Components

### Workspace
The project filesystem and runtime environment where your agent code executes. Can run using a built Docker image or mount local files with the `--local` flag.

### VNC Desktop
Browser-accessible graphical desktop for running GUI tools (e.g., RViz, calibration utilities) connected to the LX runtime. Can be started with `dts code vnc`.


## Quick Start

### 1. Working with Physical Duckiebots

**Basic workbench:**
```bash
dts code workbench -R [ROBOT_NAME]
```

**Run agent locally, connect to remote robot:**
```bash
dts code workbench -R [ROBOT_NAME] --local
```

> **Note:** Default password for Duckiebot connections is `quackquack`


### 2. Using Virtual Robots (Simulator)

**Start workbench with simulator:**

```bash
dts code start_matrix
```

```bash
dts code workbench -m -R [VIRTUAL_ROBOT_NAME]
```

> **Important:** When using virtual robots, ensure Duckiematrix is running first. The `-m` flag launches it automatically.

### 3. Desktop-Only Mode

**Open VNC desktop without starting agent:**
```bash
dts code vnc -R [ROBOT_NAME]
```

## Command Reference

### `dts code workbench` Options

| Flag | Description |
|------|-------------|
| `-R, --robot` | Robot name to connect to |
| `-m, --matrix` | Also start Duckiematrix simulator |
| `--local` | Run agent on local machine instead of robot |
| `-C, --workdir` | Project directory to work on |
| `-H, --machine` | Docker socket or robot name for agent execution |
| `-u, --username` | Docker registry username |
| `--recipe` | Custom local recipe path |
| `--recipe-version` | Test branch of recipes repository |
| `--keep` | Don't auto-remove containers (debugging) |
| `-L, --launcher` | Custom launcher for agent container |
| `-v, --verbose` | Enable verbose output |

### `dts code vnc` Options

| Flag | Description |
|------|-------------|
| `-R, --robot` | Robot name to connect to |
| `-C, --workdir` | Project directory for desktop |
| `--distro` | Custom VNC distribution |
| `--no-build` | Skip building, reuse last build |
| `--build-only` | Build VNC without running |
| `--plain` | Use plain VNC instead of project-specific |
| `--impersonate` | Username/UID to impersonate in VNC |

## Troubleshooting

### Project Directory Error
```
The path does not appear to be a Duckietown project. The metadata file '.dtproject' is missing.
```
**Solution:** Navigate to the root directory of your Duckietown project before running `dts code` commands.

### Docker Port Conflicts
```
HTTPError: 500 Server Error: Internal Server Error
Port conflicts detected
```
**Solution:** Check running containers and stop unnecessary ones:
```bash
docker ps --format "table {{.Names}}\t{{.Image}}\t{{.ID}}\t{{.Ports}}"
```

## Workflow Tips

1. **Start Order Matters:** For virtual robots, start Duckiematrix first or use the `-m` flag
3. **Use VNC Selectively:** Only open the VNC desktop when specifically requested by learning exercises
4. **Local vs Remote:** Use `--local` to run the agent on the workstation while the robot handles only low-level drivers and actuation; heavy computation is offloaded to the workstation

<!-- ## Advanced Usage

For detailed information about what happens behind the scenes, refer to the "Behind the Scenes - dts code workbench" documentation section. -->

> **Warning:** First-time users should focus on the Quick Start section and can safely skip advanced options initially.