FROM postgres:10

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
       postgresql-10-postgis-2.4 \
       postgresql-10-postgis-2.4-scripts \
       postgis \
    && rm -fr /var/lib/apt/lists/* /var/cache/apt/* \
    && mkdir -p /docker-entrypoint-initdb.d

COPY ./initdb-postgis.sh /docker-entrypoint-initdb.d/postgis.sh
COPY ./update-postgis.sh /usr/local/bin
