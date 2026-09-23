# ⚡ PowerManager API

API REST para gerenciamento de consumo de energia e faturamento, desenvolvida com **Java e Spring Boot**.

O projeto tem como objetivo aplicar, de forma prática, conceitos de desenvolvimento backend, arquitetura em camadas, APIs REST, persistência de dados, banco de dados e boas práticas de desenvolvimento.

---

## 🚀 Sobre o projeto

O **PowerManager API** é um projeto acadêmico e de portfólio desenvolvido para simular um sistema de gerenciamento de consumo de energia elétrica e faturamento.

A API será responsável por trabalhar com informações de clientes, medidores, leituras de consumo, faturas, pagamentos, taxas e usuários.

O projeto está sendo desenvolvido de forma incremental, acompanhando os conceitos estudados durante o curso de Java e Spring Boot.

---

## 🛠️ Tecnologias utilizadas

- Java 21
- Spring Boot 4.1.1
- Spring Web
- Spring Data JPA
- Hibernate
- MySQL 8.4
- Bean Validation
- Lombok
- Maven
- Docker
- Docker Compose
- Git
- GitHub

---

## 🏗️ Arquitetura

O projeto seguirá uma arquitetura em camadas:

```text
Controller
    ↓
Service
    ↓
Repository
    ↓
Database
```

### Controller

Responsável por receber as requisições HTTP e retornar as respostas da API.

### Service

Responsável pelas regras de negócio e pela lógica da aplicação.

### Repository

Responsável pelo acesso e persistência dos dados.

### Database

Responsável pelo armazenamento das informações da aplicação.

---

## 🗃️ Entidades iniciais

O projeto possui inicialmente **7 entidades/tabelas**:

1. Cliente
2. Medidor
3. Leitura de Consumo
4. Fatura
5. Pagamento
6. Taxa
7. Usuário

> Novas entidades não serão adicionadas neste momento. O modelo poderá evoluir posteriormente conforme a necessidade do projeto.

---

## 🔗 Relacionamentos iniciais

```text
Cliente
   │
   ├── 1:N ── Medidor
   │              │
   │              └── 1:N ── Leitura de Consumo
   │
   └── 1:N ── Fatura
                  │
                  ├── 1:0..1 ── Pagamento
                  │
                  └── 1:N ── Taxa

Usuário
```

Os relacionamentos e regras serão revisados durante a modelagem do banco de dados e implementação da aplicação.

---

## 🐳 Docker e MySQL

O banco de dados do projeto será executado através do **Docker Compose**.

O arquivo:

```text
docker-compose.yml
```

é responsável por configurar o container do MySQL.

A porta externa `3307` foi utilizada porque a porta `3306` já estava sendo utilizada por uma instalação do MySQL no Windows.

Mapeamento:

```text
localhost:3307
      ↓
Docker
      ↓
MySQL:3306
```

O banco também possui um volume Docker para manter os dados persistidos.

---

## 🗄️ Banco de dados

A modelagem SQL será mantida dentro do projeto:

```text
database/
└── sql/
    └── schema.sql
```

O arquivo `schema.sql` será utilizado para definir a estrutura do banco, incluindo:

- tabelas;
- campos;
- tipos de dados;
- chaves primárias;
- chaves estrangeiras;
- restrições;
- relacionamentos;
- regras de integridade.

A modelagem SQL ainda está em desenvolvimento.

---

## 🎯 Objetivos

- Desenvolver uma API REST utilizando Spring Boot.
- Aplicar arquitetura em camadas.
- Trabalhar com HTTP e REST.
- Utilizar Spring Data JPA e Hibernate.
- Utilizar MySQL para persistência dos dados.
- Trabalhar com relacionamentos entre entidades.
- Aplicar Bean Validation.
- Implementar regras de negócio.
- Trabalhar com DTOs.
- Utilizar MapStruct posteriormente no projeto.
- Implementar tratamento centralizado de erros.
- Trabalhar com paginação e consultas.
- Implementar segurança da API.
- Desenvolver testes automatizados.
- Aplicar na prática os conceitos estudados durante o curso.

---

## 📌 Status do projeto

### Etapa 1 — Preparação do projeto

- [x] Criação do projeto Spring Boot
- [x] Configuração do Maven
- [x] Configuração do Java 21
- [x] Configuração das dependências iniciais
- [x] Configuração do Git
- [x] Criação do repositório no GitHub
- [x] Configuração do README
- [x] Definição inicial das entidades
- [x] UML inicial
- [x] DER inicial

### Etapa 2 — Docker + MySQL

- [x] Configuração do Docker Compose
- [x] Configuração do MySQL 8.4
- [x] Criação do container `powermanager-mysql`
- [x] Criação do banco `powermanager`
- [x] Configuração do volume persistente
- [x] Configuração da porta `3307 → 3306`
- [x] Configuração da conexão do IntelliJ com o MySQL

### Etapa 3 — Modelagem SQL

- [ ] Definição dos campos das tabelas
- [ ] Definição dos tipos de dados
- [ ] Definição das chaves primárias
- [ ] Definição das chaves estrangeiras
- [ ] Definição das restrições
- [ ] Criação do `schema.sql`
- [ ] Revisão do modelo do banco

### Etapa 4 — JPA/Hibernate

- [ ] Configuração da conexão Spring Boot + MySQL
- [ ] Criação das entidades JPA
- [ ] Mapeamento dos relacionamentos
- [ ] Configuração dos repositórios

### Etapa 5 — API REST

- [ ] Controllers
- [ ] Services
- [ ] DTOs
- [ ] Validações
- [ ] Regras de negócio
- [ ] Tratamento centralizado de erros
- [ ] Paginação e consultas
- [ ] Segurança
- [ ] Testes

---

## 📁 Estrutura atual do projeto

```text
powermanager-api/
│
├── .gitignore
├── docker-compose.yml
├── pom.xml
├── README.md
│
├── database/
│   └── sql/
│       └── schema.sql
│
├── docs/
│   ├── diagramas/
│   ├── apostilas/
│   └── anotações/
│
└── src/
    ├── main/
    └── test/
```

---

## 👨‍💻 Autor

**Gustavo de Jesus Silva**

GitHub: [GustavoJ-dev](https://github.com/GustavoJ-dev)

LinkedIn: [Gustavo Silva](https://www.linkedin.com/in/gustavo-silva-a92b33372/)
