# Use the official Caddy Docker image
FROM caddy:latest

# Update package index and upgrade installed packages
RUN apk update && apk upgrade

# Copy Caddyfile to configure Caddy server
COPY Caddyfile /etc/caddy/Caddyfile
