# Part1 exercises

### 1.1 
```
niko@Niko-MacBook-Pro dockertest % docker ps -a
CONTAINER ID   IMAGE         COMMAND                  CREATED              STATUS                          PORTS     NAMES
5fd65ab319e4   nginx         "/docker-entrypoint.…"   31 seconds ago       Exited (0) 3 seconds ago                  pedantic_keldysh
bb3328e11e81   nginx         "/docker-entrypoint.…"   57 seconds ago       Up 56 seconds                   80/tcp    confident_knuth
9d06c85b7a7b   nginx         "/docker-entrypoint.…"   About a minute ago   Exited (0) About a minute ago             beautiful_wilson
```

### 1.2 
```
niko@Niko-MacBook-Pro dockertest % docker ps -a          
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
niko@Niko-MacBook-Pro dockertest % docker images         
REPOSITORY   TAG       IMAGE ID   CREATED   SIZE
```
### 1.3
```
niko@Niko-MacBook-Pro dockertest % docker run -dit --name ykskolme devopsdockeruh/simple-web-service:ubuntu
f2590e1002cd32d26844cd39a3d122990e0cba64be7cbe6bd4da858ca20b8d55
niko@Niko-MacBook-Pro dockertest % docker exec -it ykskolme tail -f ./text.log                             
2022-02-08 15:08:37 +0000 UTC
2022-02-08 15:08:39 +0000 UTC
2022-02-08 15:08:41 +0000 UTC
2022-02-08 15:08:43 +0000 UTC
2022-02-08 15:08:45 +0000 UTC
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
2022-02-08 15:08:47 +0000 UTC
2022-02-08 15:08:49 +0000 UTC
2022-02-08 15:08:51 +0000 UTC
```

