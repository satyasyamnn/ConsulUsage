# How to setup Consul 

## To create Consul servers 

### Update linux VM

sudo apt  update

### To install unzip package 

sudo apt install unzip

### To install consul on linux machine 

cd /usr/local/bin  
sudo wget https://releases.hashicorp.com/consul/1.4.4/consul_1.4.4_linux_amd64.zip  
sudo unzip *.zip  
sudo rm *.zip  

### To check Consul run 

sudo consul -v

### To start agent with server mode 

sudo consul agent -server -data-dir /tmp/consul


### To join consul servers (only private IP Address can be used)

sudo consul join 10.0.0.5 


### Repeat above steps to join multiple servers in server mode

## To create a client, follow the above steps and then create 

sudo consul agent -data-dir /tmp/consul -client <<private address>> -ui -join <<server private address>>  

Important point to note is, use private address of client to join to the server

### To access the site 

Use pubic IP of the client machine to acces

http://<<public address>>:8500/ui/dc1/services/consul


## references 

https://www.digitalocean.com/community/tutorials/how-to-configure-consul-in-a-production-environment-on-ubuntu-14-04  
https://jee-appy.blogspot.com/2015/09/consul-setup-tutorial.html  
