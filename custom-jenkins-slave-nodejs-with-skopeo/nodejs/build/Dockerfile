# If used with a Openshift BuildConfig of strategy Docker From gets replaced from one specificed in buildconfig.
FROM registry.redhat.io/openshift4/ose-jenkins-agent-nodejs-12-rhel8

MAINTAINER Frank Haro <fharo@redhat.com>

ARG INSTALL_PKGS="skopeo"
USER root

# Install Skopeo
RUN yum repolist > /dev/null 
RUN yum clean all
# --enablerepo=rhel-7-server-extras-rpms 
# Error: Unknown repo: 'rhel-7-server-extras-rpms'
RUN yum install -y --setopt=tsflags=nodocs $INSTALL_PKGS
RUN rpm -V $INSTALL_PKGS
RUN yum clean all
RUN skopeo -v

RUN chown -R 1001:0 $HOME && \
    chmod -R g+rw $HOME


USER 1001
