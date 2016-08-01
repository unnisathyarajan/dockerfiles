dnsmasq + dnscrypt-proxy (okTurtles and DNSCrypt.eu)

build:
~~~ sh
sudo docker build -t dnsmasq .
~~~

run:
~~~ sh
sudo docker run -d --name dnsmasq -p 127.0.0.1:53:53 -p 127.0.0.1:53:53/udp dnsmasq
~~~

logs:
~~~
sudo docker logs dnsmasq
~~~

test:
~~~
dig @127.0.0.1 google.com
~~~
