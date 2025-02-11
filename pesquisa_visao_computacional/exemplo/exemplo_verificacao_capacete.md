# Laboratório Prático - Criando verificação de Capacete com Custom Vision

* Abra o [portal do Azure](https://portal.azure.com/):
* Acesse Mais Recursos  e depois IA + Machine Learning
* Clique em Azure AI services para criar recursos do Serviços Cognitivos.

![alt text](../inputs/image.png)

* Crie um Grupo de Recursos, caso ainda não tenha
* Atribua um nome ao Grupo de Recursos

![alt text](../inputs/image-1.png)

![alt text](../inputs/image-2.png)

* Importante:
     - Adicionar uma região para o recurso
     - nomear o recurso
     - Escolher o tipo de preço **Standard S0**
     - Deixar a caixa "Ao marcar essa caixa, confirmo que li e compreendi todos os termos abaixo" - como **checada**
     - Depois Clique em Revisar e Criar e Criar novamente

![alt text](../inputs/image-3.png)

* Acesse o Serviço Cognitivo criado
* Clique em Chaves e Ponto de extremidade
* Guarde a chave e a região que criamos o serviço, iremos precisar para a aplicação

![alt text](img/image.png)

# Criando Projeto no Studio Custom Vision

Após criar os serviços cognitivos no Azure acesso o [Studio do Custom Vision](https://www.customvision.ai/)

* Clique em New Project

![alt text](img/image-1.png)

* Adicione um nome para o projeto: ""

![alt text](img/image-2.png)

* Clique em Criar Projeto e Aguarde
Agora podemos adicionar as fotos de trabalhadores com capacetes e trabalhadores sem capacete

![alt text](img/image-3.png)

* Após selecionar as imagens, coloque a tag "com_capacete"

![alt text](img/image-4.png)

* Adicione as imagens de colaboradores sem capacete, e adcione a tag "sem_capacete"

![alt text](img/image-5.png)

* Após adicionar todas as imagens
* Clique em Train para treinar o modelo

![alt text](img/image-6.png)
* Selecione: Quick Training
* Clique em Train

![alt text](img/image-7.png)

* Aguarde

![alt text](img/image-8.png)

Quando finalizar podemos testar se o modelo está bem treinado:
![alt text](img/image-9.png)

* Clique no Test e copie a URL de imagem de pessoa com capacete e uma sem capacete para verificar

## Com Capacete

![alt text](img/image-10.png)

## Sem Capacete

![alt text](img/image-11.png)

Agora Publique o modelo:
* Clique em Publish
* Adicione um nome para o modelo
* Selecione o Servico Cognitivo

![alt text](img/image-12.png)

* Agora acesse o Preciction URL para adicionar na aplciação
Você usará a URL no código da aplciação

![alt text](img/image-13.png)


# Criando a Aplicação

Em uma janela de console (como cmd, PowerShell ou Bash), crie um novo diretório para seu aplicativo e navegue até ele.

1. Criar um novo aplicativo do Node.js

    Em uma janela de console (como cmd, PowerShell ou Bash), crie um novo diretório para seu aplicativo e navegue até ele.

    > mkdir myappdetectepi && cd myappmyappdetectepi

    Execute o comando npm init para criar um aplicativo do Node com um arquivo package.json.

    > npm init

2. Instalar os pacotes npm @azure-rest/ai-vision-face:
    > npm install @azure-rest/ai-vision-face

    O arquivo package.json do seu aplicativo é atualizado com as dependências.

3. Crie um arquivo chamado index.html, abra o editor VS Code e crie o arquivo (veja o arquivo completo index.html - exemplo pasta code)
