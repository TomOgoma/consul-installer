# Consul Installer #

An auto-installer of consul by [Hashi Corp](https://www.consul.io) as a service in linux systems


## Install ##

Currently only systemd is supported

First [download consul](https://www.consul.io/downloads.html).

```
$ git clone https://github.com/tomogoma/consul-installer
$ cd consul-installer
$ ./systemdInstaller.sh /path/to/downloaded/consul.zip
```


## Install outcome ##


Start

`$ systemctl start consul.service`

Stop

`$ systemctl stop consul.service`

Check status

`$ systemctl status consul.service`


Install Directories

The consul binary is installed into
`/usr/local/bin/consul`

A systemd service unit file is created at
`/etc/systemd/system/consul.service`

## Uninstall ##

`$ cd /path/to/consul-installer`

`$ ./systemdUninstaller.sh`


## Configure a dependent systemd service ##

If your service depends on consul, in the service’s unit file add the following lines:


```
[Unit]

...

After=consul.service

Requires=consul.service

...
```
