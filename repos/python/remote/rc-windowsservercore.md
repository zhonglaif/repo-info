## `python:rc-windowsservercore`

```console
$ docker pull python@sha256:98e622b2fcf242e3a94a48b7ad282d73530f8f37aca48dea5b7538419b050796
```

-	Platforms:
	-	windows; amd64

### `python:rc-windowsservercore` - windows; amd64

-	Docker Version: 1.12.2-cs2-ws-beta
-	Manifest MIME: `application/vnd.docker.distribution.manifest.v2+json`
-	Total Size: **5.3 GB (5288030262 bytes)**  
	(compressed transfer size, not on-disk size)
-	Image ID: `sha256:7380f9eeb32b95807fe9f1481043c42a8f85a864fcc356a7b313c79ddb3c2eac`
-	Default Command: `["python"]`
-	`SHELL`: `["powershell","-Command","$ErrorActionPreference = 'Stop';"]`

```dockerfile
# Tue, 22 Nov 2016 23:24:24 GMT
RUN Apply image 10.0.14393.0
# Mon, 10 Apr 2017 22:00:56 GMT
RUN Install update 10.0.14393.1066
# Tue, 18 Apr 2017 17:08:48 GMT
SHELL [powershell -Command $ErrorActionPreference = 'Stop';]
# Tue, 20 Jun 2017 03:11:12 GMT
ENV PYTHON_VERSION=3.6.2rc1
# Tue, 20 Jun 2017 03:11:15 GMT
ENV PYTHON_RELEASE=3.6.2
# Tue, 20 Jun 2017 03:12:36 GMT
RUN $url = ('https://www.python.org/ftp/python/{0}/python-{1}-amd64.exe' -f $env:PYTHON_RELEASE, $env:PYTHON_VERSION); 	Write-Host ('Downloading {0} ...' -f $url); 	(New-Object System.Net.WebClient).DownloadFile($url, 'python.exe'); 		Write-Host 'Installing ...'; 	Start-Process python.exe -Wait 		-ArgumentList @( 			'/quiet', 			'InstallAllUsers=1', 			'TargetDir=C:\Python', 			'PrependPath=1', 			'Shortcuts=0', 			'Include_doc=0', 			'Include_pip=0', 			'Include_test=0' 		); 		$env:PATH = [Environment]::GetEnvironmentVariable('PATH', [EnvironmentVariableTarget]::Machine); 		Write-Host 'Verifying install ...'; 	Write-Host '  python --version'; python --version; 		Write-Host 'Removing ...'; 	Remove-Item python.exe -Force; 		Write-Host 'Complete.';
# Tue, 20 Jun 2017 03:12:39 GMT
ENV PYTHON_PIP_VERSION=9.0.1
# Tue, 20 Jun 2017 03:13:25 GMT
RUN Write-Host ('Installing pip=={0} ...' -f $env:PYTHON_PIP_VERSION); 	(New-Object System.Net.WebClient).DownloadFile('https://bootstrap.pypa.io/get-pip.py', 'get-pip.py'); 	python get-pip.py 		--disable-pip-version-check 		--no-cache-dir 		('pip=={0}' -f $env:PYTHON_PIP_VERSION) 	; 	Remove-Item get-pip.py -Force; 		Write-Host 'Verifying pip install ...'; 	pip --version; 		Write-Host 'Complete.';
# Tue, 20 Jun 2017 03:13:29 GMT
CMD ["python"]
```

-	Layers:
	-	`sha256:3889bb8d808bbae6fa5a33e07093e65c31371bcf9e4c38c21be6b9af52ad1548`  
		Size: 4.1 GB (4069985900 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:6d4d50238ed13902c153bc3efc3a22f8a96bca4168ea03624d01da1063728dc2`  
		Size: 1.2 GB (1161902022 bytes)  
		MIME: application/vnd.docker.image.rootfs.foreign.diff.tar.gzip
	-	`sha256:2869ce7d2a7c3a942c84de08ac9b045cb0a8deefa17949b571dffa5cd1cc28cd`  
		Last Modified: Tue, 18 Apr 2017 17:14:24 GMT  
		Size: 1.2 KB (1223 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:4e1c1e9cc9eb0ab0fe52540c53c095ac01fb477bd9487fe3415acdaa6b319645`  
		Last Modified: Tue, 20 Jun 2017 03:14:12 GMT  
		Size: 1.2 KB (1210 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:28dfde50fb8689016cfec3df6301faf4b94131c95bee5b201e6f30ffbdd71a19`  
		Last Modified: Tue, 20 Jun 2017 03:14:06 GMT  
		Size: 1.2 KB (1225 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:065696e93ebe2c14879b4efb210acdbe9a527c466d3359042e55947ad9a78b87`  
		Last Modified: Tue, 20 Jun 2017 03:14:14 GMT  
		Size: 47.0 MB (46982909 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:fc6c083818279ee7db0c1cd64f42521519d194659a906b2025b4e823590053a2`  
		Last Modified: Tue, 20 Jun 2017 03:14:06 GMT  
		Size: 1.2 KB (1222 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:283c4f0435e88d96537cbf4accf91d558c082a1611efa894080e4a963e913f95`  
		Last Modified: Tue, 20 Jun 2017 03:14:10 GMT  
		Size: 9.2 MB (9153337 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
	-	`sha256:3b374aba2ae20ccdb01a9f3d10564db2270b621c4163122412e46c67b60c1f11`  
		Last Modified: Tue, 20 Jun 2017 03:14:07 GMT  
		Size: 1.2 KB (1214 bytes)  
		MIME: application/vnd.docker.image.rootfs.diff.tar.gzip
