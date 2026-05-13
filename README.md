## 👋 Welcome to commitment 🚀  

commitment README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update commitment
```
  
## Install and run container
  
```shell
dockerHome="/var/lib/srv/$USER/docker/casjaysdevdocker/commitment/commitment/latest/rootfs"
mkdir -p "/var/lib/srv/$USER/docker/commitment/rootfs"
git clone "https://github.com/dockermgr/commitment" "$HOME/.local/share/CasjaysDev/dockermgr/commitment"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/commitment/rootfs/." "$dockerHome/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-commitment-latest \
--hostname commitment \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$dockerHome/data:/data:z" \
-v "$dockerHome/config:/config:z" \
-p 80:80 \
casjaysdevdocker/commitment:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/commitment
    container_name: casjaysdevdocker-commitment
    environment:
      - TZ=America/New_York
      - HOSTNAME=commitment
    volumes:
      - "/var/lib/srv/$USER/docker/casjaysdevdocker/commitment/commitment/latest/rootfs/data:/data:z"
      - "/var/lib/srv/$USER/docker/casjaysdevdocker/commitment/commitment/latest/rootfs/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/commitment
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/commitment" "$HOME/Projects/github/casjaysdevdocker/commitment"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/commitment"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