### 1.4
```
niko@Niko-MacBook-Pro dockertest % docker run -it --name yksnelja ubuntu sh -c 'apt -qq update; apt -qq install curl -y;  echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;' 
All packages are up to date.
The following additional packages will be installed:
  ca-certificates krb5-locales libasn1-8-heimdal libbrotli1 libcurl4 libgssapi-krb5-2 libgssapi3-heimdal libhcrypto4-heimdal libheimbase1-heimdal libheimntlm0-heimdal
  libhx509-5-heimdal libk5crypto3 libkeyutils1 libkrb5-26-heimdal libkrb5-3 libkrb5support0 libldap-2.4-2 libldap-common libnghttp2-14 libpsl5 libroken18-heimdal librtmp1
  libsasl2-2 libsasl2-modules libsasl2-modules-db libsqlite3-0 libssh-4 libssl1.1 libwind0-heimdal openssl publicsuffix
Suggested packages:
  krb5-doc krb5-user libsasl2-modules-gssapi-mit | libsasl2-modules-gssapi-heimdal libsasl2-modules-ldap libsasl2-modules-otp libsasl2-modules-sql
The following NEW packages will be installed:
  ca-certificates curl krb5-locales libasn1-8-heimdal libbrotli1 libcurl4 libgssapi-krb5-2 libgssapi3-heimdal libhcrypto4-heimdal libheimbase1-heimdal libheimntlm0-heimdal
  libhx509-5-heimdal libk5crypto3 libkeyutils1 libkrb5-26-heimdal libkrb5-3 libkrb5support0 libldap-2.4-2 libldap-common libnghttp2-14 libpsl5 libroken18-heimdal librtmp1
  libsasl2-2 libsasl2-modules libsasl2-modules-db libsqlite3-0 libssh-4 libssl1.1 libwind0-heimdal openssl publicsuffix
0 upgraded, 32 newly installed, 0 to remove and 0 not upgraded.
Need to get 5447 kB of archives.
After this operation, 16.7 MB of additional disk space will be used.
debconf: delaying package configuration, since apt-utils is not installed
Selecting previously unselected package libssl1.1:amd64.
(Reading database ... 4127 files and directories currently installed.)
Preparing to unpack .../00-libssl1.1_1.1.1f-1ubuntu2.10_amd64.deb ...
Unpacking libssl1.1:amd64 (1.1.1f-1ubuntu2.10) ...
Selecting previously unselected package openssl.
Preparing to unpack .../01-openssl_1.1.1f-1ubuntu2.10_amd64.deb ...
Unpacking openssl (1.1.1f-1ubuntu2.10) ...
Selecting previously unselected package ca-certificates.
Preparing to unpack .../02-ca-certificates_20210119~20.04.2_all.deb ...
Unpacking ca-certificates (20210119~20.04.2) ...
Selecting previously unselected package libsqlite3-0:amd64.
Preparing to unpack .../03-libsqlite3-0_3.31.1-4ubuntu0.2_amd64.deb ...
Unpacking libsqlite3-0:amd64 (3.31.1-4ubuntu0.2) ...
Selecting previously unselected package krb5-locales.
Preparing to unpack .../04-krb5-locales_1.17-6ubuntu4.1_all.deb ...
Unpacking krb5-locales (1.17-6ubuntu4.1) ...
Selecting previously unselected package libkrb5support0:amd64.
Preparing to unpack .../05-libkrb5support0_1.17-6ubuntu4.1_amd64.deb ...
Unpacking libkrb5support0:amd64 (1.17-6ubuntu4.1) ...
Selecting previously unselected package libk5crypto3:amd64.
Preparing to unpack .../06-libk5crypto3_1.17-6ubuntu4.1_amd64.deb ...
Unpacking libk5crypto3:amd64 (1.17-6ubuntu4.1) ...
Selecting previously unselected package libkeyutils1:amd64.
Preparing to unpack .../07-libkeyutils1_1.6-6ubuntu1_amd64.deb ...
Unpacking libkeyutils1:amd64 (1.6-6ubuntu1) ...
Selecting previously unselected package libkrb5-3:amd64.
Preparing to unpack .../08-libkrb5-3_1.17-6ubuntu4.1_amd64.deb ...
Unpacking libkrb5-3:amd64 (1.17-6ubuntu4.1) ...
Selecting previously unselected package libgssapi-krb5-2:amd64.
Preparing to unpack .../09-libgssapi-krb5-2_1.17-6ubuntu4.1_amd64.deb ...
Unpacking libgssapi-krb5-2:amd64 (1.17-6ubuntu4.1) ...
Selecting previously unselected package libpsl5:amd64.
Preparing to unpack .../10-libpsl5_0.21.0-1ubuntu1_amd64.deb ...
Unpacking libpsl5:amd64 (0.21.0-1ubuntu1) ...
Selecting previously unselected package publicsuffix.
Preparing to unpack .../11-publicsuffix_20200303.0012-1_all.deb ...
Unpacking publicsuffix (20200303.0012-1) ...
Selecting previously unselected package libbrotli1:amd64.
Preparing to unpack .../12-libbrotli1_1.0.7-6ubuntu0.1_amd64.deb ...
Unpacking libbrotli1:amd64 (1.0.7-6ubuntu0.1) ...
Selecting previously unselected package libroken18-heimdal:amd64.
Preparing to unpack .../13-libroken18-heimdal_7.7.0+dfsg-1ubuntu1_amd64.deb ...
Unpacking libroken18-heimdal:amd64 (7.7.0+dfsg-1ubuntu1) ...
Selecting previously unselected package libasn1-8-heimdal:amd64.
Preparing to unpack .../14-libasn1-8-heimdal_7.7.0+dfsg-1ubuntu1_amd64.deb ...
Unpacking libasn1-8-heimdal:amd64 (7.7.0+dfsg-1ubuntu1) ...
Selecting previously unselected package libheimbase1-heimdal:amd64.
Preparing to unpack .../15-libheimbase1-heimdal_7.7.0+dfsg-1ubuntu1_amd64.deb ...
Unpacking libheimbase1-heimdal:amd64 (7.7.0+dfsg-1ubuntu1) ...
Selecting previously unselected package libhcrypto4-heimdal:amd64.
Preparing to unpack .../16-libhcrypto4-heimdal_7.7.0+dfsg-1ubuntu1_amd64.deb ...
Unpacking libhcrypto4-heimdal:amd64 (7.7.0+dfsg-1ubuntu1) ...
Selecting previously unselected package libwind0-heimdal:amd64.
Preparing to unpack .../17-libwind0-heimdal_7.7.0+dfsg-1ubuntu1_amd64.deb ...
Unpacking libwind0-heimdal:amd64 (7.7.0+dfsg-1ubuntu1) ...
Selecting previously unselected package libhx509-5-heimdal:amd64.
Preparing to unpack .../18-libhx509-5-heimdal_7.7.0+dfsg-1ubuntu1_amd64.deb ...
Unpacking libhx509-5-heimdal:amd64 (7.7.0+dfsg-1ubuntu1) ...
Selecting previously unselected package libkrb5-26-heimdal:amd64.
Preparing to unpack .../19-libkrb5-26-heimdal_7.7.0+dfsg-1ubuntu1_amd64.deb ...
Unpacking libkrb5-26-heimdal:amd64 (7.7.0+dfsg-1ubuntu1) ...
Selecting previously unselected package libheimntlm0-heimdal:amd64.
Preparing to unpack .../20-libheimntlm0-heimdal_7.7.0+dfsg-1ubuntu1_amd64.deb ...
Unpacking libheimntlm0-heimdal:amd64 (7.7.0+dfsg-1ubuntu1) ...
Selecting previously unselected package libgssapi3-heimdal:amd64.
Preparing to unpack .../21-libgssapi3-heimdal_7.7.0+dfsg-1ubuntu1_amd64.deb ...
Unpacking libgssapi3-heimdal:amd64 (7.7.0+dfsg-1ubuntu1) ...
Selecting previously unselected package libsasl2-modules-db:amd64.
Preparing to unpack .../22-libsasl2-modules-db_2.1.27+dfsg-2_amd64.deb ...
Unpacking libsasl2-modules-db:amd64 (2.1.27+dfsg-2) ...
Selecting previously unselected package libsasl2-2:amd64.
Preparing to unpack .../23-libsasl2-2_2.1.27+dfsg-2_amd64.deb ...
Unpacking libsasl2-2:amd64 (2.1.27+dfsg-2) ...
Selecting previously unselected package libldap-common.
Preparing to unpack .../24-libldap-common_2.4.49+dfsg-2ubuntu1.8_all.deb ...
Unpacking libldap-common (2.4.49+dfsg-2ubuntu1.8) ...
Selecting previously unselected package libldap-2.4-2:amd64.
Preparing to unpack .../25-libldap-2.4-2_2.4.49+dfsg-2ubuntu1.8_amd64.deb ...
Unpacking libldap-2.4-2:amd64 (2.4.49+dfsg-2ubuntu1.8) ...
Selecting previously unselected package libnghttp2-14:amd64.
Preparing to unpack .../26-libnghttp2-14_1.40.0-1build1_amd64.deb ...
Unpacking libnghttp2-14:amd64 (1.40.0-1build1) ...
Selecting previously unselected package librtmp1:amd64.
Preparing to unpack .../27-librtmp1_2.4+20151223.gitfa8646d.1-2build1_amd64.deb ...
Unpacking librtmp1:amd64 (2.4+20151223.gitfa8646d.1-2build1) ...
Selecting previously unselected package libssh-4:amd64.
Preparing to unpack .../28-libssh-4_0.9.3-2ubuntu2.2_amd64.deb ...
Unpacking libssh-4:amd64 (0.9.3-2ubuntu2.2) ...
Selecting previously unselected package libcurl4:amd64.
Preparing to unpack .../29-libcurl4_7.68.0-1ubuntu2.7_amd64.deb ...
Unpacking libcurl4:amd64 (7.68.0-1ubuntu2.7) ...
Selecting previously unselected package curl.
Preparing to unpack .../30-curl_7.68.0-1ubuntu2.7_amd64.deb ...
Unpacking curl (7.68.0-1ubuntu2.7) ...
Selecting previously unselected package libsasl2-modules:amd64.
Preparing to unpack .../31-libsasl2-modules_2.1.27+dfsg-2_amd64.deb ...
Unpacking libsasl2-modules:amd64 (2.1.27+dfsg-2) ...
Setting up libkeyutils1:amd64 (1.6-6ubuntu1) ...
Setting up libpsl5:amd64 (0.21.0-1ubuntu1) ...
Setting up libssl1.1:amd64 (1.1.1f-1ubuntu2.10) ...
debconf: unable to initialize frontend: Dialog
debconf: (No usable dialog-like program is installed, so the dialog based frontend cannot be used. at /usr/share/perl5/Debconf/FrontEnd/Dialog.pm line 76.)
debconf: falling back to frontend: Readline
debconf: unable to initialize frontend: Readline
debconf: (Can't locate Term/ReadLine.pm in @INC (you may need to install the Term::ReadLine module) (@INC contains: /etc/perl /usr/local/lib/x86_64-linux-gnu/perl/5.30.0 /usr/local/share/perl/5.30.0 /usr/lib/x86_64-linux-gnu/perl5/5.30 /usr/share/perl5 /usr/lib/x86_64-linux-gnu/perl/5.30 /usr/share/perl/5.30 /usr/local/lib/site_perl /usr/lib/x86_64-linux-gnu/perl-base) at /usr/share/perl5/Debconf/FrontEnd/Readline.pm line 7.)
debconf: falling back to frontend: Teletype
Setting up libbrotli1:amd64 (1.0.7-6ubuntu0.1) ...
Setting up libsqlite3-0:amd64 (3.31.1-4ubuntu0.2) ...
Setting up libsasl2-modules:amd64 (2.1.27+dfsg-2) ...
Setting up libnghttp2-14:amd64 (1.40.0-1build1) ...
Setting up krb5-locales (1.17-6ubuntu4.1) ...
Setting up libldap-common (2.4.49+dfsg-2ubuntu1.8) ...
Setting up libkrb5support0:amd64 (1.17-6ubuntu4.1) ...
Setting up libsasl2-modules-db:amd64 (2.1.27+dfsg-2) ...
Setting up librtmp1:amd64 (2.4+20151223.gitfa8646d.1-2build1) ...
Setting up libk5crypto3:amd64 (1.17-6ubuntu4.1) ...
Setting up libsasl2-2:amd64 (2.1.27+dfsg-2) ...
Setting up libroken18-heimdal:amd64 (7.7.0+dfsg-1ubuntu1) ...
Setting up libkrb5-3:amd64 (1.17-6ubuntu4.1) ...
Setting up openssl (1.1.1f-1ubuntu2.10) ...
Setting up publicsuffix (20200303.0012-1) ...
Setting up libheimbase1-heimdal:amd64 (7.7.0+dfsg-1ubuntu1) ...
Setting up libasn1-8-heimdal:amd64 (7.7.0+dfsg-1ubuntu1) ...
Setting up libhcrypto4-heimdal:amd64 (7.7.0+dfsg-1ubuntu1) ...
Setting up ca-certificates (20210119~20.04.2) ...
debconf: unable to initialize frontend: Dialog
debconf: (No usable dialog-like program is installed, so the dialog based frontend cannot be used. at /usr/share/perl5/Debconf/FrontEnd/Dialog.pm line 76.)
debconf: falling back to frontend: Readline
debconf: unable to initialize frontend: Readline
debconf: (Can't locate Term/ReadLine.pm in @INC (you may need to install the Term::ReadLine module) (@INC contains: /etc/perl /usr/local/lib/x86_64-linux-gnu/perl/5.30.0 /usr/local/share/perl/5.30.0 /usr/lib/x86_64-linux-gnu/perl5/5.30 /usr/share/perl5 /usr/lib/x86_64-linux-gnu/perl/5.30 /usr/share/perl/5.30 /usr/local/lib/site_perl /usr/lib/x86_64-linux-gnu/perl-base) at /usr/share/perl5/Debconf/FrontEnd/Readline.pm line 7.)
debconf: falling back to frontend: Teletype
Updating certificates in /etc/ssl/certs...
128 added, 0 removed; done.
Setting up libwind0-heimdal:amd64 (7.7.0+dfsg-1ubuntu1) ...
Setting up libgssapi-krb5-2:amd64 (1.17-6ubuntu4.1) ...
Setting up libssh-4:amd64 (0.9.3-2ubuntu2.2) ...
Setting up libhx509-5-heimdal:amd64 (7.7.0+dfsg-1ubuntu1) ...
Setting up libkrb5-26-heimdal:amd64 (7.7.0+dfsg-1ubuntu1) ...
Setting up libheimntlm0-heimdal:amd64 (7.7.0+dfsg-1ubuntu1) ...
Setting up libgssapi3-heimdal:amd64 (7.7.0+dfsg-1ubuntu1) ...
Setting up libldap-2.4-2:amd64 (2.4.49+dfsg-2ubuntu1.8) ...
Setting up libcurl4:amd64 (7.68.0-1ubuntu2.7) ...
Setting up curl (7.68.0-1ubuntu2.7) ...
Processing triggers for libc-bin (2.31-0ubuntu9.2) ...
Processing triggers for ca-certificates (20210119~20.04.2) ...
Updating certificates in /etc/ssl/certs...
0 added, 0 removed; done.
Running hooks in /etc/ca-certificates/update.d...
done.
Input website:
helsinki.fi
Searching..
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>301 Moved Permanently</title>
</head><body>
<h1>Moved Permanently</h1>
<p>The document has moved <a href="https://www.helsinki.fi/">here</a>.</p>
</body></html>
```

