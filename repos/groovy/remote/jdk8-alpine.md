## `groovy:jdk8-alpine`

```console
$ docker pull groovy@sha256:08125eb4b14eddd87dd058fa8f6778e148c8351aebb69892e76825bd0db64fb7
```

-	Platforms:
	-	linux; amd64

### `groovy:jdk8-alpine` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **109.9 MB (109923296 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:4be55a9c3ca12392cea835fb23aad1cd85be8ffae1cf008fdf58e9243cd836a0`
-	Default Command: `["groovysh"]`

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
# Tue, 20 Jun 2017 18:55:50 GMT
CMD ["groovysh"]
# Tue, 20 Jun 2017 18:55:51 GMT
ENV GROOVY_HOME=/opt/groovy
# Tue, 20 Jun 2017 18:55:52 GMT
ENV GROOVY_VERSION=2.4.11
# Tue, 20 Jun 2017 18:56:05 GMT
RUN set -o errexit -o nounset 	&& echo "Installing dependencies" 	&& apk add --no-cache 		bash 		&& echo "Installing build dependencies" 	&& apk add --no-cache --virtual .build-deps 		ca-certificates 		gnupg 		openssl 		unzip 		&& echo "Downloading Groovy" 	&& wget -O groovy.zip "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip" 		&& echo "Importing keys listed in http://www.apache.org/dist/groovy/KEYS from key server" 	&& export GNUPGHOME="$(mktemp -d)" 	&& for key in 		"7FAA0F2206DE228F0DB01AD741321490758AAD6F" 		"331224E1D7BE883D16E8A685825C06C827AF6B66" 		"34441E504A937F43EB0DAEF96A65176A0FB1CD0B" 		"9A810E3B766E089FFB27C70F11B595CEDC4AEBB5" 	; do 		for server in 			ha.pool.sks-keyservers.net 			hkp://p80.pool.sks-keyservers.net:80 			pgp.mit.edu 		; do 			echo "  Trying ${server}"; 			if gpg --keyserver "${server}" --recv-keys "${key}"; then 				break; 			fi; 		done; 	done; 	if [ $(gpg --list-keys | grep -c "pub ") -ne 4 ]; then 		echo "ERROR: Failed to fetch GPG keys" >&2; 		exit 1; 	fi 		&& echo "Checking download signature" 	&& wget -O groovy.zip.asc "https://dist.apache.org/repos/dist/release/groovy/${GROOVY_VERSION}/distribution/apache-groovy-binary-${GROOVY_VERSION}.zip.asc" 	&& gpg --batch --verify groovy.zip.asc groovy.zip 	&& rm -rf "${GNUPGHOME}" 	&& rm groovy.zip.asc 		&& echo "Installing Groovy" 	&& unzip groovy.zip 	&& rm groovy.zip 	&& mkdir /opt 	&& mv "groovy-${GROOVY_VERSION}" "${GROOVY_HOME}/" 	&& ln -s "${GROOVY_HOME}/bin/grape" /usr/bin/grape 	&& ln -s "${GROOVY_HOME}/bin/groovy" /usr/bin/groovy 	&& ln -s "${GROOVY_HOME}/bin/groovyc" /usr/bin/groovyc 	&& ln -s "${GROOVY_HOME}/bin/groovyConsole" /usr/bin/groovyConsole 	&& ln -s "${GROOVY_HOME}/bin/groovydoc" /usr/bin/groovydoc 	&& ln -s "${GROOVY_HOME}/bin/groovysh" /usr/bin/groovysh 	&& ln -s "${GROOVY_HOME}/bin/java2groovy" /usr/bin/java2groovy 		&& echo "Applying workaround for https://issues.apache.org/jira/browse/GROOVY-7906" 	&& sed -i "s|#!/bin/sh|#!/bin/bash|" "${GROOVY_HOME}/bin/grape" 	&& sed -i "s|#!/bin/sh|#!/bin/bash|" "${GROOVY_HOME}/bin/groovy" 	&& sed -i "s|#!/bin/sh|#!/bin/bash|" "${GROOVY_HOME}/bin/groovyc" 	&& sed -i "s|#!/bin/sh|#!/bin/bash|" "${GROOVY_HOME}/bin/groovyConsole" 	&& sed -i "s|#!/bin/sh|#!/bin/bash|" "${GROOVY_HOME}/bin/groovydoc" 	&& sed -i "s|#!/bin/sh|#!/bin/bash|" "${GROOVY_HOME}/bin/groovysh" 	&& sed -i "s|#!/bin/sh|#!/bin/bash|" "${GROOVY_HOME}/bin/java2groovy" 		&& echo "Cleaning up build dependencies" 	&& apk del .build-deps 		&& echo "Adding groovy user and group" 	&& addgroup -S -g 1000 groovy 	&& adduser -D -S -G groovy -u 1000 -s /bin/ash groovy 	&& mkdir -p /home/groovy/.groovy/grapes 	&& chown -R groovy:groovy /home/groovy
# Tue, 20 Jun 2017 18:56:18 GMT
USER [groovy]
# Tue, 20 Jun 2017 18:56:19 GMT
VOLUME [/home/groovy/.groovy/grapes]
# Tue, 20 Jun 2017 18:56:20 GMT
WORKDIR /home/groovy
# Tue, 20 Jun 2017 18:56:45 GMT
RUN set -o errexit -o nounset 	&& echo "Testing Groovy installation" 	&& groovy --version
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
	-	`sha256:175c9f79afb934445c1dd1ceca1d07f8aeb36ddf150e9443d34d373721653f48`  
		Last Modified: Sun, 25 Jun 2017 10:17:51 GMT  
		Size: 37.9 MB (37882528 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0544158e959742bf4e3c22062732b2e27a70397d79fe6fe7f4950cf8f6fdc09e`  
		Last Modified: Sun, 25 Jun 2017 10:17:47 GMT  
		Size: 140.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
