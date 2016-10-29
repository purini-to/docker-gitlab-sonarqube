FROM busybox:latest

# redis
VOLUME /var/lib/redis:Z
# postgresql
VOLUME /var/lib/postgresql:Z
# gitlab
VOLUME /home/git/data:Z
# gitlab-runner
VOLUME /etc/gitlab-runner:Z

CMD /bin/sh
