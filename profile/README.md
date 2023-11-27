<div>
    <div>
        <img align="right" height="400px" src="https://i.imgur.com/PY8vQtq.jpg"/>
        <h1 align="center">Petshop-System</h1>
    </div>
    <div>

Seja bem-vindo a página do
`Petshop-System!`
> Aqui desenvolvemos e aprimoramos continuamente um sistema eficiente para gerenciar o fluxo de processos em petshops.

### Para mais informações do projeto:

 1. [Introdução](#intro)
 2. [Regras de Versionamento](#git)
 3. [Aplicações](#app)
 4. [Time](#time)
 4. [Outros Conteúdos](#outros)

    </div>
    <div>   

    ******

    </div>
</div>

<div id='intro'/>  

# 1 - Introdução:

> Este sistema de Petshop apresenta uma arquitetura distribuída com integração entre diferentes tecnologias. Inicialmente, a autenticação é gerenciada por uma aplicação em Java, proporcionando segurança no acesso ao sistema. A aplicação principal do petshop é implementada em Go, aproveitando a eficiência e desempenho dessa linguagem.</br></br> Para promover a comunicação assíncrona e escalável entre os diferentes componentes, utiliza-se uma fila com Apache Kafka. Isso possibilita o processamento de eventos de maneira eficiente, além de fornecer uma abordagem de mensageria robusta.</br></br> Em fases futuras do desenvolvimento, está prevista a implementação de uma interface frontend para melhor interação com os usuários. Essa camada permitirá uma experiência mais amigável e intuitiva, facilitando a utilização do sistema.

<div id='git'/>  

 # 2 - Regras de Versionamento:

>O objetivo principal deste tópico é alinhar a utilização das boas práticas de versionamento, proporcionando um fluxo de trabalho consistente e eficiente para o desenvolvimento do projeto.

## 2.1 - Branches:

| Branches | Descrição |
| --- | --- |
| `master` | **Representa a versão de produção estável.** </br></br> *(a develop é mescrlada aqui assim que estiverem pronta pra produção)* |
| `develop` |  **Branch de desenvolvimento contínuo.** </br></br> *(as features são mescladas aqui assim que estiverem prontas para teste)* |
| `feature/[#numero-da-issue]` | **Para alterações na documentação.** </br></br> *(criadas a partir de develop e mescladas de volta nela quando concluídas)* |
| `bugfix/[#numero-da-issue]` | **Para melhorias estéticas ou formatação do código.** </br></br> *(criadas a partir de develop)* |

- Exemplo:
```bash
git checkout -b feature/#3"
```

## 2.2 - Commits:

| Commit | Descrição |
| --- | --- |
| `feat:` | Para novas funcionalidades. |
| `fix:` | Para correção de bugs |
| `docs:` | Para alterações na documentação. |
| `style:` | Para melhorias estéticas ou formatação do código. |
| `refactor:` | Para refatorações no código que não corrigem bugs nem adicionam funcionalidades. |
| `test:` | Para adição ou modificação de testes. |

- Exemplo:
```bash
git commit -m "feat: Adiciona funcionalidade de cadastro de usuários"
```

## 2.3 - Configuração Inicial:

#### 2.2.1 - Atualizar o Repositório Local:
<span style="color: orange;">Objetivo:</span> Garantir que todas as informações do repositório remoto estejam atualizadas localmente.

```
git fetch
```
#### 2.3.2 - Verificar as Branches Remotas Disponíveis:
<span style="color: orange;">Objetivo:</span> Listar todas as branches remotas disponíveis.

```
git branch -r
```
* Certifique-se de que a branch develop está presente nas branches remotas.

#### 2.3.3 - Configurar o Upstream da Branch Develop:
<span style="color: orange;">Objetivo:</span> Estabelecer o rastreamento da branch local develop com a branch remota origin/develop.

* Caso não exista a branch, siga criando localmente a branch develop rastreando a branch remota origin/develop:
```
git checkout -b develop origin/develop
```
## 2.4 - Trabalhando com Features:

#### 2.4.1 - Criar uma nova branch para a Issue:
<span style="color: orange;">Objetivo:</span> Isolar o desenvolvimento de novas funcionalidades.

```
git checkout -b feature/#numero_da_issue
```
#### 2.4.2 - Mesclar a Feature de Volta na Branch Develop:
<span style="color: orange;">Objetivo:</span> Integrar as novas funcionalidades na branch principal de desenvolvimento (develop).
```
git checkout develop
git merge feature/#numero_da_issue
```

#### 2.4.3 - Atualizar o Repositório Remoto:
<span style="color: orange;">Objetivo:</span> Sincronizar as alterações feitas na branch develop com o repositório remoto.

> Impacto: Mantém o repositório remoto atualizado, permitindo que outros membros da equipe acessem as últimas atualizações.
```
git push origin develop
```

## 2.5 - Corrigindo Bugs (Bugfix):
Identificação e correção de bugs são tratados com um fluxo específico.

#### 2.5.1 - Criar uma Nova Branch para o Bugfix:
<span style="color: orange;">Objetivo:</span> Isolar a correção de bugs específicos.

```
git checkout -b bugfix/#numero_da_issue
```
#### 2.5.2 - Mesclar o Bugfix de Volta na Branch Develop:
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
