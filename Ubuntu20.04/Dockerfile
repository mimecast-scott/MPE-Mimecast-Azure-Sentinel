FROM ubuntu:20.04
LABEL maintainer="s@mck.la"
RUN mkdir -p /opt/mimecast/config \
    && apt-get update && apt-get install -y --no-install-recommends \
    python2 supervisor software-properties-common \
    && add-apt-repository ppa:deadsnakes/ppa \
    && apt-get install -y --no-install-recommends \
    python3.7 python3-distutils
ADD ../config /opt/mimecast/config
RUN tar --no-same-owner -xzf /opt/mimecast/config/MPE.Mimecast.Azure.Sentinel-1.0.7.tar.gz -C /opt \
    && cp /opt/MPE.Mimecast.Azure.Sentinel-1.0.7/MPE.Mimecast.Azure.Sentinel.Common/examples/*.conf /etc/supervisor/conf.d/ \
    && cp /opt/mimecast/config/config.ini /opt/MPE.Mimecast.Azure.Sentinel-1.0.7/ \
    && cp /opt/mimecast/config/supervisord.conf /etc/supervisor/supervisord.conf

VOLUME ["/opt/mimecast"]

ENTRYPOINT ["/usr/bin/supervisord","-c", "/etc/supervisor/supervisord.conf"]

EXPOSE 5000/tcp