FROM centos:8@sha256:a27fd8080b517143cbbbab9dfb7c8571c40d67d534bbdee55bd6c473f432b177
RUN \
    sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-* && \
    sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-* && \
    curl -fsSL https://rpm.nodesource.com/setup_lts.x | bash - && \
    yum install -y nodejs gcc-c++ make python3 && \
    yum clean all -y

WORKDIR /usr/src/app
VOLUME /usr/src/app
