FROM mysql:8.0

# Use a secret for the MySQL root password
RUN groupadd -r expense && \
    useradd -r -g expense expense && \
    mkdir -p /docker-entrypoint-initdb.d && \
    chown -R expense:expense /var/lib/mysql /var/run/mysqld /docker-entrypoint-initdb.d

COPY scripts/*.sql /docker-entrypoint-initdb.d/

USER expense

EXPOSE 3306
