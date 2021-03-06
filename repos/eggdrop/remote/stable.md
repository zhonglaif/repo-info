## `eggdrop:stable`

```console
$ docker pull eggdrop@sha256:cfd7f7ed740e2a7764dd7fad4c89be49fcb0b7f027c35aae0393701ae9200805
```

-	Platforms:
	-	linux; amd64

### `eggdrop:stable` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **7.4 MB (7375372 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:89c38dc6256903a00a33b0c89d1f518c312b85a67972a778f8f4de6f8c37320d`
-	Entrypoint: `["\/home\/eggdrop\/eggdrop\/entrypoint.sh"]`
-	Default Command: `["eggdrop.conf"]`

```dockerfile
# Mon, 19 Jun 2017 16:54:49 GMT
ADD file:cf1b74f7af8abcfbe58722467970b39b3ef9c8343665ef2d175f058f734a7f6e in / 
# Mon, 19 Jun 2017 16:55:12 GMT
CMD ["/bin/sh"]
# Mon, 19 Jun 2017 19:38:42 GMT
MAINTAINER Geo Van O <geo@eggheads.org>
# Mon, 19 Jun 2017 19:38:45 GMT
RUN adduser -S eggdrop
# Mon, 19 Jun 2017 19:38:49 GMT
RUN apk add --no-cache 'su-exec>=0.2'
# Mon, 19 Jun 2017 19:39:35 GMT
RUN apk add --no-cache tcl tcl-dev wget ca-certificates make tar gpgme bash build-base openssl openssl-dev  && wget ftp://ftp.eggheads.org/pub/eggdrop/source/1.8/eggdrop-1.8.1.tar.gz   && wget ftp://ftp.eggheads.org/pub/eggdrop/source/1.8/eggdrop-1.8.1.tar.gz.asc   && gpg --keyserver ha.pool.sks-keyservers.net --recv-key E01C240484DE7DBE190FE141E7667DE1D1A39AFF   && gpg --batch --verify eggdrop-1.8.1.tar.gz.asc eggdrop-1.8.1.tar.gz   && rm eggdrop-1.8.1.tar.gz.asc   && tar -zxvf eggdrop-1.8.1.tar.gz   && rm eggdrop-1.8.1.tar.gz   && ( cd eggdrop-1.8.1     && ./configure     && make config     && make     && make install DEST=/home/eggdrop/eggdrop )   && rm -rf eggdrop-1.8.1   && mkdir /home/eggdrop/eggdrop/data   && chown -R eggdrop /home/eggdrop/eggdrop   && apk del tcl-dev wget ca-certificates make tar gpgme build-base openssl-dev
# Mon, 19 Jun 2017 19:41:49 GMT
ENV NICK=
# Mon, 19 Jun 2017 19:41:50 GMT
ENV SERVER=
# Mon, 19 Jun 2017 19:41:51 GMT
ENV LISTEN=3333
# Mon, 19 Jun 2017 19:41:52 GMT
ENV OWNER=
# Mon, 19 Jun 2017 19:41:53 GMT
ENV USERFILE=eggdrop.user
# Mon, 19 Jun 2017 19:41:53 GMT
ENV CHANFILE=eggdrop.chan
# Mon, 19 Jun 2017 19:41:54 GMT
WORKDIR /home/eggdrop/eggdrop
# Mon, 19 Jun 2017 19:41:56 GMT
EXPOSE 3333/tcp
# Mon, 19 Jun 2017 19:41:57 GMT
COPY file:7a054cb46364a47f244469cd44e0d12e9e0c49ab06cd99348b2a2bba3a4fb1c8 in /home/eggdrop/eggdrop 
# Mon, 19 Jun 2017 19:41:59 GMT
COPY file:919804e5ddd4c807c178caccfed03e9d75a459fe0f744c3a1ada109817cb44ec in /home/eggdrop/eggdrop/scripts/ 
# Mon, 19 Jun 2017 19:42:00 GMT
ENTRYPOINT ["/home/eggdrop/eggdrop/entrypoint.sh"]
# Mon, 19 Jun 2017 19:42:01 GMT
CMD ["eggdrop.conf"]
```

-	Layers:
	-	`sha256:acb474fa89565f9f79ee5ddaaaad12c59954e2694d005ec120d6b11825bad191`  
		Last Modified: Mon, 19 Jun 2017 17:06:54 GMT  
		Size: 2.4 MB (2385060 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:9319254a3e67469944e3e87c65a0677255db5496c6c6944de830956851724b30`  
		Last Modified: Sat, 24 Jun 2017 08:24:53 GMT  
		Size: 1.3 KB (1279 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:f8f0b83c6668de689b699657c0949bc46495ebd307fa589089b8c92b918189ba`  
		Last Modified: Sat, 24 Jun 2017 08:24:54 GMT  
		Size: 8.0 KB (8007 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:b40263ed3eaca37d5b0f4c49f44ba464633673a25feb17d13748bef288db718c`  
		Last Modified: Sat, 24 Jun 2017 08:24:56 GMT  
		Size: 5.0 MB (4978589 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:8972b9a07c085ae27eed90204785236639f776038bb8def3d883f7a2e2f8e4e8`  
		Last Modified: Sat, 24 Jun 2017 08:24:54 GMT  
		Size: 1.7 KB (1741 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4e4bce80779c83ef771be81c5cf43905976209aaf813a425b6435893a0e6df5f`  
		Last Modified: Sat, 24 Jun 2017 08:24:53 GMT  
		Size: 696.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