### 1.5
```
niko@Niko-MacBook-Pro dockertest % docker run -dit --name yksviis devopsdockeruh/simple-web-service:alpine
Unable to find image 'devopsdockeruh/simple-web-service:alpine' locally
alpine: Pulling from devopsdockeruh/simple-web-service
ba3557a56b15: Pull complete 
1dace236434b: Pull complete 
4f4fb700ef54: Pull complete 
Digest: sha256:dd4d367476f86b7d7579d3379fe446ae5dfce25480903fb0966fc2e5257e0543
Status: Downloaded newer image for devopsdockeruh/simple-web-service:alpine
208136486d85dee89f09a3fd73ca70b6f489af360c8f4dd764f90431fdf6e989

niko@Niko-MacBook-Pro dockertest % docker exec -it yksviis tail -f ./text.log
2022-02-08 15:31:41 +0000 UTC
2022-02-08 15:31:43 +0000 UTC
2022-02-08 15:31:45 +0000 UTC
2022-02-08 15:31:47 +0000 UTC
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
2022-02-08 15:31:49 +0000 UTC
2022-02-08 15:31:51 +0000 UTC
2022-02-08 15:31:53 +0000 UTC
2022-02-08 15:31:55 +0000 UTC

niko@Niko-MacBook-Pro dockertest % docker images    
REPOSITORY                          TAG       IMAGE ID       CREATED         SIZE
ubuntu                              latest    54c9d81cbb44   6 days ago      72.8MB
devopsdockeruh/simple-web-service   ubuntu    4e3362e907d5   11 months ago   83MB
devopsdockeruh/simple-web-service   alpine    fd312adc88e0   11 months ago   15.7MB
```
### 1.6
https://github.com/docker-hy/docs-exercise 
pw: basics

