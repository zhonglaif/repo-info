## `python:3-onbuild`

```console
$ docker pull python@sha256:7d75b0f08ae894e74d7f680b5b88cc23c0ee4c8407ee37ae97a866ec2456ecbf
```

-	Platforms:
	-	linux; amd64

### `python:3-onbuild` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **270.8 MB (270763365 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:5e8502cd1971bfc5a072d55194e9b3883716a085f3ca166f436a77216992901f`
-	Default Command: `["python3"]`

```dockerfile
# Tue, 20 Jun 2017 20:13:32 GMT
ADD file:9c48682ff75c756544d4491472081a078edf5dd0bb5038d1cb850a1f9c480e3e in / 
# Tue, 20 Jun 2017 20:13:34 GMT
CMD ["bash"]
# Tue, 20 Jun 2017 21:03:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 20 Jun 2017 21:06:21 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Tue, 20 Jun 2017 21:09:42 GMT
RUN set -ex; 	apt-get update; 	apt-get install -y --no-install-recommends 		autoconf 		automake 		bzip2 		file 		g++ 		gcc 		imagemagick 		libbz2-dev 		libc6-dev 		libcurl4-openssl-dev 		libdb-dev 		libevent-dev 		libffi-dev 		libgdbm-dev 		libgeoip-dev 		libglib2.0-dev 		libjpeg-dev 		libkrb5-dev 		liblzma-dev 		libmagickcore-dev 		libmagickwand-dev 		libncurses-dev 		libpng-dev 		libpq-dev 		libreadline-dev 		libsqlite3-dev 		libssl-dev 		libtool 		libwebp-dev 		libxml2-dev 		libxslt-dev 		libyaml-dev 		make 		patch 		xz-utils 		zlib1g-dev 				$( 			if apt-cache show 'default-libmysqlclient-dev' 2>/dev/null | grep -q '^Version:'; then 				echo 'default-libmysqlclient-dev'; 			else 				echo 'libmysqlclient-dev'; 			fi 		) 	; 	rm -rf /var/lib/apt/lists/*
# Wed, 21 Jun 2017 18:13:10 GMT
ENV PATH=/usr/local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Wed, 21 Jun 2017 18:13:11 GMT
ENV LANG=C.UTF-8
# Wed, 21 Jun 2017 18:13:24 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		tcl 		tk 	&& rm -rf /var/lib/apt/lists/*
# Wed, 21 Jun 2017 18:44:46 GMT
ENV GPG_KEY=0D96DF4D4110E5C43FBFB17F2D347EA6AA65421D
# Wed, 21 Jun 2017 18:44:47 GMT
ENV PYTHON_VERSION=3.6.1
# Wed, 21 Jun 2017 18:46:20 GMT
RUN set -ex 	&& buildDeps=' 		dpkg-dev 		tcl-dev 		tk-dev 	' 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 		&& wget -O python.tar.xz "https://www.python.org/ftp/python/${PYTHON_VERSION%%[a-z]*}/Python-$PYTHON_VERSION.tar.xz" 	&& wget -O python.tar.xz.asc "https://www.python.org/ftp/python/${PYTHON_VERSION%%[a-z]*}/Python-$PYTHON_VERSION.tar.xz.asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$GPG_KEY" 	&& gpg --batch --verify python.tar.xz.asc python.tar.xz 	&& rm -rf "$GNUPGHOME" python.tar.xz.asc 	&& mkdir -p /usr/src/python 	&& tar -xJC /usr/src/python --strip-components=1 -f python.tar.xz 	&& rm python.tar.xz 		&& cd /usr/src/python 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--enable-loadable-sqlite-extensions 		--enable-shared 		--with-system-expat 		--with-system-ffi 		--without-ensurepip 	&& make -j "$(nproc)" 	&& make install 	&& ldconfig 		&& apt-get purge -y --auto-remove $buildDeps 		&& find /usr/local -depth 		\( 			\( -type d -a -name test -o -name tests \) 			-o 			\( -type f -a -name '*.pyc' -o -name '*.pyo' \) 		\) -exec rm -rf '{}' + 	&& rm -rf /usr/src/python
# Wed, 21 Jun 2017 18:46:22 GMT
RUN cd /usr/local/bin 	&& ln -s idle3 idle 	&& ln -s pydoc3 pydoc 	&& ln -s python3 python 	&& ln -s python3-config python-config
# Wed, 21 Jun 2017 18:46:23 GMT
ENV PYTHON_PIP_VERSION=9.0.1
# Wed, 21 Jun 2017 18:46:28 GMT
RUN set -ex; 		wget -O get-pip.py 'https://bootstrap.pypa.io/get-pip.py'; 		python get-pip.py 		--disable-pip-version-check 		--no-cache-dir 		"pip==$PYTHON_PIP_VERSION" 	; 	pip --version; 		find /usr/local -depth 		\( 			\( -type d -a -name test -o -name tests \) 			-o 			\( -type f -a -name '*.pyc' -o -name '*.pyo' \) 		\) -exec rm -rf '{}' +; 	rm -f get-pip.py
# Wed, 21 Jun 2017 18:46:28 GMT
CMD ["python3"]
# Wed, 21 Jun 2017 18:50:04 GMT
RUN mkdir -p /usr/src/app
# Wed, 21 Jun 2017 18:50:05 GMT
WORKDIR /usr/src/app
# Wed, 21 Jun 2017 18:50:06 GMT
ONBUILD COPY requirements.txt /usr/src/app/
# Wed, 21 Jun 2017 18:50:06 GMT
ONBUILD RUN pip install --no-cache-dir -r requirements.txt
# Wed, 21 Jun 2017 18:50:07 GMT
ONBUILD COPY . /usr/src/app
```

