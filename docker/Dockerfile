FROM registry.access.redhat.com/ubi9/ubi-minimal
RUN microdnf update -y && microdnf install bind-utils nmap-ncat libaio --noplugins --setopt=install_weak_deps=0 --nodocs -y && microdnf clean all
USER root
RUN curl -O https://download.oracle.com/otn_software/linux/instantclient/2112000/el9/oracle-instantclient-basic-21.12.0.0.0-1.el9.x86_64.rpm && \
    curl -O https://download.oracle.com/otn_software/linux/instantclient/2112000/el9/oracle-instantclient-sqlplus-21.12.0.0.0-1.el9.x86_64.rpm
RUN rpm -i oracle-instant*.rpm && rm -rf oracle-instant*.rpm
ENTRYPOINT ["/bin/bash"]
