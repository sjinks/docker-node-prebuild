FROM centos:7

RUN \
    curl -LfSs https://rpm.nodesource.com/setup_lts.x | bash - && \
    yum install -y nodejs gcc-c++ make python3 && \
    yum clean all -y

WORKDIR /usr/src/app
VOLUME /usr/src/app
