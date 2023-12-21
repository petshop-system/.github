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
 2. [System Design](#system_design)
 3. [Padrão de Versionamento](#git)
<!-- 4. [Aplicações](#app)
 5. [Time](#time)
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

# 1 - Introdução:

Este sistema de Petshop apresenta uma arquitetura distribuída com integração entre diferentes tecnologias. Inicialmente, a autenticação é gerenciada por uma aplicação em Java, proporcionando segurança no acesso ao sistema. A aplicação principal do petshop é implementada em Go, aproveitando a eficiência e desempenho dessa linguagem.</br></br> Para promover a comunicação assíncrona e escalável entre os diferentes componentes, utiliza-se uma fila com Apache Kafka. Isso possibilita o processamento de eventos de maneira eficiente, além de fornecer uma abordagem de mensageria robusta.</br></br> Em fases futuras do desenvolvimento, está prevista a implementação de uma interface frontend para melhor interação com os usuários. Essa camada permitirá uma experiência mais amigável e intuitiva, facilitando a utilização do sistema.

<div id='system_design'/>  

# 2 - Design System

<div>
    <img align="center" src="https://github.com/petshop-system/.github/blob/master/profile/img/petshop-system_-_design_system.png"/>
    <p/>
</div>
    
<div id='git'/>  

# 3 - Padrão de Versionamento:

O objetivo principal deste tópico é alinhar a utilização das boas práticas de versionamento, proporcionando um fluxo de trabalho consistente e eficiente para o desenvolvimento do projeto.

## 3.1 - Branches:

| Branches | Descrição |
| --- | --- |
| `master` | **Representa a versão de produção estável.** </br></br> *(a develop é mescrlada aqui assim que estiverem pronta pra produção)* |
| `develop` |  **Branch de desenvolvimento contínuo.** </br></br> *(as features são mescladas aqui assim que estiverem prontas para teste)* |
| `feature/#numero-da-issue` | **Para alterações na documentação.** </br></br> *(criadas a partir da develop e mescladas de volta nela quando concluídas)* |
| `bugfix/#numero-da-issue` | **Para melhorias estéticas ou formatação do código.** </br></br> *(criadas a partir da develop)* |



### Iniciando uma branch para desenvolvimento:

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


## 3.2 - Commits:

| Commit | Descrição |
| --- | --- |
| `feat:` | Para novas funcionalidades. |
| `fix:` | Para correção de bugs |
| `docs:` | Para alterações na documentação. |
| `style:` | Para melhorias estéticas ou formatação do código. |
| `refactor:` | Para refatorações no código que não corrigem bugs nem adicionam funcionalidades. |
| `test:` | Para adição ou modificação de testes. |

### Criando o commit:

- Realize e confirme as alterações necessárias:

```bash
git commit -m "feat: Descrição da sua feature"
```
- Envie o branch com as alterações para o repositório remoto:

```bash
git push origin feature/#numero_da_issue
```
## 3.3 - Configuração Inicial:

#### 2.3.1 - Atualizar o Repositório Local:

<span style="color: orange;">Objetivo:</span> Garantir que todas as informações do repositório remoto estejam atualizadas localmente.

```bash
git fetch
```
#### 3.3.2 - Verificar as Branches Remotas Disponíveis:

<span style="color: orange;">Objetivo:</span> Listar todas as branches remotas disponíveis.

```bash
git branch -r
```
* Certifique-se de que a branch develop está presente nas branches remotas.

#### 3.3.3 - Configurar o Upstream da Branch Develop:

<span style="color: orange;">Objetivo:</span> Estabelecer o rastreamento da branch local develop com a branch remota origin/develop.

* Caso não exista a branch, siga criando localmente a branch develop rastreando a branch remota origin/develop:

```bash
git checkout -b develop origin/develop
```
## 3.4 - Trabalhando com Features:

#### 3.4.1 - Criar uma nova branch para a Issue:

<span style="color: orange;">Objetivo:</span> Isolar o desenvolvimento de novas funcionalidades.

```bash
git checkout -b feature/#numero_da_issue
```
#### 3.4.2 - Mesclar a Feature de Volta na Branch Develop:

<span style="color: orange;">Objetivo:</span> Integrar as novas funcionalidades na branch principal de desenvolvimento (develop).

```bash
git checkout develop
git merge feature/#numero_da_issue
```

#### 3.4.3 - Atualizar o Repositório Remoto:

<span style="color: orange;">Objetivo:</span> Sincronizar as alterações feitas na branch develop com o repositório remoto.

```bash
git push origin develop
```

## 3.5 - Corrigindo Bugs (Bugfix):

Identificação e correção de bugs são tratados com um fluxo específico.

#### 3.5.1 - Criar uma Nova Branch para o Bugfix:

<span style="color: orange;">Objetivo:</span> Isolar a correção de bugs específicos.

```bash
git checkout -b bugfix/#numero_da_issue
```
#### 3.5.2 - Mesclar o Bugfix de Volta na Branch Develop:

<span style="color: orange;">Objetivo:</span> Integrar correções na branch principal de desenvolvimento.

```bash
git checkout develop
git merge feature/#numero_da_issue
```
#### 3.5.3 - Atualizar o Repositório Remoto:

<span style="color: orange;">Objetivo:</span> Sincronizar as alterações feitas na branch develop com o repositório remoto.

```bash
git push origin develop
```
