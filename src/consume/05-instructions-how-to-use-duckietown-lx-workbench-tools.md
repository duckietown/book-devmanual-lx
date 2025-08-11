```{seo}
:description: Discover how to use the Duckietown Workbench environment to run simulations and agent-based tools in robotics education.
:keywords: Duckietown, workbench, robotics simulation, tools, learning experience
```

# DTS Code Workbench

## Overview

The `dts code workbench` command provides a complete development environment for Duckietown robotics projects. It creates a virtual desktop (VNC) and runtime environment that allows you to:

- Run GUI tools for visualization and calibration
- Deploy agents to both virtual (Duckiematrix) and physical Duckiebots
- Test solutions locally or on remote robots
- Access a browser-based graphical desktop for development

## Core Components

### VNC Desktop
A browser-accessible graphical desktop for running GUI tools like RViz and calibration utilities. This is for visualization only - code editing should be done with `dts code editor`.

### Workspace
The project filesystem and runtime environment where your agent code executes. Can run using a built Docker image or mount local files with the `--local` flag.

### Duckiematrix Simulator
Provides virtual robots for testing without physical hardware. Must be started before connecting agents.

## Quick Start

### 1. Working with Physical Duckiebots

**Basic workbench with visualization:**
```bash
dts code workbench -R [ROBOT_NAME]
```

**Run agent locally, connect to remote robot:**
```bash
dts code workbench -R [ROBOT_NAME] --local
```

> **Note:** Default password for first-time Duckiebot connections is `quackquack`

### 2. Using Virtual Robots (Simulator)

**Start workbench with simulator:**
```bash
dts code workbench -m -R [VIRTUAL_ROBOT_NAME]
```

**Alternative - start simulator separately:**
```bash
dts code start_matrix
dts code workbench -R [VIRTUAL_ROBOT_NAME]
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
2. **Two URLs Generated:** When using virtual robots, you'll get simulator view and VNC desktop URLs
3. **Use VNC Selectively:** Only open the VNC desktop when specifically requested by learning exercises
4. **Local vs Remote:** Use `--local` flag to run agent on your machine while connecting to remote robot drivers

## Advanced Usage

For detailed information about what happens behind the scenes, refer to the "Behind the Scenes - dts code workbench" documentation section.

> **Warning:** First-time users should focus on the Quick Start section and can safely skip advanced options initially.