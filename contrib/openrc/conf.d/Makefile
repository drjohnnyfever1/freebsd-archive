# $FreeBSD$

PACKAGE=runtime

CONFS=          bootmisc fsck ipfw ldconfig localmount moused netmount powerd rarpd \
		savecore staticroute swap syscons tmpfiles urandom

NO_OBJ=
CONFDIR=       /etc/conf.d
CONFMODE=      755

.include <bsd.prog.mk>

include ../mk/net.mk

DIR=	${CONFDIR}
CONF=	bootmisc fsck hostname localmount netmount swap urandom ${CONF-${OS}}

ifeq (${MKNET},yes)
CONF+= network staticroute
endif

MK=	../mk
include ${MK}/os.mk

CONF-FreeBSD=	ipfw modules moused powerd rarpd savecore syscons

CONF-Linux=	agetty consolefont devfs dmesg hwclock keymaps killprocs modules \
	mtab net-online

CONF-NetBSD=	moused rarpd savecore

include ${MK}/scripts.mk
