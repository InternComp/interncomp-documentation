# Issues

Q -> Docker isn't running, getting the following error:
```bash
ERROR: permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Head "http://%2Fvar%2Frun%2Fdocker.sock/_ping": dial unix /var/run/docker.sock: connect: permission denied
```

Ans -> Run the following code to fix this:
```bash
sudo addgroup --system docker
sudo adduser $USER docker
newgrp docker
# And something needs to be done so $USER always runs in group `docker` on the `Ubuntu` WSL
sudo chown root:docker /var/run/docker.sock
sudo chmod g+w /var/run/docker.sock
```

Link: [https://github.com/rancher-sandbox/rancher-desktop/issues/1156#issuecomment-1017042882](https://github.com/rancher-sandbox/rancher-desktop/issues/1156#issuecomment-1017042882)


