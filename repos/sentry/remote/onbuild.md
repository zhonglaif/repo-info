## `sentry:onbuild`

```console
$ docker pull sentry@sha256:1ca46e078773846bcc007380b9691a839c5969ba39e52affc9fc67a105a985cc
```

-	Platforms:
	-	linux; amd64

### `sentry:onbuild` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **189.7 MB (189748613 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:67a3b4318eaf287b0094106d6658f273f344d89b8f4a116651fede0d53f570cc`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["run","web"]`

```dockerfile
# Tue, 20 Jun 2017 20:13:32 GMT
ADD file:9c48682ff75c756544d4491472081a078edf5dd0bb5038d1cb850a1f9c480e3e in / 
# Tue, 20 Jun 2017 20:13:34 GMT
CMD ["bash"]
# Wed, 21 Jun 2017 18:15:44 GMT
ENV PATH=/usr/local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 21 Jun 2017 18:15:45 GMT
ENV LANG=C.UTF-8
# Wed, 21 Jun 2017 18:15:56 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		libgdbm3 		libsqlite3-0 		libssl1.0.0 	&& rm -rf /var/lib/apt/lists/*
# Wed, 21 Jun 2017 18:15:57 GMT
ENV GPG_KEY=C01E1CAD5EA2C4F0B8E3571504C367C218ADD4FF
# Wed, 21 Jun 2017 18:15:57 GMT
ENV PYTHON_VERSION=2.7.13
# Wed, 21 Jun 2017 18:18:03 GMT
RUN set -ex 	&& buildDeps=' 		dpkg-dev 		gcc 		libbz2-dev 		libc6-dev 		libdb-dev 		libgdbm-dev 		libncurses-dev 		libreadline-dev 		libsqlite3-dev 		libssl-dev 		make 		tcl-dev 		tk-dev 		wget 		xz-utils 		zlib1g-dev 	' 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 		&& wget -O python.tar.xz "https://www.python.org/ftp/python/${PYTHON_VERSION%%[a-z]*}/Python-$PYTHON_VERSION.tar.xz" 	&& wget -O python.tar.xz.asc "https://www.python.org/ftp/python/${PYTHON_VERSION%%[a-z]*}/Python-$PYTHON_VERSION.tar.xz.asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$GPG_KEY" 	&& gpg --batch --verify python.tar.xz.asc python.tar.xz 	&& rm -rf "$GNUPGHOME" python.tar.xz.asc 	&& mkdir -p /usr/src/python 	&& tar -xJC /usr/src/python --strip-components=1 -f python.tar.xz 	&& rm python.tar.xz 		&& cd /usr/src/python 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--enable-shared 		--enable-unicode=ucs4 	&& make -j "$(nproc)" 	&& make install 	&& ldconfig 		&& apt-get purge -y --auto-remove $buildDeps 		&& find /usr/local -depth 		\( 			\( -type d -a -name test -o -name tests \) 			-o 			\( -type f -a -name '*.pyc' -o -name '*.pyo' \) 		\) -exec rm -rf '{}' + 	&& rm -rf /usr/src/python
# Wed, 21 Jun 2017 18:18:03 GMT
ENV PYTHON_PIP_VERSION=9.0.1
# Wed, 21 Jun 2017 18:18:19 GMT
RUN set -ex; 		apt-get update; 	apt-get install -y --no-install-recommends wget; 	rm -rf /var/lib/apt/lists/*; 		wget -O get-pip.py 'https://bootstrap.pypa.io/get-pip.py'; 		apt-get purge -y --auto-remove wget; 		python get-pip.py 		--disable-pip-version-check 		--no-cache-dir 		"pip==$PYTHON_PIP_VERSION" 	; 	pip --version; 		find /usr/local -depth 		\( 			\( -type d -a -name test -o -name tests \) 			-o 			\( -type f -a -name '*.pyc' -o -name '*.pyo' \) 		\) -exec rm -rf '{}' +; 	rm -f get-pip.py
# Wed, 21 Jun 2017 18:18:20 GMT
CMD ["python2"]
# Fri, 23 Jun 2017 10:49:41 GMT
RUN groupadd -r sentry && useradd -r -m -g sentry sentry
# Fri, 23 Jun 2017 10:50:07 GMT
RUN apt-get update && apt-get install -y --no-install-recommends         gcc         git         libffi-dev         libjpeg-dev         libpq-dev         libxml2-dev         libxslt-dev         libyaml-dev     && rm -rf /var/lib/apt/lists/*
# Fri, 23 Jun 2017 10:50:08 GMT
ENV PIP_NO_CACHE_DIR=off
# Fri, 23 Jun 2017 10:50:09 GMT
ENV PIP_DISABLE_PIP_VERSION_CHECK=on
# Fri, 23 Jun 2017 10:50:10 GMT
ENV GOSU_VERSION=1.10
# Fri, 23 Jun 2017 10:50:23 GMT
RUN set -x     && apt-get update && apt-get install -y --no-install-recommends wget && rm -rf /var/lib/apt/lists/*     && wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)"     && wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc"     && export GNUPGHOME="$(mktemp -d)"     && gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4     && gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu     && rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc     && chmod +x /usr/local/bin/gosu     && gosu nobody true     && apt-get purge -y --auto-remove wget
# Fri, 23 Jun 2017 10:50:23 GMT
ENV TINI_VERSION=v0.14.0
# Fri, 23 Jun 2017 10:50:35 GMT
RUN set -x     && apt-get update && apt-get install -y --no-install-recommends wget && rm -rf /var/lib/apt/lists/*     && wget -O /usr/local/bin/tini "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini"     && wget -O /usr/local/bin/tini.asc "https://github.com/krallin/tini/releases/download/$TINI_VERSION/tini.asc"     && export GNUPGHOME="$(mktemp -d)"     && gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 6380DC428747F6C393FEACA59A84159D7001A4E5     && gpg --batch --verify /usr/local/bin/tini.asc /usr/local/bin/tini     && rm -r "$GNUPGHOME" /usr/local/bin/tini.asc     && chmod +x /usr/local/bin/tini     && tini -h     && apt-get purge -y --auto-remove wget
# Fri, 23 Jun 2017 10:50:55 GMT
RUN set -x     && apt-get update && apt-get install -y --no-install-recommends make && rm -rf /var/lib/apt/lists/*     && pip install librabbitmq==1.6.1     && python -c 'import librabbitmq'     && apt-get purge -y --auto-remove make
# Fri, 23 Jun 2017 10:53:34 GMT
ENV SENTRY_VERSION=8.17.0
# Fri, 23 Jun 2017 10:55:08 GMT
RUN set -x     && apt-get update && apt-get install -y --no-install-recommends wget g++ && rm -rf /var/lib/apt/lists/*     && mkdir -p /usr/src/sentry     && wget -O /usr/src/sentry/sentry-${SENTRY_VERSION}-py27-none-any.whl "https://github.com/getsentry/sentry/releases/download/${SENTRY_VERSION}/sentry-${SENTRY_VERSION}-py27-none-any.whl"     && wget -O /usr/src/sentry/sentry-${SENTRY_VERSION}-py27-none-any.whl.asc "https://github.com/getsentry/sentry/releases/download/${SENTRY_VERSION}/sentry-${SENTRY_VERSION}-py27-none-any.whl.asc"     && wget -O /usr/src/sentry/sentry_plugins-${SENTRY_VERSION}-py2.py3-none-any.whl "https://github.com/getsentry/sentry/releases/download/${SENTRY_VERSION}/sentry_plugins-${SENTRY_VERSION}-py2.py3-none-any.whl"     && wget -O /usr/src/sentry/sentry_plugins-${SENTRY_VERSION}-py2.py3-none-any.whl.asc "https://github.com/getsentry/sentry/releases/download/${SENTRY_VERSION}/sentry_plugins-${SENTRY_VERSION}-py2.py3-none-any.whl.asc"     && export GNUPGHOME="$(mktemp -d)"     && gpg --keyserver ha.pool.sks-keyservers.net --recv-keys D8749766A66DD714236A932C3B2D400CE5BBCA60     && gpg --batch --verify /usr/src/sentry/sentry-${SENTRY_VERSION}-py27-none-any.whl.asc /usr/src/sentry/sentry-${SENTRY_VERSION}-py27-none-any.whl     && gpg --batch --verify /usr/src/sentry/sentry_plugins-${SENTRY_VERSION}-py2.py3-none-any.whl.asc /usr/src/sentry/sentry_plugins-${SENTRY_VERSION}-py2.py3-none-any.whl     && pip install         /usr/src/sentry/sentry-${SENTRY_VERSION}-py27-none-any.whl         /usr/src/sentry/sentry_plugins-${SENTRY_VERSION}-py2.py3-none-any.whl     && sentry --help     && sentry plugins list     && rm -r "$GNUPGHOME" /usr/src/sentry     && apt-get purge -y --auto-remove wget g++
# Fri, 23 Jun 2017 10:55:09 GMT
ENV SENTRY_CONF=/etc/sentry SENTRY_FILESTORE_DIR=/var/lib/sentry/files
# Fri, 23 Jun 2017 10:55:11 GMT
RUN mkdir -p $SENTRY_CONF && mkdir -p $SENTRY_FILESTORE_DIR
# Fri, 23 Jun 2017 10:55:12 GMT
COPY file:6b5c0c264ecaf40e9fe1838ff0926e09a661f89950c3c2b6f1612e948324733d in /etc/sentry/ 
# Fri, 23 Jun 2017 10:55:13 GMT
COPY file:d1a7cd4cbf7c842d84a135ed530ecf78f6858eaffe7f2d78824cc2906088bdd1 in /etc/sentry/ 
# Fri, 23 Jun 2017 10:55:14 GMT
COPY file:f490e4be17b442272f00cb3dac92d70a1d0164325552588b163a33fad4701f18 in /entrypoint.sh 
# Fri, 23 Jun 2017 10:55:15 GMT
EXPOSE 9000/tcp
# Fri, 23 Jun 2017 10:55:16 GMT
VOLUME [/var/lib/sentry/files]
# Fri, 23 Jun 2017 10:55:16 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Fri, 23 Jun 2017 10:55:17 GMT
CMD ["run" "web"]
# Fri, 23 Jun 2017 10:55:43 GMT
WORKDIR /usr/src/sentry
# Fri, 23 Jun 2017 10:55:44 GMT
ENV PYTHONPATH=/usr/src/sentry
# Fri, 23 Jun 2017 10:55:44 GMT
ONBUILD COPY . /usr/src/sentry
# Fri, 23 Jun 2017 10:55:45 GMT
ONBUILD RUN if [ -s requirements.txt ]; then pip install -r requirements.txt; fi
# Fri, 23 Jun 2017 10:55:46 GMT
ONBUILD RUN if [ -s setup.py ]; then pip install -e .; fi
# Fri, 23 Jun 2017 10:55:47 GMT
ONBUILD RUN if [ -s sentry.conf.py ]; then cp sentry.conf.py $SENTRY_CONF/; fi 	&& if [ -s config.yml ]; then cp config.yml $SENTRY_CONF/; fi
```

