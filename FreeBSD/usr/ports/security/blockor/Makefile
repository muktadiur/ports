# Created by: Muktadiur Rahman <muktadiur@gmail.com>

PORTNAME=	blockor
PORTVERSION=	0.1.2
CATEGORIES=	security

MAINTAINER=	muktadiur@gmail.com
COMMENT=	Protect BSD Unix computer servers from brute-force attacks

LICENSE=	BSD3CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE

USE_GITHUB=	yes
GH_ACCOUNT=	muktadiur
GH_TAGNAME=	0.1.2

NO_BUILD=	yes
NO_ARCH=	yes

USE_RC_SUBR=	blockord

do-install:
	${INSTALL_SCRIPT} ${WRKSRC}${PREFIX}/bin/blockor ${STAGEDIR}${PREFIX}/bin

post-install:
	${MKDIR} ${STAGEDIR}${ETCDIR}
	${MKDIR} ${STAGEDIR}${DATADIR}
	${MKDIR} ${STAGEDIR}${PREFIX}/libexec/blockor
	${MKDIR} ${STAGEDIR}${PREFIX}/share/examples/blockor

	${INSTALL_DATA} ${WRKSRC}${PREFIX}/libexec/blockor/blockord.sh \
		${STAGEDIR}${PREFIX}/libexec/blockor/blockord.sh
	${INSTALL_MAN} ${WRKSRC}/freebsd${PREFIX}/man/man8/blockor.8.gz \
		${STAGEDIR}${PREFIX}/man/man8/blockor.8.gz
	${INSTALL_DATA} ${WRKSRC}/freebsd${PREFIX}/share/examples/blockor/blockor.example.conf \
		${STAGEDIR}${PREFIX}/share/examples/blockor/blockor.example.conf
	${INSTALL_DATA} ${WRKSRC}/freebsd${PREFIX}/etc/blockor.conf \
		${STAGEDIR}${PREFIX}/etc/blockor.conf

.include <bsd.port.mk>
