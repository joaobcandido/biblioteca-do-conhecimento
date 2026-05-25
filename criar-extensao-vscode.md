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

 ## 5. Para compilar (fazer o build) e instalar a sua extensão definitivamente no seu VS Code local (sem depender do modo de depuração/F5), você vai precisar de uma ferramenta oficial da Microsoft chamada vsce (VS Code Extension Manager). 

 Aqui está o passo a passo simplificado para fazer isso:
 ### Passo 1: Instalar a ferramenta de empacotamento
 Abra o seu terminal (pode ser o do próprio VS Code ou o do seu sistema) e instale o @vscode/vsce globalmente usando o npm:
````bash
npm install -g @vscode/vsce
````
  ### Passo 2: Ajustar o package.json
  Antes de gerar o arquivo final, o VS Code exige que algumas informações básicas estejam preenchidas no seu arquivo package.json.     Abra ele e verifique se os seguintes campos existem e não estão com os valores padrões de template:
  - publisher: O nome do autor/editor (ex: "meu-nome"). Se não tiver esse campo, adicione: "publisher": "seu-nome-ou-empresa".
  - repository: Opcional, mas se o vsce reclamar, você pode adicionar a flag de ignorar (mostrada no passo 3).
  - engines: Garanta que a versão do VS Code declarada seja compatível com a sua atual.

  ### Passo 3: Gerar o arquivo de instalação (.vsix)
  No terminal, navegue até a pasta raiz do projeto da sua extensão e execute o comando de empacotamento:
````bash
vsce package
````
Esse comando vai ler seus arquivos, compilar o TypeScript (se houver um script de vscode:prepublish configurado) e gerar um arquivo com a extensão .vsix na raiz do seu projeto (ex: teste-01-0.0.1.vsix). Esse arquivo é o instalador da sua extensão.

  ### Passo 4: Instalar definitivamente no VS Code
  Agora que você tem o arquivo .vsix, basta instalá-lo diretamente no seu editor:
  - Abra o VS Code.
  - Vá até a aba de Extensões (Ctrl+Shift+X ou Cmd+Shift+X).
  - Clique nos três pontinhos (...) no canto superior direito do painel de extensões.
  - Selecione a opção "Instalar de VSIX..." (Install from VSIX...).
  - Escolha o arquivo .vsix que foi gerado no Passo 3.
    
Pronto! A extensão agora está instalada de forma definitiva no seu ambiente de trabalho. Ela vai carregar automaticamente toda vez que você abrir o VS Code, exatamente como qualquer outra extensão baixada da Marketplace. Se você quiser atualizar o código no futuro, basta alterar a versão no package.json, rodar o vsce package novamente e reinstalar o novo arquivo gerador.











  
