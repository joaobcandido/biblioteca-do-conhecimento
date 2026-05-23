# como criar um extensao no vscode?
Criar uma extensão para o VS Code é surpreendentemente simples. A própria Microsoft fornece um gerador de código que cria toda a estrutura do projeto em segundos. Como você já programa, o fluxo vai ser bem natural.

Aqui está o passo a passo para criar o "esqueleto" da sua extensão.

## 1. Pré-requisitos
Você vai precisar do Node.js instalado na sua máquina e do Git.

Com o Node pronto, instale o gerador oficial do VS Code (Yo Code) e o gerenciador de pacotes vsce (usado para empacotar a extensão) rodando o seguinte comando no seu terminal:
```bash
npm install -g yo generator-code @vscode/vsce
```
## 2. Gerando o Projeto
Abra o terminal na pasta onde deseja salvar o projeto e execute:
````bash
yo code
````

