FROM registry.redhat.io/openshift3/jenkins-agent-maven-35-rhel7:v3.11

MAINTAINER Frank Haro <fharo@redhat.com>

ENV MAVEN_VERSION=3.5

# Install Skopeo
RUN yum repolist > /dev/null && \
    yum clean all && \
    INSTALL_PKGS="skopeo" && \
    yum install -y --enablerepo=rhel-7-server-extras-rpms --setopt=tsflags=nodocs $INSTALL_PKGS && \
    rpm -V $INSTALL_PKGS && \
    yum clean all

RUN chown -R 1001:0 $HOME && \
    chmod -R g+rw $HOME


USER 1001
