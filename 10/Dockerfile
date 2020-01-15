FROM onomondo/debian:10.2

COPY --chown=root:root 10/etc/apt/sources.list.d/nodesource.list /etc/apt/sources.list.d/nodesource.list
COPY --chown=root:root etc/apt/sources.list.d/yarn.list /etc/apt/sources.list.d/yarn.list

RUN curl -s https://deb.nodesource.com/gpgkey/nodesource.gpg.key | apt-key add - \
 && curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - \
 && apt-get update \
 && apt-get install --assume-yes build-essential nodejs yarn

CMD [ "node" ]
