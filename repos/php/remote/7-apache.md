## `php:7-apache`

```console
$ docker pull php@sha256:ea895f2654b77821296299bc7361c8c2ea1f5e0a35201453e4b36393e3807e76
```

-	Platforms:
	-	linux; amd64

### `php:7-apache` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **164.4 MB (164357771 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:0caa2bf87d65150ab8bd662c408e72ade27b81399661a8ad1baea67754c809ff`
-	Entrypoint: `["docker-php-entrypoint"]`
-	Default Command: `["apache2-foreground"]`

```dockerfile
# Tue, 20 Jun 2017 20:13:32 GMT
ADD file:9c48682ff75c756544d4491472081a078edf5dd0bb5038d1cb850a1f9c480e3e in / 
# Tue, 20 Jun 2017 20:13:34 GMT
CMD ["bash"]
# Wed, 21 Jun 2017 16:05:06 GMT
ENV PHPIZE_DEPS=autoconf 		dpkg-dev 		file 		g++ 		gcc 		libc-dev 		libpcre3-dev 		make 		pkg-config 		re2c
# Wed, 21 Jun 2017 16:05:39 GMT
RUN apt-get update && apt-get install -y 		$PHPIZE_DEPS 		ca-certificates 		curl 		libedit2 		libsqlite3-0 		libxml2 		xz-utils 	--no-install-recommends && rm -r /var/lib/apt/lists/*
# Wed, 21 Jun 2017 16:05:40 GMT
ENV PHP_INI_DIR=/usr/local/etc/php
# Wed, 21 Jun 2017 16:05:42 GMT
RUN mkdir -p $PHP_INI_DIR/conf.d
# Wed, 21 Jun 2017 16:10:12 GMT
RUN apt-get update 	&& apt-get install -y --no-install-recommends 		apache2 	&& rm -rf /var/lib/apt/lists/*
# Wed, 21 Jun 2017 16:10:13 GMT
ENV APACHE_CONFDIR=/etc/apache2
# Wed, 21 Jun 2017 16:10:13 GMT
ENV APACHE_ENVVARS=/etc/apache2/envvars
# Wed, 21 Jun 2017 16:10:15 GMT
RUN set -ex 		&& sed -ri 's/^export ([^=]+)=(.*)$/: ${\1:=\2}\nexport \1/' "$APACHE_ENVVARS" 		&& . "$APACHE_ENVVARS" 	&& for dir in 		"$APACHE_LOCK_DIR" 		"$APACHE_RUN_DIR" 		"$APACHE_LOG_DIR" 		/var/www/html 	; do 		rm -rvf "$dir" 		&& mkdir -p "$dir" 		&& chown -R "$APACHE_RUN_USER:$APACHE_RUN_GROUP" "$dir"; 	done
# Wed, 21 Jun 2017 16:10:16 GMT
RUN a2dismod mpm_event && a2enmod mpm_prefork
# Wed, 21 Jun 2017 16:10:18 GMT
RUN set -ex 	&& . "$APACHE_ENVVARS" 	&& ln -sfT /dev/stderr "$APACHE_LOG_DIR/error.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/access.log" 	&& ln -sfT /dev/stdout "$APACHE_LOG_DIR/other_vhosts_access.log"
# Wed, 21 Jun 2017 16:10:19 GMT
RUN { 		echo '<FilesMatch \.php$>'; 		echo '\tSetHandler application/x-httpd-php'; 		echo '</FilesMatch>'; 		echo; 		echo 'DirectoryIndex disabled'; 		echo 'DirectoryIndex index.php index.html'; 		echo; 		echo '<Directory /var/www/>'; 		echo '\tOptions -Indexes'; 		echo '\tAllowOverride All'; 		echo '</Directory>'; 	} | tee "$APACHE_CONFDIR/conf-available/docker-php.conf" 	&& a2enconf docker-php
# Wed, 21 Jun 2017 16:10:20 GMT
ENV PHP_EXTRA_BUILD_DEPS=apache2-dev
# Wed, 21 Jun 2017 16:10:21 GMT
ENV PHP_EXTRA_CONFIGURE_ARGS=--with-apxs2
# Wed, 21 Jun 2017 16:10:22 GMT
ENV PHP_CFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Wed, 21 Jun 2017 16:10:23 GMT
ENV PHP_CPPFLAGS=-fstack-protector-strong -fpic -fpie -O2
# Wed, 21 Jun 2017 16:10:23 GMT
ENV PHP_LDFLAGS=-Wl,-O1 -Wl,--hash-style=both -pie
# Wed, 21 Jun 2017 16:10:24 GMT
ENV GPG_KEYS=A917B1ECDA84AEC2B568FED6F50ABC807BD5DCD0 528995BFEDFBA7191D46839EF9BA0ADA31CBD89E
# Wed, 21 Jun 2017 16:10:25 GMT
ENV PHP_VERSION=7.1.6
# Wed, 21 Jun 2017 16:10:26 GMT
ENV PHP_URL=https://secure.php.net/get/php-7.1.6.tar.xz/from/this/mirror PHP_ASC_URL=https://secure.php.net/get/php-7.1.6.tar.xz.asc/from/this/mirror
# Wed, 21 Jun 2017 16:10:26 GMT
ENV PHP_SHA256=01584dc521ab7ec84b502b61952f573652fe6aa00c18d6d844fb9209f14b245b PHP_MD5=eafc7a79cc8cc62c9292c96f9c9ccf90
# Wed, 21 Jun 2017 16:10:39 GMT
RUN set -xe; 		fetchDeps=' 		wget 	'; 	apt-get update; 	apt-get install -y --no-install-recommends $fetchDeps; 	rm -rf /var/lib/apt/lists/*; 		mkdir -p /usr/src; 	cd /usr/src; 		wget -O php.tar.xz "$PHP_URL"; 		if [ -n "$PHP_SHA256" ]; then 		echo "$PHP_SHA256 *php.tar.xz" | sha256sum -c -; 	fi; 	if [ -n "$PHP_MD5" ]; then 		echo "$PHP_MD5 *php.tar.xz" | md5sum -c -; 	fi; 		if [ -n "$PHP_ASC_URL" ]; then 		wget -O php.tar.xz.asc "$PHP_ASC_URL"; 		export GNUPGHOME="$(mktemp -d)"; 		for key in $GPG_KEYS; do 			gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key"; 		done; 		gpg --batch --verify php.tar.xz.asc php.tar.xz; 		rm -r "$GNUPGHOME"; 	fi; 		apt-get purge -y --auto-remove $fetchDeps
# Wed, 21 Jun 2017 16:10:40 GMT
COPY file:207c686e3fed4f71f8a7b245d8dcae9c9048d276a326d82b553c12a90af0c0ca in /usr/local/bin/ 
# Wed, 21 Jun 2017 16:13:02 GMT
RUN set -xe 	&& buildDeps=" 		$PHP_EXTRA_BUILD_DEPS 		libcurl4-openssl-dev 		libedit-dev 		libsqlite3-dev 		libssl-dev 		libxml2-dev 	" 	&& apt-get update && apt-get install -y $buildDeps --no-install-recommends && rm -rf /var/lib/apt/lists/* 		&& export CFLAGS="$PHP_CFLAGS" 		CPPFLAGS="$PHP_CPPFLAGS" 		LDFLAGS="$PHP_LDFLAGS" 	&& docker-php-source extract 	&& cd /usr/src/php 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& debMultiarch="$(dpkg-architecture --query DEB_BUILD_MULTIARCH)" 	&& ./configure 		--build="$gnuArch" 		--with-config-file-path="$PHP_INI_DIR" 		--with-config-file-scan-dir="$PHP_INI_DIR/conf.d" 				--disable-cgi 				--enable-ftp 		--enable-mbstring 		--enable-mysqlnd 				--with-curl 		--with-libedit 		--with-openssl 		--with-zlib 				--with-pcre-regex=/usr 		--with-libdir="lib/$debMultiarch" 				$PHP_EXTRA_CONFIGURE_ARGS 	&& make -j "$(nproc)" 	&& make install 	&& { find /usr/local/bin /usr/local/sbin -type f -executable -exec strip --strip-all '{}' + || true; } 	&& make clean 	&& cd / 	&& docker-php-source delete 		&& apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false $buildDeps 		&& pecl update-channels 	&& rm -rf /tmp/pear ~/.pearrc
# Wed, 21 Jun 2017 16:13:04 GMT
COPY multi:3775aa35856908376b7ea71c79fad1e546e92e4ef56dcfc5821b2cc6e2ed6cdc in /usr/local/bin/ 
# Wed, 21 Jun 2017 16:13:05 GMT
ENTRYPOINT ["docker-php-entrypoint"]
# Wed, 21 Jun 2017 16:13:06 GMT
COPY file:24613ecbb1ce6a09f683b0753da9c26a1af07547326e8a02f6eec80ad6f2774a in /usr/local/bin/ 
# Wed, 21 Jun 2017 16:13:07 GMT
WORKDIR /var/www/html
# Wed, 21 Jun 2017 16:13:08 GMT
EXPOSE 80/tcp
# Wed, 21 Jun 2017 16:13:09 GMT
CMD ["apache2-foreground"]
```

