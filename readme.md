# Docker Template for Display Mounting

### Explaination

This repo gives a minimal template for convenient software development with Docker. *Important*: for display mounting, the `/tmp/.X11-unix` directory must exist, i.e. it has to be executed on Ubuntu! 
Volumes are set, s.t. the host machine display is mounted, i.e. plots etc executed in the container are displayed.
Consider using the [Remote Explorer](https://marketplace.visualstudio.com/items?itemName=ms-vscode.remote-explorer) VS Code extension, to open VS Code directly inside the container.

### Folder structure

    .
    ├── docker_launch_files     # Files to launch the container
    │   ├── Dockerfile          # Setup for the image
    │   └── docker-compose.yml  # Setup for the container
    └── docker volume           # Files that are simultaneously accessed by host and container
        └── plot.py             # example that uses numpy and matplotlib

### Compile

Before building the container, run

    xhost +local:docker

to enable display mounting. Then run the setup with 

    docker-compose run --rm example_image

inside the `docker_launch_files` dir.

