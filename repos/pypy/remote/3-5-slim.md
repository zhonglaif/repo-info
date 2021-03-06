## `pypy:3-5-slim`

```console
$ docker pull pypy@sha256:74dab02a91c8e29d1e04f2954802ac8080e25e8c02e5b7775a02996d8da8ebed
```

-	Platforms:
	-	linux; amd64

### `pypy:3-5-slim` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **62.3 MB (62282811 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a3915b19e37356aa948a0249b073612b2d6ea2b9fcfae9833615c08a2f523311`
-	Default Command: `["pypy3"]`

```dockerfile
# Tue, 20 Jun 2017 20:14:51 GMT
ADD file:ede5a88363e384813454439a3c2b44c445aea433284d040a20e4149bf9f18a5c in / 
# Tue, 20 Jun 2017 20:14:52 GMT
CMD ["bash"]
# Fri, 23 Jun 2017 04:15:49 GMT
ENV PATH=/usr/local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Fri, 23 Jun 2017 04:15:50 GMT
ENV LANG=C.UTF-8
# Fri, 23 Jun 2017 04:16:06 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		libexpat1 		libffi6 		libgdbm3 		libsqlite3-0 	&& rm -rf /var/lib/apt/lists/*
# Fri, 23 Jun 2017 04:16:06 GMT
ENV PYPY_VERSION=5.8.0
# Fri, 23 Jun 2017 04:18:21 GMT
ENV PYPY_SHA256SUM=57d871a7f1135719c138cee4e3533c3275d682a76a40ff668e95150c65923035
# Fri, 23 Jun 2017 04:18:21 GMT
ENV PYTHON_PIP_VERSION=9.0.1
# Fri, 23 Jun 2017 04:18:50 GMT
RUN set -ex; 		fetchDeps=' 		bzip2 		wget 	'; 	apt-get update && apt-get install -y $fetchDeps --no-install-recommends && rm -rf /var/lib/apt/lists/*; 		wget -O pypy.tar.bz2 "https://bitbucket.org/pypy/pypy/downloads/pypy3-v${PYPY_VERSION}-linux64.tar.bz2"; 	echo "$PYPY_SHA256SUM *pypy.tar.bz2" | sha256sum -c; 	tar -xjC /usr/local --strip-components=1 -f pypy.tar.bz2; 	rm pypy.tar.bz2; 		wget -O get-pip.py 'https://bootstrap.pypa.io/get-pip.py'; 		pypy3 get-pip.py 		--disable-pip-version-check 		--no-cache-dir 		"pip==$PYTHON_PIP_VERSION" 	; 	pip --version; 		rm -f get-pip.py; 		apt-get purge -y --auto-remove $fetchDeps
# Fri, 23 Jun 2017 04:18:51 GMT
CMD ["pypy3"]
```

-	Layers:
	-	`sha256:f5cc0ee7a6f68b065e4d0a517a2cbae2e3bffb242b3252b53fe77496adaae514`  
		Last Modified: Tue, 20 Jun 2017 20:38:12 GMT  
		Size: 30.1 MB (30130289 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:06309528502813b1bf8496a0df75f32fe057460ad23ea27cdfdc2f9c4458baac`  
		Last Modified: Sat, 24 Jun 2017 20:39:27 GMT  
		Size: 2.9 MB (2860866 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:012d2b66380d1bf945b2bf39e4a0d5dc36d87bdddc4affdb9494614499d0cddf`  
		Last Modified: Sat, 24 Jun 2017 20:45:55 GMT  
		Size: 29.3 MB (29291656 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
