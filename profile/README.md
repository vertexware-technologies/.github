# Sistema de Controle de Finanças

## Descrição do Projeto

Este projeto é um sistema de controle de finanças desenvolvido para ajudar os usuários a gerenciar suas receitas e despesas de forma eficaz. O sistema inclui as seguintes funcionalidades:

- Gerenciamento de usuários
- Registro e categorização de receitas
- Registro e categorização de despesas
- Relatórios financeiros

## Responsabilidades da Equipe
- Bruno Robson (Líder): Coordenação do projeto, integração das funcionalidades, e gerenciamento do código-fonte.
- Lucas: Desenvolvimento da API e gerenciamento do banco de dados.
- Paulo: Desenvolvimento do frontend e integração com a API.

## Tecnologias Utilizadas

- [Laravel](https://laravel.com/) - Framework PHP
- [MySQL](https://www.mysql.com/) - Banco de dados relacional
- [Composer](https://getcomposer.org/) - Gerenciador de dependências PHP
- [PHP](https://www.php.net/) - Linguagem de programação

## Instalação

### Pré-requisitos

Certifique-se de ter o seguinte instalado em sua máquina:

- PHP (>= 8.0)
- Composer
- MySQL
- Git

### Passos para Instalação

1. Clone o repositório para sua máquina local:

   ```bash
   git clone https://github.com/seu-usuario/nome-do-repositorio.git
   cd nome-do-repositorio
2. Instale as dependências do projeto com o Composer:

   ```bash
  composer install
3. Copie o arquivo de exemplo .env e configure as informações do banco de dados:

    ```bash
    cp .env.example .env

4. Gere a chave da aplicação:

    ```bash
    php artisan key:generate

5. Configure seu arquivo .env com as informações do seu banco de dados.

6. Execute as migrações para criar as tabelas do banco de dados:

    ```bash
    php artisan migrate

7. Opcionalmente, você pode popular o banco de dados com dados iniciais:

    ```bash
    php artisan db:seed
8. Inicie o servidor de desenvolvimento:

    ```bash
    php artisan serve

O servidor estará disponível em http://localhost:8000.

### Uso da API
O sistema inclui uma API para gerenciar usuários, receitas e despesas. Aqui está um guia rápido de uso da API com exemplos de endpoints:

## Autenticação
A API usa autenticação baseada em tokens. Após o registro, você receberá um token de acesso para usar nas solicitações.

## Endpoints
Os endpoints nesse momento estão apenas de forma simbolíca após a construção dos mesmos atualizaremos os endpoints.
### Usuários

- POST /api/register - Registrar um novo usuário
- POST /api/login - Fazer login
- GET /api/user - Obter informações do usuário autenticado
### Receitas

- GET /api/receitas - Listar todas as receitas
- POST /api/receitas - Criar uma nova receita
- PUT /api/receitas/{id} - Atualizar uma receita
- DELETE /api/receitas/{id} - Excluir uma receita

### Despesas

- GET /api/despesas - Listar todas as despesas
- POST /api/despesas - Criar uma nova despesa
- PUT /api/despesas/{id} - Atualizar uma despesa
- DELETE /api/despesas/{id} - Excluir uma despesa


## Git Commit Message Conventions

Rules to most readable commits

### Commit Message Format
Each commit message consists of a **header**, a **body** and a **footer**.  The header has a special
format that includes a **type**, a **scope** and a **subject**:

```
<type>(<scope>): <subject>
<BLANK LINE>
<body>
<BLANK LINE>
<footer>
```

The **header** is mandatory and the **scope** of the header is optional.

Any line of the commit message cannot be longer 100 characters! This allows the message to be easier
to read on GitHub as well as in various git tools.

### Type
Must be one of the following:

* **fit**: General changes not found in other types (prefer to use the specific types below)
* **build**: Changes that affect the build system or external dependencies (example scopes: gulp, broccoli, npm)
* **ci**: Changes to our CI configuration files and scripts (example scopes: Travis, Circle, BrowserStack, SauceLabs)
* **docs**: Documentation only changes
* **feat**: A new feature
* **fix**: A bug fix
* **perf**: A code change that improves performance
* **refactor**: A code change that neither fixes a bug nor adds a feature
* **style**: Changes that do not affect the meaning of the code (white-space, formatting, missing semi-colons, etc)
* **test**: Adding missing tests or correcting existing tests

### Subject
The subject contains a succinct description of the change:

* use the imperative, present tense: "change" not "changed" nor "changes"
* don't capitalize the first letter
* no dot (.) at the end

### Body
Just as in the **subject**, use the imperative, present tense: "change" not "changed" nor "changes".
The body should include the motivation for the change and contrast this with previous behavior.

### Footer
The footer should contain any information about **Breaking Changes** and is also the place to
reference GitHub issues that this commit **Closes**.

**Breaking Changes** should start with the word `BREAKING CHANGE:` with a space or two newlines. The rest of the commit message is then used for this.

### Examples
<hr>

**Commit message with description and breaking change footer**
```
feat: allow provided config object to extend other configs

BREAKING CHANGE: `extends` key in config file is now used for extending other config files
```

**Commit message with ! to draw attention to breaking change**
```
feat!: send an email to the customer when a product is shipped
```

**Commit message with scope and ! to draw attention to breaking change**
```
feat(api)!: send an email to the customer when a product is shipped
```

**Commit message with both ! and BREAKING CHANGE footer**
```
fit!: drop support for Node 6

BREAKING CHANGE: use JavaScript features not available in Node 6.
```

**Commit message with no body**
```
docs: correct spelling of CHANGELOG
```

**Commit message with scope**
```
feat(lang): add Polish language
```

**Commit message with multi-paragraph body and multiple footers**
```
fix: prevent racing of requests

Introduce a request id and a reference to latest request. Dismiss
incoming responses other than from latest request.

Remove timeouts which were used to mitigate the racing issue but are
obsolete now.


