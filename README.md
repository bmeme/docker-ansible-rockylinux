[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg)](https://GitHub.com/Naereen/StrapDown.js/graphs/commit-activity)
[![MIT license](https://img.shields.io/badge/License-MIT-blue.svg)](https://lbesson.mit-license.org/)

Rockylinux "Ansible Ready" Packaged by Bmeme
=========

Rockylinux "Ansible Ready" images based on [official Rocky Enterprise Software Foundation repository](https://hub.docker.com/r/rockylinux/rockylinux), currently used by Bmeme for its `molecule` tests during Ansible Role development.

## What is contained in the images
* ansible-core
* initscripts
* sudo
* which
* python3
* python3-libs
* python3-pip

## Supported tags and respective `Dockerfile` links
- `9.4-2.15`, `latest` [Dockerfile](https://github.com/bmeme/docker-ansible-rockylinux/blob/main/9/9.4/2.15/Dockerfile)
- `8.10-2.11` [Dockerfile](https://github.com/bmeme/docker-ansible-rockylinux/blob/main/8/8.10/2.11/Dockerfile)

## Old tags not more supported 
- `9.3-2.15`, `latest` [Dockerfile](https://github.com/bmeme/docker-ansible-rockylinux/blob/main/9/9.3/2.15/Dockerfile)
- `8.9-2.11` [Dockerfile](https://github.com/bmeme/docker-ansible-rockylinux/blob/main/8/8.9/2.11/Dockerfile)
- `8.8-2.11` [Dockerfile](https://github.com/bmeme/docker-ansible-rockylinux/blob/main/8/8.8/2.11/Dockerfile)
- `8.7-2.11` [Dockerfile](https://github.com/bmeme/docker-ansible-rockylinux/blob/main/8/8.9/2.11/Dockerfile)

This old images was based on the Docker official repo (https://hub.docker.com/_/rockylinux)

## Tag system
The tag of each image is composed by two values, separated by a `-`. 
The first one represents the Rockylinux version. The second one represents the
`ansible-core` version.

## Credits
This project is a contribution of [Bmeme :: The Digital Factory](http://www.bmeme.com).
This library is actually maintained by [Daniele Piaggesi](https://github.com/g0blin79) and
[Roberto Mariani](https://github.com/jean-louis).
Any other contribution will be really appreciated.