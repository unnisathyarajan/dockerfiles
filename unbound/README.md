unbound + dnscrypt-proxy

build:
~~~ sh
sudo docker build -t unbound .
~~~

run:
~~~ sh
sudo docker run -d --name unbound -p 127.0.0.1:53:53 -p 127.0.0.1:53:53/udp unbound
~~~

logs:
~~~
sudo docker logs unbound
~~~

test:
~~~
dig @127.0.0.1 google.com
~~~
