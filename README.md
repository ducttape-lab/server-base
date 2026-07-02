Base image for internal use lab (bootable) container applications
=================================================================


### Virtual Machine (cloud)
Use [`ducttape`](https://github.com/ducttape-infra/ducttape/) to `pull` the image and start

```sh
$ ducttape pull ghcr.io/ducttape-lab/server-base-cloud
$ dutctape start ghcr.io/ducttape-lab/server-base-cloud -n server`
```


### Container
You can use Podman or Nerdctl
```sh
$ podman run --rm -it --name server ghcr.io/ducttape-lab/server-base
```


### Virtual Machine (bootc)

```shell
$ wget https://github.com/ducttape-lab/server-base/releases/download/latest/disk.qcow2 \
     -O base.qcow2
$ sudo virt-install \
    --name base --os-variant fedora-eln \
    --cpu host --vcpus 4 --memory 4096 \
    --import --disk ./base.qcow2,format=qcow2
```

which allows you to use bootc `ghcr.io/ducttape-lab/server-base-bootc`



#### Update
To update the base or application, you can use the `bootc update`-command.

```shell
$ ssh admin@<ip>
$ sudo bootc update
```

