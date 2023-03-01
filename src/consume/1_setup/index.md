# Step 1: Environment Setup

Before working through any Duckietown Learning Experience, you first need to set up your development environment.

```{important}
🚧 Complete the following setup steps carefully to prevent running into bugs later on. 🚧
```

### 0) Requirements

We assume in this manual that you have already set up your Duckietown development environment following the steps in the
[Environment Setup]() section of the Duckiebot operation manual.

### 1) Docker Configuration

After completing Duckietown development setup instructions, add your `docker.io` credentials to the Duckietown shell by running the following 
command,

    dts challenges config --docker-username <USERNAME> --docker-password <PASSWORD>

**NOTE:** these are the `<USERNAME>` and `<PASSWORD>` that you use to log in to DockerHub (hub.docker.io) when 
setting up Docker in the Duckiebot operation mmanual.

### 2) LX Installations

To install the LX specific tools, start by installing a new dependency,

    sudo apt install libnss3-tools

Then update your Duckietown shell and shell commands,

    pip3 install -U duckietown-shell

    dts update

### 3) SSL certificate

Next, set up your local SSL certificate needed to run the learning experience editor,

    dts setup mkcert

### 4) hello-world LX

We will be walking through the **hello-world** LX in following pages. Fork and clone the `duckietown-lx` repository to follow along and complete the tutorial activities. This will give you access to the full library of Duckietown Learning Experiences.

1) To store your own code, while also keeping the ability to pull updates from our version of this repo, create your own fork. Start by pressing "Fork" in the top right corner of [the duckietown-lx repository page on GitHub](https://github.com/duckietown/duckietown-lx). You will be able to create a new 
    fork that will appear in your GitHub repository list as: 

        `<your_username>/duckietown-lx`
    
    Then clone your new repository, replacing your GitHub username in the command below,
    
        git clone -b mooc2022 git@github.com:<your_username>/duckietown-lx

2) Now we will configure the Duckietown version of this repository as the upstream repository to sync with your fork. List the current remote repository for your fork,
    
        git remote -v
    
    Specify a new remote upstream repository,
    
        git remote add upstream https://github.com/duckietown/duckietown-lx
    
    Confirm that the new upstream repository was added to the list,
    
        git remote -v
    
    You can now push your work to your own repository using the standard GitHub workflow, and the beginning of every 
    learning experience will prompt you to pull from the upstream repository - updating your exercises to the latest Duckietown 
    version,
    
        git pull upstream mooc2022

And that's it! You are ready to move on to the next section and start your development journey with 
the `dts code` workflow.