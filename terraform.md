 Instalar o Terraform no WSL (Windows Subsystem for Linux) é um processo relativamente simples.
 Aqui estão os passos que você pode seguir, geralmente focando em distribuições Linux baseadas em Debian/Ubuntu, que são muito comuns no WSL:<br>
 ### 1. Atualizar Pacotes:
 Primeiro, é sempre bom garantir que seus pacotes estejam atualizados. Abra seu terminal WSL e execute:
  ````bash
  sudo apt update && sudo apt upgrade -y
  ````
  
  ### 2. Adicionar o Repositório HashiCorp:
  A HashiCorp, a empresa por trás do Terraform, mantém um repositório oficial. Para adicionar
  a chave GPG e o repositório, execute os seguintes comandos:
  ````bash
curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -
sudo apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"
````
### 3. Instalar o Terraform:
Agora que o repositório está adicionado, você pode instalar o Terraform:
````bash
sudo apt update && sudo apt install terraform
````
### 4. Verificar a Instalação:
Para verificar se o Terraform foi instalado corretamente, execute:
````bash
terraform --version
````


