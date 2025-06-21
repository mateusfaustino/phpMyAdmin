# 🐳 Ambiente Docker com MySQL e phpMyAdmin

Este projeto configura um ambiente de desenvolvimento utilizando **Docker Compose**, com os serviços:

- **MySQL 8.0**
- **phpMyAdmin**

Ideal para desenvolvimento local com aplicações PHP (como Laravel).

---

## 📦 Estrutura dos Serviços

- **MySQL**
  - Porta exposta: `3300 -> 3306`
  - Dados persistidos em: `./.docker/mysql/dbdata`
  - Variáveis de ambiente configuráveis via arquivo `.env`

- **phpMyAdmin**
  - Acesso via navegador: [http://localhost:8080](http://localhost:8080)
  - Conectado automaticamente ao container `db`

---

## ⚙️ Como usar

### 1. Pré-requisitos

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/)

### 2. Clone o repositório

```bash
git clone https://github.com/mateusfaustino/phpMyAdmin.git
cd phpMyAdmin
```

### 3. Crie um arquivo .env

```
DB_DATABASE=laravel
DB_USERNAME=username
DB_PASSWORD=userpass
```
### 4. Suba os containers
```
docker-compose up -d
```

### 🛠️ Acesso aos Serviços
phpMyAdmin: http://localhost:8080

Usuário: o valor de DB_USERNAME ou root

Senha: o valor de DB_PASSWORD ou userpass

MySQL: acessível na porta 3300, ideal para conectar com aplicações locais

### 📁 Volumes
Os dados do banco são persistidos localmente em:
```
.docker/mysql/dbdata
```
### 🌐 Rede Docker
Todos os serviços compartilham a mesma rede Docker laravel, permitindo a comunicação interna usando os nomes dos serviços:

Exemplo: phpMyAdmin se conecta ao banco via db:3306

### 🚫 Parar os containers
```
docker-compose down
```

### Se quiser remover os volumes:
```
docker-compose down -v
```

### 📋 Licença
Este projeto não está sob nenhuma licença. Faça o que quiser e serja feliz.