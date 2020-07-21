FROM registry.redhat.io/rhpam-7/rhpam-businesscentral-rhel8:7.7.1

ADD ./contrib/rhpam-7.7.1-case-mgmt-showcase-eap7-deployable.zip /tmp/rhpam-7.7.1-case-mgmt-showcase-eap7-deployable.zip
ADD ./contrib/web.xml /tmp/web.xml

RUN pushd /tmp && unzip rhpam-7.7.1-case-mgmt-showcase-eap7-deployable.zip && chown -R jboss:root jboss-eap-7.2 && mv jboss-eap-7.2/standalone/deployments/rhpam-case-mgmt-showcase.war/ /opt/eap/standalone/deployments/rhpam-case-mgmt-showcase.war/ && mv jboss-eap-7.2/standalone/deployments/rhpam-case-mgmt-showcase.war.dodeploy /opt/eap/standalone/deployments/rhpam-case-mgmt-showcase.war.dodeploy && popd

USER root
RUN pushd /tmp && chown jboss:root web.xml && mv web.xml /opt/eap/standalone/deployments/rhpam-case-mgmt-showcase.war/WEB-INF/web.xml && popd

USER jboss
