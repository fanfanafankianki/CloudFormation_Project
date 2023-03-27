# Pobierz obraz Ubuntu
FROM ubuntu:latest
LABEL "Project"="PwrTrckr"
LABEL "Author"="fanfan"

# Aktualizacja indeksów pakietów i instalacja Memcached
RUN apt-get update && \
    apt-get install -y memcached

# Ustawienie zmiennej środowiskowej
ENV MEMCACHED_MEMORY_LIMIT 64
ENV MEMCACHED_MAX_CONNECTIONS 1024
ENV MEMCACHED_THREADS 4
ENV MEMCACHED_LISTEN_IP 0.0.0.0
ENV MEMCACHED_LISTEN_PORT 11211

# Ustawienie portu nasłuchiwania Memcached
EXPOSE 11211

# Uruchamianie Memcached
CMD ["/usr/bin/memcached", "-m", "${MEMCACHED_MEMORY_LIMIT}", "-c", "${MEMCACHED_MAX_CONNECTIONS}", "-t", "${MEMCACHED_THREADS}", "-l", "${MEMCACHED_LISTEN_IP}", "-p", "${MEMCACHED_LISTEN_PORT}"]
