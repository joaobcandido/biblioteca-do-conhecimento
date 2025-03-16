### 1. Você pode obter esse endereço IP de dentro do WSL usando o seguinte comando:
````bash
cat /etc/resolv.conf | grep nameserver | awk '{print $2}'
````
### 2. instalar aws-cli:
````bash
sudo snap install aws-cli --classic
````

