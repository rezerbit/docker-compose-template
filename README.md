# Docker Compose Template

## Install Docker

```
brew install docker docker-compose docker-machine xhyve docker-machine-driver-xhyve
```

### Set permissions

```
sudo chown root:wheel $(brew --prefix)/opt/docker-machine-driver-xhyve/bin/docker-machine-driver-xhyve
sudo chmod u+s $(brew --prefix)/opt/docker-machine-driver-xhyve/bin/docker-machine-driver-xhyve
```

### Create docker machine

```
docker-machine create default --driver xhyve --xhyve-experimental-nfs-share
```

This command creates a docker machine, using the xhyve driver.
`--xhyve-experimental-nfs-share` – this flag allows you to share each file in your `/Users/` folder between Mac OS and Linux run on Docker.

```
eval $(docker-machine env default)
```

It registers a few variables, which allow you to use default docker machine without typing “default” each time.

Add this command to your `.bashrc` or `.zshrc` file.
