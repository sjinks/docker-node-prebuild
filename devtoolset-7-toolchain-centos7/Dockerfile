FROM centos/devtoolset-7-toolchain-centos7
USER root
RUN yum install -y rh-nodejs14-nodejs && yum clean all -y
COPY entrypoint.sh /entrypoint.sh
WORKDIR /usr/src/app
VOLUME /usr/src/app
ENTRYPOINT ["/entrypoint.sh"]
