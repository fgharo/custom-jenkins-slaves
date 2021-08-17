# If used with a Openshift BuildConfig of strategy Docker From gets replaced from one specificed in buildconfig.
FROM registry.redhat.io/openshift4/ose-jenkins-agent-base

MAINTAINER Frank Haro <fharo@redhat.com>

USER root

# Install Skopeo
RUN curl -s "https://raw.githubusercontent.com/kubernetes-sigs/kustomize/master/hack/install_kustomize.sh" | bash
RUN mv kustomize /usr/bin

RUN chown -R 1001:0 $HOME && \
    chmod -R g+rw $HOME

USER 1001
