# Installation Guide for Docker

## Installing in WSL (Windows Subsystem for Linux)

Assuming that you have Ubuntu 22 LTS installed as WSL distro, and this is WSL2

Run the following code:

Update packages:
```bash
sudo apt update
sudo apt upgrade
```

Remove any residue (this should fail ideally):
```bash
sudo apt remove docker docker-engine docker.io containerd runc
```

Install dependencies:
```bash
sudo apt install --no-install-recommends apt-transport-https ca-certificates curl gnupg2
```

Temporarily set some OS-specific variables:
```bash
. /etc/os-release
```

Make sure that `apt` will trust the repo:
```bash
curl -fsSL https://download.docker.com/linux/${ID}/gpg | sudo tee /etc/apt/trusted.gpg.d/docker.asc
```

Update repo:
```bash
echo "deb [arch=amd64] https://download.docker.com/linux/${ID} ${VERSION_CODENAME} stable" | sudo tee /etc/apt/sources.list.d/docker.list
sudo apt update
```

Install Docker:
```bash
sudo apt install docker-ce docker-ce-cli containerd.io
```

Add user to docker group:
```bash
sudo usermod -aG docker $USER
```


Guide used: [https://dev.to/bowmanjd/install-docker-on-windows-wsl-without-docker-desktop-34m9](https://dev.to/bowmanjd/install-docker-on-windows-wsl-without-docker-desktop-34m9)