### 1. Você pode obter esse endereço IP de dentro do WSL usando o seguinte comando:
````bash
cat /etc/resolv.conf | grep nameserver | awk '{print $2}'
````
### 2. instalar aws-cli:
````bash
sudo snap install aws-cli --classic
````
### 3. listar todos os s3:
````bash
aws s3 ls --endpoint-url=http://localhost:4566
````
### 4. criar um novo bucket pelo aws-cli:
````bash
aws s3api create-bucket --bucket meu-bucket1 --endpoint-url=http://localhost:4566
````

