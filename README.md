Base image for internal use Homelab (bootable) container applications
=====================================================================


### Virtual Machine

```shell
$ wget https://github.com/ducttape-lab/server-base/releases/download/latest/disk.qcow2 \
     -O base.qcow2
$ sudo virt-install \
    --name base --os-variant fedora-eln \
    --cpu host --vcpus 4 --memory 4096 \
    --import --disk ./base.qcow2,format=qcow2
```


#### Update
To update the base or application, you can use the `bootc update`-command.

```shell
$ ssh admin@<ip>
$ sudo bootc update
```

