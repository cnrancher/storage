FROM ceph/daemon-base:v3.1.0-stable-3.1-jewel-ubuntu-16.04-x86_64
RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y jq curl kmod && \
    DEBIAN_FRONTEND=noninteractive apt-get autoremove -y && \
    DEBIAN_FRONTEND=noninteractive apt-get clean && \
    rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*
COPY storage common/* rbd/rancher-rbd /usr/bin/
CMD ["start.sh", "storage", "--driver-name", "rancher-rbd"]
