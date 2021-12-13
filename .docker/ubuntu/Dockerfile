FROM ubuntu:rolling

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update
RUN apt-get -y install \
    curl \
    git

RUN curl -fsSL https://deb.nodesource.com/setup_16.x | bash -

RUN apt-get update
RUN apt-get -y install nodejs

RUN apt-get update
RUN apt-get -y install \
    gcc  \
    g++  \
    make

RUN corepack enable

RUN mkdir "/home/solana"
WORKDIR /home/solana

RUN sh -c "$(curl -sSfL https://release.solana.com/stable/install)"
ENV PATH="/root/.local/share/solana/install/active_release/bin:$PATH"

RUN npm install --global ts-node

RUN echo "export PATH=$PATH" > /etc/environment

ENTRYPOINT ["tail"]
CMD ["-f","/dev/null"]