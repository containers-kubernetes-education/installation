# Installation

The purpose of this repository is to provide some instruction of all the prerequisites that will be required for the "code along" during the two sessions. There are some addtional components that might be useful to download, but not strictly required.

## Session 1

The main requirement for this session is some form of container runtime. There are a number available (Docker, Podman, Containerd, etc) but for these sessions I will be concentrating on Podman, due to the freely available license even within businesses. Podman and Docker actually follow very closely in terms of commands and structure, so if you already have Docker installed and would prefer to use it, it will be very simple to switch between the two.

### Podman
The instruction of how to install Podman can be found here: https://podman.io/getting-started/installation

If you are using a Mac, it should be as simple as:
```
// install the podman CLI
brew install podman

// Define a podman VM called machine
podman machine init

// Start up the container vm
podman machine start
```

Note that if you are using a Windows machine, you will need to install into WSL2, and use something like a Ubuntu distro. (https://www.microsoft.com/store/productId/9MTTCL66CPXJ). In my testing on my Windows PC, I also had to install qemu into the ubuntu image to get podman working correctly (`sudo apt-get install qemu-system`)

Make sure you can bring up a container using this command (We will revisit what this is exactly doing in the session):
```
// This will ask which location to download from, choose docker.io 
podman run -p 8765:80 nginxdemos/hello
```
This leaves a process running on the terminal, but goto http://localhost:8765/ and make sure you can see NGINX page. If not, contact me (James Davies on Slack) and I can help you resolve this.

### Docker (Instead of Podman)
If you have permission to use docker and you would rather use that. You can download Docker-Desktop here: https://www.docker.com/products/docker-desktop/

Please do the same check above to make sure the install is working:
``` 
docker run -p 8765:80 nginxdemos/hello
```

### Golang (Optional)
The demo I will be using will be written in Golang, and if you wish to edit or work with the demo after the session you will need to install go, and setup your go path. You can find the go binaries here: https://go.dev/dl/. However I do show in the education how to compile the application using a contianer without having golang installed in the session

I will also be providing compiled binaries in the demo repositories so you can still run the demo with golang installed, but you wont be able to rebuild them without.

## Session 2

TBD
