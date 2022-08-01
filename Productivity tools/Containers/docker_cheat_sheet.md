# Docker cheat sheet
## Install Docker
- On ubuntu
```bash
sudo apt-get remove docker docker.io containerd runc -y
sudo apt-get install ca-certificates curl gnupg lsb-release wget -y
sudo mkdir -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
echo   "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-compose-plugin -y
sudo apt-get update
sudo usermod -aG docker ${USER}
```

## Containers
### Run a container
`docker run --name <custome_name> -d <official_image>:<tag>`

### Monitor docker containers
`docker stats` *(performances focused)* or `docker ps` *(informations focused)*

### Access container's bash
`docker exec -it <containers_Id> bash`

### Stop a container
`docker stop <containers_Id>`

### Get the container IP on the bridge docker default network
`docker inspect <containers_name> | grep IPAddress`

## Images
### Pull an image
`docker pull <official_image>:<tag>`

### List docker images
`docker image ls`
