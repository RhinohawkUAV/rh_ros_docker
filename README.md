We are planning to standardize development tools across all developers by using containers. This ensures that everything will run as-is once we integrate all the different parts of the system.

This repository only has Docker build files. The build files will be used to build container images on your development box. Contaimer images once created are not portable across different CPU platforms but images built with the same build file will have the indentical software available. It should be noted that this does not translate to specialized hardware items such as systems with GPUs. We will cross that bridge as we get closer to the goal line.

## Usage:
To run the build command and run the containers you will need to have Docker installed on you computer. The scripts provided assume that you are on a Linux or OSX system. You can probably run the scripts by modifying the shell scripts to run as batch scripts. 

  1. Clone the repository to your local system. (git clone ...)
  2. Open terminal and CD to the required directory. (See section below)
  3. run sh ./build.sh
  
This will take a few minutes to complete. If you need to clean the image and start fresh, run the ./clean_build.sh

Once the image is ready you can verify them by running.
>> docker images

To  start into the image and run a shell.
>> docker run -it rhinohawk/ros-base /bin/bash

To look at what containers are running.
>> docker ps

To stop a running container gracefully you will need the container ID. The previous command will get you that info.
>> docker stop <container-id>
  
To kill a running container
>> docker kill <container-id>

### Docker Images
There are several directories with differnet packages installed in each.

#### ros-base
Base image for all ros-based containers. This container is configured with the following packages
* Ubuntu 18.04
* ROS Medlodic-base

#### ros-navigation
<TBD>
  
#### ros-camera
<TBD>
  
#### ros-all
<TBD>






