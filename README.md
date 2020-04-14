1) Clone this repo in any directory on your machine and choose this directory as your working directory.
```bash
sudo git clone https://github.com/mjco0085/docker_tomcat
```
2) Check settings in files server.xml (ports on Connectors) and Dockerfile (ports for authbind) 
it's 80 for HTTPS and 443 for HTTPS by default. You may change it, if you need, but dont forget to change it in both places.
3) Run building docker image by command
```bash
sudo docker build -t my_image .
```
4) Run container by command
```bash
sudo docker run  run my_image -p 80:80 -p 443:443
```
Dont't forget to change ports for you own settings, if it needs.
___________________
Btw, you can create you own certificate by command from main directory of repo.(You should delete old certificates first.)
```bash
sudo openssl req -x509 -newkey rsa:4096 -keyout ./ssl/localhost-rsa-key.pem -out ./ssl/localhost-rsa-cert.pem -days 36500
```
