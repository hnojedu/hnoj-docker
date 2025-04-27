FROM ubuntu:jammy

RUN apt-get update && \
    apt-get install -y curl inotify-tools && \
    apt-get autoremove -y && \
    rm -rf /var/lib/apt/lists/*

COPY jnotify/jnotify.sh /
RUN chmod +x /jnotify.sh

CMD ["/jnotify.sh", "/problems", "/jnotify/jnotify.conf"]