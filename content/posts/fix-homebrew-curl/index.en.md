+++
categories = ['technical']
date = '2022-05-09T00:00:00+00:00'
draft = false
title = 'Fixing stuff: Homebrew cannot find curl'
+++

*TL;DR: install curl using* `apt`

A few days ago I ran into a problem after installing Homebrew: it couldn’t find the curl binary even though it was already installed. Following the Homebrew guide, I ran the installation script. Everything went fine until it got to downloading `portable ruby`. Since that part failed, I had to manually download it and copy the folder to the directory the installer was looking for.

After that quick fix, the installation completed successfully, so I ran a check using `brew` to install some libraries. Unfortunately, I encountered the following error:

```shell
$ brew doctor

  Error: Please update your system curl. 
  Minimum required version: 7.41.0 
  Your curl version: 
  Your curl executable: 
  Your system is ready to brew.
```

Homebrew wasn’t detecting the curl version even though it was installed on my Ubuntu 22.04 LTS

```shell
$ curl --version

  curl 7.82.0 (x86_64-pc-linux-gnu) libcurl/7.82.0 OpenSSL/1.1.1f
  zlib/1.2.11 brotli/1.0.7 zstd/1.4.4 libidn2/2.2.0 libpsl/0.21.0
  (+libidn2/2.2.0) libssh/0.9.3/openssl/zlib nghttp2/1.40.0 librtmp/2.3
  libgsasl/1.8.1 OpenLDAP/2.4.49 
  Release-Date: 2022-03-05 
  Protocols: dict file ftp ftps gopher gophers http https imap imaps
  ldap ldaps mqtt pop3 pop3s rtmp rtsp scp sftp smb smbs smtp smtps
  telnet tftp
  Features: alt-svc AsynchDNS brotli gsasl GSS-API HSTS HTTP2
  HTTPS-proxy IDN IPv6 Kerberos Largefile libz NTLM NTLM_WB PSL SPNEGO
  SSL TLS-SRP UnixSockets zstd
```

### _The solution_

I realized that the curl binaries were installed as snap packages, probably during Ubuntu’s own installation process. So I decided to install curl using apt.

```shell
$ sudo apt-get install curl
```

After the installation, running brew doctor again showed everything was working correctly:

```shell
$ brew doctor
Your system is ready to brew.
```

Problem solved :)

Now, the thing is: this isn’t the most optimal solution, since I’m essentially duplicating packages. Although I didn’t try it, the best approach would probably be to investigate why brew can’t resolve the PATH for binaries installed via snap, and fix it using environment variables. In any case, I wanted to share my workaround here in case it helps someone else :D

> 🖼️ A female acetylene welder at work in an aircraft factory in the Midlands, September 1918; photograph by George P. Lewis