 Comando para instalar o kubectl no wsl:
 ````bash
      curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
chmod +x ./kubectl
sudo mv ./kubectl /usr/local/bin/kubectl
````
Para confirmar que o kubectl foi instalado corretamente, execute o seguinte comando:
````bash
kubectl version --client
````
deve devolver algo como:

Client Version: v1.33.0  
Kustomize Version: v5.6.0

comando para instalar o multipass no wsl:
````bash
  sudo snap install multipass
````
Verifique se o diretório /snap/bin existe:
````bash
  ls /snap/bin
````
Você deverá ver o executável multipass listado.
Adicione /snap/bin ao seu PATH:
````bash
  export PATH="$PATH:/snap/bin"
````
Após executar este comando, tente usar o multipass novamente:
````bash
  multipass version
````








