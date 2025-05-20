+++
categories = ['Blog Técnico']
date = '2022-05-09T00:00:00+00:00'
draft = false
title = 'Arreglando cosillas: Homebrew cannot find curl'
+++

*TL;DR: instala curl con* `apt`

Hace unos días me encontré con un problema tras instalar Homebrew: no podía encontrar el binario de curl a pesar de que estaba instalado. Siguiendo la guía de brew, ejecuté el script de instalación. Todo fue bien hasta que llegó a la descarga de `portable ruby`. Al fallarme tuve que descargarlo manualmente y copiar la carpeta en el directorio que estaba buscando el instalador.

Después de este apaño la instalación terminó de forma correcta, así que hice un chequeo con `brew` para instalar algunas librerías. Por desgracia, me encontré con el siguiente error:

```shell
$ brew doctor

  Error: Please update your system curl. 
  Minimum required version: 7.41.0 
  Your curl version: 
  Your curl executable: 
  Your system is ready to brew.
```

Homebrew no estaba detectando la versión de curl a pesar de que estaba instalado en mi **Ubuntu 22.04 LTS**

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

### _La solución_

Me di cuenta de que los binarios de `curl` estaban instalados como paquetes `snap`, probablemente durante la instalación del propio Ubuntu. Así que decidí instalar `curl` usando `apt`.

```shell
$ sudo apt-get install curl
```

Tras la instalación, al ejecutar de nuevo la verificación con `brew`, todo estaba funcionando correctamente

```shell
$ brew doctor
Your system is ready to brew.
```

Problema resuelto :)

Ahora la cuestión es: esta no es una solución óptima, ya que al final lo único que estoy haciendo es duplicar los paquetes. Aunque no he llegado a probarlo, es probable que lo mejor hubiese sido encontrar por qué `brew` no es capaz de resolver el `PATH` de los binarios instalados mediante `snap` y resolverlo mediante variables de entorno. En cualquier caso, he querido dejar reflejado en este post mi solución por si a alguien le sirve de ayuda :D

> 🖼️ Una soldadora de acetileno trabajando en una fábrica de aviones en Midlands, septiembre de 1918; fotografía de George P. Lewis