```
niko@Niko-MacBook-Pro dockertest % docker run -it --name ykskuus devopsdockeruh/pull_exercise
Give me the password: basics
You found the correct password. Secret message is:
"This is the secret message"
```
### 1.7

Dockerfile:
```
FROM devopsdockeruh/simple-web-service:alpine
CMD server
```
Output:
```
niko@Niko-MacBook-Pro dockertest % docker build . -t web-server
[+] Building 0.1s (5/5) FINISHED                                                                                                                                              
 => [internal] load build definition from Dockerfile                                                                                                                     0.0s
 => => transferring dockerfile: 98B                                                                                                                                      0.0s
 => [internal] load .dockerignore                                                                                                                                        0.0s
 => => transferring context: 2B                                                                                                                                          0.0s
 => [internal] load metadata for docker.io/devopsdockeruh/simple-web-service:alpine                                                                                      0.0s
 => [1/1] FROM docker.io/devopsdockeruh/simple-web-service:alpine                                                                                                        0.0s
 => exporting to image                                                                                                                                                   0.0s
 => => exporting layers                                                                                                                                                  0.0s
 => => writing image sha256:978fbf315695ef5a3ec2e77ee411c4dcd9aa9b867fbc7ea3d26962545fda0585                                                                             0.0s
 => => naming to docker.io/library/web-server                                                                                                                            0.0s

Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them
niko@Niko-MacBook-Pro dockertest % docker run web-server
[GIN-debug] [WARNING] Creating an Engine instance with the Logger and Recovery middleware already attached.

[GIN-debug] [WARNING] Running in "debug" mode. Switch to "release" mode in production.
 - using env:	export GIN_MODE=release
 - using code:	gin.SetMode(gin.ReleaseMode)

[GIN-debug] GET    /*path                    --> server.Start.func1 (3 handlers)
[GIN-debug] Listening and serving HTTP on :8080
^C%                                         
```
### 1.8
Dockerfile:
```
FROM ubuntu:20.04

RUN apt -qq update; apt -qq install curl -y

CMD echo "Input website:"; read website; echo "Searching.."; sleep 1; curl http://$website;
```
Output:
```
niko@Niko-MacBook-Pro dockertest % docker build . -t curler                                 
[+] Building 10.7s (7/7) FINISHED                                                                                                                                             
 => [internal] load build definition from Dockerfile                                                                                                                     0.0s
 => => transferring dockerfile: 199B                                                                                                                                     0.0s
 => [internal] load .dockerignore                                                                                                                                        0.0s
 => => transferring context: 2B                                                                                                                                          0.0s
 => [internal] load metadata for docker.io/library/ubuntu:20.04                                                                                                          2.2s
 => [auth] library/ubuntu:pull token for registry-1.docker.io                                                                                                            0.0s
 => [1/2] FROM docker.io/library/ubuntu:20.04@sha256:669e010b58baf5beb2836b253c1fd5768333f0d1dbcb834f7c07a4dc93f474be                                                    0.0s
 => [2/2] RUN apt -qq update; apt -qq install curl -y                                                                                                                    8.1s
 => exporting to image                                                                                                                                                   0.3s 
 => => exporting layers                                                                                                                                                  0.3s 
 => => writing image sha256:c72bea87ec88452248b26d806bebc59cc7f3654b8541e8c472c6a00b738c9e76                                                                             0.0s 
 => => naming to docker.io/library/curler                                                                                                                                0.0s 
                                                                                                                                                                              
Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them                                                                          
niko@Niko-MacBook-Pro dockertest % docker run -it curler
Input website:
helsinki.fi
Searching..
<!DOCTYPE HTML PUBLIC "-//IETF//DTD HTML 2.0//EN">
<html><head>
<title>301 Moved Permanently</title>
</head><body>
<h1>Moved Permanently</h1>
<p>The document has moved <a href="https://www.helsinki.fi/">here</a>.</p>
</body></html>
niko@Niko-MacBook-Pro dockertest % 
```
### 1.9
```
niko@Niko-MacBook-Pro dockertest % touch text.log
niko@Niko-MacBook-Pro dockertest % docker run -v "$(pwd)/text.log:/usr/src/app/text.log" devopsdockeruh/simple-web-service
Starting log output
Wrote text to /usr/src/app/text.log
Wrote text to /usr/src/app/text.log
Wrote text to /usr/src/app/text.log
Wrote text to /usr/src/app/text.log
Wrote text to /usr/src/app/text.log
Wrote text to /usr/src/app/text.log
Wrote text to /usr/src/app/text.log
Wrote text to /usr/src/app/text.log
^C
niko@Niko-MacBook-Pro dockertest % cat text.log
2022-02-08 16:38:01 +0000 UTC
2022-02-08 16:38:03 +0000 UTC
2022-02-08 16:38:05 +0000 UTC
2022-02-08 16:38:07 +0000 UTC
2022-02-08 16:38:09 +0000 UTC
Secret message is: 'You can find the source code here: https://github.com/docker-hy'
2022-02-08 16:38:11 +0000 UTC
2022-02-08 16:38:13 +0000 UTC
```
### 1.10 
```
niko@Niko-MacBook-Pro dockertest % docker run -p 8080:8080 web-server  
[GIN-debug] [WARNING] Creating an Engine instance with the Logger and Recovery middleware already attached.

[GIN-debug] [WARNING] Running in "debug" mode. Switch to "release" mode in production.
 - using env:	export GIN_MODE=release
 - using code:	gin.SetMode(gin.ReleaseMode)

[GIN-debug] GET    /*path                    --> server.Start.func1 (3 handlers)
[GIN-debug] Listening and serving HTTP on :8080
[GIN] 2022/02/08 - 16:46:26 | 200 |      44.335µs |      172.17.0.1 | GET      "/"
[GIN] 2022/02/08 - 16:46:26 | 200 |      96.392µs |      172.17.0.1 | GET      "/favicon.ico"
```
browser: 
```
{"message":"You connected to the following path: /","path":"/"}
```
### 1.11
Dockerfile:
```
FROM openjdk:8

EXPOSE 8080

WORKDIR /usr/src/app

COPY . .

RUN ./mvnw package

CMD ["java", "-jar", "./target/docker-example-1.1.3.jar"]
```
Output:
```
niko@Niko-MacBook-Pro spring-example-project % docker build . -t spring-project
[+] Building 28.4s (9/9) FINISHED                                                                                                                                             
 => [internal] load build definition from Dockerfile                                                                                                                     0.0s
 => => transferring dockerfile: 271B                                                                                                                                     0.0s
 => [internal] load .dockerignore                                                                                                                                        0.0s
 => => transferring context: 2B                                                                                                                                          0.0s
 => [internal] load metadata for docker.io/library/openjdk:8                                                                                                             0.6s
 => [1/4] FROM docker.io/library/openjdk:8@sha256:77e3337d92fead0c2bc59dbae4af86092b43cecfcc36dad9cb926d1ea3f0b333                                                       0.0s
 => [internal] load build context                                                                                                                                        0.0s
 => => transferring context: 1.55kB                                                                                                                                      0.0s
 => CACHED [2/4] WORKDIR /usr/src/app                                                                                                                                    0.0s
 => [3/4] COPY . .                                                                                                                                                       0.0s
 => [4/4] RUN ./mvnw package                                                                                                                                            27.1s
 => exporting to image                                                                                                                                                   0.5s
 => => exporting layers                                                                                                                                                  0.5s
 => => writing image sha256:13608b7a1b41df150f59ab9bfbc3a8522c74e183290de9553fe4a3964d52d9aa                                                                             0.0s 
 => => naming to docker.io/library/spring-project                                                                                                                        0.0s 
                                                                                                                                                                              
Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them                                                                          
niko@Niko-MacBook-Pro spring-example-project % docker run -p 8080:8080 spring-project

  .   ____          _            __ _ _
 /\\ / ___'_ __ _ _(_)_ __  __ _ \ \ \ \
( ( )\___ | '_ | '_| | '_ \/ _` | \ \ \ \
 \\/  ___)| |_)| | | | | || (_| |  ) ) ) )
  '  |____| .__|_| |_|_| |_\__, | / / / /
 =========|_|==============|___/=/_/_/_/
 :: Spring Boot ::        (v2.1.3.RELEASE)

