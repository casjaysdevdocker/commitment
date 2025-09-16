## 👋 Welcome to commitment_temp 🚀  

commitment_temp README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update commitment_temp
```
  
## Install and run container
  
```shell
dockerHome="/var/lib/srv/$USER/docker/casjaysdevdocker/commitment_temp/commitment_temp/latest/rootfs"
mkdir -p "/var/lib/srv/$USER/docker/commitment_temp/rootfs"
git clone "https://github.com/dockermgr/commitment_temp" "$HOME/.local/share/CasjaysDev/dockermgr/commitment_temp"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/commitment_temp/rootfs/." "$dockerHome/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-commitment_temp-latest \
--hostname commitment_temp \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$dockerHome/data:/data:z" \
-v "$dockerHome/config:/config:z" \
-p 80:80 \
casjaysdevdocker/commitment_temp:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/commitment_temp
    container_name: casjaysdevdocker-commitment_temp
    environment:
      - TZ=America/New_York
      - HOSTNAME=commitment_temp
    volumes:
      - "/var/lib/srv/$USER/docker/casjaysdevdocker/commitment_temp/commitment_temp/latest/rootfs/data:/data:z"
      - "/var/lib/srv/$USER/docker/casjaysdevdocker/commitment_temp/commitment_temp/latest/rootfs/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/commitment_temp
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/commitment_temp" "$HOME/Projects/github/casjaysdevdocker/commitment_temp"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/commitment_temp"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
