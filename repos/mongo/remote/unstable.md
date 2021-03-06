## `mongo:unstable`

```console
$ docker pull mongo@sha256:618b9d9c5ea11b5a2688d06a5f6f5d2add59c3bff63166f39fb6318b003de7a1
```

-	Platforms:
	-	linux; amd64

### `mongo:unstable` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **128.7 MB (128700084 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:2c8d3153eeef5ca8e7866e8764d26e47865dcfc3c699ff232a80a2697116f8c9`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["mongod","--bind_ip_all"]`

```dockerfile
# Tue, 20 Jun 2017 20:14:51 GMT
ADD file:ede5a88363e384813454439a3c2b44c445aea433284d040a20e4149bf9f18a5c in / 
# Tue, 20 Jun 2017 20:14:52 GMT
CMD ["bash"]
# Thu, 22 Jun 2017 20:46:35 GMT
RUN groupadd -r mongodb && useradd -r -g mongodb mongodb
# Thu, 22 Jun 2017 20:49:42 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		ca-certificates 		jq 		numactl 	&& rm -rf /var/lib/apt/lists/*
# Thu, 22 Jun 2017 20:49:43 GMT
ENV GOSU_VERSION=1.7
# Thu, 22 Jun 2017 20:49:59 GMT
RUN set -x 	&& apt-get update && apt-get install -y --no-install-recommends wget && rm -rf /var/lib/apt/lists/* 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true 	&& apt-get purge -y --auto-remove wget
# Thu, 22 Jun 2017 20:50:00 GMT
RUN mkdir /docker-entrypoint-initdb.d
# Thu, 22 Jun 2017 20:51:22 GMT
ENV GPG_KEYS=2930ADAE8CAF5059EE73BB4B58712A2291FA4AD5
# Thu, 22 Jun 2017 20:51:25 GMT
RUN set -ex; 	export GNUPGHOME="$(mktemp -d)"; 	for key in $GPG_KEYS; do 		gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 	done; 	gpg --export $GPG_KEYS > /etc/apt/trusted.gpg.d/mongodb.gpg; 	rm -r "$GNUPGHOME"; 	apt-key list
# Thu, 22 Jun 2017 20:51:26 GMT
ARG MONGO_PACKAGE=mongodb-org-unstable
# Thu, 22 Jun 2017 20:51:26 GMT
ARG MONGO_REPO=repo.mongodb.org
# Thu, 22 Jun 2017 20:51:27 GMT
ENV MONGO_PACKAGE=mongodb-org-unstable MONGO_REPO=repo.mongodb.org
# Thu, 22 Jun 2017 20:51:28 GMT
ENV MONGO_MAJOR=3.5
# Thu, 22 Jun 2017 20:51:29 GMT
ENV MONGO_VERSION=3.5.9
# Thu, 22 Jun 2017 20:51:30 GMT
RUN echo "deb http://$MONGO_REPO/apt/debian jessie/${MONGO_PACKAGE%-unstable}/$MONGO_MAJOR main" | tee "/etc/apt/sources.list.d/${MONGO_PACKAGE%-unstable}.list"
# Thu, 22 Jun 2017 20:51:49 GMT
RUN set -x 	&& apt-get update 	&& apt-get install -y 		${MONGO_PACKAGE}=$MONGO_VERSION 		${MONGO_PACKAGE}-server=$MONGO_VERSION 		${MONGO_PACKAGE}-shell=$MONGO_VERSION 		${MONGO_PACKAGE}-mongos=$MONGO_VERSION 		${MONGO_PACKAGE}-tools=$MONGO_VERSION 	&& rm -rf /var/lib/apt/lists/* 	&& rm -rf /var/lib/mongodb 	&& mv /etc/mongod.conf /etc/mongod.conf.orig
# Thu, 22 Jun 2017 20:51:51 GMT
RUN mkdir -p /data/db /data/configdb 	&& chown -R mongodb:mongodb /data/db /data/configdb
# Thu, 22 Jun 2017 20:51:51 GMT
VOLUME [/data/db /data/configdb]
# Thu, 22 Jun 2017 20:51:53 GMT
COPY file:2693b7d26a4d17558bb637a0ad2c43c3be68788377b0e9eb105cd67726d4b645 in /usr/local/bin/ 
# Thu, 22 Jun 2017 20:51:54 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Thu, 22 Jun 2017 20:51:54 GMT
EXPOSE 27017/tcp
# Thu, 22 Jun 2017 20:51:55 GMT
CMD ["mongod" "--bind_ip_all"]
```

-	Layers:
	-	`sha256:f5cc0ee7a6f68b065e4d0a517a2cbae2e3bffb242b3252b53fe77496adaae514`  
		Last Modified: Tue, 20 Jun 2017 20:38:12 GMT  
		Size: 30.1 MB (30130289 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d99b18c5f0ce9c19f6a53a4fe962536e120578dd2739e500b485bad5aa6b5d8c`  
		Last Modified: Thu, 22 Jun 2017 20:53:43 GMT  
		Size: 2.1 KB (2058 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2abe504e54922f1683c3b7c5bc14d2bb9e5f2199784dd8e3e03fa26e0b8bb02d`  
		Last Modified: Thu, 22 Jun 2017 20:55:02 GMT  
		Size: 2.4 MB (2399182 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:010336760fd558342d46bcb45fd9e064be8f2e65e3f38cc2fed4e83af3c8f596`  
		Last Modified: Thu, 22 Jun 2017 20:55:01 GMT  
		Size: 881.7 KB (881712 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1bebc569a09bda60617428252c336fc162f14b774d1233d20e81fd8986ddbab5`  
		Last Modified: Thu, 22 Jun 2017 20:55:01 GMT  
		Size: 115.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4b9e8d47828ff0174cadb0a3e8ef6124f2ec31a5b323ed40ed64f752a5814357`  
		Last Modified: Thu, 22 Jun 2017 20:57:09 GMT  
		Size: 1.4 KB (1436 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2f1cdb6d2abf7625200e4ff1268e1adc7cf698be1d9c3240e7c5dbced66e3793`  
		Last Modified: Thu, 22 Jun 2017 20:57:09 GMT  
		Size: 223.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d9aeab0ad068d448a1495f4c80a379cdaab135392eaf97c5abfa39f84db04d82`  
		Last Modified: Thu, 22 Jun 2017 20:57:29 GMT  
		Size: 95.3 MB (95281760 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a9718f708e7839bb1144b79a214c7905d46498bdac6b182dabdd980cbcab69b9`  
		Last Modified: Thu, 22 Jun 2017 20:57:09 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:916ca7d8ca824a38929ad36bd6c58d6cdb622fb3f7dc08cdbae7c60ed4fbc943`  
		Last Modified: Thu, 22 Jun 2017 20:57:09 GMT  
		Size: 3.2 KB (3170 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
