## :octocat: Intro

Hello World! flask application | DevOps Study Case

```
git clone https://github.com/<project-url>>
```

## Installation dependencies

Needs to install [Vagrant](https://www.vagrantup.com/downloads) and [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

## Running the server in development

|       Vagrant CLI CMD        |              Function              |                     Use Case                      |
|:----------------------------:|:----------------------------------:|:-------------------------------------------------:|
|         `vagrant up`         |    **provision** dev env on vm     |      🟢 installation of env for a first time      |
|        `vagrant ssh`         |         **ssh** to the vm          |      🟡 making some changes on the vm itself      |
|       `vagrant reload`       |          **reloading** vm          |     🟡 in case of changing vagrant box config     |
|     `vagrant provision`      |       **re-provisioning** vm       |    🟡 in case of changing provisioning config     |
| `vagrant reload --provision` | **reload** and **re-provision** vm | 🟡 in case of changing vm config and provisioning |
|        `vagrant halt`        |          **halt** the vm           |      🟡 in case of stopping the vm temporary      |
|       `vagrant resume`       |         **resume** the vm          |          🟡 for resuming the stopped vm           |
|      `vagrant destroy`       |       **destroying** the vm        |          🔴 deleting the vagrant box vm           |

For more info, kindly visit [vagrant](https://www.vagrantup.com/docs/cli) documentation.

## How `vagrant up` work under-hood ❓❗

1. Provision Vagrant Box on VirtualBox based on ubuntu/bionic64.
2. Customize the amount of memory on the VM: memory = 2048, cpus = 2 .
3. Port-forward guest: **30010**, host: **30010**.
4. Run bootstrap script installing some dependencies: deps packages, nginx, docker, minikube, kubectl, ansible.
5. Run `docker build` to build docker image under name tag **devops-task:latest**.
6. Finally, run ansible playbook to provision minikube cluster with the needed kubernetes infrastructure inside `la3eb` namespace.

## Finally 🚀 !!

You can access the application on you local browser on `localhost:30010`, `127.0.0.1:30010` or `0.0.0.0:30010`