-	Layers:
	-	`sha256:9f0706ba7422412cd468804fee456786f88bed94bf9aea6dde2a47f770d19d27`  
		Last Modified: Tue, 20 Jun 2017 20:35:47 GMT  
		Size: 52.6 MB (52614808 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aba3c97cb9e152495a89a39958e5e64c5e88c60fc3015696d9c89794a90f4310`  
		Last Modified: Wed, 21 Jun 2017 18:57:48 GMT  
		Size: 3.5 MB (3474032 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:30b5dae4817fffe48023fe6224d23184e59abb8b40c1a29b95ba0a93401fa4ea`  
		Last Modified: Wed, 21 Jun 2017 18:57:52 GMT  
		Size: 15.0 MB (15002181 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7f659be4383b4e8c83b6d5b5fad3777b06dc54012c8a3d245547eaf08c4199bb`  
		Last Modified: Wed, 21 Jun 2017 18:57:48 GMT  
		Size: 1.7 MB (1736327 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:79bec317811a8eac58e98c5d1a22ab524d25115276fcbae8ed6ffe8321593763`  
		Last Modified: Sun, 25 Jun 2017 00:15:58 GMT  
		Size: 4.4 KB (4379 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:288b506f2fc4ae4ea2a41ff1ca68128f225dbec12a2e525c22a8a7decc4158a9`  
		Last Modified: Sun, 25 Jun 2017 00:16:16 GMT  
		Size: 63.9 MB (63850236 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a5870a3e34657553926d5a52147f54ae313cccdb76c4a4b74f94912f070d4869`  
		Last Modified: Sun, 25 Jun 2017 00:15:57 GMT  
		Size: 620.1 KB (620146 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ca081e57f773e8aba88c1dd530c852e0c4f5095246974a9eda2c31527a4cb501`  
		Last Modified: Sun, 25 Jun 2017 00:15:57 GMT  
		Size: 127.4 KB (127430 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f6ae4b7a44d7c063a8b19ed7d28e9219e7fffbd06d3cb815c49be717933a7527`  
		Last Modified: Sun, 25 Jun 2017 00:15:56 GMT  
		Size: 2.4 MB (2357651 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:edb929eb4005100ba4e439995908834ae86e21bddbc830c30b6eb2d4249a9cff`  
		Last Modified: Sun, 25 Jun 2017 00:18:45 GMT  
		Size: 50.0 MB (49956225 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ee459ff1949c06da284283ea836d9a1c8758e2c3df8ac9047c40bc4587991393`  
		Last Modified: Sun, 25 Jun 2017 00:18:21 GMT  
		Size: 172.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9cd27baefb9f10416080a4daa201ba43fb3712a2a6c47d5256debb5c71622640`  
		Last Modified: Sun, 25 Jun 2017 00:18:21 GMT  
		Size: 3.4 KB (3404 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7e4d008e74985b6b8e885d5975af349ec7e998c12217ac6b6fa31fb8c5a3cc67`  
		Last Modified: Sun, 25 Jun 2017 00:18:21 GMT  
		Size: 1.1 KB (1063 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b8d5489c6a7f7f1aecf7b97aeebd40fdc55ae515c96bb68c660d3deedae5ee20`  
		Last Modified: Sun, 25 Jun 2017 00:18:21 GMT  
		Size: 428.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f862920694765323d1b4ee176072db01e4eedd6bf002c907f4b263bc1821be55`  
		Last Modified: Sun, 25 Jun 2017 00:20:39 GMT  
		Size: 131.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
