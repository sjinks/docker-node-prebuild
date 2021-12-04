FROM centos/devtoolset-7-toolchain-centos7
USER root
RUN \
    curl -LfSs https://rpm.nodesource.com/setup_lts.x | bash - && \
    yum install -y nodejs && \
    yum clean all -y

WORKDIR /usr/src/app
VOLUME /usr/src/app
