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
	    json-c-devel \
	    libcurl-devel \
	    libevent-devel \
	    libibmad-devel \
	    libibumad-devel \
	    libipmi* \
	    libssh2-devel \
	    lua-devel \
	    lz4-devel \
	    man \
	    man2html \
	    mariadb \
	    mariadb-devel \
	    munge \
	    munge-devel \
	    ncurses-devel \
	    numactl-devel \
	    openssl-devel \
	    pam-devel \
	    perl-ExtUtils-MakeMaker \
	    python3 \
	    readline-devel \
	    rrdtool-devel \
	    vim \
	    which
RUN echo "thisismysecretmungekeythatis32bytes" > /etc/munge/munge.key
RUN chown munge:munge /etc/munge/munge.key
RUN chmod 0400 /etc/munge/munge.key
WORKDIR /slurm

RUN (cd /lib/systemd/system/sysinit.target.wants/; for i in *; do [ $i == systemd-tmpfiles-setup.service ] || rm -f $i; done); \
rm -f /lib/systemd/system/multi-user.target.wants/*;\
rm -f /etc/systemd/system/*.wants/*;\
rm -f /lib/systemd/system/local-fs.target.wants/*; \
rm -f /lib/systemd/system/sockets.target.wants/*udev*; \
rm -f /lib/systemd/system/sockets.target.wants/*initctl*; \
rm -f /lib/systemd/system/basic.target.wants/*;\
rm -f /lib/systemd/system/anaconda.target.wants/*;



CMD /usr/sbin/init