2022-02-08 17:03:41.166  INFO 1 --- [           main] c.d.dockerexample.DemoApplication        : Starting DemoApplication v1.1.3 on 58a9ba351c91 with PID 1 (/usr/src/app/target/docker-example-1.1.3.jar started by root in /usr/src/app)
2022-02-08 17:03:41.169  INFO 1 --- [           main] c.d.dockerexample.DemoApplication        : No active profile set, falling back to default profiles: default
2022-02-08 17:03:42.165  INFO 1 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat initialized with port(s): 8080 (http)
2022-02-08 17:03:42.191  INFO 1 --- [           main] o.apache.catalina.core.StandardService   : Starting service [Tomcat]
2022-02-08 17:03:42.191  INFO 1 --- [           main] org.apache.catalina.core.StandardEngine  : Starting Servlet engine: [Apache Tomcat/9.0.16]
2022-02-08 17:03:42.201  INFO 1 --- [           main] o.a.catalina.core.AprLifecycleListener   : The APR based Apache Tomcat Native library which allows optimal performance in production environments was not found on the java.library.path: [/usr/java/packages/lib/amd64:/usr/lib64:/lib64:/lib:/usr/lib]
2022-02-08 17:03:42.268  INFO 1 --- [           main] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring embedded WebApplicationContext
2022-02-08 17:03:42.268  INFO 1 --- [           main] o.s.web.context.ContextLoader            : Root WebApplicationContext: initialization completed in 1061 ms
2022-02-08 17:03:42.479  INFO 1 --- [           main] o.s.s.concurrent.ThreadPoolTaskExecutor  : Initializing ExecutorService 'applicationTaskExecutor'
2022-02-08 17:03:42.600  INFO 1 --- [           main] o.s.b.a.w.s.WelcomePageHandlerMapping    : Adding welcome page template: index
2022-02-08 17:03:42.757  INFO 1 --- [           main] o.s.b.w.embedded.tomcat.TomcatWebServer  : Tomcat started on port(s): 8080 (http) with context path ''
2022-02-08 17:03:42.760  INFO 1 --- [           main] c.d.dockerexample.DemoApplication        : Started DemoApplication in 1.903 seconds (JVM running for 2.256)
2022-02-08 17:03:48.706  INFO 1 --- [nio-8080-exec-1] o.a.c.c.C.[Tomcat].[localhost].[/]       : Initializing Spring DispatcherServlet 'dispatcherServlet'
2022-02-08 17:03:48.707  INFO 1 --- [nio-8080-exec-1] o.s.web.servlet.DispatcherServlet        : Initializing Servlet 'dispatcherServlet'
2022-02-08 17:03:48.716  INFO 1 --- [nio-8080-exec-1] o.s.web.servlet.DispatcherServlet        : Completed initialization in 9 ms
```
### 1.12 
Dockerfile:
```
FROM node:16

