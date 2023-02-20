# Step 1: Environment Setup

Before working through any Duckietown Learning Experience, you first need to set up your development environment.

### Requirements

We assume in this manual that you have already set up your Duckietown development environment following the steps in the
[Environment Setup]() section of the Duckiebot operation manual.

### Docker Configuration

After completing those instructions, add your `docker.io` credentials to the Duckietown shell by running the following 
command,

    dts challenges config --docker-username <USERNAME> --docker-password <PASSWORD>

**NOTE:** these are the `<USERNAME>` and `<PASSWORD>` that you use to log in to DockerHub (hub.docker.io) when 
setting up Docker in the Duckiebot operation mmanual.

### LX Installations

To install the LX specific tools, start by installing a new dependency,

    sudo apt install libnss3-tools

Then update your Duckietown shell and shell commands,

    pip3 install -U duckietown-shell

    dts update

### SSL certificate

Next, set up your local SSL certificate needed to run the learning experience editor,

    dts setup mkcert

And that's it! You are ready to move on to the next section and start your journey toward becoming an expert user of 
the `dts code` workflow.