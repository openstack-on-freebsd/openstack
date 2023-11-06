PORTNAME=	os-traits
PORTVERSION=	3.0.0
CATEGORIES=	devel python
MASTER_SITES=	PYPI
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	chuck@tuffli.net
COMMENT=	OpenStack standardized trait strings
WWW=		https://docs.openstack.org/os-traits/latest\

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	${PYTHON_PKGNAMEPREFIX}pbr>=2.0.0:devel/py-pbr@${PY_FLAVOR}
RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}pbr>=2.0.0:devel/py-pbr@${PY_FLAVOR}

USES=		python:3.8+
USE_PYTHON=	autoplist pep517
NO_ARCH=	yes

.include <bsd.port.mk>
