# docker/postgres/Dockerfile
FROM postgres:15

# Install build prerequisites and Postgres server dev libs
RUN apt-get update && apt-get install -y \
    git \
    build-essential \
    postgresql-server-dev-15 \
 && rm -rf /var/lib/apt/lists/*

# Clone pgvector from GitHub and compile/install
RUN cd /tmp \
 && git clone --branch v0.5.0 https://github.com/pgvector/pgvector.git \
 && cd pgvector \
 && make && make install \
 && cd .. \
 && rm -rf pgvector
