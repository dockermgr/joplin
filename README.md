## 👋 Welcome to joplin 🚀  

joplin README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update joplin
```
  
## Install and run container
  
```shell
mkdir -p "$HOME/.local/share/srv/docker/joplin/rootfs"
git clone "https://github.com/dockermgr/joplin" "$HOME/.local/share/CasjaysDev/dockermgr/joplin"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/joplin/rootfs/." "$HOME/.local/share/srv/docker/joplin/rootfs/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-joplin \
--hostname joplin \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-joplin/rootfs/data:/data:z" \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-joplin/rootfs/config:/config:z" \
-p 80:80 \
casjaysdevdocker/joplin:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/joplin
    container_name: casjaysdevdocker-joplin
    environment:
      - TZ=America/New_York
      - HOSTNAME=joplin
    volumes:
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-joplin/rootfs/data:/data:z"
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-joplin/rootfs/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/joplin
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/joplin" "$HOME/Projects/github/casjaysdevdocker/joplin"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/joplin"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
