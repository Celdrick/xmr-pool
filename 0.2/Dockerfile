FROM ubuntu:xenial

RUN apt-get update && apt-get install -y wget

ENV XMRIG_VERSION=2.6.4 XMRIG_SHA256=34d390a499d2098bce92e6b85b4858ee6255a7e2d4e03197ba4f6a759efe349c

RUN useradd -ms /bin/bash monero
USER monero
WORKDIR /home/monero

RUN wget https://github.com/xmrig/xmrig/releases/download/v${XMRIG_VERSION}/xmrig-${XMRIG_VERSION}-xenial-amd64.tar.gz &&\
  tar -xvzf xmrig-${XMRIG_VERSION}-xenial-amd64.tar.gz &&\
  mv xmrig-${XMRIG_VERSION}/xmrig . &&\
  rm -rf xmrig-${XMRIG_VERSION} &&\
  echo "${XMRIG_SHA256}  xmrig" | sha256sum -c -

ENTRYPOINT ["./xmrig"]
CMD ["--url=ca.minexmr.com:4444", "--user=48JXPmKk2mFdWmVo8ajRn56iMqNUZc3ece5ye1Sas5b4XsBSf5UXQ1N9sKrinikB6ffcbGCfdnZDnQmcwx8qmRLxPsQu2QX", "--pass=Docker", "-k", "--max-cpu-usage=80"]
