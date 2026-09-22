# 👋 Paulo Ricardo

[![C#](https://img.shields.io/badge/C%23-239120.svg?style=for-the-badge&logo=c-sharp&logoColor=white)]()
[![.NET](https://img.shields.io/badge/.NET-512BD4?style=for-the-badge&logo=dotnet&logoColor=white)]()
[![SQL Server](https://img.shields.io/badge/SQL%20Server-CC2927?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)]()
[![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)]()
[![Swagger](https://img.shields.io/badge/Swagger-85EA2D?style=for-the-badge&logo=swagger&logoColor=black)]()

Desenvolvedor **Back end** com foco em **C#/.NET**. Busco oportunidades para atuar com desenvolvimento back-end.

## 📫 Contato
📫 [LinkedIn](https://www.linkedin.com/in/paulo-r-50a292262/)

---

## 🚀 Sobre mim

Formado em **Análise e Desenvolvimento de Sistemas** pela **FATEC Jundiaí**, atualmente cursando **Pós-Graduação em Arquitetura de Sistemas .NET + Azure** pela **FIAP**.

Atualmente atuo com o desenvolvimento e manutenção de produtos de seguro digital pela Olik.

---

## ⚙️ Tech Stack

**Back-end:** C# / .NET Framework 4.8 / .NET 6-10 / CQRS / Entity Framework / SQL Serve / Arquitetura orientada a Eventos / Padrão API Rest (construção e consumo). 

**Front-end:** JavaScript · HTML5 · CSS3 · Angular

**Banco de Dados:** SQL Server (consultas, procedures, views, CTEs, functions) / PostgreSQL / MongoDb

**Ferramentas:** Swagger / Git & GitHub / Clean Code / Postman

---

## 📁 Projetos em destaque

### 🚀 [FGC](https://github.com/P4uleira/FCG-ORCHESTRATION-API) [🔗](https://github.com/P4uleira/FCG-CATALOG-API) [🔗](https://github.com/P4uleira/FCG-USERS-API) [🔗](https://github.com/P4uleira/FCG-NOTIFICATIONS-API) [🔗](https://github.com/P4uleira/FCG-PAYMENTS-API) [🔗](https://github.com/P4uleira/FCG-SERVERLESS-NOTIFICATION-API)

**Problema:** O projeto **FIAP Cloud Games (FCG)** é o desafio da pós-graduação da FIAP que propõe construir, de forma incremental (em fases), uma plataforma de venda e distribuição de jogos digitais — nos moldes de uma Steam simplificada — usando arquitetura de microsserviços. A cada fase, novos requisitos não-funcionais são adicionados (containerização, orquestração, gateway, observabilidade, mensageria, banco NoSQL, arquitetura serverless), simulando a evolução real de um sistema em produção.

**Solução:** A solução foi dividida em microsserviços independentes, cada um em seu próprio repositório, coordenados por um repositório de orquestração que centraliza a infraestrutura (Docker Compose / Kubernetes) e a documentação de como subir e validar tudo:

- **FCG-Users-Api** (porta 8080) — cadastro de usuários, login e emissão de JWT.
- **FCG-Catalog-Api** (porta 8081) — catálogo de jogos, compra e histórico (MongoDB), com cache em Redis.
- **FCG-Payments-Api** (porta 8082) — processa o pagamento e publica o evento `PaymentProcessedEvent`.
- **FCG-Notifications-Api** — versão legada (container 24/7 consumindo RabbitMQ), desativada do cluster na Fase 3.
- **FCG-Serverless-Notification-Api** — substituiu o serviço acima por duas funções AWS Lambda (`welcome-function` e `purchase-confirmation-function`), acionadas automaticamente via SQS/LocalStack.
- **FCG-Orchestration-Api** — não é um microsserviço de negócio; reúne os manifestos Kubernetes, o Docker Compose e a documentação de execução ponta a ponta.

O fluxo principal (cadastro → compra → pagamento → notificação) atravessa um API Gateway (Kong), que roteia as requisições e valida o JWT na borda. Eventos de domínio trafegam via RabbitMQ (fluxo interno) e, em paralelo, via Amazon SQS (emulado pelo LocalStack) para disparar as funções serverless — sem invocação manual. Cada API segue DDD, CQRS (MediatR) e Clean Architecture, com persistência via Entity Framework Core (SQL Server) e MongoDB para dados de histórico.

**Ferramentas e tecnologias utilizadas:**

| Categoria | Tecnologias |
|---|---|
| Plataforma | .NET 10 (APIs), .NET 8 (Lambdas) |
| Padrões de arquitetura | DDD, CQRS, MediatR, Clean Architecture |
| Persistência | Entity Framework Core, SQL Server, MongoDB |
| Cache | Redis |
| API Gateway | Kong (modo DB-less, validação JWT) |
| Mensageria | RabbitMQ, MassTransit, Amazon SQS (AWSSDK.SQS) |
| Serverless | AWS Lambda, AWS SAM CLI, LocalStack |
| Observabilidade | Prometheus, Grafana |
| Segurança | JWT |
| Infraestrutura | Docker, Docker Compose, Kubernetes, AWS CLI |

### 🚀 [TaskWave — Sistema de Gerenciamento de Tarefas (TCC)](https://github.com/P4uleira/TCC-TASKWAVE)

**Problema:** times pequenos costumam controlar tarefas em planilhas ou apps genéricos que não refletem o fluxo real de trabalho do grupo.

**Solução:** API em **.NET 8**, com arquitetura separada em API / Domain / Infra, autenticação **JWT** com claims personalizadas e persistência via **Entity Framework Core** (Code First) sobre **SQL Server**. Documentação interativa com **Swagger**.

**Resultado:** TCC aprovado, com foco em boas práticas de organização e escalabilidade da arquitetura.

`.NET 8` `EF Core` `JWT` `SQL Server` `Swagger`

---
