# Overview

This is just a place where  I can experiment a bit with mkdocs 

## docker

currently using a docker image [polinux/mkdocs](https://hub.docker.com/r/polinux/mkdocs) to develop this

```bash
docker pull polinux/mkdocs:1.1.2
``` 

with this image created the container `mkdocs_learn` as follows

```bash
docker run \
    --name mkdocs_learn \
    -p 9090:9000 \
    -e "ADD_MODULES=mkdocs-bootstrap mkdocs-gitbook mkdocs-bootstrap4" \
    -e "LIVE_RELOAD_SUPPORT=true" \
    -e "FAST_MODE=true" \
    -e "DOCS_DIRECTORY=/learn-mkdocs" \
    -e "AUTO_UPDATE=true" \
    -e "UPDATE_INTERVAL=1" \
    -e "DEV_ADDR=0.0.0.0:9000" \
    -v ${HOME}/.ssh/id_github_wsl2_wk:/root/.ssh/id_rsa \
    -v ${HOME}/github/learn-mkdocs:/learn-mkdocs \
    polinux/mkdocs:1.1.2
```

to connect to the website created by mkdocs type `http://localhost:9090` into your browser of choice


