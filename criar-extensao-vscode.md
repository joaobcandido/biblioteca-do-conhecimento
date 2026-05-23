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
O assistente vai te fazer algumas perguntas. Para criar o agente do Copilot, escolha as seguintes opções:

**What type of extension do you want to create?** Escolha New Extension (TypeScript).

**What's the name of your extension?** Digite algo como teste-01.

**What's the identifier of your extension?** Pode dar Enter para aceitar o padrão (teste-01).

**What's the description?** Uma breve descrição (ex: teste).

Initialize a git repository? Yes.

Bundle the source code with webpack? No (para começar simples, mas pode escolher Yes se preferir).

Which package manager to use? npm.

Pronto! O gerador vai criar uma pasta com todos os arquivos necessários.

## 3. Entendendo a Estrutura do Projeto
Abra a pasta gerada no seu VS Code. Os dois arquivos mais importantes que você vai mexer são:
- **package.json:** É o manifesto da extensão. É aqui que você diz ao VS Code quando sua extensão deve ser ativada (activation events) e quais comandos ou agentes de chat ela vai registrar (contributes).
- **src/extension.ts:** É o ponto de entrada do código. É aqui que a mágica acontece e onde você vai colar a lógica do agente do Copilot que passei na resposta anterior.

  ## 4. Testando e Depurando (Debug)
O VS Code torna o teste de extensões extremamente fácil:

Dentro do projeto da sua extensão, aperte F5 (ou vá na aba de Debug e clique em "Run and Debug").

Uma nova janela do VS Code vai se abrir. Essa janela é chamada de Extension Development Host. Ele já roda com a sua extensão instalada e ativa.

Para testar o comando padrão que o gerador cria: nessa nova janela, aperte Ctrl + Shift + P (ou Cmd + Shift + P no Mac), digite Hello World e dê Enter. Uma notificação vai aparecer no canto inferior direito.











  
