# Docker

If you wish, there is a development docker container ([docker hub](https://hub.docker.com/r/cognipilot/dream), [docker source](https://github.com/CogniPilot/docker)) for CogniPilot with Nvidia GPU support. If you use this option, do not run the native\_install script, as the packages are already installed.


## Dependencies

You must install the latest official docker.

* [Install Docker](https://docs.docker.com/engine/install/ubuntu/)

!!! tip

	Don't forget [Linux Post Install](https://docs.docker.com/engine/install/linux-postinstall/) 

## Clone Docker Repository

<span style="color:blue">On the Host</span>
```bash
mkdir -p ~/cognipilot
cd ~/cognipilot
git clone https://github.com/cognipilot/docker
cd  ~/cognipilot/docker
git submodule update --init --recursive
```

## Start the Docker Image

The dream start command, automatically pulls the [dream image](https://hub.docker.com/r/cognipilot/dream) from dockerhub, and starts the image.

<span style="color:blue">On the Host</span>
```bash
cd ~/cognipilot/docker/dream
./dream start
```

## Execute a Command on the Docker Image

This starts a shell within the container.

<span style="color:blue">On the Host</span>
```bash
./dream exec
```

If passed extra arguments will run those commands as well.

## Convenience Scripts (Docker Specific)


### unlock

This command executes the script [docs](https://github.com/CogniPilot/helmet/blob/398e99d98c1a9aabef663ad601d3ac5c141b54f2/install/resources/unlock).

* Unlocks GPG and SSH keys mounted in the docker image.

<span style="color:blue">Within the Container</span>
```bash
unlock
```

See the other non-docker specific scripts in the [main installation](../install.md#convenience-scripts)

## Build the Docker Image (For Advanced Users)

This process will take awhile. It is usually sufficient to use dream start instead, which will automatically pull the latest image from dockerhub.

<span style="color:blue">On the Host</span>
```bash
cd ~/cognipilot/docker/dream
./dream build
```
