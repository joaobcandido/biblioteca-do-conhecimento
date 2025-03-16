# comandos aws-cli 

### 1. listar todos os buckets s3:
````bash
aws s3 ls --endpoint-url=http://localhost:4566
````
### 2. criar um novo bucket pelo aws-cli:
````bash
aws s3api create-bucket --bucket meu-bucket1 --endpoint-url=http://localhost:4566
````
