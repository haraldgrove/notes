#WSL2

Random steps that made the docker daemon start

```bash
DOCKER_DIR=/mnt/wsl/shared-docker
mkdir -pm o=,ug=rwx "$DOCKER_DIR"
chgrp docker "$DOCKER_DIR"
export DOCKER_HOST=unix:///mnt/wsl/shared-docker/docker.sock
sudo dockerd
```