-	Layers:
	-	`sha256:9f0706ba7422412cd468804fee456786f88bed94bf9aea6dde2a47f770d19d27`  
		Last Modified: Tue, 20 Jun 2017 20:35:47 GMT  
		Size: 52.6 MB (52614808 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4c407763908f0d63b21189df6608f3623dbaa58948aa929b98bf75104d435581`  
		Last Modified: Wed, 21 Jun 2017 16:52:52 GMT  
		Size: 82.5 MB (82495882 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:82e2bc3a45c1409c931a9feef79a4758849d6fe3f74ea295cdc687201ed364b0`  
		Last Modified: Wed, 21 Jun 2017 16:52:30 GMT  
		Size: 178.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c84e1013aed14b359861a7bef1eae3f92ccee99eeede577dec563474671489d2`  
		Last Modified: Wed, 21 Jun 2017 16:58:11 GMT  
		Size: 2.8 MB (2783957 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a3b5e03d7e247cb9670dbaaef4fce4711989d5756a56463f79c459f20f1a0cb9`  
		Last Modified: Wed, 21 Jun 2017 16:58:10 GMT  
		Size: 1.2 KB (1249 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:917f836a88be268955f536c3ebd06de203e53aa7c5b9b14232fc1083dbc69de3`  
		Last Modified: Wed, 21 Jun 2017 16:58:10 GMT  
		Size: 427.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b2dc54431819e985c69a38bb02873dadea819dfa587d8870afe346a9a1537258`  
		Last Modified: Wed, 21 Jun 2017 16:58:10 GMT  
		Size: 223.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a60b574790b87e69d0de663eb7d3ee5b84ee5c0ce1a8abe9501cdd1d7ea1143c`  
		Last Modified: Wed, 21 Jun 2017 16:58:07 GMT  
		Size: 475.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:6edd671e0b3874ec04702768c59ed7e944c83ec7ffb6924a25b611b430165c41`  
		Last Modified: Wed, 21 Jun 2017 16:58:10 GMT  
		Size: 12.9 MB (12935855 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a38554bba508af73d46f9d8a7e44a768d235d8334e42fd7e4adb1d10f38d2b85`  
		Last Modified: Wed, 21 Jun 2017 16:58:07 GMT  
		Size: 494.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7e6554e0e0588fdbf3e60e3e3b426995646c49d3af236618812337b742d8a510`  
		Last Modified: Wed, 21 Jun 2017 16:58:12 GMT  
		Size: 13.5 MB (13521205 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3548be1f1016a680570fd575eb90725658bb1ec572db5db59db3f752deb58020`  
		Last Modified: Wed, 21 Jun 2017 16:58:07 GMT  
		Size: 2.1 KB (2125 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5ee1a52c53c7f810950b10f8ea2c403241d1eff114134c56d89a411cc4119ae7`  
		Last Modified: Wed, 21 Jun 2017 16:58:07 GMT  
		Size: 893.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
