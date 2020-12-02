# Provision Kubernetes cluster with lxc containers

####* This repo contains the necessary files to provision kuberenets cluster I will try step by step approach for this.

I am using Neo User (Ubuntu 20-04) for this purpose. First install lxd runtime as below.

* `sudo snap install lxd`
* `sudo snap start lxd`
* `sudo snap enale lxd`


Initialize the container runtime

* `lxd init`


#### Provide default option for all the questions but make sure you choose storage backend as dir.

`Name of the storage backend to use (btrfs, dir, lvm) [default=btrfs]: dir`


####

#### First create profile for k8s cluster

`lxc profile create k8s`

`lxc profile edit k8s`

Copy the contents from lxd-profile into k8s profile.

#### Time to create a new cluster

Launch the containers, i will choose centos 7 for this task

`lxc launch images:centos/7 k8smaster --profile k8s`

`lxc launch images:centos/7 k8sworker --profile k8s`

`lxc launch images:centos/7 k8sworker --profile k8s`
