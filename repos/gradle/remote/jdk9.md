## `gradle:jdk9`

```console
$ docker pull gradle@sha256:0f00007441db0a76668cd23fc3f8ff13d4383f2e1d46c359ffd9b1519b6f39e2
```

-	Platforms:
	-	linux; amd64

### `gradle:jdk9` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **330.8 MB (330793744 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:c5d874b287e6a2b4f594fa9e56e5d035343f1caa6442e8928e539c6c7714e66c`
-	Default Command: `["gradle"]`

```dockerfile
# Tue, 20 Jun 2017 20:20:10 GMT
ADD file:f1ecd61b58b0033ca44bae2e926027ea8f983690afae114fa2d6909514c1e660 in / 
# Tue, 20 Jun 2017 20:20:11 GMT
CMD ["bash"]
# Tue, 20 Jun 2017 21:12:16 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Tue, 20 Jun 2017 21:15:04 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzr 		git 		mercurial 		openssh-client 		subversion 				procps 	&& rm -rf /var/lib/apt/lists/*
# Fri, 23 Jun 2017 02:43:39 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		bzip2 		unzip 		xz-utils 	&& rm -rf /var/lib/apt/lists/*
# Fri, 23 Jun 2017 02:43:41 GMT
RUN echo 'deb http://deb.debian.org/debian experimental main' > /etc/apt/sources.list.d/experimental.list
# Fri, 23 Jun 2017 02:43:42 GMT
ENV LANG=C.UTF-8
# Fri, 23 Jun 2017 02:43:43 GMT
RUN { 		echo '#!/bin/sh'; 		echo 'set -e'; 		echo; 		echo 'dirname "$(dirname "$(readlink -f "$(which javac || which java)")")"'; 	} > /usr/local/bin/docker-java-home 	&& chmod +x /usr/local/bin/docker-java-home
# Fri, 23 Jun 2017 02:43:45 GMT
RUN ln -svT "/usr/lib/jvm/java-9-openjdk-$(dpkg --print-architecture)" /docker-java-home
# Fri, 23 Jun 2017 02:43:46 GMT
ENV JAVA_HOME=/docker-java-home
# Fri, 23 Jun 2017 02:43:46 GMT
ENV JAVA_VERSION=9~b170
# Fri, 23 Jun 2017 02:43:47 GMT
ENV JAVA_DEBIAN_VERSION=9~b170-2
# Fri, 23 Jun 2017 02:44:23 GMT
RUN set -ex; 		apt-get update; 	apt-get install -y 		openjdk-9-jdk-headless="$JAVA_DEBIAN_VERSION" 	; 	rm -rf /var/lib/apt/lists/*; 		[ "$(readlink -f "$JAVA_HOME")" = "$(docker-java-home)" ]; 		update-alternatives --get-selections | awk -v home="$(readlink -f "$JAVA_HOME")" 'index($3, home) == 1 { $2 = "manual"; print | "update-alternatives --set-selections" }'; 	update-alternatives --query java | grep -q 'Status: manual'
# Fri, 23 Jun 2017 14:56:19 GMT
CMD ["gradle"]
# Fri, 23 Jun 2017 14:56:19 GMT
ENV GRADLE_HOME=/opt/gradle
# Fri, 23 Jun 2017 14:56:20 GMT
ENV GRADLE_VERSION=4.0
# Fri, 23 Jun 2017 14:56:21 GMT
ARG GRADLE_DOWNLOAD_SHA256=56bd2dde29ba2a93903c557da1745cafd72cdd8b6b0b83c05a40ed7896b79dfe
# Fri, 23 Jun 2017 14:56:28 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=56bd2dde29ba2a93903c557da1745cafd72cdd8b6b0b83c05a40ed7896b79dfe
RUN set -o errexit -o nounset 	&& echo "Downloading Gradle" 	&& wget --no-verbose --output-document=gradle.zip "https://services.gradle.org/distributions/gradle-${GRADLE_VERSION}-bin.zip" 		&& echo "Checking download hash" 	&& echo "${GRADLE_DOWNLOAD_SHA256} *gradle.zip" | sha256sum --check - 		&& echo "Installing Gradle" 	&& unzip gradle.zip 	&& rm gradle.zip 	&& mv "gradle-${GRADLE_VERSION}" "${GRADLE_HOME}/" 	&& ln --symbolic "${GRADLE_HOME}/bin/gradle" /usr/bin/gradle 		&& echo "Adding gradle user and group" 	&& groupadd --system --gid 1000 gradle 	&& useradd --system --gid gradle --uid 1000 --shell /bin/bash --create-home gradle 	&& mkdir /home/gradle/.gradle 	&& chown --recursive gradle:gradle /home/gradle
# Fri, 23 Jun 2017 14:56:29 GMT
USER [gradle]
# Fri, 23 Jun 2017 14:56:30 GMT
VOLUME [/home/gradle/.gradle]
# Fri, 23 Jun 2017 14:56:31 GMT
WORKDIR /home/gradle
# Fri, 23 Jun 2017 14:56:45 GMT
# ARGS: GRADLE_DOWNLOAD_SHA256=56bd2dde29ba2a93903c557da1745cafd72cdd8b6b0b83c05a40ed7896b79dfe
RUN set -o errexit -o nounset 	&& echo "Testing Gradle installation" 	&& gradle --version
```

-	Layers:
	-	`sha256:f836f6e9bd1ef868da87e8fdcd0443c718f899e6da05effb84bb370ddc2c039f`  
		Last Modified: Tue, 20 Jun 2017 20:43:38 GMT  
		Size: 45.2 MB (45198775 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:866f097affeb6c2272cae889af2ad71060e7e1e31baef46758f838a060c70da5`  
		Last Modified: Wed, 21 Jun 2017 00:37:41 GMT  
		Size: 11.2 MB (11232752 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d18aed9d248a8afaf498a6787ee843c48d241dc80091cf7efbc33de3acb70820`  
		Last Modified: Wed, 21 Jun 2017 00:38:28 GMT  
		Size: 50.9 MB (50944155 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aafdc1ff995f06118d33f415857ceb8d4e24d0b7c32b5426088056d5140ff119`  
		Last Modified: Sat, 24 Jun 2017 17:11:53 GMT  
		Size: 655.3 KB (655296 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3757ef3932c594ddbc6d58d598e052b19c47c5fc06f27abd582f354e3c19c8ff`  
		Last Modified: Sat, 24 Jun 2017 17:11:53 GMT  
		Size: 214.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:029d9b23b6fb14a96fd7eee8757d8c1ea5f845cd678c9bf2c3810824e4b36615`  
		Last Modified: Sat, 24 Jun 2017 17:11:52 GMT  
		Size: 241.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:204e75e7398e0bfee00671670df45422320717110fdf1e09cdc73316ea356e09`  
		Last Modified: Sat, 24 Jun 2017 17:11:51 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ff02fd93ff0fa3cfe531b4acca7890e817537957965f773cd1b30bc6d8f59f7a`  
		Last Modified: Sat, 24 Jun 2017 17:12:10 GMT  
		Size: 155.3 MB (155259068 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:42ad1462ab481a75277158577ac2e09118f08f8f3f4cebd6cf49e91e4da59aa5`  
		Last Modified: Sun, 25 Jun 2017 09:28:53 GMT  
		Size: 67.5 MB (67502974 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:71cd29372b69f391c8ca81ba18ad0ec952586e644281af4c6a3333e6f31b407d`  
		Last Modified: Sun, 25 Jun 2017 09:28:47 GMT  
		Size: 139.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
