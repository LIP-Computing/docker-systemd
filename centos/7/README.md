# centos-systemd:7
Docker image with ansible based on the [official CentOS Docker Image](https://registry.hub.docker.com/_/centos/)

## Installed packages

Base:

- [CentOS (7) minimal](https://hub.docker.com/_/centos/)

Image specific:
- centos-systemd

## Usage

### Build image
```bash
$ docker build --rm -t local/centos_systemclt .
```

### Run container with systemd support

The container is mounted in the host cgroup.

```bash
$ docker run -d --cap-add=SYS_ADMIN --privileged -v /tmp/$(mktemp -d):/run -v /sys/fs/cgroup:/sys/fs/cgroup:ro local/centos-systemd
645c6aaf886c9a05d40c10ac5275ae24ee58b3bca636041d43b1bc423cd48921
```

### Execute commands on the already created container

```bash
$ docker exec -it 645c6aaf886c9a05d40c10ac5275ae24ee58b3bca636041d43b1bc423cd48921 '/bin/bash'
```
