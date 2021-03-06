## `ghost:latest`

```console
$ docker pull ghost@sha256:7693584cf95b7eda0ef7c623072d4666a322097377fe3f2a753f77af3e04891e
```

-	Platforms:
	-	linux; amd64

### `ghost:latest` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **112.1 MB (112091019 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:73792478deb5019be5ddf13a203fe3941c82c398b6f861dbac90c404afefebd2`
-	Entrypoint: `["docker-entrypoint.sh"]`
-	Default Command: `["npm","start"]`

```dockerfile
# Tue, 20 Jun 2017 20:13:32 GMT
ADD file:9c48682ff75c756544d4491472081a078edf5dd0bb5038d1cb850a1f9c480e3e in / 
# Tue, 20 Jun 2017 20:13:34 GMT
CMD ["bash"]
# Tue, 20 Jun 2017 21:03:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 23 Jun 2017 00:59:13 GMT
RUN groupadd --gid 1000 node   && useradd --uid 1000 --gid node --shell /bin/bash --create-home node
# Fri, 23 Jun 2017 00:59:18 GMT
RUN set -ex   && for key in     9554F04D7259F04124DE6B476D5A82AC7E37093B     94AE36675C464D64BAFA68DD7434390BDBE9B9C5     FD3A5288F042B6850C66B31F09FE44734EB7990E     71DCFD284A79C3B38668286BC97EC7A07EDE3FC1     DD8F2338BAE7501E3DD5AC78C273792F7D83545D     B9AE9905FFD7803F25714661B63B535A4C206CA9     C4F0DFFF4E8C1A8236409D08E73BC641CC11F4C8     56730D5401028683275BD23C23EFEFE93C4CFFFE   ; do     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ||     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ;   done
# Fri, 23 Jun 2017 00:59:18 GMT
ENV NPM_CONFIG_LOGLEVEL=info
# Fri, 23 Jun 2017 01:06:50 GMT
ENV NODE_VERSION=4.8.3
# Fri, 23 Jun 2017 01:07:03 GMT
RUN buildDeps='xz-utils'     && set -x     && apt-get update && apt-get install -y $buildDeps --no-install-recommends     && rm -rf /var/lib/apt/lists/*     && curl -SLO "https://nodejs.org/dist/v$NODE_VERSION/node-v$NODE_VERSION-linux-x64.tar.xz"     && curl -SLO --compressed "https://nodejs.org/dist/v$NODE_VERSION/SHASUMS256.txt.asc"     && gpg --batch --decrypt --output SHASUMS256.txt SHASUMS256.txt.asc     && grep " node-v$NODE_VERSION-linux-x64.tar.xz\$" SHASUMS256.txt | sha256sum -c -     && tar -xJf "node-v$NODE_VERSION-linux-x64.tar.xz" -C /usr/local --strip-components=1     && rm "node-v$NODE_VERSION-linux-x64.tar.xz" SHASUMS256.txt.asc SHASUMS256.txt     && apt-get purge -y --auto-remove $buildDeps     && ln -s /usr/local/bin/node /usr/local/bin/nodejs
# Fri, 23 Jun 2017 01:07:05 GMT
ENV YARN_VERSION=0.24.4
# Fri, 23 Jun 2017 01:07:09 GMT
RUN set -ex   && for key in     6A010C5166006599AA17F08146C2130DFD2497F5   ; do     gpg --keyserver pgp.mit.edu --recv-keys "$key" ||     gpg --keyserver keyserver.pgp.com --recv-keys "$key" ||     gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ;   done   && curl -fSLO --compressed "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-v$YARN_VERSION.tar.gz"   && curl -fSLO --compressed "https://yarnpkg.com/downloads/$YARN_VERSION/yarn-v$YARN_VERSION.tar.gz.asc"   && gpg --batch --verify yarn-v$YARN_VERSION.tar.gz.asc yarn-v$YARN_VERSION.tar.gz   && mkdir -p /opt/yarn   && tar -xzf yarn-v$YARN_VERSION.tar.gz -C /opt/yarn --strip-components=1   && ln -s /opt/yarn/bin/yarn /usr/local/bin/yarn   && ln -s /opt/yarn/bin/yarn /usr/local/bin/yarnpkg   && rm yarn-v$YARN_VERSION.tar.gz.asc yarn-v$YARN_VERSION.tar.gz
# Fri, 23 Jun 2017 01:07:10 GMT
CMD ["node"]
# Fri, 23 Jun 2017 14:51:21 GMT
RUN groupadd user && useradd --create-home --home-dir /home/user -g user user
# Fri, 23 Jun 2017 14:51:21 GMT
ENV GOSU_VERSION=1.7
# Fri, 23 Jun 2017 14:51:27 GMT
RUN set -x 	&& wget -O /usr/local/bin/gosu "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture)" 	&& wget -O /usr/local/bin/gosu.asc "https://github.com/tianon/gosu/releases/download/$GOSU_VERSION/gosu-$(dpkg --print-architecture).asc" 	&& export GNUPGHOME="$(mktemp -d)" 	&& gpg --keyserver ha.pool.sks-keyservers.net --recv-keys B42F6819007F00F88E364FD4036A9C25BF357DD4 	&& gpg --batch --verify /usr/local/bin/gosu.asc /usr/local/bin/gosu 	&& rm -r "$GNUPGHOME" /usr/local/bin/gosu.asc 	&& chmod +x /usr/local/bin/gosu 	&& gosu nobody true
# Fri, 23 Jun 2017 14:51:28 GMT
ENV GHOST_SOURCE=/usr/src/ghost
# Fri, 23 Jun 2017 14:51:29 GMT
WORKDIR /usr/src/ghost
# Fri, 23 Jun 2017 14:51:30 GMT
ENV GHOST_VERSION=0.11.10
# Fri, 23 Jun 2017 14:52:28 GMT
RUN set -ex; 		buildDeps=' 		gcc 		make 		python 		unzip 	'; 	apt-get update; 	apt-get install -y $buildDeps --no-install-recommends; 	rm -rf /var/lib/apt/lists/*; 		wget -O ghost.zip "https://github.com/TryGhost/Ghost/releases/download/${GHOST_VERSION}/Ghost-${GHOST_VERSION}.zip"; 	unzip ghost.zip; 		npm install --production; 		apt-get purge -y --auto-remove $buildDeps; 		rm ghost.zip; 	npm cache clean; 	rm -rf /tmp/npm*
# Fri, 23 Jun 2017 14:52:29 GMT
ENV GHOST_CONTENT=/var/lib/ghost
# Fri, 23 Jun 2017 14:52:31 GMT
RUN mkdir -p "$GHOST_CONTENT" 	&& chown -R user:user "$GHOST_CONTENT" 	&& ln -s "$GHOST_CONTENT/config.js" "$GHOST_SOURCE/config.js"
# Fri, 23 Jun 2017 14:52:32 GMT
VOLUME [/var/lib/ghost]
# Fri, 23 Jun 2017 14:52:34 GMT
COPY file:9cace68ea99d0317c469464495249094669747893a60585016756f169051a609 in /usr/local/bin/ 
# Fri, 23 Jun 2017 14:52:35 GMT
RUN ln -s usr/local/bin/docker-entrypoint.sh /entrypoint.sh # backwards compat
# Fri, 23 Jun 2017 14:52:36 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Fri, 23 Jun 2017 14:52:37 GMT
EXPOSE 2368/tcp
# Fri, 23 Jun 2017 14:52:38 GMT
CMD ["npm" "start"]
```

