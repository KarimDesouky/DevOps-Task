## Intro

Hello World! flask application | DevOps Study Case

```
git clone https://github.com/<project-url>>
```

## Installation dependencies

Needs to install [Vagrant](https://www.vagrantup.com/downloads) and [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

## Running the server in development

|       Vagrant CLI CMD        |              Function              |                                   Use Case                                   |
|:----------------------------:|:----------------------------------:|:----------------------------------------------------------------------------:|
|         `vagrant up`         |    **provision** dev env on vm     |      ![#f03c15]()<font color="green"> installation of env for a first time </font>       |
|        `vagrant ssh`         |         **ssh** to the vm          |      <font color="yellow"> making some changes on the vm itself </font>      |
|       `vagrant reload`       |          **reloading** vm          |     <font color="yellow"> in case of changing vagrant box config </font>     |
|     `vagrant provision`      |       **re-provisioning** vm       |    <font color="yellow"> in case of changing provisioning config </font>     |
| `vagrant reload --provision` | **reload** and **re-provision** vm | <font color="yellow"> in case of changing vm config and provisioning </font> |
|        `vagrant halt`        |          **halt** the vm           |      <font color="yellow"> in case of stopping the vm temporary </font>      |
|       `vagrant resume`       |         **resume** the vm          |          <font color="yellow"> for resuming the stopped vm </font>           |
|      `vagrant destroy`       |       **destroying** the vm        |            <font color="red"> deleting the vagrant box vm </font>            |

For more info, kindly visit [vagrant](https://www.vagrantup.com/docs/cli) documentation.

## How `vagrant up` work under-hood ?!

1. Provision Vagrant Box on VirtualBox based on ubuntu/bionic64.
2. Customize the amount of memory on the VM: memory = 2048, cpus = 2 .
3. Port-forward guest: **30010**, host: **30010**.
4. Run bootstrap script installing some dependencies: deps packages, nginx, docker, minikube, kubectl, ansible.
5. Run `docker build` to build docker image under name tag **devops-task:latest**.
6. Finally, run ansible playbook to provision minikube cluster with the needed kubernetes infrastructure inside `la3eb` namespace.

## Finally !!

You can access the application on you local browser on `localhost:30010`, `127.0.0.1:30010` or `0.0.0.0:30010`

 ![#f03c15](https://via.placeholder.com/15/f03c15/000000?text=+)
- ![#c5f015](https://via.placeholder.com/15/c5f015/000000?text=+) `#c5f015`
- ![#1589F0](https://via.placeholder.com/15/1589F0/000000?text=+) `#1589F0`
