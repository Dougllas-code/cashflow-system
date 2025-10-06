# 💰 CashFlow System# 💰 CashFlow - Sistema de Gestão Financeira



![Architecture](https://img.shields.io/badge/Architecture-Microservices-blue)Um sistema completo de gestão financeira desenvolvido com arquitetura de microsserviços, utilizando .NET, Angular e mensageria assíncrona.

![.NET](https://img.shields.io/badge/.NET-8.0-purple)

![Angular](https://img.shields.io/badge/Angular-18-red)## 🏗️ Arquitetura do Sistema

![Docker](https://img.shields.io/badge/Docker-Compose-blue)

![MySQL](https://img.shields.io/badge/Database-MySQL-orange)```

![RabbitMQ](https://img.shields.io/badge/Message%20Broker-RabbitMQ-orange)┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐

│   Frontend      │    │    Backend      │    │    Reports      │

Sistema completo de controle de fluxo de caixa desenvolvido com arquitetura de microsserviços, utilizando as melhores práticas de desenvolvimento e containerização.│   (Angular)     │◄──►│    (.NET 8)     │◄──►│   Worker        │

│                 │    │                 │    │   (.NET 8)      │

## 🏗️ Arquitetura do Sistema└─────────────────┘    └─────────────────┘    └─────────────────┘

         │                       │                       │

```mermaid         │                       │                       │

graph TB         └───────────────────────┼───────────────────────┘

    subgraph "Frontend"                                 │

        UI[Angular SPA]                        ┌─────────────────┐

    end                        │   MySQL 8.0     │

                            │   RabbitMQ      │

    subgraph "Backend Services"                        └─────────────────┘

        API[CashFlow API<br/>(.NET 8)]```

        WORKER[Reports Worker<br/>(.NET 8)]

    end### 📂 Componentes

    

    subgraph "Infrastructure"- **[Frontend](./cashflow-front)**: Interface web em Angular com dashboard interativo

        DB[(MySQL 8.0)]- **[Backend](./cashflow-back)**: API REST em .NET 8 com autenticação JWT

        MQ[RabbitMQ]- **[Reports Worker](./cashflow-reports)**: Processamento assíncrono de relatórios

    end- **MySQL**: Banco de dados relacional

    - **RabbitMQ**: Mensageria para comunicação assíncrona

    UI --> API

    API --> DB## 🚀 Como Executar

    API --> MQ

    WORKER --> MQ### Execução Rápida

    WORKER --> DB

    ```bash

    style UI fill:#e1f5fe# Clone o repositório com todos os submódulos

    style API fill:#f3e5f5git clone --recursive https://github.com/Dougllas-code/cashflow

    style WORKER fill:#fff3e0

    style DB fill:#e8f5e8# Entre no diretório

    style MQ fill:#fff8e1cd cashflow

```

# Configure as variáveis de ambiente

## 🚀 Tecnologias Utilizadascp .env.example .env



### Frontend# Execute todos os serviços

- **Angular 18** - Framework web modernodocker-compose up

- **TypeScript** - Tipagem estática```

- **SCSS** - Estilização avançada

- **Nginx** - Servidor web para produção### Acessos



### Backend- **Frontend**: http://localhost

- **.NET 8** - Framework principal- **Backend API**: http://localhost:5000

- **Entity Framework Core** - ORM- **RabbitMQ Management**: http://localhost:15672 (admin/admin123)

- **JWT Authentication** - Autenticação segura- **MySQL**: localhost:3306

- **AutoMapper** - Mapeamento de objetos

- **FluentValidation** - Validação de dados## 🛠️ Desenvolvimento



### Infrastructure### Estrutura dos Submódulos

- **MySQL 8.0** - Banco de dados relacional

- **RabbitMQ** - Message broker para comunicação assíncrona```

- **Docker & Docker Compose** - Containerização e orquestraçãocashflow/

├── cashflow-front/     # Submódulo: Frontend Angular

## 📁 Estrutura do Projeto├── cashflow-back/      # Submódulo: Backend .NET

├── cashflow-reports/   # Submódulo: Worker de Relatórios

```├── docker-compose.yml  # Orquestração completa

cashflow-system/└── .env.example       # Configurações de ambiente

├── 🌐 cashflow-front/          # Frontend Angular```

├── ⚡ cashflow-back/           # API Backend .NET

├── 📊 cashflow-reports/        # Worker de Relatórios### Trabalhando com Submódulos

├── 🐳 docker-compose.yml       # Orquestração completa

├── ⚙️ .env.example            # Configurações de ambiente```bash

└── 📖 README.md               # Esta documentação# Inicializar submódulos (se não usou --recursive)

```git submodule update --init --recursive



## ⚡ Quick Start# Atualizar todos os submódulos para a versão mais recente

git submodule update --remote

### Pré-requisitos

- Docker e Docker Compose instalados# Trabalhar em um submódulo específico

- Git instaladocd cashflow-front

git checkout main

### 1. Clone o repositório principal# Faça suas alterações...

```bashgit add . && git commit -m "feat: nova funcionalidade"

git clone --recursive https://github.com/Dougllas-code/cashflow-system.gitgit push origin main

cd cashflow-system

```# Volte ao repositório principal e atualize a referência

cd ..

### 2. Configure as variáveis de ambientegit add cashflow-front

```bashgit commit -m "chore: atualiza referência do frontend"

cp .env.example .env```

# Edite o arquivo .env com suas configurações se necessário

```## 🔧 Configuração de Ambiente



### 3. Inicie todo o sistema### Variáveis de Ambiente (.env)

```bash

docker-compose up -d```bash

```# Database Configuration

MYSQL_ROOT_PASSWORD=sua_senha_mysql

### 4. Acesse os serviçosMYSQL_DATABASE=cashflowdb

- 🌐 **Frontend**: http://localhost

- ⚡ **API**: http://localhost:5000# RabbitMQ Configuration

- 🐰 **RabbitMQ Management**: http://localhost:15672 (admin/admin123)RABBITMQ_DEFAULT_USER=admin

- 🗄️ **MySQL**: localhost:3306RABBITMQ_DEFAULT_PASS=admin123



## 🔧 Desenvolvimento# JWT Configuration

JWT_SIGNING_KEY=sua_chave_jwt_com_pelo_menos_32_caracteres

### Para desenvolver individualmente cada serviço:

# Application Environment

#### Frontend (Angular)ASPNETCORE_ENVIRONMENT=Production

```bash```

cd cashflow-front

npm install**Arquivo `.env` (configurações padrão):**

ng serve```bash

# Disponível em http://localhost:4200# Database Configuration

```MYSQL_ROOT_PASSWORD=Senha1234

MYSQL_DATABASE=cashflowdb

#### Backend (.NET)

```bash# RabbitMQ Configuration

cd cashflow-backRABBITMQ_DEFAULT_USER=admin

dotnet restoreRABBITMQ_DEFAULT_PASS=admin123

dotnet run --project src/CashFlow.Api

# Disponível em http://localhost:5000# Application Environment

```ASPNETCORE_ENVIRONMENT=Production

```

#### Worker de Relatórios

```bash### 2. Configuração dos appsettings

cd cashflow-reports

dotnet restoreOs arquivos de configuração já estão preparados para diferentes ambientes:

dotnet run --project Cashflow-reports

```#### Backend API (`cashflow-back/src/CashFlow.Api/`):

- `appsettings.Development.json` - Desenvolvimento local (localhost)

### Atualizando submodules- `appsettings.Production.json` - Docker/Produção (nomes dos containers)

```bash- `appsettings.Testing.json` - Para testes unitários

# Atualizar todos os submodules

git submodule update --remote#### Worker Reports (`cashflow-reports/Cashflow-reports/`):

- `appsettings.Development.json` - Desenvolvimento local (localhost)

# Atualizar um submodule específico- `appsettings.Production.json` - Docker/Produção (nomes dos containers)

git submodule update --remote cashflow-front

```**⚠️ IMPORTANTE:** As configurações de RabbitMQ e Database são diferentes para cada ambiente:



## 🐳 Docker Commands| Ambiente | Database Host | RabbitMQ Host | Uso |

|----------|---------------|---------------|-----|

```bash| Development | `localhost` | `localhost` | Desenvolvimento local |

# Iniciar todos os serviços| Production | `mysql` | `rabbitmq` | Docker Compose |

docker-compose up -d

## 🚀 Como executar

# Ver logs de todos os serviços

docker-compose logs -f1. Clone o repositório

2. Configure as variáveis de ambiente (passo 1 acima)

# Ver logs de um serviço específico3. Execute o projeto com Docker Compose:

docker-compose logs -f backend   ```bash

   docker compose up -d

# Parar todos os serviços   ```

docker-compose down

## Serviços disponíveis

# Rebuild e restart

docker-compose up -d --build- **Frontend**: http://localhost (porta 80)

- **Backend API**: http://localhost:5000

# Limpar volumes (⚠️ apaga dados do banco)- **MySQL**: localhost:3306

docker-compose down -v- **RabbitMQ Management**: http://localhost:15672 (admin/admin123)

```

## Estrutura do projeto

## 🏃‍♂️ Health Checks

```

O sistema possui health checks configurados para garantir que os serviços estejam funcionando:├── docker-compose.yml

├── .env

- **Backend API**: `GET /Health`├── cashflow-front/          # Frontend Angular

- **MySQL**: Ping interno do mysqladmin│   ├── Dockerfile

- **RabbitMQ**: Diagnostics ping│   └── ...

├── cashflow-back/           # API Backend .NET

## 📊 Funcionalidades│   ├── Dockerfile

│   └── src/

### 💰 Gestão Financeira└── cashflow-reports/        # Worker de Relatórios

- ✅ Cadastro de receitas e despesas    ├── Dockerfile

- ✅ Categorização de transações    └── ...

- ✅ Dashboard com visão geral```

- ✅ Filtros por período e categoria

## 💻 Desenvolvimento Local (sem Docker)

### 📈 Relatórios

- ✅ Relatórios em PDF com gráficosSe você quiser executar os serviços localmente para desenvolvimento:

- ✅ Relatórios em Excel para análise

- ✅ Processamento assíncrono via RabbitMQ### 1. Pré-requisitos adicionais:

- ✅ Histórico de relatórios gerados- .NET 8 SDK

- Node.js 18+

### 🔐 Segurança- MySQL Server

- ✅ Autenticação JWT- RabbitMQ Server

- ✅ Autorização baseada em roles

- ✅ Validação de dados robusta### 2. Configuração local:

- ✅ Tratamento de erros centralizado```bash

# MySQL local (ajuste a connection string no appsettings.Development.json)

## 🌍 Variáveis de AmbienteServer=localhost;Database=cashflowdb;Uid=root;Pwd=sua_senha;



| Variável | Descrição | Valor Padrão |# RabbitMQ local (configurações no appsettings.Development.json)

|----------|-----------|--------------|Host: localhost

| `MYSQL_ROOT_PASSWORD` | Senha do MySQL | `Smidvarg0091` |Username: admin (ou guest para instalação padrão)

| `MYSQL_DATABASE` | Nome do banco | `cashflowdb` |Password: admin123 (ou guest para instalação padrão)

| `RABBITMQ_DEFAULT_USER` | Usuário RabbitMQ | `admin` |```

| `RABBITMQ_DEFAULT_PASS` | Senha RabbitMQ | `admin123` |

| `JWT_SIGNING_KEY` | Chave JWT | `YOUR_SUPER_SECRET_JWT_KEY...` |### 3. Execução:

| `ASPNETCORE_ENVIRONMENT` | Ambiente .NET | `Production` |```bash

# Backend

## 🚀 Deploy em Produçãocd cashflow-back/src/CashFlow.Api

dotnet run

### Docker Swarm

```bash# Worker

docker swarm initcd cashflow-reports/Cashflow-reports

docker stack deploy -c docker-compose.yml cashflowdotnet run

```

# Frontend

### Kubernetescd cashflow-front

```bashnpm install

# Converter docker-compose para k8snpm start

kompose convert```

kubectl apply -f .

```## 🛠️ Comandos úteis



## 🧪 Testes```bash

# Parar todos os serviços

### Backenddocker-compose down

```bash

cd cashflow-back# Rebuild e restart

dotnet testdocker-compose up --build -d

```

# Ver logs

### Frontenddocker-compose logs -f [service-name]

```bash

cd cashflow-front# Ver logs específicos

npm testdocker-compose logs -f backend

```docker-compose logs -f frontend

docker-compose logs -f worker

## 📄 API Documentation

# Executar apenas um serviço

Quando o backend estiver rodando, acesse:docker-compose up [service-name]

- **Swagger UI**: http://localhost:5000/swagger

# Acessar container

## 🤝 Contribuindodocker-compose exec backend bash

docker-compose exec mysql mysql -u root -p

1. Fork o projeto```

2. Crie uma branch para sua feature (`git checkout -b feature/AmazingFeature`)

3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)## 🔧 Troubleshooting

4. Push para a branch (`git push origin feature/AmazingFeature`)

5. Abra um Pull Request### Problema: Frontend não conecta com Backend

**Solução:** Verifique se as URLs nos arquivos de environment estão corretas:

## 📋 Roadmap- `cashflow-front/src/environments/environment.ts` (desenvolvimento)

- `cashflow-front/src/environments/environment.prod.ts` (Docker)

- [ ] Implementar notificações em tempo real

- [ ] Dashboard avançado com métricas### Problema: Backend não conecta com RabbitMQ/MySQL

- [ ] API para integração com bancos**Solução:** Verifique:

- [ ] App mobile React Native1. Se os containers estão rodando: `docker-compose ps`

- [ ] Análise de dados com IA2. Se as variáveis de ambiente estão corretas no `.env`

## 📊 Funcionalidades

## 📝 Licença

### Frontend (Angular)

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.- Dashboard financeiro interativo

- Cadastro de receitas e despesas

## 👨‍💻 Autor- Relatórios visuais com gráficos

- Autenticação JWT

- **Dougllas Souza** - [@Dougllas-code](https://github.com/Dougllas-code)- Interface responsiva



## 🔗 Repositórios dos Serviços### Backend (.NET 8)

- API REST com documentação Swagger

- 🌐 [CashFlow Frontend](https://github.com/Dougllas-code/cashflow-front)- Autenticação e autorização JWT

- ⚡ [CashFlow Backend](https://github.com/Dougllas-code/cashflow-back)- Validação de dados com FluentValidation

- 📊 [CashFlow Reports](https://github.com/Dougllas-code/cashflow-reports)- Padrões CQRS e Clean Architecture

- Health checks

---- Logging estruturado



⭐ **Se este projeto te ajudou, por favor considere dar uma estrela!**### Reports Worker
- Processamento assíncrono de relatórios
- Integração com RabbitMQ
- Geração de PDFs
- Notificações por email
- Resilência e retry automático

## 🧪 Testes

```bash
# Executar testes do backend
cd cashflow-back
dotnet test

# Executar testes do frontend
cd cashflow-front
npm test

# Executar testes do worker
cd cashflow-reports
dotnet test
```

## 📋 Tecnologias Utilizadas

### Backend
- .NET 8
- Entity Framework Core
- FluentValidation
- AutoMapper
- JWT Authentication
- Serilog
- MediatR (CQRS)

### Frontend
- Angular 17+
- TypeScript
- Bootstrap/Angular Material
- Chart.js
- RxJS

### Infraestrutura
- Docker & Docker Compose
- MySQL 8.0
- RabbitMQ 3.x
- Nginx (Proxy Reverso)

## 👨‍💻 Autor

**Dougllas** - [GitHub](https://github.com/Dougllas-code)

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

⭐ **Se este projeto foi útil para você, deixe uma estrela!**
# Primeiro, verifique se as referências nos .csproj estão corretas
cd cashflow-reports
dotnet build CashflowReports.sln

# Se o build local funcionar, rebuild o Docker
docker compose down
docker compose build worker --no-cache
```

### Problema: Erro de permissão no MySQL
**Solução:** Remova os volumes e recrie:
```bash
docker-compose down -v
docker-compose up -d
```

## 🔒 Segurança e Produção

### ⚠️ ANTES DE USAR EM PRODUÇÃO:

1. **Altere todas as senhas padrão:**
   ```bash
   # No arquivo .env
   MYSQL_ROOT_PASSWORD=SUA_SENHA_FORTE_AQUI
   RABBITMQ_DEFAULT_PASS=SUA_SENHA_RABBITMQ_AQUI
   ```

2. **Configure JWT com chave segura:**
   ```json
   // appsettings.Production.json
   "SigningKey": "SUA_CHAVE_JWT_SUPER_SECRETA_COM_PELO_MENOS_32_CARACTERES"
   ```

3. **Use HTTPS em produção:**
   - Configure certificados SSL/TLS
   - Atualize URLs nos environments do Angular para HTTPS

4. **Variáveis de ambiente recomendadas para produção:**
   ```bash
   # Use Azure Key Vault, AWS Secrets Manager, ou similar
   ConnectionStrings__DefaultConnection="Server=mysql;Database=cashflowdb;Uid=root;Pwd=${MYSQL_ROOT_PASSWORD}"
   Settings__Jwt__SigningKey="${JWT_SIGNING_KEY}"
   Settings__RabbitMq__Password="${RABBITMQ_PASSWORD}"
   ```

5. **Configure backup automático do MySQL:**
   ```yaml
   # Adicione ao docker-compose.yml para produção
   volumes:
     - ./backups:/backups
   ```

### 📝 Checklist de Deploy:
- [ ] Senhas alteradas
- [ ] HTTPS configurado
- [ ] Backup configurado
- [ ] Monitoramento configurado
- [ ] Logs centralizados
- [ ] Firewall configurado
- [ ] Certificados válidos