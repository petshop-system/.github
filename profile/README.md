<div>
    <div>
        <img align="right" height="400px" src="https://i.imgur.com/PY8vQtq.jpg"/>
        <h1 align="center">Seja bem-vindo ao Projeto

`Petshop-System!`
        </h1>
    </div>  
    <div>

Aqui desenvolvemos e aprimoramos continuamente um sistema eficiente para gerenciar o fluxo de processos em petshops.

### Para mais informações do projeto:

 1. [Introdução](#intro)
 2. [Design](#design)
 3. [Stack](#stack)
 4. [Padrão de Versionamento](#git)
 5. [Aplicações](#app)
 <!-- 5. [Time](#time)
 6. [Outros Conteúdos](#outros) -->


   </div>

</div>

<div>   
    <p/> &nbsp;
    <p/> &nbsp;
</br>
    <hr align="center" width="100%"/>
</div>

<div id='intro'/>  

# 1 - Introdução

Este sistema de Petshop apresenta uma arquitetura distribuída com integração entre diferentes tecnologias. Inicialmente, a autenticação é gerenciada por uma aplicação em Java, proporcionando segurança no acesso ao sistema. A aplicação principal do petshop é implementada em Go, aproveitando a eficiência e desempenho dessa linguagem.</br></br> Para promover a comunicação assíncrona e escalável entre os diferentes componentes, utiliza-se uma fila com Apache Kafka. Isso possibilita o processamento de eventos de maneira eficiente, além de fornecer uma abordagem de mensageria robusta.</br></br> Em fases futuras do desenvolvimento, está prevista a implementação de uma interface frontend para melhor interação com os usuários. Essa camada permitirá uma experiência mais amigável e intuitiva, facilitando a utilização do sistema.

<div id='design'/>  

# 2 - Design 

## 2.1 - Design System

<div>
    <img align="center" src="https://github.com/petshop-system/.github/blob/master/profile/img/petshop-system_-_design_system.png"/>
    <p/>
</div>

## 2.2 - Design de tela e fluxo

Para atender a concepção das telas e do fluxo da aplicação será utilizado o [Figma](https://www.figma.com/file/ZpoeDPZITzuaznlX7d4kHc/Petshop-System?type=design&node-id=3%3A125&mode=design&t=0rZxpFY0YyEr9pgw-1).

<div markdown="1">
<iframe style="border: 1px solid rgba(0, 0, 0, 0.1);" width="800" height="450" src="https://www.figma.com/embed?embed_host=share&url=https%3A%2F%2Fwww.figma.com%2Ffile%2FZpoeDPZITzuaznlX7d4kHc%2FPetshop-System%3Ftype%3Ddesign%26node-id%3D3%253A125%26mode%3Ddesign%26t%3D0rZxpFY0YyEr9pgw-1" allowfullscreen></iframe>
</div>
    
<div id='stack'/>  

# 3 - Stack

Para atender a solução proposta, as seguintes tecnologias estão sendo utilizadas:

* Go (Golang)
* Java (Spring Boot)
* Kafka (Message)
* PostgreSQL
* Python
* Redis (Cache)
* Swift (IOS)

<div id='git'/>  

# 4 - Padrão de Versionamento

O objetivo principal deste tópico é alinhar a utilização das boas práticas de versionamento, proporcionando um fluxo de trabalho consistente e eficiente para o desenvolvimento do projeto.

## 4.1 - Branches

| Branches | Descrição |
| --- | --- |
| `master` | **Representa a versão de produção estável.** </br></br> *(a develop é mescrlada aqui assim que estiverem pronta pra produção)* |
| `develop` |  **Branch de desenvolvimento contínuo.** </br></br> *(as features são mescladas aqui assim que estiverem prontas para teste)* |
| `feature/#numero-da-issue` | **Para alterações na documentação.** </br></br> *(criadas a partir da develop e mescladas de volta nela quando concluídas)* |
| `bugfix/#numero-da-issue` | **Para melhorias estéticas ou formatação do código.** </br></br> *(criadas a partir da develop)* |

### Iniciando uma branch para desenvolvimento

- Certifique-se de estar na branch develop:

```bash
git checkout develop
```

- Atualize a branch develop com as últimas alterações do repositório remoto:

```bash
git pull origin develop
```
- Crie um novo branch para o seu pull request:

```bash
git checkout -b feature/#numero_da_issue
```


## 4.2 - Commits

| Commit | Descrição |
| --- | --- |
| `feat:` | Para novas funcionalidades. |
| `fix:` | Para correção de bugs |
| `docs:` | Para alterações na documentação. |
| `style:` | Para melhorias estéticas ou formatação do código. |
| `refactor:` | Para refatorações no código que não corrigem bugs nem adicionam funcionalidades. |
| `test:` | Para adição ou modificação de testes. |

### Criando o commit

- Realize e confirme as alterações necessárias:

```bash
git commit -m "feat: Descrição da sua feature"
```
- Envie o branch com as alterações para o repositório remoto:

```bash
git push origin feature/#numero_da_issue
```
## 4.3 - Configuração Inicial

#### 4.3.1 - Atualizar o Repositório Local

<span style="color: orange;">Objetivo:</span> Garantir que todas as informações do repositório remoto estejam atualizadas localmente.

```bash
git fetch
```
#### 4.3.2 - Verificar as Branches Remotas Disponíveis

<span style="color: orange;">Objetivo:</span> Listar todas as branches remotas disponíveis.

```bash
git branch -r
```
* Certifique-se de que a branch develop está presente nas branches remotas.

#### 4.3.3 - Configurar o Upstream da Branch Develop

<span style="color: orange;">Objetivo:</span> Estabelecer o rastreamento da branch local develop com a branch remota origin/develop.

* Caso não exista a branch, siga criando localmente a branch develop rastreando a branch remota origin/develop:

```bash
git checkout -b develop origin/develop
```
## 4.4 - Trabalhando com Features

#### 4.4.1 - Criar uma nova branch para a Issue

<span style="color: orange;">Objetivo:</span> Isolar o desenvolvimento de novas funcionalidades.

```bash
git checkout -b feature/#numero_da_issue
```
#### 4.4.2 - Mesclar a Feature de Volta na Branch Develop

<span style="color: orange;">Objetivo:</span> Integrar as novas funcionalidades na branch principal de desenvolvimento (develop).

```bash
git checkout develop
git merge feature/#numero_da_issue
```

#### 4.4.3 - Atualizar o Repositório Remoto

<span style="color: orange;">Objetivo:</span> Sincronizar as alterações feitas na branch develop com o repositório remoto.

```bash
git push origin develop
```

## 4.5 - Corrigindo Bugs (Bugfix)

Identificação e correção de bugs são tratados com um fluxo específico.

#### 4.5.1 - Criar uma Nova Branch para o Bugfix

<span style="color: orange;">Objetivo:</span> Isolar a correção de bugs específicos.

```bash
git checkout -b bugfix/#numero_da_issue
```
#### 4.5.2 - Mesclar o Bugfix de Volta na Branch Develop:

<span style="color: orange;">Objetivo:</span> Integrar correções na branch principal de desenvolvimento.

```bash
git checkout develop
git merge feature/#numero_da_issue
```
#### 4.5.3 - Atualizar o Repositório Remoto:

<span style="color: orange;">Objetivo:</span> Sincronizar as alterações feitas na branch develop com o repositório remoto.

```bash
git push origin develop
```

<div id='app'/>  

# 5 - Aplicações

A solução que o projeto Petshop-System proporciona é suportada por um conjunto de aplicações que combinadas possibilitam que as atividades sejam executadas.

| Aplicação                                                                              | Host                          | Porta     | Linguagem |
|----------------------------------------------------------------------------------------|-------------------------------|-----------|-----------|
| [petshop-api](https://github.com/petshop-system/petshop-api)                           | localhost,petshop-api         | 5001      | Go        | 
| [petshop-api-gateway](https://github.com/petshop-system/petshop-api-gateway)           | localhost,petshop-api-gateway | 9999      | Go        |
| [petshop-admin-api](https://github.com/petshop-system/petshop-admin-api)               | localhost,petshop-admin-api   | 5002      | Java      |
| [petshop-autenticacao-api](https://github.com/petshop-system/petshop-autenticacao-api) | localhost                     | undefined | undefined |
| [petshop-bff-desktop](https://github.com/petshop-system/petshop-bff-desktop)           | localhost                     | 9998      | Java      |
| petshop-bff-mobile                                                                     | localhost                     | 9997      | undefined |
| [petshop-message-api](https://github.com/petshop-system/petshop-message-api)           | localhost,petshop-message-api | 5003      | Java      | 
| [petshop-reports-api](https://github.com/petshop-system/petshop-reports-api)           | localhost                     | undefined | Python    |
| [petshop-system-ios](https://github.com/petshop-system/petshop-system-ios)             | undefined                     | undefined | Swift (IOS)    |



Para iniciar as aplicações de forma padronizada se faz necessário configurar as variáveis de ambiente `DEV_ENV_FOLDER` e `PETSHOP_GO_FOLDER`. Essas variáveis devem conter as pastas padrões de desenvolvimento, desta forma, facilitando e padronizando a utilização do docker-compose para inicializar as aplicações.

```
$ export DEV_ENV_FOLDER=[PASTA RAÍZ DE DESENVOLVIMENTO] // ex.: /home/[MINHA_PASTA]/Desenvolvimento
$ export PETSHOP_GO_FOLDER=$GOPATH/src/github.com/petshop-system
```

Estrutura esperada.

```
DEV_ENV_FOLDER
| [JAVA_PROJECTS]
| - go
| -- src
| --- github.com
| ---- petshop-system
| ----- [GO_PROJECTS]
```

OBS: pode-se adicionar (exportar) as variáveis de ambiente ao arquivo `bashrc` ou `zshrc`.

Exemplo no arquivo `bashrc` ou `zshrc`:

```
export DEV_ENV_FOLDER=/home/[MINHA_PASTA]/Desenvolvimento
export PETSHOP_GO_FOLDER=$GOPATH/src/github.com/petshop-system
PATH=$DEV_ENV_FOLDER:$PETSHOP_GO_FOLDER:$PATH
```

## 5.1 - Arquivos

* [docker-compose](configuration/docker-compose.yaml);
* [init.sql](configuration/init.sql);
