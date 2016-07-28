FROM centos:7
RUN yum -y groupinstall 'Development Tools'
RUN yum -y install epel-release
RUN yum -y install \
	    clang \
	    clang-analyzer \
	    expect \
	    gtk2-devel \
	    hdf5-devel \
	    hwloc-devel \
	    libibmad \
	    libibumad \
	    lua-devel \
	    man \
	    man2html \
	    munge \
	    munge-devel \
	    mysql-devel \
	    ncurses-devel \
	    numactl-devel \
	    openssl-devel \
	    pam-devel \
	    readline-devel \
	    rrdtool-devel
RUN echo "thisismysecretmungekeythatis32bytes" > /etc/munge/munge.key
RUN chown munge:munge /etc/munge/munge.key
RUN chmod 0400 /etc/munge/munge.key
WORKDIR /slurm
CMD ["/bin/bash"]
