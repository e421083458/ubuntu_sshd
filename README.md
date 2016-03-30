# Ubuntu_sshd

Dockerized SSH service, built on top of [official Ubuntu](https://registry.hub.docker.com/_/ubuntu/) images.

## Image tags

- rastasheep/ubuntu-sshd:14.04 (trusty)

## Installed packages

Base:

- [trusty (14.04) minimal](http://packages.ubuntu.com/trusty/ubuntu-minimal)

Image specific:
- [openssh-server](https://help.ubuntu.com/community/SSH/OpenSSH/Configuring)

Config:

  - `PermitRootLogin yes`
  - `UsePAM no`
  - exposed port 22
  - default command: `/usr/sbin/sshd -D`
  - root password: `root`

## Run example

```bash
docker build -t e421083458/ubuntu14.04_sshd .
docker run -d -p 3022:22 --name test_sshd_3022 ubuntu14.04_sshd
//optional --restart=always

ssh root@127.0.0.1 -p 3022
```

## Issues

If you run into any problems with this image, please check (and potentially file new) issues on the [rastasheep/ubuntu-sshd](https://github.com/rastasheep/ubuntu-sshd/issues) repo, which is the source for this image.

