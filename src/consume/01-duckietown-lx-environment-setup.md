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
The `<USERNAME>` and `<PASSWORD>` correspond to [`DockerHub`] (hub.docker.io) credentials configured during Docker setup in the Duckiebot Operation Manual.
```

## 3 - SSL certificate

SSL certificates and TLS encryption are used to guarantee a high standard of safety and privacy.

Set up a local SSL certificate needed to run the LX editor inside your browser:

```bash
dts setup mkcert
```

## 4 - The `Braitenberg` LX

The following pages use the **Braitenberg** LX as a running example.

Fork and clone the [`Braitenberg`](https://github.com/duckietown/lx-braitenberg) repository to follow along.

1) To store changes while retaining the ability to pull updates from the canonical repository, create a personal fork. Press "Fork" in the top right corner of [the lx-braitenberg repository page on GitHub](https://github.com/duckietown/lx-braitenberg).
   The new repository fork will appear in the GitHub repository list as:

        <GITHUB_USERNAME>/lx-braitenberg

    Then clone the forked repository. Replace `<GITHUB_USERNAME>` and `<LEARNING_EXPERIENCE>` (e.g., `braitenberg`) in the command below:
    
```bash
git clone -b ente git@github.com:<GITHUB_USERNAME>/lx-<LEARNING_EXPERIENCE>
```

2) Configure the Duckietown version of this repository as the upstream repository to synchronize with the fork. Navigate to the repository folder and list current remotes:

```bash
git remote -v
```

    Specify a new remote upstream repository:

```bash
git remote add upstream https://github.com/duckietown/lx-<LEARNING_EXPERIENCE>
```

    Confirm that the new upstream repository was added to the list:

```bash
git remote -v
```

    Work can now be pushed using the standard GitHub workflow. Each learning experience begins by prompting a pull from the upstream repository to update exercises to the latest Duckietown version:

```bash
git pull upstream ente
```

Proceed to the next section to start development with the `dts code` workflow.
