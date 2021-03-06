## `orientdb:latest`

```console
$ docker pull orientdb@sha256:2b8199000ebb2ca1ab2909580e9128116b658b36c8369897f4be1ef65d443246
```

-	Platforms:
	-	linux; amd64

### `orientdb:latest` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **115.5 MB (115460623 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:534132d8f5d4584589a0ede8cdc3880463d70dfd38b27035313c0a2d0b0f32dd`
-	Default Command: `["server.sh"]`

```dockerfile
# Mon, 19 Jun 2017 16:58:00 GMT
ADD file:90d7b7a4bad6a39f91c8e1c988e5ee0a7fb9f28b6364b50b6d74dada40258cca in / 
# Mon, 19 Jun 2017 16:58:46 GMT
CMD ["/bin/sh"]
# Mon, 19 Jun 2017 22:32:06 GMT
ENV LANG=C.UTF-8
# Mon, 19 Jun 2017 22:32:08 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Mon, 19 Jun 2017 22:35:27 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.8-openjdk
# Mon, 19 Jun 2017 22:35:28 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Mon, 19 Jun 2017 22:35:29 GMT
ENV JAVA_VERSION=8u131
# Mon, 19 Jun 2017 22:35:29 GMT
ENV JAVA_ALPINE_VERSION=8.131.11-r2
# Mon, 19 Jun 2017 22:36:00 GMT
RUN set -x 	&& apk add --no-cache 		openjdk8="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Mon, 19 Jun 2017 22:38:21 GMT
MAINTAINER OrientDB LTD (info@orientdb.com)
# Mon, 19 Jun 2017 22:41:19 GMT
ARG ORIENTDB_DOWNLOAD_SERVER
# Mon, 19 Jun 2017 22:41:44 GMT
ENV ORIENTDB_VERSION=2.2.22
# Mon, 19 Jun 2017 22:41:45 GMT
ENV ORIENTDB_DOWNLOAD_MD5=e882a61a79d93a40fa1a38f8e8845a0f
# Mon, 19 Jun 2017 22:41:46 GMT
ENV ORIENTDB_DOWNLOAD_SHA1=c9ef48dc96a01daf9a2841b9340d31b9567f7691
# Mon, 19 Jun 2017 22:41:47 GMT
ENV ORIENTDB_DOWNLOAD_URL=http://central.maven.org/maven2/com/orientechnologies/orientdb-community/2.2.22/orientdb-community-2.2.22.tar.gz
# Mon, 19 Jun 2017 22:41:52 GMT
RUN apk add --update tar curl     && rm -rf /var/cache/apk/*
# Mon, 19 Jun 2017 22:41:57 GMT
RUN mkdir /orientdb &&   wget  $ORIENTDB_DOWNLOAD_URL   && echo "$ORIENTDB_DOWNLOAD_MD5 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | md5sum -c -   && echo "$ORIENTDB_DOWNLOAD_SHA1 *orientdb-community-$ORIENTDB_VERSION.tar.gz" | sha1sum -c -   && tar -xvzf orientdb-community-$ORIENTDB_VERSION.tar.gz -C /orientdb --strip-components=1   && rm orientdb-community-$ORIENTDB_VERSION.tar.gz   && rm -rf /orientdb/databases/*
# Mon, 19 Jun 2017 22:41:59 GMT
ENV PATH=/orientdb/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.8-openjdk/jre/bin:/usr/lib/jvm/java-1.8-openjdk/bin
# Mon, 19 Jun 2017 22:42:01 GMT
VOLUME [/orientdb/backup /orientdb/databases /orientdb/config]
# Mon, 19 Jun 2017 22:42:03 GMT
WORKDIR /orientdb
# Mon, 19 Jun 2017 22:42:04 GMT
EXPOSE 2424/tcp
# Mon, 19 Jun 2017 22:42:05 GMT
EXPOSE 2480/tcp
# Mon, 19 Jun 2017 22:42:06 GMT
CMD ["server.sh"]
```

-	Layers:
	-	`sha256:43d680a959df2b2131639a5e0915cc03e6eeeaba1a22abf3d8881136728bc2ee`  
		Last Modified: Mon, 19 Jun 2017 17:09:10 GMT  
		Size: 2.0 MB (1990164 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6e40d7806c43a66123981ef727087e5dabea9084a00cd28bccd782bd5bd319a4`  
		Last Modified: Tue, 20 Jun 2017 20:52:30 GMT  
		Size: 230.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:35d6fbc2ab6eafc4e238b99bdbd470d39d99dffe9d70123777c74469211364bb`  
		Last Modified: Tue, 20 Jun 2017 21:04:41 GMT  
		Size: 70.1 MB (70050234 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:87917c268a1f489468c4f5e93d6d5838d09913da373e448326ae847ebc84c2e6`  
		Last Modified: Sat, 24 Jun 2017 17:35:52 GMT  
		Size: 646.6 KB (646643 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ed5e590d98fb6c4fb7f652abc01b12d4af5935df1f31cf0a56009acc08399982`  
		Last Modified: Sat, 24 Jun 2017 17:35:56 GMT  
		Size: 42.8 MB (42773352 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
