FROM rockylinux/rockylinux:8.10-ubi
LABEL   com.bmeme.project.family='RockyLinux Docker Image' \
        com.bmeme.project.version='8.10-2.13' \
        com.bmeme.maintainer.1='Daniele Piaggesi <daniele.piaggesi@bmeme.com>' \
        com.bmeme.maintainer.2='Roberto Mariani <roberto.mariani@bmeme.com>' \
        com.bmeme.refreshedat='2025-02-06'

ENV LANG C.UTF-8
ENV LC_ALL C.UTF-8
env ANSIBLE_CORE_VERSION=2.13

RUN (cd /lib/systemd/system/sysinit.target.wants/; for i in *; do [ $i == systemd-tmpfiles-setup.service ] || rm -f $i; done); \
    rm -f /lib/systemd/system/multi-user.target.wants/*;\
    rm -f /etc/systemd/system/*.wants/*;\
    rm -f /lib/systemd/system/local-fs.target.wants/*; \
    rm -f /lib/systemd/system/sockets.target.wants/*udev*; \
    rm -f /lib/systemd/system/sockets.target.wants/*initctl*; \
    rm -f /lib/systemd/system/basic.target.wants/*;\
    rm -f /lib/systemd/system/anaconda.target.wants/*;

# Install requirements.
RUN dnf makecache \
    && dnf -y install \
        iproute \
        initscripts \
        sudo \
        which \
        python3 \
        python3-libs \
        python3-pip \
    && dnf clean all

# Upgrade Pip, install and configure Ansible.
RUN python3 -m pip install --upgrade pip; \
    python3 -m pip install --no-cache-dir ansible-core==${ANSIBLE_CORE_VERSION}; \
    sed -i -e 's/^\(Defaults\s*requiretty\)/#--- \1/'  /etc/sudoers; \
    mkdir -p /etc/ansible; \
    echo -e '[local]\nlocalhost ansible_connection=local' > /etc/ansible/hosts

VOLUME ["/sys/fs/cgroup"]
CMD ["/usr/lib/systemd/systemd"]