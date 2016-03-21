Vault Docker Container

~~~ sh
sudo docker run --name vault -d -p 8200:8200 -v /data/vault:/var/lib/vault vault
~~~