EXPOSE 5000

WORKDIR /usr/src/app

COPY . .

RUN npm install
RUN npm run build

RUN npm install -g serve

CMD ["serve", "-s", "-l", "5000", "build"]
```
Output: (Port 5000 is used by Airport Server on macOS, had to use other port)
```
niko@Niko-MacBook-Pro example-frontend % docker build . -t example-frontend
[+] Building 12.6s (11/11) FINISHED                                                                                                                                           
 => [internal] load build definition from Dockerfile                                                                                                                     0.0s
 => => transferring dockerfile: 206B                                                                                                                                     0.0s
 => [internal] load .dockerignore                                                                                                                                        0.0s
 => => transferring context: 34B                                                                                                                                         0.0s
 => [internal] load metadata for docker.io/library/node:16                                                                                                               0.6s
 => [1/6] FROM docker.io/library/node:16@sha256:2033f4cc18f9d8b5d0baa7f276aaeffd202e1a2c6fe9af408af05a34fe68cbfb                                                         0.0s
 => [internal] load build context                                                                                                                                        0.0s
 => => transferring context: 1.21kB                                                                                                                                      0.0s
 => CACHED [2/6] WORKDIR /usr/src/app                                                                                                                                    0.0s
 => CACHED [3/6] COPY . .                                                                                                                                                0.0s
 => CACHED [4/6] RUN npm install                                                                                                                                         0.0s
 => CACHED [5/6] RUN npm run build                                                                                                                                       0.0s
 => CACHED [6/6] RUN npm install -g serve                                                                                                                                0.0s
 => exporting to image                                                                                                                                                  11.9s
 => => exporting layers                                                                                                                                                 11.9s
 => => writing image sha256:6e84f6239c936d04e8e18b093c79b0734c08d41158ccb3764c18730c84e5bd6f                                                                             0.0s
 => => naming to docker.io/library/example-frontend                                                                                                                      0.0s

