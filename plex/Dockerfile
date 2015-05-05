FROM ubuntu:trusty

RUN apt-get update && apt-get install -y \
    avahi-daemon \
    avahi-utils

# Expose requisite ports
EXPOSE 32400

# Add the Plex Media Server package
COPY plexmediaserver_0.9.11.4.739-a4e710f_amd64.deb /tmp/plexmediaserver.deb

# Install Media Server
RUN dpkg -i /tmp/plexmediaserver.deb

# Declare necessary volumes
VOLUME /var/lib/plexmediaserver
VOLUME /plex/media

# Make sure plex owns its config and media, and can play media
RUN chown -R plex:plex /var/lib/plexmediaserver /plex && chmod -R 660 /plex

CMD ["/usr/sbin/start_pms"]
