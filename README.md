# 💊 API Sistema de Gerenciamento de Farmácia

**Projeto Final - Bloco 02 | Bootcamp Java Full Stack (Generation Brasil)**

Uma API RESTful desenvolvida em Java com Spring Boot para o gerenciamento completo do ecossistema de uma farmácia. O sistema permite o controle de estoque de medicamentos, categorização de itens e gerenciamento de usuários, aplicando validações rigorosas e relacionamentos de banco de dados.

## 🛠️ Tecnologias Utilizadas

* **Java 21**
* **Spring Boot 3.5.14** (Web, Data JPA, Validation)
* **MySQL** (Banco de dados relacional)
* **Hibernate** (Mapeamento Objeto-Relacional)
* **Insomnia** (Testes de API)

## ✨ Principais Funcionalidades

A aplicação opera baseada em uma arquitetura de camadas (Controller, Service, Repository e Model) com as seguintes entidades:

* **👤 Usuários:** Sistema de cadastro e autenticação, com validação de formato de email e força de senha.
* **🏷️ Categorias:** Agrupamento de medicamentos (ex: Antibióticos, Analgésicos). Oculta produtos em cascata ao ser deletada.
* **💊 Produtos:** Controle detalhado do estoque de medicamentos, incluindo preço (`BigDecimal`), quantidade e datas de atualização automáticas (`@UpdateTimestamp`).

**Relacionamentos:**

* `ManyToOne`: Produtos são vinculados a uma Categoria e a um Usuário.
* `OneToMany`: Usuários e Categorias possuem listas de produtos atrelados a eles (com comportamentos otimizados de `EAGER` e `LAZY` loading, além de deleção em cascata).

## 🚀 Como Executar o Projeto

1. **Clone o repositório:**
```bash
git clone https://github.com/Eliane-orlandin/projeto_final_bloco_02.git

```


2. **Configure o Banco de Dados:**
Crie um banco chamado `farmacia_db` no seu MySQL. Em seguida, acesse o arquivo `src/main/resources/application.properties` e atualize com suas credenciais:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/farmacia_db
spring.datasource.username=seu_usuario
spring.datasource.password=sua_senha
spring.jpa.hibernate.ddl-auto=update

```


3. **Rode a Aplicação:**
Inicie o projeto na sua IDE (STS ou IntelliJ). A API estará disponível em `http://localhost:8080/api`.

---

👨‍💻 Desenvolvido por **Eliane Orlandin do Carmo**.
