FROM quay.io/eduk8s/pkgs-k8s-tools:200731.043551.e3512b8 AS k8s-tools

FROM fedora:31

RUN HOME=/root && \
    INSTALL_PKGS=" \
        findutils \
        bind-utils \
        sudo \
    " && \
    dnf install -y --setopt=tsflags=nodocs $INSTALL_PKGS && \
    dnf clean -y --enablerepo='*' all && \
    sed -i.bak -e '1i auth requisite pam_deny.so' /etc/pam.d/su && \
    sed -i.bak -e 's/^%wheel/# %wheel/' /etc/sudoers && \
    useradd -u 1001 -g 0 -M -d /home/kubeuser kubeuser && \
    mkdir -p /home/kubeuser && \
    chown -R 1001:0 /home/kubeuser && \
    chmod -R g=u /home/kubeuser && \
    chmod g+w /etc/passwd && \
    chown 1001:0 /opt


COPY --from=k8s-tools --chown=1001:0 /opt/kubernetes/bin/kubectl@1.18 /usr/local/bin/kubectl
COPY --from=k8s-tools --chown=1001:0 /opt/kubernetes/bin/ytt /usr/local/bin/ytt
COPY --from=k8s-tools --chown=1001:0 /opt/kubernetes/bin/kapp /usr/local/bin/kapp

COPY  --chown=1001:0 . /home/kubeuser

WORKDIR /home/kubeuser
USER 1001