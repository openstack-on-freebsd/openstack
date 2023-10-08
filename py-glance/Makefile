PORTNAME=	glance
DISTVERSION=	26.0.0
CATEGORIES=	www python
MASTER_SITES=	PYPI
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	chuck@tuffli.net
COMMENT=	OpenStack Image Registry and Delivery Service
WWW=		https://docs.openstack.org/glance/latest\

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	${PYTHON_PKGNAMEPREFIX}setuptools>=62.6:devel/py-setuptools@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}wheel>=0.37.1:devel/py-wheel@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pbr>=3.1.1:devel/py-pbr@${PY_FLAVOR}
RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}pbr>=3.1.1:devel/py-pbr@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}defusedxml>=0.6.0:devel/py-defusedxml@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}sqlalchemy14>=1.3.14:databases/py-sqlalchemy14@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}eventlet>=0.25.1:net/py-eventlet@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pastedeploy>=1.5.0:www/py-pastedeploy@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}routes>=2.3.1:www/py-routes@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}webob>=1.8.1:www/py-webob@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}sqlparse>=0.2.2:databases/py-sqlparse@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}alembic>=0.9.6:databases/py-alembic@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}httplib2>=0.9.1:www/py-httplib2@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.config>=8.1.0:devel/py-oslo.config@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.concurrency>=4.5.1:devel/py-oslo.concurrency@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.context>=2.22.0:devel/py-oslo.context@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.upgradecheck>=1.3.0:devel/py-oslo.upgradecheck@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.utils>=4.7.0:devel/py-oslo.utils@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}stevedore>3.0.0:devel/py-stevedore@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}futurist>=1.2.0:devel/py-futurist@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}taskflow>=4.0.0:devel/py-taskflow@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}keystoneauth1>=3.4.0:devel/py-keystoneauth1@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}keystonemiddleware>=5.1.0:devel/py-keystonemiddleware@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}wsme>=0.8.0:devel/py-wsme@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}prettytable>=0.7.1:devel/py-prettytable@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}Paste>=2.0.2:www/py-paste@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}jsonschema3>=3.2.0:devel/py-jsonschema3@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}python-keystoneclient>=3.8.0:net/py-python-keystoneclient@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}openssl>=17.1.0:security/py-openssl@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.db>=5.0.0:devel/py-oslo.db@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.i18n>=5.0.0:devel/py-oslo.i18n@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.limit>=1.6.0:devel/py-oslo.limit@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.log>=4.5.0:devel/py-oslo.log@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.messaging>9.0.0:devel/py-oslo.messaging@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.middleware>=3.31.0:devel/py-oslo.middleware@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.reports>=1.18.0:devel/py-oslo.reports@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.policy>=3.11.0:devel/py-oslo.policy@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}retrying>1.3.0:devel/py-retrying@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}osprofiler>=1.4.0:devel/py-osprofiler@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}debtcollector>=1.19.0:devel/py-debtcollector@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}cryptography>=2.6.1:security/py-cryptography@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}cursive>=0.2.1:devel/py-cursive@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}iso8601>=0.1.11:devel/py-iso8601@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}os-win>=4.0.1:devel/py-os-win@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}castellan>=0.17.0:devel/py-castellan@${PY_FLAVOR}
# XXX
#		${PYTHON_PKGNAMEPREFIX}glance-store>=2.3.0:devel/py-glance-store@${PY_FLAVOR} \

USES=		python:3.8+
USE_PYTHON=	autoplist concurrent pep517
NO_ARCH=	yes

USERS=		glance
GROUPS=		glance

CONFLICTS_INSTALL=	py??-glance-*

OPTIONS_GROUP=		MISC
OPTIONS_GROUP_MISC=	MEMCACHED MONGODB
OPTIONS_RADIO=		DB
OPTIONS_RADIO_DB=	MYSQL PGSQL

MEMCACHED_DESC=		memcached support
MONGODB_DESC=		MongoDB support (used for messaging services)
MYSQL_DESC=		MySQL/MariaDB support
PGSQL_DESC=		PostgreSQL support

MEMCACHED_RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}python-memcached>=1.56:databases/py-python-memcached@${PY_FLAVOR}
MONGODB_RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}pymongo>=3.0.2:databases/pymongo@${PY_FLAVOR}
MYSQL_RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}pymysql>=0:databases/py-pymysql@${PY_FLAVOR}
PGSQL_RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}psycopg2>=0:databases/py-psycopg2@${PY_FLAVOR}

MY_CONFFILES=	glance-api.conf glance-cache.conf glance-manage.conf \
		glance-policy-generator.conf glance-scrubber.conf \
		glance-api-paste.ini \
		schema-image.json

MY_REGEX=	(/etc/)(ceph|glance|nova|pki|ssl)

post-extract:
	@(cd ${WRKSRC}/etc && for f in ${MY_CONFFILES} ; do ${MV} $${f} $${f}.sample; done)
	@(cd ${WRKSRC}/etc/metadefs && for f in *.json ; do ${MV} $${f} $${f}.sample; done)

post-patch:
	# Prevent the installation of files into ${ETCDIR} by distutils. We do it
	# manually in the post-install target
	@${REINPLACE_CMD} -e '/etc\//d' ${WRKSRC}/setup.cfg
	# Replace (hardcoded) paths of config, documentation and Python files
	@${GREP} -Rl -Ee '${MY_REGEX}' --null \
		${WRKSRC}/etc ${WRKSRC}/doc ${WRKSRC}/glance | \
			${XARGS} -0 ${REINPLACE_CMD} -i '' -Ee \
				"s,${MY_REGEX},${PREFIX}\1\2,g"

post-install:
	@${MKDIR} ${STAGEDIR}${ETCDIR}/metadefs
.for f in ${MY_CONFFILES}
	${INSTALL_DATA} ${WRKSRC}/etc/$f.sample ${STAGEDIR}${ETCDIR}
.endfor
	${INSTALL_DATA} ${WRKSRC}/etc/metadefs/* ${STAGEDIR}${ETCDIR}/metadefs

.include <bsd.port.mk>
