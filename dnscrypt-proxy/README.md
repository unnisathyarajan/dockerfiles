dnscrypt-proxy containers for okturtles.com and dnscrypt.eu

okTurtles
~~~
docker build -t okurtles .
docker run -d --name okturtles.com -p 127.0.0.1:1053:1053 -p 127.0.0.1:1053:1053/udp okturtles
~~~

DNSCrypt.eu
~~~
docker build -t dnscrypt
docker run -d --name dnscrypt.eu -p 127.0.0.1:2053:2053 -p 127.0.0.1:2053:2053/udp dnscrypt.eu
~~~

Lookup
~~~
dig -p 1053 @127.0.0.1 xe.com
dig -p 2053 @127.0.0.1 google.com
~~~




