FROM ubuntu:22.04
ENV TZ=America/Denver
RUN ln -snf /usr/share/zoneinfo/$TZ /etc/localtime && echo $TZ > /etc/timezone
RUN apt-get update && apt-get install -y \
	    autoconf \
	    build-essential \
	    check \
	    clang \
	    clang-tools \
	    expect \
	    flex \
	    git \
	    git-gui \
	    gitk \
	    hdf5-tools \
	    iputils-ping \
	    net-tools \
	    libcurl4-gnutls-dev \
	    libdbus-1-dev \
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
	    vim

# ROCM
RUN wget -q -O - https://repo.radeon.com/rocm/rocm.gpg.key | apt-key add -
RUN echo "deb http://archive.ubuntu.com/ubuntu/ focal main restricted" > /etc/apt/sources.list.d/rocm.list
RUN echo "deb http://archive.ubuntu.com/ubuntu/ focal main universe" >> /etc/apt/sources.list.d/rocm.list
RUN echo "deb [arch=amd64] https://repo.radeon.com/rocm/apt/debian/ ubuntu main" >> /etc/apt/sources.list.d/rocm.list
RUN apt-get update && apt-get install -y rocm-smi-lib
RUN rm /etc/apt/sources.list.d/rocm.list

RUN echo "thisismysecretmungekeythatis32bytes" > /etc/munge/munge.key
WORKDIR /slurm
CMD ["/bin/bash"]
