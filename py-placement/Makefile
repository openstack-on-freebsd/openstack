PORTNAME=	openstack-placement
DISTVERSION=	10.0.0
CATEGORIES=	www python
MASTER_SITES=	PYPI
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	chuck@tuffli.net
COMMENT=	OpenStack Resource Provider Inventory Allocation Service
WWW=		https://docs.openstack.org/placement/latest\

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	${PYTHON_PKGNAMEPREFIX}setuptools>=62.6:devel/py-setuptools@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}tox>=3.18.0:devel/py-tox@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}wheel>=0.37.1:devel/py-wheel@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pbr>=3.1.1:devel/py-pbr@${PY_FLAVOR}
RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}pbr>=3.1.1:devel/py-pbr@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}sqlalchemy14>=1.4.0:databases/py-sqlalchemy14@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}keystonemiddleware>=4.18.0:devel/py-keystonemiddleware@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}routes>=2.3.1:www/py-routes@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}webob>=1.8.2:www/py-webob@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}jsonschema>=3.2.0:devel/py-jsonschema@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}requests>=2.25.0:www/py-requests@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.concurrency>=3.26.0:devel/py-oslo.concurrency@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.config>=6.7.0:devel/py-oslo.config@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.context>=2.22.0:devel/py-oslo.context@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.log>=4.3.0:devel/py-oslo.log@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.serialization>=2.25.0:devel/py-oslo.serialization@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.utils>=4.5.0:devel/py-oslo.utils@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.db>=8.6.0:devel/py-oslo.db@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.policy>=3.7.0:devel/py-oslo.policy@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.middleware>=3.31.0:devel/py-oslo.middleware@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.upgradecheck>=1.3.0:devel/py-oslo.upgradecheck@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}os-resource-classes>=1.1.0:devel/py-@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}os-traits>=3.0.0:devel/py-@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}microversion-parse>=0.2.1:devel/py-microversion-parse@${PY_FLAVOR}

USES=		python:3.8+
USE_PYTHON=	autoplist pep517
NO_ARCH=	yes

USERS=		placement
GROUPS=		placement

CONFLICTS_INSTALL=	py??-openstack-placement-*

ETCDIR=		${PREFIX}/etc/placement

post-patch:
	(cd ${WRKSRC} && \
		tox -egenconfig; \
		tox -egenpolicy; )
	@${GREP} -Rl -e '/etc/placement/' --null \
		${WRKSRC}/etc ${WRKSRC}/doc ${WRKSRC}/placement | \
			${XARGS} -0 ${REINPLACE_CMD} -i '' -Ee \
				"s|/etc/placement/|${ETCDIR}/|g"

post-install:
	@${MKDIR} ${STAGEDIR}${ETCDIR}
	(cd ${WRKSRC}/etc/placement && \
		${COPYTREE_SHARE} . ${STAGEDIR}${ETCDIR} "! -name README.rst -and ! -name \*-generator.conf")

.include <bsd.port.mk>
