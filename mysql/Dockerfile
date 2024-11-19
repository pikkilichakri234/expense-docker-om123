
FROM mysql:8.0.40

# Do not hardcode sensitive information in Dockerfile
# Instead, use a build argument or pass it as an environment variable during runtime
ARG MYSQL_ROOT_PASSWORD
ENV MYSQL_ROOT_PASSWORD=${MYSQL_ROOT_PASSWORD}

# Other configurations (create group, etc.)
RUN groupadd expense && \
    useradd -m -g expense expense

# Additional setup (e.g., copying app files, setting permissions)
COPY ./myapp /app
WORKDIR /app
# Expose the necessary port for the MySQL container
EXPOSE 3306
