# 📚 Projeto Web Services com Spring Boot e JPA/Hibernate

Este projeto é um exemplo completo de uma aplicação Java utilizando **Spring Boot** e **JPA/Hibernate** para criar um sistema de web services com operações CRUD, tratamento de exceções e deploy no Heroku. Desenvolvido como parte do curso do **Dr. Nelio Alves** (devsuperior.com.br).

---

## 🛠️ Tecnologias Utilizadas

- **Java 17**
- **Spring Boot** (Spring Web, Spring Data JPA)
- **H2 Database** (para ambiente de teste)
- **PostgreSQL** (para ambientes de desenvolvimento e produção)
- **Heroku** (deploy)
- **Maven** (gerenciamento de dependências)

---

## 📂 Estrutura do Projeto

### Camadas Lógicas
1. **Resource Layer (Controllers)**: Endpoints REST.
2. **Service Layer**: Lógica de negócio.
3. **Repository Layer (Data Access)**: Comunicação com o banco de dados via JPA.
4. **Entities**: Modelos de domínio (ex: `User`, `Order`, `Product`).

### Modelo de Domínio
- **Entidades Principais**:
  - `User`: Usuários do sistema.
  - `Order`: Pedidos associados a usuários.
  - `Product`: Produtos disponíveis.
  - `Category`: Categorias de produtos.
  - `OrderItem`: Itens de pedido (associação muitos-para-muitos com atributos extras).
- **Enums**: `OrderStatus` para status dos pedidos.

---

## 🚀 Funcionalidades

### ✔️ CRUD Completo
- **Create**: Inserir usuários, pedidos, produtos.
- **Retrieve**: Buscar dados por ID ou listar todos.
- **Update**: Atualizar informações.
- **Delete**: Remover registros.

### 🛡️ Tratamento de Exceções
- `ResourceNotFoundException`: Recurso não encontrado.
- `DatabaseException`: Violação de integridade do banco.
- `EntityNotFoundException`: Entidade não encontrada durante atualização.

### 🌐 Banco de Dados
- **H2**: Configurado para testes (memória).
- **PostgreSQL**: Para desenvolvimento (`dev`) e produção (`prod`).
  - **Configurações**:
    - `application-test.properties`: H2.
    - `application-dev.properties`: PostgreSQL local.
    - `application-prod.properties`: PostgreSQL no Heroku.

---

## 🔧 Configuração

### Dependências (Maven)
```xml
<!-- JPA -->
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-data-jpa</artifactId>
</dependency>

<!-- H2 (Teste) -->
<dependency>
    <groupId>com.h2database</groupId>
    <artifactId>h2</artifactId>
    <scope>runtime</scope>
</dependency>

<!-- PostgreSQL (Dev/Prod) -->
<dependency>
    <groupId>org.postgresql</groupId>
    <artifactId>postgresql</artifactId>
    <scope>runtime</scope>
</dependency>

```

# Arquivos de Configuração
application.properties: Define o perfil ativo (test, dev, prod).

application-{profile}.properties: Configurações específicas de cada ambiente.
