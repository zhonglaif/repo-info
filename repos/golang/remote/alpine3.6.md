## `golang:alpine3.6`

```console
$ docker pull golang@sha256:812e7efc81048bf45ac7f45f5228696b5fbb1f176cd07b4e1772907bda6beff9
```

-	Platforms:
	-	linux; amd64

### `golang:alpine3.6` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **78.4 MB (78381415 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:f38603c0c30ea638798e763958386ad870242b98ea81984053769da046ccc037`
-	Default Command: `["\/bin\/sh"]`

```dockerfile
# Mon, 19 Jun 2017 16:58:00 GMT
ADD file:90d7b7a4bad6a39f91c8e1c988e5ee0a7fb9f28b6364b50b6d74dada40258cca in / 
# Mon, 19 Jun 2017 16:58:46 GMT
CMD ["/bin/sh"]
# Mon, 19 Jun 2017 19:53:16 GMT
RUN apk add --no-cache ca-certificates
# Mon, 19 Jun 2017 20:10:42 GMT
ENV GOLANG_VERSION=1.8.3
# Mon, 19 Jun 2017 20:10:43 GMT
COPY file:8bfad5c310fe0639fcf658b30e2f65d04df13ad329573b58a3e782441bb7839c in /go-alpine-patches/ 
# Mon, 19 Jun 2017 20:11:55 GMT
RUN set -eux; 	apk add --no-cache --virtual .build-deps 		bash 		gcc 		musl-dev 		openssl 		go 	; 	export 		GOROOT_BOOTSTRAP="$(go env GOROOT)" 		GOOS="$(go env GOOS)" 		GOARCH="$(go env GOARCH)" 		GO386="$(go env GO386)" 		GOARM="$(go env GOARM)" 		GOHOSTOS="$(go env GOHOSTOS)" 		GOHOSTARCH="$(go env GOHOSTARCH)" 	; 		wget -O go.tgz "https://golang.org/dl/go$GOLANG_VERSION.src.tar.gz"; 	echo '5f5dea2447e7dcfdc50fa6b94c512e58bfba5673c039259fd843f68829d99fa6 *go.tgz' | sha256sum -c -; 	tar -C /usr/local -xzf go.tgz; 	rm go.tgz; 		cd /usr/local/go/src; 	for p in /go-alpine-patches/*.patch; do 		[ -f "$p" ] || continue; 		patch -p2 -i "$p"; 	done; 	./make.bash; 		rm -rf /go-alpine-patches; 	apk del .build-deps; 		export PATH="/usr/local/go/bin:$PATH"; 	go version
# Mon, 19 Jun 2017 20:11:57 GMT
ENV GOPATH=/go
# Mon, 19 Jun 2017 20:11:58 GMT
ENV PATH=/go/bin:/usr/local/go/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin
# Mon, 19 Jun 2017 20:11:59 GMT
RUN mkdir -p "$GOPATH/src" "$GOPATH/bin" && chmod -R 777 "$GOPATH"
# Mon, 19 Jun 2017 20:12:00 GMT
WORKDIR /go
# Mon, 19 Jun 2017 20:12:02 GMT
COPY file:f6191f2c86edc9343569339f101facba47e886e33e29d70da6916ca6b1101a53 in /usr/local/bin/ 
```

-	Layers:
	-	`sha256:43d680a959df2b2131639a5e0915cc03e6eeeaba1a22abf3d8881136728bc2ee`  
		Last Modified: Mon, 19 Jun 2017 17:09:10 GMT  
		Size: 2.0 MB (1990164 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:ea5c3eeef649a10687852b5d0c032cf5f25931cba67f0e1462a378a5958ea068`  
		Last Modified: Sat, 24 Jun 2017 09:33:02 GMT  
		Size: 351.3 KB (351290 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:908d006bfe5e586b254adf90cee49aac0bca349ec7e39e0be5892eb4e30d258a`  
		Last Modified: Sat, 24 Jun 2017 09:46:17 GMT  
		Size: 487.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:1f26205a7cf3aab02819276615839a5aef64a538b001f018c70014d95f7bd892`  
		Last Modified: Sat, 24 Jun 2017 09:46:40 GMT  
		Size: 76.0 MB (76037999 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:964c08715df3979bcb1122d614db1fce7cc56a3975587bd9f66e38b682412c12`  
		Last Modified: Sat, 24 Jun 2017 09:46:16 GMT  
		Size: 126.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:618d1e38fe3c7121e0259ffc5c5e9a41c21e8600e72f8780d8c06a43f6e6621c`  
		Last Modified: Sat, 24 Jun 2017 09:46:16 GMT  
		Size: 1.3 KB (1349 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
