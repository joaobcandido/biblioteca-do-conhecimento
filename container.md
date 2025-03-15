### 1. Publicando nossa App Java dentro de um container:
crie um arquivo na raiz do projeto
````bash
Dockerfile
````
### 2. build o projeto com o comando:
````bash
./mvnw install
````
isso gera um arquivo .jar na pasta target

### 3. adicione esse conteudo no arquivo Dockerfile:
````dockerfile
FROM docker.io/openjdk:21
WORKDIR api
COPY target/api-0.0.1-SNAPSHOT.jar api.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "api.jar"]
````

### 4. crie a imagem:
````bash
podman build . -t jocandido/public-api:lasted
````
### 5. para fazer login no podman abra o arquivo :
````bash
sudo nano /etc/containers/registries.conf
````
adicione essas linhas e salve:
````bash
unqualified-search-registries = ["docker.io"]

[[registry]]
prefix = "docker.io"
location = "docker.io"
````
### 6. faça login com o comando:
````bash
 podman login
````
### 7. envie a imagem para o dockerhub:
````bash
 podman  push jocandido/public-api:latest
````
### 8. para criar um container com a imagem da aplicacao use o comando:
````bash
podman run -p 8080:8080 jocandido/public-api:latest
````




