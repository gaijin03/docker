FROM centos:6
RUN yum -y groupinstall 'Development Tools'
RUN yum -y install epel-release
RUN yum -y install \
	    clang \
	    clang-analyzer \
	    expect \
	    gtk2-devel \
	    hdf5-devel \
	    hwloc-devel \
	    json-c-devel \
	    libcurl-devel \
	    libevent-devel \
	    libibmad-devel \
	    libibumad-devel \
	    libssh2-devel \
	    lua-devel \
	    lz4-devel \
	    man \
	    man2html \
	    munge \
	    munge-devel \
	    mysql-devel \
	    ncurses-devel \
	    numactl-devel \
	    openssl-devel \
	    pam-devel \
	    perl-ExtUtils-MakeMaker \
	    python34 \
	    readline-devel \
	    rrdtool-devel \
	    vim
RUN echo "thisismysecretmungekeythatis32bytes" > /etc/munge/munge.key
RUN chown munge:munge /etc/munge/munge.key
RUN chmod 0400 /etc/munge/munge.key
WORKDIR /slurm
CMD ["/bin/bash"]
