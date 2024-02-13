# Use the official PostgreSQL image
FROM postgres
# Set environment variable to trust connections; for development use only
ENV POSTGRES_HOST_AUTH_METHOD=trust
COPY words.sql /docker-entrypoint-initdb.d/
