# references 

https://www.digitalocean.com/community/tutorials/how-to-configure-consul-in-a-production-environment-on-ubuntu-14-04
https://jee-appy.blogspot.com/2015/09/consul-setup-tutorial.html


# To create Consul servers 

# to update linux VM

sudo apt  update

# to install unzip package 

sudo apt install unzip

# to install consul on linux machine 

cd /usr/local/bin
sudo wget https://releases.hashicorp.com/consul/1.4.4/consul_1.4.4_linux_amd64.zip

sudo unzip *.zip
sudo rm *.zip

# to run 

sudo consul -v

# to start agent with server mode 

sudo consul agent -server -data-dir /tmp/consul


#to join servers (only private IP Address can be used)

sudo consul join 10.0.0.5 


Repeat above steps to join multiple servers in server mode



# To create a client, follow the above steps and then create 

sudo consul agent -data-dir /tmp/consul -client 10.0.0.7 -ui -join 10.0.0.4

# To access the site 

http://13.71.7.48:8500/ui/dc1/services/consul