-	Layers:
	-	`sha256:9f0706ba7422412cd468804fee456786f88bed94bf9aea6dde2a47f770d19d27`  
		Last Modified: Tue, 20 Jun 2017 20:35:47 GMT  
		Size: 52.6 MB (52614808 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d3942a742d221ef22a0a335c4eebf09e15a36dcfb224b5a2d0cdcc405f374ccb`  
		Last Modified: Wed, 21 Jun 2017 00:33:28 GMT  
		Size: 19.3 MB (19264368 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:62b1123c88f67a9ad43d9bf3f552bbe3352696a674e82712fda785db4f71a655`  
		Last Modified: Wed, 21 Jun 2017 00:34:52 GMT  
		Size: 43.2 MB (43227273 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2dac6294ef18334118b559af1635702b07a71719c31cd022b7351f9392023a34`  
		Last Modified: Wed, 21 Jun 2017 00:36:36 GMT  
		Size: 131.8 MB (131822878 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a7bb658fb0990a639c73970536d0835a6ca0a5b0b1a3648e4dff1acbf04fe3da`  
		Last Modified: Wed, 21 Jun 2017 18:56:18 GMT  
		Size: 2.9 MB (2897400 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a811de274338d32e061939cb5da027948d733fcc247c67de43c7b0c085dcafdb`  
		Last Modified: Wed, 21 Jun 2017 19:18:26 GMT  
		Size: 19.3 MB (19277390 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:771f11f32dc9d5e19445e007c367862c0cee9f6c3f4afbe4df81d84f4ee5dcb1`  
		Last Modified: Wed, 21 Jun 2017 19:18:20 GMT  
		Size: 232.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a16d4d6b543c0041cf44a80dce965df9fabb791c3d388a999d3e93b351cc4f05`  
		Last Modified: Wed, 21 Jun 2017 19:18:20 GMT  
		Size: 1.7 MB (1658890 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ecfe144186d3d9fd5fdca14c6b7459993167c5a3bb8daa43ea2c789d5771b0ea`  
		Last Modified: Wed, 21 Jun 2017 19:25:44 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
