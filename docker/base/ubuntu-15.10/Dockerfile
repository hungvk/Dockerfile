#+++++++++++++++++++++++++++++++++++++++
# Dockerfile for webdevops/base:ubuntu-15.10
#    -- automatically generated  --
#+++++++++++++++++++++++++++++++++++++++

FROM webdevops/bootstrap:ubuntu-15.10

ENV DOCKER_CONF_HOME=/opt/docker/ \
    LOG_STDOUT="" \
    LOG_STDERR=""

COPY conf/ /opt/docker/

# Install services
RUN chmod +x /opt/docker/bin/* \
    && /usr/local/bin/apt-install \
        supervisor \
        wget \
        curl \
        net-tools \
    && chmod +s /sbin/gosu \
    && /opt/docker/bin/bootstrap.sh \
    && docker-image-cleanup

ENTRYPOINT ["/entrypoint"]
CMD ["supervisord"]
