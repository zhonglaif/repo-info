## `adminer:fastcgi`

```console
$ docker pull adminer@sha256:ccc4b046d9171605223de78c089b9c1f4791ce942a8c2de059b85f4d30f6e247
```

-	Platforms:
	-	linux; amd64

### `adminer:fastcgi` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **32.0 MB (31966306 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:a4f196a90051f7e37b85ca02c1c9a4b8899262efd45d6c09bb37d5cf78a83ea5`
-	Entrypoint: `["entrypoint.sh","docker-php-entrypoint"]`
-	Default Command: `["php-fpm"]`

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
# Mon, 19 Jun 2017 22:58:27 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--enable-fpm --with-fpm-user=www-data --with-fpm-group=www-data
# Mon, 19 Jun 2017 22:58:28 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Mon, 19 Jun 2017 22:58:29 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Mon, 19 Jun 2017 22:58:54 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Mon, 19 Jun 2017 23:31:33 GMT
ENV GPG_KEYS=1A4E8B7277C42E53DBA9C7B9BCAA30EA9C0D5763 6E4F6AB321FDC07F2C332E3AC2BF0BC433CFC8B3
# Mon, 19 Jun 2017 23:31:34 GMT
ENV PHP_VERSION=7.0.20
# Mon, 19 Jun 2017 23:31:35 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.0.20.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.0.20.tar.xz.asc/from/this/mirror
# Mon, 19 Jun 2017 23:31:36 GMT
ENV PHP_SHA256=31b9cf1fb83fe3cd82c2f6603a0ae81ae6abacb5286827e362d8f85e68908e0a PHP_MD5=e84615871c1c6dbd0860746a31f3a7c8
# Mon, 19 Jun 2017 23:31:44 GMT
RUN set -xe; 		apk add --no-cache --virtual .fetch-deps 		gnupg 		openssl 	; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apk del .fetch-deps
# Mon, 19 Jun 2017 23:31:45 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Mon, 19 Jun 2017 23:36:35 GMT
RUN set -xe 	&& apk add --no-cache --virtual .build-deps 		$PHPIZE_DEPS 		coreutils 		curl-dev 		libedit-dev 		libxml2-dev 		openssl-dev 		sqlite-dev 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				--with-pcre-regex=/usr 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -perm +0111 -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --no-cache --virtual .php-rundeps $runDeps 		&& apk del .build-deps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Mon, 19 Jun 2017 23:36:38 GMT
COPY multi:1401feee8064a06ad514519ec870939c946ecfdf381c82a90cb2035486938ee9 in /usr/local/bin/ 
# Mon, 19 Jun 2017 23:36:39 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Mon, 19 Jun 2017 23:36:40 GMT
WORKDIR /var/www/html
# Mon, 19 Jun 2017 23:36:41 GMT
RUN set -ex 	&& cd /usr/local/etc 	&& if [ -d php-fpm.d ]; then 		sed 's!=NONE/!=!g' php-fpm.conf.default | tee php-fpm.conf > /dev/null; 		cp php-fpm.d/www.conf.default php-fpm.d/www.conf; 	else 		mkdir php-fpm.d; 		cp php-fpm.conf.default php-fpm.d/www.conf; 		{ 			echo '[global]'; 			echo 'include=etc/php-fpm.d/*.conf'; 		} | tee php-fpm.conf; 	fi 	&& { 		echo '[global]'; 		echo 'error_log = /proc/self/fd/2'; 		echo; 		echo '[www]'; 		echo '; if we send this to /proc/self/fd/1, it never appears'; 		echo 'access.log = /proc/self/fd/2'; 		echo; 		echo 'clear_env = no'; 		echo; 		echo '; Ensure worker stdout and stderr are sent to the main error log.'; 		echo 'catch_workers_output = yes'; 	} | tee php-fpm.d/docker.conf 	&& { 		echo '[global]'; 		echo 'daemonize = no'; 		echo; 		echo '[www]'; 		echo 'listen = [::]:9000'; 	} | tee php-fpm.d/zz-docker.conf
# Mon, 19 Jun 2017 23:36:42 GMT
EXPOSE 9000/tcp
# Mon, 19 Jun 2017 23:36:43 GMT
CMD ["php-fpm"]
# Tue, 20 Jun 2017 17:42:11 GMT
RUN addgroup -S adminer &&	adduser -S -G adminer adminer &&	mkdir -p /var/www/html &&	mkdir -p /var/www/html/plugins-enabled &&	chown -R adminer:adminer /var/www/html
# Tue, 20 Jun 2017 17:42:15 GMT
RUN apk add --no-cache libpq
# Tue, 20 Jun 2017 17:42:33 GMT
RUN set -x &&	apk add --no-cache --virtual .build-deps 	postgresql-dev 	sqlite-dev &&	docker-php-ext-install pdo_mysql pdo_pgsql pdo_sqlite &&	apk del .build-deps
# Tue, 20 Jun 2017 17:42:34 GMT
COPY multi:515cdb7e8ed0278965e56c4b579e89987c42be4b42a309c70682464e9c9451c5 in /var/www/html/ 
# Tue, 20 Jun 2017 17:42:35 GMT
ENV ADMINER_VERSION=4.3.1
# Tue, 20 Jun 2017 17:42:36 GMT
ENV ADMINER_DOWNLOAD_SHA256=71688c5db4d4e504c48c26ec2966ad85e721ef61e0377c5505cfb50b026d5491
# Tue, 20 Jun 2017 17:42:37 GMT
ENV ADMINER_SRC_DOWNLOAD_SHA256=fd016c93bb3bb8e85ed9cf826064584012c4db83f30c4948d701250e29a6d953
# Tue, 20 Jun 2017 17:42:40 GMT
RUN set -x &&	curl -fsSL https://github.com/vrana/adminer/releases/download/v$ADMINER_VERSION/adminer-$ADMINER_VERSION-en.php -o adminer.php &&	echo "$ADMINER_DOWNLOAD_SHA256  adminer.php" |sha256sum -c - &&	curl -fsSL https://github.com/vrana/adminer/archive/v$ADMINER_VERSION.tar.gz -o source.tar.gz &&	echo "$ADMINER_SRC_DOWNLOAD_SHA256  source.tar.gz" |sha256sum -c - &&	tar xzf source.tar.gz --strip-components=1 "adminer-$ADMINER_VERSION/designs/" "adminer-$ADMINER_VERSION/plugins/" &&	rm source.tar.gz
# Tue, 20 Jun 2017 17:42:41 GMT
COPY file:9bd2234bd2d16bb29c56ca41cb797761bce45cf629f48bc911f36b2c284cde46 in /usr/local/bin/ 
# Tue, 20 Jun 2017 17:42:42 GMT
ENTRYPOINT ["entrypoint.sh" "docker-php-entrypoint"]
# Tue, 20 Jun 2017 17:42:43 GMT
USER [adminer]
# Tue, 20 Jun 2017 17:42:44 GMT
CMD ["php-fpm"]
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
	-	`sha256:b5e45ac3b8ea807d262238d26f5e374e4d412512a2d9f37b25a8b828c72e28ff`  
		Last Modified: Tue, 20 Jun 2017 14:59:32 GMT  
		Size: 12.8 MB (12777888 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b80298ec4bfdb8d2332b46151215c792cdd6b137f546d7a2ad8fca2c8e921662`  
		Last Modified: Tue, 20 Jun 2017 14:59:31 GMT  
		Size: 485.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:26c55a54194c6dd12b96859a109df56d08935bdd126ad89822f2a4eb4d77c28b`  
		Last Modified: Tue, 20 Jun 2017 14:59:35 GMT  
		Size: 14.1 MB (14059342 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:368ea13c5beb61aedd62f5d9f37d724ea618dd33e92d26e08ac8f03fda6efec4`  
		Last Modified: Tue, 20 Jun 2017 14:59:30 GMT  
		Size: 2.1 KB (2110 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:416a9a710629a89f54106407b8443dd738c95e68b99b5f7d1bb196618cbc4818`  
		Last Modified: Tue, 20 Jun 2017 14:59:30 GMT  
		Size: 129.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:46ddd7409c8fba2e0170a1eb1ba6838ee560232ccd725f488e1f7dd16673beba`  
		Last Modified: Tue, 20 Jun 2017 14:59:30 GMT  
		Size: 7.7 KB (7652 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1bd5c35b77380d1dbca20f427e633b2f19fd2d330f8369de46c2fd4562661d45`  
		Last Modified: Sat, 24 Jun 2017 05:25:59 GMT  
		Size: 1.4 KB (1382 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:72266bed620430e5b7232ddcdc9fc94d2be1c96268027cd9b4ecfc1f25ea5708`  
		Last Modified: Sat, 24 Jun 2017 05:26:00 GMT  
		Size: 1.2 MB (1210640 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5899109bb4d6a744c8f74a5420e62397e1e00b879f401136c6f86dc116e03685`  
		Last Modified: Sat, 24 Jun 2017 05:25:59 GMT  
		Size: 118.0 KB (117973 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:00ccb651ad401881044a2f9af89596ddc1b67d3d3ef0dc3af6a0a66166887484`  
		Last Modified: Sat, 24 Jun 2017 05:26:00 GMT  
		Size: 1.4 KB (1426 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3e06a305b6fe9f38c5d5dc638d385e2d09828ed354f746adac8ea724ae7f8403`  
		Last Modified: Sat, 24 Jun 2017 05:25:59 GMT  
		Size: 319.1 KB (319102 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f3d4c8e028ba366d70c22b97c66683d5ac4bc316fe37e54837caa399e7b9688d`  
		Last Modified: Sat, 24 Jun 2017 05:25:59 GMT  
		Size: 368.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
