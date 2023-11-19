# hortonworks_sandbox
for Hortonworks Sandbox on Ubuntu20

Install docker
```
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
sudo apt install docker-ce
sudo systemctl status docker
sudo usermod -aG docker username
su - username
sudo usermod -aG docker username
```

```
sudo apt install unzip -y
curl -O https://archive.cloudera.com/hwx-sandbox/hdp/hdp-2.6.5/HDP_2.6.5_deploy-scripts_180624d542a25.zip
unzip HDP_2.6.5_deploy-scripts_180624d542a25.zip
bash docker-deploy-hdp265.sh
curl localhost:8080
```

Apache Ambari should now be available in the browser from
http://localhost:8080/#/login
Username: raj_ops
Password: raj_ops
Logout now. Login via Port 2222. HDP Sandbox terminal can be accessed from
Port: 2222
Username: root
Password: hadoop
Login using these credentials at Port 2222
After logging in verify,
sandbox-version
Output should be:


Check installed version of Hadoop and Hive
hadoop version
hive --version
Hadoop 2.7.3.2.6.5.0-292 & Hive 1.2.1000.2.6.5.0-292 should be obtained.
On reboot, the docker container does not start. Do the follow for it to restart after every reboot.
sudo reboot
docker stop sandbox-hdp
docker stop sandbox-proxy
docker update --restart unless-stopped sandbox-hdp
docker update --restart unless-stopped sandbox-proxy
docker container start sandbox-hdp
docker container start sandbox-proxy
Checking docker container status with:
docker container ls -a
bash docker-deploy-hdp265.sh

sudo sandbox/proxy/proxy-deploy.sh
