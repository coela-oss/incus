FROM ubuntu:jammy

# [Optional] Uncomment the next line to use go get to install anything else you need
# RUN go get -x <your-dependency-or-tool>
ENV CGO_CFLAGS="-I/go/deps/raft/include/ -I/go/deps/cowsql/include/"
ENV CGO_LDFLAGS="-L/go/deps/raft/.libs -L/go/deps/cowsql/.libs/"
ENV LD_LIBRARY_PATH="/go/deps/raft/.libs/:/go/deps/cowsql/.libs/"
ENV CGO_LDFLAGS_ALLOW="(-Wl,-wrap,pthread_create)|(-Wl,-z,now)"
# [Optional] Uncomment this section to install additional OS packages.
RUN apt-get update \
  && apt-get -y install \
  gpg \
  software-properties-common \
  && add-apt-repository ppa:ubuntu-lxc/daily -y --no-update \
  && add-apt-repository ppa:cowsql/stable -y --no-update \
  && apt-get update \
  && DEBIAN_FRONTEND=noninteractive \
  apt-get -y install --no-install-recommends \
  curl \
  gettext \
  git \
  libacl1-dev \
  libcap-dev \
  libdbus-1-dev \
  libcowsql-dev \
  liblxc-dev \
  lxc-templates \
  libseccomp-dev \
  libselinux-dev \
  libsqlite3-dev \
  libtool \
  shellcheck \
  gcc \
  autoconf \
  automake \
  acl \
  attr \
  dnsmasq-base \
  libudev-dev \
  liblz4-dev \
  libuv1-dev \
  make \
  pkg-config \
  rsync \
  squashfs-tools \
  tar \
  tcl \
  xz-utils \
  ebtables \
  python3-pip \
  && python3 -m pip install flake8

# [Optional] Uncomment this line to install global node packages.
# RUN su vscode -c "source /usr/local/share/nvm/nvm.sh && npm install -g <your-package-here>" 2>&1