PORTNAME=	keystone
DISTVERSION=	23.0.0
CATEGORIES=	www security python
MASTER_SITES=	PYPI
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	chuck@tuffli.net
COMMENT=	OpenStack Identity Service
WWW=		https://docs.openstack.org/keystone/latest/

LICENSE=	APACHE20
LICENSE_FILE=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	rustc:lang/${RUST_DEFAULT} \
		${PYTHON_PKGNAMEPREFIX}setuptools>=62.6:devel/py-setuptools@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}wheel>=0.37.1:devel/py-wheel@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pbr>=2.0.0:devel/py-pbr@${PY_FLAVOR}
# XXX these dependencies are a problem because they need to exclude versions
#		oslo.serialization!=2.19.1,>=2.18.0 : specify >2.19.1
#		pycadf!=2.0.0,>=1.1.0 : specify >2.0.0
RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}pbr>=2.0.0:devel/py-pbr@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}webob>=1.7.1:www/py-webob@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}Flask>=1.0.2:www/py-flask@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}Flask-RESTful>=0.3.5:www/py-flask-restful@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}cryptography>=2.7:security/py-cryptography@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}sqlalchemy14>=1.3.0:databases/py-sqlalchemy14@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}sqlalchemy-migrate>=0.13.0:databases/py-sqlalchemy-migrate@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}stevedore>=1.20.0:devel/py-stevedore@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}passlib>=1.7.0:security/py-passlib@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}python-keystoneclient>=3.8.0:net/py-python-keystoneclient@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}keystonemiddleware>=7.0.0:devel/py-keystonemiddleware@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}bcrypt>=3.1.3:security/py-bcrypt@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}scrypt>=0.8.0:security/py-scrypt@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.cache>=1.26.0:devel/py-oslo.cache@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.config>=6.8.0:devel/py-oslo.config@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.context>=2.22.0:devel/py-oslo.context@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.messaging>=5.29.0:devel/py-oslo.messaging@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.db>=6.0.0:devel/py-oslo.db@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.i18n>=3.15.3:devel/py-oslo.i18n@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.log>=3.44.0:devel/py-oslo.log@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.middleware>=3.31.0:devel/py-oslo.middleware@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.policy>=3.10.0:devel/py-oslo.policy@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.serialization>2.19.1:devel/py-oslo.serialization@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.upgradecheck>=1.3.0:devel/py-oslo.upgradecheck@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oslo.utils>=3.33.0:devel/py-oslo.utils@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}oauthlib>=0.6.2:security/py-oauthlib@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pycadf>2.0.0:devel/py-pycadf@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pysaml2>=5.0.0:security/py-pysaml2@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pyjwt>=1.6.1:www/py-pyjwt@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}dogpile.cache>=1.0.2:devel/py-dogpile.cache@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}jsonschema3>=3.2.0:devel/py-jsonschema3@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}msgpack>=0.5.0:devel/py-msgpack@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}osprofiler>=1.4.0:devel/py-osprofiler@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pytz>=2013.6:devel/py-pytz@${PY_FLAVOR}

USES=		python:3.8+
USE_PYTHON=	autoplist concurrent pep517
NO_ARCH=	yes

USERS=		keystone
GROUPS=		keystone

SUB_FILES=	pkg-message

CONFLICTS_INSTALL=	py??-keystone-*

OPTIONS_GROUP=		MISC
OPTIONS_GROUP_MISC=	LDAP MEMCACHED MONGODB
OPTIONS_RADIO=		DB
OPTIONS_RADIO_DB=	MYSQL PGSQL

LDAP_DESC=		LDAP support
MEMCACHED_DESC=		memcached support
MONGODB_DESC=		MongoDB support (used for messaging services)
MYSQL_DESC=		MySQL/MariaDB support
PGSQL_DESC=		PostgreSQL support

LDAP_RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}ldap>=2.4.20:net/py-ldap@${PY_FLAVOR} \
			${PYTHON_PKGNAMEPREFIX}ldappool>=2.0.0:net/py-ldappool@${PY_FLAVOR}
MEMCACHED_RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}python-memcached>=1.56:databases/py-python-memcached@${PY_FLAVOR}
MONGODB_RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}pymongo>=3.0.2:databases/pymongo@${PY_FLAVOR}
MYSQL_RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}pymysql>=0:databases/py-pymysql@${PY_FLAVOR}
PGSQL_RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}psycopg2>=0:databases/py-psycopg2@${PY_FLAVOR}

post-patch:
	(cd ${WRKSRC} && \
		oslo-config-generator --config-file=config-generator/keystone.conf; \
		oslopolicy-sample-generator --config-file=config-generator/keystone-policy-generator.conf; )
	@${GREP} -Rl -e '/etc/keystone/' --null \
		${WRKSRC}/etc ${WRKSRC}/doc ${WRKSRC}/keystone | \
			${XARGS} -0 ${REINPLACE_CMD} -i '' -Ee \
				"s|/etc/keystone/|${ETCDIR}/|g"

	@${GREP} -Rl -e '/var/log/apache2/' --null \
		${WRKSRC}/doc ${WRKSRC}/httpd | \
			${XARGS} -0 ${REINPLACE_CMD} -i '' -Ee \
				"s|(/var/log)/apache2|\1|g"

post-install:
	@${MKDIR} ${STAGEDIR}${ETCDIR}
	(cd ${WRKSRC}/etc && for f in *; do \
		${INSTALL_DATA} $${f} ${STAGEDIR}${ETCDIR}; done)

.include <bsd.port.mk>
