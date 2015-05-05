FROM debian:jessie

RUN apt-get update && apt-get install -y \
    libssl1.0.0

# Copy and unzip to /utserver
ADD utserver.tar.gz /opt
COPY utserver.conf /opt/utorrent-server-alpha-v3_3/

# WebUI Port
EXPOSE 8080
# BitTorrent protocol port
EXPOSE 6881

# Volume for containing data
VOLUME /utserver

WORKDIR /opt/utorrent-server-alpha-v3_3/
CMD ["./utserver", "-configfile", "utserver.conf", "-logfile", "/var/log/utserver.log"]



