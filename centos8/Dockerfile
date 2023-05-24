FROM centos:8
RUN \
    curl -fsSL https://rpm.nodesource.com/setup_lts.x | bash - && \
    sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-* && \
    sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-* && \
    yum install -y nodejs gcc-c++ make python3 && \
    yum clean all -y

WORKDIR /usr/src/app
VOLUME /usr/src/app