-	Layers:
	-	`sha256:9f0706ba7422412cd468804fee456786f88bed94bf9aea6dde2a47f770d19d27`  
		Last Modified: Tue, 20 Jun 2017 20:35:47 GMT  
		Size: 52.6 MB (52614808 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d3942a742d221ef22a0a335c4eebf09e15a36dcfb224b5a2d0cdcc405f374ccb`  
		Last Modified: Wed, 21 Jun 2017 00:33:28 GMT  
		Size: 19.3 MB (19264368 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8fe38782ba6f17ba90e104826d2017f1fd86b7873f12c4632c9ea52cbcd88e1b`  
		Last Modified: Sat, 24 Jun 2017 15:13:02 GMT  
		Size: 4.4 KB (4372 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0e0a1d2307e1b2182bc4238e3223c1b03059a05af2a1ebf73db6d30349e490d1`  
		Last Modified: Sat, 24 Jun 2017 15:13:02 GMT  
		Size: 119.2 KB (119152 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9d328af0cf3b02f233627fe3215495194d40f1f711b5131a5a8e294711677312`  
		Last Modified: Sat, 24 Jun 2017 15:32:35 GMT  
		Size: 12.6 MB (12572594 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c973e3df1e1c910e347cd076a91deeb978c8be9e0ca32d56ef2c80289d1506e8`  
		Last Modified: Sat, 24 Jun 2017 15:32:29 GMT  
		Size: 900.6 KB (900593 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:53fc6d232172a98868d73bb5a6bd57567faf415b790f412077cb6f32aa0bbeaa`  
		Last Modified: Sun, 25 Jun 2017 09:06:18 GMT  
		Size: 4.4 KB (4415 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:0520b515eb5820e94203faef40ef03b8cb7516fc628aa4b76b2a0f59377d7985`  
		Last Modified: Sun, 25 Jun 2017 09:06:15 GMT  
		Size: 818.8 KB (818817 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:7b726f9ed6cd83dc600e6b42f5537c8d4f721fea0704cb7a8147e2de1183dacd`  
		Last Modified: Sun, 25 Jun 2017 09:06:15 GMT  
		Size: 130.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4fda82f37b5914f87efbc7256b571c9d9b293a23d47bb17f954fd2d74f22de2e`  
		Last Modified: Sun, 25 Jun 2017 09:06:32 GMT  
		Size: 25.8 MB (25790819 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f2ab1733de1d1aad85a647fbc679dace7e98feb67c8d526a52644bce5438346a`  
		Last Modified: Sun, 25 Jun 2017 09:06:15 GMT  
		Size: 212.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a0546f3f16cad2f4d5629ce7931cde1f27fdd39a056f52292db1364845ea9516`  
		Last Modified: Sun, 25 Jun 2017 09:06:15 GMT  
		Size: 618.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:65eb3c84687c34ba65f6e737b5d3e7793047d0524742e2ea5e71695c49333e44`  
		Last Modified: Sun, 25 Jun 2017 09:06:15 GMT  
		Size: 121.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
