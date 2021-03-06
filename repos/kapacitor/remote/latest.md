## `kapacitor:latest`

```console
$ docker pull kapacitor@sha256:3caad26b5cc4692f8d184711d7f5b7db9d3049d52e268fdd78002c6904fa4b4c
```

-	Platforms:
	-	linux; amd64

### `kapacitor:latest` - linux; amd64

-	Docker Version: 17.03.1-ce
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **92.6 MB (92624645 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:ecaf798e4ea21e35ce10a640a6bd22f8b55bf82147b2eb08211c12d62ba0896a`
-	Entrypoint: `["\/entrypoint.sh"]`
-	Default Command: `["kapacitord"]`

```dockerfile
# Tue, 20 Jun 2017 20:13:32 GMT
ADD file:9c48682ff75c756544d4491472081a078edf5dd0bb5038d1cb850a1f9c480e3e in / 
# Tue, 20 Jun 2017 20:13:34 GMT
CMD ["bash"]
# Tue, 20 Jun 2017 21:03:33 GMT
RUN apt-get update && apt-get install -y --no-install-recommends 		ca-certificates 		curl 		wget 	&& rm -rf /var/lib/apt/lists/*
# Fri, 23 Jun 2017 00:21:44 GMT
RUN set -ex &&     for key in         05CE15085FC09D18E99EFB22684A14CF2582E0C5 ;     do         gpg --keyserver ha.pool.sks-keyservers.net --recv-keys "$key" ||         gpg --keyserver pgp.mit.edu --recv-keys "$key" ||         gpg --keyserver keyserver.pgp.com --recv-keys "$key" ;     done
# Fri, 23 Jun 2017 00:26:10 GMT
ENV KAPACITOR_VERSION=1.3.1
# Fri, 23 Jun 2017 00:26:16 GMT
RUN wget -q https://dl.influxdata.com/kapacitor/releases/kapacitor_${KAPACITOR_VERSION}_amd64.deb.asc &&     wget -q https://dl.influxdata.com/kapacitor/releases/kapacitor_${KAPACITOR_VERSION}_amd64.deb &&     gpg --batch --verify kapacitor_${KAPACITOR_VERSION}_amd64.deb.asc kapacitor_${KAPACITOR_VERSION}_amd64.deb &&     dpkg -i kapacitor_${KAPACITOR_VERSION}_amd64.deb &&     rm -f kapacitor_${KAPACITOR_VERSION}_amd64.deb*
# Fri, 23 Jun 2017 00:26:17 GMT
COPY file:4046787774ea4c49703132e9dbc6fb3a19cb54632aa7032dd8379f12b56034d9 in /etc/kapacitor/kapacitor.conf 
# Fri, 23 Jun 2017 00:26:18 GMT
EXPOSE 9092/tcp
# Fri, 23 Jun 2017 00:26:19 GMT
VOLUME [/var/lib/kapacitor]
# Fri, 23 Jun 2017 00:26:20 GMT
COPY file:e5d90b0779cb7845ca3a7981c04a97fd959fea211a2ce19c8da8b949f9d9d04c in /entrypoint.sh 
# Fri, 23 Jun 2017 00:26:21 GMT
ENTRYPOINT ["/entrypoint.sh"]
# Fri, 23 Jun 2017 00:26:22 GMT
CMD ["kapacitord"]
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
	-	`sha256:41be322bc8fd93f4bebccc5ad8e6b4074a4d3b764bd10299bd804cbfc3f651d0`  
		Last Modified: Fri, 23 Jun 2017 17:19:00 GMT  
		Size: 6.8 KB (6789 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:a38399938a39e50f97cee47d8f86ee560ff0b1a7c9af6b565fedcfdf9ceef9c6`  
		Last Modified: Sat, 24 Jun 2017 12:16:27 GMT  
		Size: 20.7 MB (20738227 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:293fe8dbd741547d66feb05321fa5870e1b30f09400fbeb9ac59aaa6518131c8`  
		Last Modified: Sat, 24 Jun 2017 12:16:21 GMT  
		Size: 223.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:5f5e4dac247f7ef1ecd88fd696688b363606536bed8c650c2be35388b67f7ad5`  
		Last Modified: Sat, 24 Jun 2017 12:16:21 GMT  
		Size: 230.0 B  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