Use 'docker scan' to run Snyk tests against images to find vulnerabilities and learn how to fix them
niko@Niko-MacBook-Pro example-frontend % docker run -p 5001:5000 example-frontend
INFO: Accepting connections at http://localhost:5000
^C
INFO: Gracefully shutting down. Please wait...
```

### 1.13
Dockerfile:
```
FROM golang:1.16

EXPOSE 8080

WORKDIR /usr/src/app

COPY . .

RUN go build

CMD ["./server"]
```
output:
```
niko@Niko-MacBook-Pro example-backend % docker run -p 8080:8080 example-backend 
[Ex 2.4+] REDIS_HOST env was not passed so redis connection is not initialized
[Ex 2.6+] POSTGRES_HOST env was not passed so postgres connection is not initialized
[GIN-debug] [WARNING] Creating an Engine instance with the Logger and Recovery middleware already attached.

[GIN-debug] [WARNING] Running in "debug" mode. Switch to "release" mode in production.
 - using env:	export GIN_MODE=release
 - using code:	gin.SetMode(gin.ReleaseMode)

[GIN-debug] GET    /ping                     --> server/router.pingpong (4 handlers)
[GIN-debug] GET    /messages                 --> server/controller.GetMessages (4 handlers)
[GIN-debug] POST   /messages                 --> server/controller.CreateMessage (4 handlers)
[GIN-debug] Listening and serving HTTP on :8080
[GIN] 2022/02/08 - 17:29:21 | 200 |      94.492µs |      172.17.0.1 | GET      "/ping"
[GIN] 2022/02/08 - 17:29:23 | 200 |       15.75µs |      172.17.0.1 | GET      "/ping"
[GIN] 2022/02/08 - 17:29:23 | 404 |       8.813µs |      172.17.0.1 | GET      "/favicon.ico"
```
### 1.14
Dockerfile front:
```
FROM node:16

