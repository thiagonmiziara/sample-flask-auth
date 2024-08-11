# Projeto Flask CRUD com Autenticação

Este projeto é uma aplicação web simples construída com Flask, que implementa um sistema de autenticação de usuários e operações CRUD (Criar, Ler, Atualizar, Excluir) para gerenciar usuários.

## Tecnologias Utilizadas

- **Flask**: Framework web para Python.
- **Flask-Login**: Extensão para gerenciar sessões de usuário.
- **SQLAlchemy**: ORM para interagir com o banco de dados.
- **bcrypt**: Biblioteca para hash de senhas.
- **MySQL**: Sistema de gerenciamento de banco de dados.

## Pré-requisitos

- Python 3.x
- MySQL
- pip (gerenciador de pacotes do Python)

## Instalação

1. Clone o repositório:
   ```bash
   git clone <URL_DO_REPOSITORIO>
   cd <NOME_DO_REPOSITORIO>
   ```
2. Crie um ambiente virtual e ative-o:

```bash
 python -m venv venv
 source venv/bin/activate  # Para Linux/Mac
 venv\Scripts\activate  # Para Windows
```

3. Instale as dependências:

   ```bash
   pip install -r requirements.txt
   ```

4. Configure o banco de dados MySQL. Utilize o Docker para criar um container MySQL com as seguintes configurações:

```
services:
db:
image: mysql:latest
restart: always
environment:
MYSQL_USER: "admin"
MYSQL_PASSWORD: "admin123"
MYSQL_DATABASE: "flask-crud"
MYSQL_ROOT_PASSWORD: "admin123"
ports: - "3306:3306"
volumes: - sua pasta de armazenamento

```

5. Execute a aplicação:

```bash
  python app.py
```

## Endpoints

- POST /login: Autentica um usuário.
- GET /logout: Realiza logout do usuário autenticado.
- POST /user: Cria um novo usuário.
- GET /user/int:user_id: Retorna informações de um usuário específico.
- PUT /user/int:user_id: Atualiza informações de um usuário específico.
- DELETE /user/int:user_id: Exclui um usuário específico.

## Uso

1. Para criar um usuário, envie um POST para /user com um corpo JSON contendo username e password.

2. Para autenticar, envie um POST para /login com username e password.

3. Para obter, atualizar ou excluir um usuário, utilize os endpoints correspondentes, garantindo que você esteja autenticado.
