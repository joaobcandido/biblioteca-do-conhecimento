# como subir um container localstack com o podman
### 1. crie um arquivo com o nome docker-compose.yml na raiz do projeto:
````yml
version: '3.9'
services:
  localstack:
    image: docker.io/localstack/localstack:latest
    container_name: local-aws-service
    environment:
     - SERVICES= s3,sqs,lambda,dynamodb
     - AWS_ACCESS_KEY_ID=test
     - AWS_SECRET_ACCESS_KEY=test
     - AWS_DEFAULT_REGION=us-east-1
    ports:
      - "4566:4566"
    volumes:
      - ./localstack-data:/var/lib/localstack
````
### 2. dentro do diretorio que contem o arquivo docker-compose.yml ,rode o comando:
````bash
podman-compose up
````
se deu tudo certo retorna algo como:
````bash
[localstack] | Ready.
````
### 3. abra um novo terminal e verifique se tem o aws-cli instalado:
````bash
aws --version
````
se deu tudo certo retorna algo como:
````bash
aws-cli/2.24.24 Python/3.12.9 Linux/5.15.167.4-microsoft-standard-WSL2 exe/x86_64.ubuntu.24
````

### 4. criando um novo bucket pelo terminal:
````bash
aws s3api create-bucket --bucket meu-bucket --endpoint-url=http://localhost:4566
````
se deu tudo certo retorna algo como:
````bash
{
    "Location": "/meu-bucket"
}
````
### 5. lista todos os buckets s3:
````bash
aws s3 ls --endpoint-url=http://localhost:4566
````
retorna algo como:
````bash
2025-03-16 10:36:12 meu-bucket
````
### 6. verificar na localstack ui atravez do caminho:
````bash
https://app.localstack.cloud/inst/default/resources/s3
````
![image](https://github.com/user-attachments/assets/66141d5d-0846-4b7f-8004-5e6883d4333e)


### 7. criar outro bucket agora pela ui:
![capture_250316_112309](https://github.com/user-attachments/assets/5cdf2909-d2a5-41cc-9769-e0ae8736c967)
![capture_250316_112509](https://github.com/user-attachments/assets/cd05c624-5f54-458c-ae45-0d7465284603)
![capture_250316_112758](https://github.com/user-attachments/assets/0e3209cc-d966-43c5-8c03-3ef91b4c10f5)
listar pelo terminal para confirmar:
````bash
aws s3 ls --endpoint-url=http://localhost:4566
````
deve aparecer algo como:
````bash
2025-03-16 10:36:12 meu-bucket
2025-03-16 11:27:33 meu-bucket-criado-pela-ui
````

