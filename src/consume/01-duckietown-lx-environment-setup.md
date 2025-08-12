```{seo}
:description: Set up your development environment for Duckietown Learning Experiences with Docker, SSL certificates, and the Duckietown shell.
:keywords: Duckietown, environment setup, LX, docker, development environment, duckietown shell, SSL, hello-world
```

(env-setup)=
# Step 1: Environment Setup

Before starting any Duckietown Learning Experience (LX), ensure the development environment is set up.

```{important}
Complete the following setup steps carefully to prevent running into bugs later on.
```

## 1 - Requirements

Assume the Duckietown development environment was set up following the [Setup - Laptop](book-opmanual-duckiebot:laptop-setup) and [Setup - Account](book-opmanual-duckiebot:dt-account) sections of the Duckiebot Operation Manual.

Then, install the following dependency libraries:

`````{tab-set}
````{tab-item} Linux
Open a terminal and run the following command:
```bash
sudo apt install libnss3-tools
```
````

````{tab-item} macOS
Open a terminal and run the following command:
```bash
brew install nss
```
````
`````

Then update the Duckietown shell and the shell commands:

```bash
pip3 install -U duckietown-shell
dts update
```

## 2 - Docker Configuration

After completing Duckietown development setup instructions, add `docker.io` credentials to the Duckietown shell using the following command:

```bash
dts config docker credentials set --username <USERNAME> --password <PASSWORD>
```

Expected confirmation:
```bash
Docker access credentials stored!
```

```{note}
The `<USERNAME>` and `<PASSWORD>` correspond to [DockerHub](https://hub.docker.com) credentials configured during Docker setup in the Duckiebot Operation Manual.
```

## 3 - SSL certificate

SSL certificates and TLS encryption are used to guarantee a high standard of safety and privacy.

Set up a local SSL certificate needed to run the LX editor inside your browser:

```bash
dts setup mkcert
```

## 4 - The `ROS-Basics` LX

The following pages use the **ROS-Basics** LX as a running example.

Fork and clone the [`ros-basics`](https://github.com/duckietown/lx-ros-basics) repository to follow along.

1. To store changes while retaining the ability to pull updates from the canonical repository, create a personal fork. Press "Fork" in the top right corner of the [lx-ros-basics](https://github.com/duckietown/lx-ros-basics) repository page on GitHub.
   The new repository fork will appear in the GitHub repository list as: `<GITHUB_USERNAME>/lx-ros-basics`

Then clone the forked repository. Replace `<GITHUB_USERNAME>` and `<LEARNING_EXPERIENCE>` (e.g., `ros-basics`) in the command below:
    
```bash
git clone -b ente git@github.com:<GITHUB_USERNAME>/lx-<LEARNING_EXPERIENCE>
```

2. Configure the Duckietown version of this repository as the upstream repository to synchronize with the fork. Navigate to the repository folder and list current remotes:

```bash
git remote -v
```
Expected output:
```bash
upstream	https://github.com/duckietown/lx-ros-basics (fetch)
upstream	https://github.com/duckietown/lx-ros-basics (push)
```
Specify a new remote upstream repository:

```bash
git remote add upstream https://github.com/duckietown/lx-<LEARNING_EXPERIENCE>
```

3. Confirm that the new upstream repository was added to the list:

```bash
git remote -v
```
Expected output:
```bash
origin	https://github.com/duckietown/lx-ros-basics.git (fetch)
origin	https://github.com/duckietown/lx-ros-basics.git (push)
upstream	https://github.com/duckietown/lx-ros-basics (fetch)
upstream	https://github.com/duckietown/lx-ros-basics (push)
```

4. Work can now be pushed using the standard GitHub workflow. Each learning experience begins by prompting a pull from the upstream repository to update exercises to the latest Duckietown version:

```bash
git pull upstream ente
```

Proceed to the next section to start development with the `dts code` workflow.
