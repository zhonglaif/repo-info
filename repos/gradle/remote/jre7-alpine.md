## `gradle:jre7-alpine`

```console
$ docker pull gradle@sha256:6ef0f922447832d389895bc4befd499aff9d37834dbfb329eb9faac34356dc2d
```

-	Platforms:
	-	linux; amd64

### `gradle:jre7-alpine` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **132.1 MB (132067801 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:bbe1583d79201ca8f27f704d12184f6a3576ba38c4fa69932c84be2f51fbce57`
-	Default Command: `["gradle"]`

```dockerfile
# Mon, 19 Jun 2017 16:58:00 GMT
ADD file:90d7b7a4bad6a39f91c8e1c988e5ee0a7fb9f28b6364b50b6d74dada40258cca in / 
# Mon, 19 Jun 2017 16:58:46 GMT
CMD ["/bin/sh"]
# Mon, 19 Jun 2017 22:32:06 GMT
ENV LANG=C.UTF-8
# Mon, 19 Jun 2017 22:32:08 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Mon, 19 Jun 2017 22:33:48 GMT
ENV JAVA_HOME=/usr/lib/jvm/java-1.7-openjdk/jre
# Mon, 19 Jun 2017 22:33:48 GMT
ENV PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/lib/jvm/java-1.7-openjdk/jre/bin:/usr/lib/jvm/java-1.7-openjdk/bin
# Mon, 19 Jun 2017 22:33:49 GMT
ENV JAVA_VERSION=7u131
# Mon, 19 Jun 2017 22:33:50 GMT
ENV JAVA_ALPINE_VERSION=7.131.2.6.9-r1
# Mon, 19 Jun 2017 22:34:23 GMT
RUN set -x 	&& apk add --no-cache 		openjdk7-jre="$JAVA_ALPINE_VERSION" 	&& [ "$JAVA_HOME" = "$(docker-java-home)" ]
# Tue, 20 Jun 2017 18:45:28 GMT
CMD ["gradle"]
# Tue, 20 Jun 2017 18:45:29 GMT
ENV GRADLE_HOME=/opt/gradle
# Tue, 20 Jun 2017 18:45:30 GMT
ENV GRADLE_VERSION=4.0
# Tue, 20 Jun 2017 18:45:30 GMT
ARG GRADLE_DOWNLOAD_SHA256=56bd2dde29ba2a93903c557da1745cafd72cdd8b6b0b83c05a40ed7896b79dfe
# Tue, 20 Jun 2017 18:46:07 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=56bd2dde29ba2a93903c557da1745cafd72cdd8b6b0b83c05a40ed7896b79dfe
RUN set -o errexit -o nounset 	&& echo "Installing dependencies" 	&& apk add --no-cache 		bash 		libstdc++ 		&& echo "Installing build dependencies" 	&& apk add --no-cache --virtual .build-deps 		ca-certificates 		openssl 		unzip 		&& echo "Downloading Gradle" 	&& wget -O gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum -c - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mkdir /opt 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln -s "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& apk del .build-deps 		&& echo "Adding gradle user and group" 	&& addgroup -S -g 1000 gradle 	&& adduser -D -S -G gradle -u 1000 -s /bin/ash gradle 	&& mkdir /home/gradle/.gradle 	&& chown -R gradle:gradle /home/gradle
# Tue, 20 Jun 2017 18:46:21 GMT
USER [gradle]
# Tue, 20 Jun 2017 18:46:22 GMT
VOLUME [/home/gradle/.gradle]
# Tue, 20 Jun 2017 18:46:23 GMT
WORKDIR /home/gradle
# Tue, 20 Jun 2017 18:46:52 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=56bd2dde29ba2a93903c557da1745cafd72cdd8b6b0b83c05a40ed7896b79dfe
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
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
	-	`sha256:a5f47a67697276d89884397784cfb1845ff4bd1bb20a75f965110a46fb14ddaa`  
		Last Modified: Tue, 20 Jun 2017 20:57:53 GMT  
		Size: 61.1 MB (61130312 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6e0e55c90ca00b0bc4a562e98a6533fdbebfbf41f9f92200416b344191abb7bf`  
		Last Modified: Sun, 25 Jun 2017 09:18:03 GMT  
		Size: 68.9 MB (68946957 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bf971654329bcd03ad982d35764cb52b4b541194c4c5985548aba62654876739`  
		Last Modified: Sun, 25 Jun 2017 09:17:56 GMT  
		Size: 138.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
