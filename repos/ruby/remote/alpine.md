## `ruby:alpine`

```console
$ docker pull ruby@sha256:2726874f6bf49e3029704526deee6b2cc45a9be4fc76af6b328c6a4e61e2bff2
```

-	Platforms:
	-	linux; amd64

### `ruby:alpine` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **27.7 MB (27690310 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:77a3d0f5295c20e2afc977c8248174b911642508d16f76768ab7e4cedbfdee82`
-	Default Command: `["irb"]`

```dockerfile
# Mon, 19 Jun 2017 16:54:49 GMT
ADD file:cf1b74f7af8abcfbe58722467970b39b3ef9c8343665ef2d175f058f734a7f6e in / 
# Mon, 19 Jun 2017 16:55:12 GMT
CMD ["/bin/sh"]
# Tue, 20 Jun 2017 00:45:39 GMT
RUN mkdir -p /usr/local/etc 	&& { 		echo 'install: --no-document'; 		echo 'update: --no-document'; 	} >> /usr/local/etc/gemrc
# Tue, 20 Jun 2017 01:01:13 GMT
ENV RUBY_MAJOR=2.4
# Tue, 20 Jun 2017 01:01:14 GMT
ENV RUBY_VERSION=2.4.1
# Tue, 20 Jun 2017 01:01:15 GMT
ENV RUBY_DOWNLOAD_SHA256=4fc8a9992de3e90191de369270ea4b6c1b171b7941743614cc50822ddc1fe654
# Tue, 20 Jun 2017 01:01:16 GMT
ENV RUBYGEMS_VERSION=2.6.12
# Tue, 20 Jun 2017 01:04:30 GMT
RUN set -ex 		&& apk add --no-cache --virtual .ruby-builddeps 		autoconf 		bison 		bzip2 		bzip2-dev 		ca-certificates 		coreutils 		dpkg-dev dpkg 		gcc 		gdbm-dev 		glib-dev 		libc-dev 		libffi-dev 		libxml2-dev 		libxslt-dev 		linux-headers 		make 		ncurses-dev 		openssl 		openssl-dev 		procps 		readline-dev 		ruby 		tar 		yaml-dev 		zlib-dev 		xz 		&& wget -O ruby.tar.xz "https://cache.ruby-lang.org/pub/ruby/${RUBY_MAJOR%-rc}/ruby-$RUBY_VERSION.tar.xz" 	&& echo "$RUBY_DOWNLOAD_SHA256 *ruby.tar.xz" | sha256sum -c - 		&& mkdir -p /usr/src/ruby 	&& tar -xJf ruby.tar.xz -C /usr/src/ruby --strip-components=1 	&& rm ruby.tar.xz 		&& cd /usr/src/ruby 		&& { 		echo '#define ENABLE_PATH_CHECK 0'; 		echo; 		cat file.c; 	} > file.c.new 	&& mv file.c.new file.c 		&& autoconf 	&& gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)" 	&& export ac_cv_func_isnan=yes ac_cv_func_isinf=yes 	&& ./configure 		--build="$gnuArch" 		--disable-install-doc 		--enable-shared 	&& make -j "$(nproc)" 	&& make install 		&& runDeps="$( 		scanelf --needed --nobanner --recursive /usr/local 			| awk '{ gsub(/,/, "\nso:", $2); print "so:" $2 }' 			| sort -u 			| xargs -r apk info --installed 			| sort -u 	)" 	&& apk add --virtual .ruby-rundeps $runDeps 		bzip2 		ca-certificates 		libffi-dev 		openssl-dev 		yaml-dev 		procps 		zlib-dev 	&& apk del .ruby-builddeps 	&& cd / 	&& rm -r /usr/src/ruby 		&& gem update --system "$RUBYGEMS_VERSION"
# Tue, 20 Jun 2017 01:04:31 GMT
ENV BUNDLER_VERSION=1.15.1
# Tue, 20 Jun 2017 01:04:33 GMT
RUN gem install bundler --version "$BUNDLER_VERSION"
# Tue, 20 Jun 2017 01:04:57 GMT
ENV GEM_HOME=/usr/local/bundle
# Tue, 20 Jun 2017 01:04:58 GMT
ENV BUNDLE_PATH=/usr/local/bundle BUNDLE_BIN=/usr/local/bundle/bin BUNDLE_SILENCE_ROOT_WARNING=1 BUNDLE_APP_CONFIG=/usr/local/bundle
# Tue, 20 Jun 2017 01:04:59 GMT
ENV PATH=/usr/local/bundle/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Tue, 20 Jun 2017 01:05:23 GMT
RUN mkdir -p "$GEM_HOME" "$BUNDLE_BIN" 	&& chmod 777 "$GEM_HOME" "$BUNDLE_BIN"
# Tue, 20 Jun 2017 01:05:24 GMT
CMD ["irb"]
```

-	Layers:
	-	`sha256:acb474fa89565f9f79ee5ddaaaad12c59954e2694d005ec120d6b11825bad191`  
		Last Modified: Mon, 19 Jun 2017 17:06:54 GMT  
		Size: 2.4 MB (2385060 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f5f986f0b5dfbbcb794d4956e9692d572e78f0c33762a4252feaebe49d352d15`  
		Last Modified: Sat, 24 Jun 2017 23:38:26 GMT  
		Size: 194.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:185088e50e0b3191e536581eb68afa6528a65472fce84aa35ba164708a576ef3`  
		Last Modified: Sat, 24 Jun 2017 23:53:39 GMT  
		Size: 24.6 MB (24627009 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:156001392dac4df436767a346506a14dfd3d404e4ea8db27cd1220d4f496e555`  
		Last Modified: Sat, 24 Jun 2017 23:53:33 GMT  
		Size: 677.9 KB (677895 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fc0df2beeb6cef9e8ba8a16f153d728266e6e84f701cc37c006894fc394a3602`  
		Last Modified: Sat, 24 Jun 2017 23:53:32 GMT  
		Size: 152.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
