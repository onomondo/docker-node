FROM onomondo/debian:10.2

COPY --chown=root:root 10/etc/apt/sources.list.d/nodesource.list /etc/apt/sources.list.d/nodesource.list
COPY --chown=root:root etc/apt/sources.list.d/yarn.list /etc/apt/sources.list.d/yarn.list

RUN curl -s https://deb.nodesource.com/gpgkey/nodesource.gpg.key | apt-key add - \
 && curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - \
 && apt-get update \
 && apt-get install --assume-yes build-essential openssh-client nodejs yarn git \
 && sed -i 's/#   StrictHostKeyChecking ask/    StrictHostKeyChecking no/g' /etc/ssh/ssh_config \
 #
 # Create node user
 && groupadd --gid 1000 node \
 && useradd --uid 1000 --gid node --shell /bin/bash --create-home node \
 && echo node ALL=\(root\) NOPASSWD:ALL > /etc/sudoers.d/node \
 && chmod 0440 /etc/sudoers.d/node \
 #
 # Clean up
 && apt-get autoremove -y \
 && apt-get clean -y \
 && rm -rf /var/lib/apt/lists/* /tmp/*

CMD [ "node" ]
