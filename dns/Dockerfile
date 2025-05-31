FROM ubuntu:22.04

RUN apt-get update && apt-get install -y bind9 bind9utils bind9-doc dnsutils && \
    rm -rf /var/lib/apt/lists/*

COPY zonefile.db /etc/bind/db.example.com
COPY named.conf /etc/bind/named.conf.local

EXPOSE 53/udp

CMD ["named", "-g", "-c", "/etc/bind/named.conf.local"]
