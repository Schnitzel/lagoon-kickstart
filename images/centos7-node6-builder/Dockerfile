ARG IMAGE_REPO
FROM ${IMAGE_REPO:-lagoon}/centos7-node6

### Installing GIT
RUN yum install -y https://centos7.iuscommunity.org/ius-release.rpm && \
    yum install -y git2u && \
    yum clean all

### Installing additional tools that might be used by node
RUN yum install -y \
                gcc gcc-c++ \
                file \
                openssl openssl-devel \
                libcurl-devel \
                && \
    yum clean all -y

### Use `docker-sleep.sh` as `CMD` which will cause a Container creates from this image to keep running without doing anything.
COPY docker-sleep.sh /usr/local/bin/docker-sleep
CMD ["/usr/local/bin/docker-sleep"]
