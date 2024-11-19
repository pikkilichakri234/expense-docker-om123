FROM mysql:8.0

# Set the root password and other environment variables
ENV MYSQL_ROOT_PASSWORD=ExpenseApp@1 \
    MYSQL_DATABASE=transactions \
    MYSQL_USER=expense \
    MYSQL_PASSWORD=ExpenseApp@1

# Create a group and user, and set permissions
RUN groupadd expense && \
    useradd -g expense expense && \
    chown -R expense:expense /var/lib/mysql /var/run/mysqld /docker-entrypoint-initdb.d

# Copy initialization scripts to the MySQL init directory
COPY scripts/*.sql /docker-entrypoint-initdb.d/

# Switch to non-root user
USER expense

# Expose the MySQL port
EXPOSE 3306

# Use the default MySQL entrypoint
CMD ["mysqld"]