EXPOSE 5000

WORKDIR /usr/src/app

COPY . .

ENV REACT_APP_BACKEND_URL=http://localhost:8080

RUN npm install
RUN npm run build

RUN npm install -g serve

CMD ["serve", "-s", "-l", "5000", "build"]
```
Dockerfile back:
```
FROM golang:1.16

EXPOSE 8080

WORKDIR /usr/src/app

ENV REQUEST_ORIGIN=http://localhost:5001

COPY . .

RUN go build

CMD ["./server"]
```
Output back:
```
niko@Niko-MacBook-Pro example-backend % docker run -p 8080:8080 example-backend
[Ex 2.4+] REDIS_HOST env was not passed so redis connection is not initialized
[Ex 2.6+] POSTGRES_HOST env was not passed so postgres connection is not initialized
[GIN-debug] [WARNING] Creating an Engine instance with the Logger and Recovery middleware already attached.

[GIN-debug] [WARNING] Running in "debug" mode. Switch to "release" mode in production.
 - using env:	export GIN_MODE=release
 - using code:	gin.SetMode(gin.ReleaseMode)

[GIN-debug] GET    /ping                     --> server/router.pingpong (4 handlers)
[GIN-debug] GET    /messages                 --> server/controller.GetMessages (4 handlers)
[GIN-debug] POST   /messages                 --> server/controller.CreateMessage (4 handlers)
[GIN-debug] Listening and serving HTTP on :8080
[GIN] 2022/02/08 - 17:44:19 | 200 |      49.913µs |      172.17.0.1 | GET      "/ping"
```
Output front:
```
niko@Niko-MacBook-Pro example-frontend % docker run -p 5001:5000 example-frontend
INFO: Accepting connections at http://localhost:5000
```
### 1.15 
skip

### 1.16
https://docker-mooc-test.herokuapp.com/

```
niko@Niko-MacBook-Pro dockertest % heroku container:login
Login Succeeded
niko@Niko-MacBook-Pro dockertest % docker tag devopsdockeruh/coursepage registry.heroku.com/docker-mooc-test/web
niko@Niko-MacBook-Pro dockertest % docker push registry.heroku.com/docker-mooc-test/web
Using default tag: latest
The push refers to repository [registry.heroku.com/docker-mooc-test/web]
6f413faad0c5: Pushed 
e15245eff772: Pushed 
25c4d12b64e7: Pushed 
1d454e07796f: Pushed 
970073eeaee3: Pushed 
8d3ac3489996: Pushed 
latest: digest: sha256:8e8b3117fe9c50b5d8abacb9fac265d6c762d319a4fa61db96b85d7310fc3512 size: 1580
niko@Niko-MacBook-Pro dockertest % heroku container:release web --app docker-mooc-test
Releasing images web to docker-mooc-test... done
```