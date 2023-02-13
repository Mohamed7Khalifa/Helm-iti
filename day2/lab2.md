install helm in ubuntu:
```bash
curl https://baltocdn.com/helm/signing.asc | gpg --dearmor | sudo tee /usr/share/keyrings/helm.gpg > /dev/null
sudo apt-get install apt-transport-https --yes
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/helm.gpg] https://baltocdn.com/helm/stable/debian/ all main" | sudo tee /etc/apt/sources.list.d/helm-stable-debian.list
sudo apt-get update
sudo apt-get install helm
```

add bitnami repo:
```bash
helm repo add bitnami https://charts.bitnami.com/bitnami
helm repo update
```

install redis repo
```bash
 helm install redis bitnami/redis
```

install docker and pull python image:

```bash
sudo apt update
sudo apt install apt-transport-https ca-certificates curl software-properties-common
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu focal stable"
apt-cache policy docker-ce
sudo apt install docker-ce -y
sudo usermod -aG docker ${USER}
```

```bash
docker pull osamahassan/paython_helm_app
```

create python chart:
```bash
helm create python_app 
```
change dir to templates to check the files:
```bash
cd python_app/templates
ls
```
delete all files:
```bash
rm -r templates/*
```


