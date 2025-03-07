# HogWarp - Linux Server Installation


## Install Prerequisites

Open Terminal and type:

> **sudo apt install dotnet-sdk-8.0**

> **sudo apt install dotnet-runtime-8.0**

**_We need docker_**, to install it, go to

https://www.digitalocean.com/community/tutorials/how-to-install-and-use-docker-on-ubuntu-22-04


## Install HogWarp 
To get server files, we need to download docker image.

Open Terminal and type:

1.	Download Docker image:

  	    docker pull tiltedphoques/hogwarp
2.	Run docker image in background:

        docker run -d tiltedphoques/hogwarp
3.	Get ID of running container:

        docker container list
  	![image](https://github.com/user-attachments/assets/89415afb-0357-42bb-bae2-b198a466e659)

5.	Export docker as .tar with the ID of container.
   **_(change Container_ID with your container ID)_**
   
  	    docker export Container_ID -o hogwarp.tar
   > **Example: docker export 83ab9e41a8ef -o hogwarp.tar**
   
5.	Extract .tar:

        tar -xvf hogwarp.tar

6.	Create another directory and Move “app” folder to the newly created directory

        mkdir ../HogWarts 
        mv app/ ../HogWarts
        cd ../HogWarts/app
7.	Copy your API key to config.json

        nano config.json
  	![image](https://github.com/user-attachments/assets/0b72f6b1-f821-4ada-a235-cb466cb5ed75)

9.	Run server:
   
        ./Server.Loader
   ![image](https://github.com/user-attachments/assets/6367bc71-e724-41fc-93a7-f618ad1e669b)

