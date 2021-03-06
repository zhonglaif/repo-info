## `docker:stable-dind`

```console
$ docker pull docker@sha256:e0d035f1b073761dac7c350c0db6d86fe94c8e78ddf56633af7eab942d1ce024
```

-	Platforms:
	-	linux; amd64

### `docker:stable-dind` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **32.8 MB (32771463 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:dbf7e61a4cc7603891ecac195d746e0802055c0a9841c5c379fa48172e443de6`
-	Entrypoint: `["dockerd-entrypoint.sh"]`
-	Default Command: `[]`

```dockerfile
# Mon, 19 Jun 2017 16:56:25 GMT
ADD file:dc33e8c0381ed8cecdd07c4b77c58a0c1bfa3266629bbce3fc0e49a047fbdd62 in / 
# Mon, 19 Jun 2017 16:56:48 GMT
CMD ["/bin/sh"]
# Mon, 19 Jun 2017 18:27:27 GMT
RUN apk add --no-cache 		ca-certificates
# Mon, 19 Jun 2017 18:34:56 GMT
ENV DOCKER_CHANNEL=stable
# Mon, 19 Jun 2017 18:34:58 GMT
ENV DOCKER_VERSION=17.03.1-ce
# Mon, 19 Jun 2017 18:35:05 GMT
RUN set -ex; 	apk add --no-cache --virtual .fetch-deps 		curl 		tar 	; 		apkArch="$(apk --print-arch)"; 	case "$apkArch" in 		x86_64) dockerArch='x86_64' ;; 		*) echo >&2 "error: unsupported architecture ($apkArch)"; exit 1 ;;	esac; 		if ! curl -fL -o docker.tgz "https://download.docker.com/linux/static/${DOCKER_CHANNEL}/${dockerArch}/docker-${DOCKER_VERSION}.tgz"; then 		echo >&2 "error: failed to download 'docker-${DOCKER_VERSION}' from '${DOCKER_CHANNEL}' for '${dockerArch}'"; 		exit 1; 	fi; 		tar --extract 		--file docker.tgz 		--strip-components 1 		--directory /usr/local/bin/ 	; 	rm docker.tgz; 		apk del .fetch-deps; 		dockerd -v; 	docker -v
# Mon, 19 Jun 2017 18:35:06 GMT
COPY file:0d94e1cd679f133aab807891a1b00b6aef1a9f1f884108e7a17ddf50ab88f1fb in /usr/local/bin/ 
# Mon, 19 Jun 2017 18:35:07 GMT
ENTRYPOINT ["docker-entrypoint.sh"]
# Mon, 19 Jun 2017 18:35:08 GMT
CMD ["sh"]
# Mon, 19 Jun 2017 18:35:38 GMT
RUN apk add --no-cache 		btrfs-progs 		e2fsprogs 		e2fsprogs-extra 		iptables 		xfsprogs 		xz
# Mon, 19 Jun 2017 18:35:39 GMT
RUN set -x 	&& addgroup -S dockremap 	&& adduser -S -G dockremap dockremap 	&& echo 'dockremap:165536:65536' >> /etc/subuid 	&& echo 'dockremap:165536:65536' >> /etc/subgid
# Mon, 19 Jun 2017 18:35:40 GMT
ENV DIND_COMMIT=3b5fac462d21ca164b3778647420016315289034
# Mon, 19 Jun 2017 18:35:45 GMT
RUN set -ex; 	apk add --no-cache --virtual .fetch-deps libressl; 	wget -O /usr/local/bin/dind "https://raw.githubusercontent.com/docker/docker/${DIND_COMMIT}/hack/dind"; 	chmod +x /usr/local/bin/dind; 	apk del .fetch-deps
# Mon, 19 Jun 2017 18:36:07 GMT
COPY file:7070e4b35c137a8ec5904300d19b8f7ee74aa76659517767c617249cece98a4a in /usr/local/bin/ 
# Mon, 19 Jun 2017 18:36:08 GMT
VOLUME [/var/lib/docker]
# Mon, 19 Jun 2017 18:36:10 GMT
EXPOSE 2375/tcp
# Mon, 19 Jun 2017 18:36:11 GMT
ENTRYPOINT ["dockerd-entrypoint.sh"]
# Mon, 19 Jun 2017 18:36:11 GMT
CMD []
```

-	Layers:
	-	`sha256:c800c6a61b4898becded5aa2cd373c6549651b809d2317b6922cbb269b7bbd0c`  
		Last Modified: Mon, 19 Jun 2017 17:08:03 GMT  
		Size: 2.0 MB (1970311 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:35ce9161c0e9905cb5fada429be2ea2d3882d148f8e6d7afdb3db50d93a93be2`  
		Last Modified: Thu, 22 Jun 2017 19:24:46 GMT  
		Size: 350.6 KB (350623 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:aeb3b5097ffe33aa849eaa53de34ad699fd33dcba4bcb872e80c7df4afc97f53`  
		Last Modified: Thu, 22 Jun 2017 19:38:26 GMT  
		Size: 28.1 MB (28106864 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:33cb916625ed62160cce53248e47bd342706b3f9463cb9c677870fec21c548dc`  
		Last Modified: Thu, 22 Jun 2017 19:38:19 GMT  
		Size: 731.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:25c47fe3089b65dc7924f724977e45a5c92411d82a21be3c449bf4f670987826`  
		Last Modified: Thu, 22 Jun 2017 19:40:14 GMT  
		Size: 2.2 MB (2165471 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:c877445d8d36609b30bccabfbd0c8e3648a4daf2468f8b1b85963a045bcace03`  
		Last Modified: Thu, 22 Jun 2017 19:40:13 GMT  
		Size: 1.3 KB (1302 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b17e9a7ee20ddb279986b27723586d17d4add4fb980cb92857f5d79a59096f59`  
		Last Modified: Thu, 22 Jun 2017 19:40:13 GMT  
		Size: 175.7 KB (175674 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:d7a10ee874d894d6f016870c310ac44e0eca5a27357f77114e56bf71ba1ef90b`  
		Last Modified: Thu, 22 Jun 2017 19:40:13 GMT  
		Size: 487.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
