### 1. Você pode obter esse endereço IP de dentro do WSL usando o seguinte comando:
````bash
cat /etc/resolv.conf | grep nameserver | awk '{print $2}'
````
### 2. instalar aws-cli:
````bash
sudo snap install aws-cli --classic
````
### 3. comando para verificar se a port esta rodando algum processo:
````bash
  sudo lsof -i :5432
````

### 4. comando para matar o processo:
```bash
sudo kill -9 <pid>
````

