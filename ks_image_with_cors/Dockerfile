FROM registry.redhat.io/rhpam-7/rhpam-kieserver-rhel8:7.5.0

ADD ./contrib/standalone-openshift.xml /opt/eap/standalone/configuration/standalone-openshift.xml
USER root
RUN chown jboss:root /opt/eap/standalone/configuration/standalone-openshift.xml && chmod 664 /opt/eap/standalone/configuration/standalone-openshift.xml
USER jboss
