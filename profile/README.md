<div>
    <div>
        <img align="right" height="350px" src="https://i.imgur.com/PY8vQtq.jpg"/>
        <h1 align="center">Petshop-System</h1>
    </div>
    <div>
    <p>Seja bem-vindo a página do Petshop-System! Aqui desenvolvemos e aprimoramos continuamente um sistema eficiente para gerenciar o fluxo de processos em petshops.</p>

### Para mais informações do projeto:

 1. [Introdução](#intro)
 2. [Regras de Versionamento](#git)
 3. [Aplicações](#app)
 4. [Time](#time)
 4. [Outros Conteúdos](#outros)



    </div>
</div>



*****

<div id='intro'/>  

# 1 - Introdução:

Este sistema de Petshop apresenta uma arquitetura distribuída com integração entre diferentes tecnologias. Inicialmente, a autenticação é gerenciada por uma aplicação em Java, proporcionando segurança no acesso ao sistema. A aplicação principal do petshop é implementada em Go, aproveitando a eficiência e desempenho dessa linguagem.

Para promover a comunicação assíncrona e escalável entre os diferentes componentes, utiliza-se uma fila com Apache Kafka. Isso possibilita o processamento de eventos de maneira eficiente, além de fornecer uma abordagem de mensageria robusta.

Em fases futuras do desenvolvimento, está prevista a implementação de uma interface frontend para melhor interação com os usuários. Essa camada permitirá uma experiência mais amigável e intuitiva, facilitando a utilização do sistema.



<div id='git'/>  

 # 2 - Regras de Versionamento:

O objetivo principal deste tópico é alinhar a utilização das boas práticas de versionamento, proporcionando um fluxo de trabalho consistente e eficiente para o desenvolvimento do projeto.

## 2.1 - Branches & Commits:



#### 2.1.1 - Branches:

* <span style="color: yellow;">master:</span>
    * Representa a versão de produção estável.

* <span style="color: yellow;">develop:</span> 
    * Branch de desenvolvimento contínuo. 
    * As features são mescladas aqui assim que estiverem prontas para teste.

* <span style="color: yellow;">feature/<span style="color: gray;">[#numero-da-issue]:</span></span>
    * Branches para desenvolvimento de novas funcionalidades. 
    * Criadas a partir de develop e mescladas de volta nela quando concluídas.

* <span style="color: yellow;">bugfix/<span style="color: gray;">[#numero-da-issue]:</span></span> 
    * Semelhante às features, mas para correção de bugs. 
    * Criadas a partir de develop.

#### 2.1.2 - Commits:

* <span style="color: yellow;">feat:</span>
    * Para novas funcionalidades.
* <span style="color: yellow;">fix:</span>
    * Para correção de bugs.
* <span style="color: yellow;">docs:</span>
    * Para alterações na documentação.
* <span style="color: yellow;">style:</span>
    * Para melhorias estéticas ou formatação do código.
* <span style="color: yellow;">refactor:</span>
    * Para refatorações no código que não corrigem bugs nem adicionam funcionalidades.
* <span style="color: yellow;">test:</span>
    * Para adição ou modificação de testes.

## 2.2 - Configuração Inicial:

#### 2.2.1 - Atualizar o Repositório Local:
<span style="color: orange;">Objetivo:</span> Garantir que todas as informações do repositório remoto estejam atualizadas localmente.

```
git fetch
```
#### 2.2.2 - Verificar as Branches Remotas Disponíveis:
<span style="color: orange;">Objetivo:</span> Listar todas as branches remotas disponíveis.

```
git branch -r
```
* Certifique-se de que a branch develop está presente nas branches remotas.

#### 2.2.3 - Configurar o Upstream da Branch Develop:
<span style="color: orange;">Objetivo:</span> Estabelecer o rastreamento da branch local develop com a branch remota origin/develop.


* Caso não exista a branch, siga criando localmente a branch develop rastreando a branch remota origin/develop:
```
git checkout -b develop origin/develop
```

## 2.3 - Trabalhando com Features:

#### 2.3.1 - Criar uma nova branch para a Issue:
<span style="color: orange;">Objetivo:</span> Isolar o desenvolvimento de novas funcionalidades.

```
git checkout -b feature/#numero_da_issue
```
#### 2.3.2 - Mesclar a Feature de Volta na Branch Develop:
<span style="color: orange;">Objetivo:</span> Integrar as novas funcionalidades na branch principal de desenvolvimento (develop).
```
git checkout develop
git merge feature/#numero_da_issue
```

#### 2.3.3 - Atualizar o Repositório Remoto:
<span style="color: orange;">Objetivo:</span> Sincronizar as alterações feitas na branch develop com o repositório remoto.
Impacto: Mantém o repositório remoto atualizado, permitindo que outros membros da equipe acessem as últimas atualizações.
```
git push origin develop
```

## 2.4 - Corrigindo Bugs (Bugfix):
Identificação e correção de bugs são tratados com um fluxo específico.

#### 2.4.1 - Criar uma Nova Branch para o Bugfix:
<span style="color: orange;">Objetivo:</span> Isolar a correção de bugs específicos.

```
git checkout -b bugfix/#numero_da_issue
```
#### 2.4.2 - Mesclar o Bugfix de Volta na Branch Develop:
<span style="color: orange;">Objetivo:</span> Integrar correções na branch principal de desenvolvimento.
Impacto: Garante que correções estejam disponíveis para testes e revisão.

```
git checkout develop
git merge feature/#numero_da_issue
```
#### 2.4.3 - Atualizar o Repositório Remoto:
<span style="color: orange;">Objetivo:</span> Sincronizar as alterações feitas na branch develop com o repositório remoto.

```
git push origin develop
```
