# nginx-container
[reference link](https://docs.docker.com/engine/install/ubuntu/)
1) create a linuxVM 
2) login to the VM 
3) Run below commands:

    ```bash
    sudo apt-get update

    // Install packages to allow apt to use the repository over HTTPS

    sudo apt-get install \
        ca-certificates \
        curl \
        gnupg \
        lsb-release
    // Add Docker official GPG key

    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
    // Setup a stable repository

    echo \
    "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu \
    $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

    // Update the package index

    sudo apt-get update

    // Install docker and containerd

    sudo apt-get install docker-ce docker-ce-cli containerd.io
    // create a container and lunch

    sudo docker run --name mynginx -p 80:80 -d nginx
    ```
To see the images you have 
```bash
sudo docker images 
```
To check the container you have
```bash
sudo docker ps
```
Now add an inbound rule in your VM (service as HTTP)
Copy the public IP of your VM and run in a different window. \
Hurrah !!!! \
### *You successfully launched a niinx in a docker Container.*