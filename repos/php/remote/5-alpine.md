## `php:5-alpine`

```console
$ docker pull php@sha256:68d50dd481a474b6d6df9d9a53fa91c981cc3209c34f6c771cdd13a858465813
```

-	Platforms:
	-	linux; amd64

### `php:5-alpine` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **22.5 MB (22488256 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:613ce68fe96270d078740c759c330aabfdf7557afd32c2a0cda54cd561a396be`
-	Entrypoint: `["docker-php-entrypoint"]`
-	Default Command: `["php","-a"]`

```dockerfile
# Mon, 19 Jun 2017 16:54:49 GMT
ADD file:cf1b74f7af8abcfbe58722467970b39b3ef9c8343665ef2d175f058f734a7f6e in / 
# Mon, 19 Jun 2017 16:55:12 GMT
CMD ["/bin/sh"]
# Mon, 19 Jun 2017 22:46:44 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev dpkg 		file 		g++ 		gcc 		libc-dev 		make 		pcre-dev 		pkgconf 		re2c
# Mon, 19 Jun 2017 22:46:48 GMT
RUN apk add --no-cache --virtual .persistent-deps 		ca-certificates 		curl 		tar 		xz
# Mon, 19 Jun 2017 22:46:50 GMT
RUN set -x 	&& addgroup -g 82 -S www-data 	&& adduser -u 82 -D -S -G www-data www-data
# Mon, 19 Jun 2017 22:46:52 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Mon, 19 Jun 2017 22:46:53 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Mon, 19 Jun 2017 22:46:55 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Mon, 19 Jun 2017 22:46:56 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Mon, 19 Jun 2017 22:46:57 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Mon, 19 Jun 2017 23:51:12 GMT
ENV GPG_KEYS=0BD78B5F97500D450838F95DFE857D9A90D90EC1 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Mon, 19 Jun 2017 23:51:13 GMT
ENV PHP_VERSION=5.6.30
# Mon, 19 Jun 2017 23:51:14 GMT
ENV PHP_URL=https://secure.php.net/get/php-5.6.30.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-5.6.30.tar.xz.asc/from/this/mirror
# Mon, 19 Jun 2017 23:51:15 GMT
ENV PHP_SHA256=a363185c786432f75e3c7ff956b49c3369c3f6906a6b10459f8d1ddc22f70805 PHP_MD5=68753955a8964ae49064c6424f81eb3e
# Mon, 19 Jun 2017 23:51:25 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		openssl 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Mon, 19 Jun 2017 23:51:27 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Mon, 19 Jun 2017 23:55:36 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libxml2-dev 		openssl-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				--with-pcre-regex=/usr 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Mon, 19 Jun 2017 23:55:40 GMT
COPY multi:a2a7a051ede432913cebaf532ceb4314b5a5c79d08a5a33e42d3563097520588 in /usr/local/bin/ 
# Mon, 19 Jun 2017 23:55:41 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Mon, 19 Jun 2017 23:55:42 GMT
CMD ["php" "-a"]
```

-	Layers:
	-	`sha256:acb474fa89565f9f79ee5ddaaaad12c59954e2694d005ec120d6b11825bad191`  
		Last Modified: Mon, 19 Jun 2017 17:06:54 GMT  
		Size: 2.4 MB (2385060 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:dabaad5e9926028cc146660baf944edb2684f3920faf2156ebf44ed92cf44133`  
		Last Modified: Tue, 20 Jun 2017 14:35:02 GMT  
		Size: 1.1 MB (1081308 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f33401fdb9aa65db74d315ebb85f68ae379f28e026bdbc5b9ce92224bccefc95`  
		Last Modified: Tue, 20 Jun 2017 14:34:59 GMT  
		Size: 1.3 KB (1276 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:bad83aa6d5dabea040da9162ce26e4da6e8212756b4f1279068078313bfa16d6`  
		Last Modified: Tue, 20 Jun 2017 14:34:59 GMT  
		Size: 165.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ad485f94e81228d9e9b24be738cc2f9c835f0b3b104ac3377a8def392ea01436`  
		Last Modified: Tue, 20 Jun 2017 15:05:03 GMT  
		Size: 12.6 MB (12623136 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5414fdefd64a4fa785d93dac12b9b8ebeaa0ffeeb15b595deabb6bbfa0c04e18`  
		Last Modified: Tue, 20 Jun 2017 15:05:00 GMT  
		Size: 486.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f5ee2b725e565e325b63ac4c5c59f833ca6b2cc7300e551b84f29a16526b6ad3`  
		Last Modified: Tue, 20 Jun 2017 15:05:03 GMT  
		Size: 6.4 MB (6394718 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:2ec007296ca40c6e948f69a2e9c577b9a392908739133d96d7f4ed19d8c7aad0`  
		Last Modified: Tue, 20 Jun 2017 15:04:59 GMT  
		Size: 2.1 KB (2107 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
