## `irssi:1-alpine`

```console
$ docker pull irssi@sha256:d27e0609bf76463cce47f096ad3d6d5182b7ff1e0f5070e27e1b5ec4d3bc9cfb
```

-	Platforms:
	-	linux; amd64

### `irssi:1-alpine` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **18.7 MB (18745618 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:21ee51506649d2099d4a8433c36da3181ba69e015cd1c70084ce32d8a1835346`
-	Default Command: `["irssi"]`

```dockerfile
# Mon, 19 Jun 2017 16:58:00 GMT
ADD file:90d7b7a4bad6a39f91c8e1c988e5ee0a7fb9f28b6364b50b6d74dada40258cca in / 
# Mon, 19 Jun 2017 16:58:46 GMT
CMD ["/bin/sh"]
# Mon, 19 Jun 2017 22:30:52 GMT
RUN apk --no-cache add 	ca-certificates
# Mon, 19 Jun 2017 22:30:53 GMT
ENV HOME=/home/user
# Mon, 19 Jun 2017 22:30:56 GMT
RUN adduser -u 1001 -D user 	&& mkdir -p $HOME/.irssi 	&& chown -R user:user $HOME
# Mon, 19 Jun 2017 22:30:57 GMT
ENV LANG=C.UTF-8
# Mon, 19 Jun 2017 22:30:59 GMT
ENV IRSSI_VERSION=1.0.3
# Mon, 19 Jun 2017 22:31:54 GMT
RUN set -x 	&& apk add --no-cache --virtual .build-deps 		autoconf 		automake 		coreutils 		dpkg-dev dpkg 		gcc 		glib-dev 		gnupg 		libc-dev 		libtool 		lynx 		make 		ncurses-dev 		openssl 		openssl-dev 		perl-dev 		pkgconf 		tar 	&& wget "https://github.com/irssi/irssi/releases/download/${IRSSI_VERSION}/irssi-${IRSSI_VERSION}.tar.xz" -O /tmp/irssi.tar.xz 	&& wget "https://github.com/irssi/irssi/releases/download/${IRSSI_VERSION}/irssi-${IRSSI_VERSION}.tar.xz.asc" -O /tmp/irssi.tar.xz.asc 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys 7EE65E3082A5FB06AC7C368D00CCB587DDBEF0E1 	&& gpg --batch --verify /tmp/irssi.tar.xz.asc /tmp/irssi.tar.xz 	&& rm -r "$GNUPGHOME" /tmp/irssi.tar.xz.asc 	&& mkdir -p /usr/src/irssi 	&& tar -xf /tmp/irssi.tar.xz -C /usr/src/irssi --strip-components 1 	&& rm /tmp/irssi.tar.xz 	&& cd /usr/src/irssi 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--enable-true-color 		--with-bot 		--with-proxy 		--with-socks 	&& make -j "$(nproc)" 	&& make install 	&& rm -rf /usr/src/irssi 	&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --no-cache --virtual .irssi-rundeps $runDeps perl-libwww 	&& apk del .build-deps
# Mon, 19 Jun 2017 22:32:05 GMT
WORKDIR /home/user
# Mon, 19 Jun 2017 22:32:06 GMT
USER [user]
# Mon, 19 Jun 2017 22:32:07 GMT
CMD ["irssi"]
```

-	Layers:
	-	`sha256:43d680a959df2b2131639a5e0915cc03e6eeeaba1a22abf3d8881136728bc2ee`  
		Last Modified: Mon, 19 Jun 2017 17:09:10 GMT  
		Size: 2.0 MB (1990164 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4eab8864477d718b9f27677ce564e2962cba1d30e9d0e0dbbc12652143cd046d`  
		Last Modified: Mon, 19 Jun 2017 22:34:43 GMT  
		Size: 351.3 KB (351293 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:201df4cb35e65be87e733c79de43d82b8267554fd7fe6b70c714c0e6051a2c90`  
		Last Modified: Mon, 19 Jun 2017 22:34:44 GMT  
		Size: 1.3 KB (1262 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c3ac0af1501e3778a9224e299522df0819fd3a6d045d934ea0228c5a0aaed7e1`  
		Last Modified: Mon, 19 Jun 2017 22:34:46 GMT  
		Size: 16.4 MB (16402899 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
