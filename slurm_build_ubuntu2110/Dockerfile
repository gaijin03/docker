FROM ubuntu:21.10
ENV TZ=America/Denver
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt-get update && apt-get install -y \
	    autoconf \
	    build-essential \
	    clang \
	    clang-tools \
	    expect \
	    flex \
	    git \
	    hdf5-tools \
	    iputils-ping \
	    net-tools \
	    libcurl4-gnutls-dev \
	    libevent-dev \
            libfreeipmi-dev \
	    libgtk2.0-dev \
	    libhdf5-dev \
            libhttp-parser-dev \
	    libhwloc-dev \
	    libibmad-dev \
	    libibumad-dev \
	    libipmi* \
            libipmimonitoring-dev \
            libibverbs-dev \
	    libjson-c-dev \
            libjwt-dev \
	    liblua5.3-dev \
	    libmunge-dev \
	    libmysqlclient-dev \
	    libncurses-dev \
            libnvidia-ml-dev \
	    libpam0g-dev \
	    librrd-dev \
	    libssh2-1-dev \
	    libssl-dev \
	    liblz4-dev \
            libyaml-dev \
	    man2html \
	    munge \
	    mysql-client \
	    openssh-server \
	    python \
	    vim
RUN echo "thisismysecretmungekeythatis32bytes" > /etc/munge/munge.key
WORKDIR /slurm
CMD ["/bin/bash"]
