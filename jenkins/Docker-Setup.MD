## Install Docker
```sh
yum install docker
systemctl start docker    #service docker status (old command)
systemctl enable docker   #service docker start (old command)
chkconfig docker on       #docker service start on reboot of instance
```

## provide permissions to jenkins user in jenkins server to access docker
```sh
  sudo groupadd docker                 #when we install docker by default we will get a group docker--->cat /etc/group | grep -i docker
  sudo usermod -aG docker jenkins      # adding the jenkins user to the docker group--sothat whenever we can run docker comands from jenkins
  sudo chmod 777 /var/run/docker.sock  # we need to provide full accesss to docker.soc file so that jenkins can able to access it
```
## Add Jenkins user into sudoers file to get sudo access
```sh
   vi /etc/sudoers
   jenkins ALL=(ALL) NOPASSWD: ALL
```   
   

