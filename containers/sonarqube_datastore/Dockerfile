FROM busybox:latest

# sonarqube
# add plugins
WORKDIR /opt/sonarqube/extensions/plugins
RUN set -x \
    && wget http://nexus.talanlabs.com/content/groups/public_release/com/synaptix/sonar-gitlab-plugin/1.7.0/sonar-gitlab-plugin-1.7.0.jar \
    && wget http://nexus.talanlabs.com/content/groups/public_release/com/synaptix/sonar-auth-gitlab-plugin/1.0.0/sonar-auth-gitlab-plugin-1.0.0.jar
VOLUME /opt/sonarqube/conf
VOLUME /opt/sonarqube/data
VOLUME /opt/sonarqube/extensions
VOLUME /opt/sonarqube/lib/bundled-plugins
# postgresql
VOLUME /var/lib/postgresql
VOLUME /var/lib/postgresql/data

CMD bin/sh
