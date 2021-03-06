# Created by: Po-Chuan Hsieh <sunpoet@FreeBSD.org>
# $FreeBSD$

PORTNAME=	FFI-Platypus
PORTVERSION=	0.74
CATEGORIES=	devel perl5
MASTER_SITES=	CPAN
PKGNAMEPREFIX=	p5-

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Write Perl bindings to non-Perl libraries with FFI

LICENSE=	ART10 GPLv1+
LICENSE_COMB=	dual
LICENSE_FILE=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	${RUN_DEPENDS}
LIB_DEPENDS=	libffi.so:devel/libffi
RUN_DEPENDS=	p5-Capture-Tiny>=0:devel/p5-Capture-Tiny \
		p5-FFI-CheckLib>=0.05:devel/p5-FFI-CheckLib

USES=		gmake perl5 pkgconfig
USE_PERL5=	configure

.include <bsd.port.pre.mk>

.if ${PERL_LEVEL} < 502600
BUILD_DEPENDS+=	p5-ExtUtils-MakeMaker>=7.12:devel/p5-ExtUtils-MakeMaker \
		p5-Scalar-List-Utils>=1.45:lang/p5-Scalar-List-Utils
RUN_DEPENDS+=	p5-ExtUtils-MakeMaker>=7.12:devel/p5-ExtUtils-MakeMaker \
		p5-Scalar-List-Utils>=1.45:lang/p5-Scalar-List-Utils
.endif

post-install:
	${STRIP_CMD} ${STAGEDIR}${PREFIX}/${SITE_ARCH_REL}/auto/FFI/Platypus/Platypus.so

.include <bsd.port.post.mk>
