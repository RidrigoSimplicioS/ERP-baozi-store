#  Baozi Store - API REST & Sistema ERP

Projeto acadêmico desenvolvido para a disciplina de **Desenvolvimento Back-end** do curso de Análise e Desenvolvimento de Sistemas. O foco principal da aplicação é a construção de uma **API RESTful** robusta em Java com Spring Boot para gerenciamento de clientes, produtos e pedidos, acompanhada de uma interface web estática para consumo e demonstração das rotas.

---

##  Objetivos da Disciplina (Back-end)

* Implementação de arquitetura em camadas seguindo o padrão **MVC (Model-View-Controller)**.
* Criação de endpoints RESTful aplicando os verbos HTTP (`GET`, `POST`, `PUT`, `DELETE`).
* Mapeamento Objeto-Relacional (ORM) e persistência de dados com **Spring Data JPA** e **MySQL**.
* Validação e testes de requisições utilizando o **Postman**.

---

##  Tecnologias Utilizadas

### Back-end (Foco Principal)
* **Java 17** (JavaSE-17)
* **Spring Boot** (Spring Web, Spring Data JPA)
* **MySQL** (Banco de dados relacional)
* **Maven** (Gerenciador de dependências e build)

### Front-end (Interface de Consumo)
* **HTML5, CSS3 e JavaScript** (Servidos estaticamente via Spring Boot)

### Ferramentas de Apoio
* **Eclipse IDE** (Ambiente de desenvolvimento)
* **Postman** (Testes e documentação das rotas da API)
* **Git & GitHub** (Controle de versão)

---

##  Arquitetura e Estrutura do Projeto

O projeto está estruturado no padrão **MVC**, separando responsabilidades entre controladores, entidades de domínio e repositórios de acesso a dados:

```text
store/
├── src/main/java/com/baozi/store/
│   ├── StoreApplication.java        # Classe principal de inicialização do Spring Boot
│   ├── controller/                  # Camada de Controle (Endpoints da API REST)
│   │   ├── ClienteController.java
│   │   ├── PedidoController.java
│   │   └── ProdutoController.java
│   ├── model/                       # Camada de Modelo (Entidades JPA / Tabelas do Banco)
│   │   ├── Cliente.java
│   │   ├── Pedido.java
│   │   └── Produto.java
│   └── repository/                  # Camada de Persistência (Interfaces Spring Data JPA)
│       ├── ClienteRepository.java
│       ├── PedidoRepository.java
│       └── ProdutoRepository.java
├── src/main/resources/
│   ├── static/
│   │   └── index.html               # Interface web para consumo da API
│   └── application.properties       # Configurações do servidor e conexão com o MySQL
└── pom.xml                          # Dependências e configurações do Maven
```

---

##  Pré-requisitos

Antes de iniciar, certifique-se de ter instalado em sua máquina:
1. **Java JDK 17** (ou superior)
2. **MySQL Server** ativo na porta padrão (`3306`)
3. Uma IDE Java (como **Eclipse**, IntelliJ ou VS Code)
4. **Git** instalado

---

##  Como Configurar e Rodar o Projeto

### 1. Clonar o repositório
Abra o terminal e execute o comando abaixo para baixar o projeto:
```bash
git clone [https://github.com/RidrigoSimplicioS/ERP-baozi-store.git]
```

### 2. Configurar o Banco de Dados (MySQL)
1. Abra o seu gerenciador de banco de dados (MySQL Workbench, DBeaver ou terminal) e crie o banco de dados:
```sql
CREATE DATABASE baozi_store;
```
2. No projeto, abra o arquivo `src/main/resources/application.properties` e verifique/ajuste suas credenciais locais do MySQL e a porta do servidor:
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/baozi_store?createDatabaseIfNotExist=true
spring.datasource.username=root
spring.datasource.password=SUA_SENHA_AQUI

spring.jpa.hibernate.ddl-auto=update
server.port=8081
```

### 3. Executar a Aplicação no Eclipse
1. Importe a pasta `store` no Eclipse via **File > Import > Maven > Existing Maven Projects**.
2. Aguarde o Maven baixar todas as dependências do `pom.xml`.
3. Navegue até `src/main/java/com/baozi/store/StoreApplication.java`, clique com o botão direito e selecione **Run As > Java Application** (ou **Spring Boot App**).
4. A API estará rodando localmente na porta `8081`.

---

##  Endpoints da API REST

As rotas estão divididas entre os três controladores do sistema e podem ser testadas via **Postman**:

###  Produtos (`/produtos`)

| Método | Rota | Descrição |
| :--- | :--- | :--- |
| `GET` | `/produtos` | Lista todos os produtos cadastrados |
| `GET` | `/produtos/{id}` | Busca um produto pelo ID |
| `POST` | `/produtos` | Cadastra um novo produto |
| `PUT` | `/produtos/{id}` | Atualiza os dados de um produto |
| `DELETE` | `/produtos/{id}` | Remove um produto |

###  Clientes (`/clientes`)

| Método | Rota | Descrição |
| :--- | :--- | :--- |
| `GET` | `/clientes` | Lista todos os clientes cadastrados |
| `GET` | `/clientes/{id}` | Busca um cliente pelo ID |
| `POST` | `/clientes` | Cadastra um novo cliente |
| `PUT` | `/clientes/{id}` | Atualiza os dados de um cliente |
| `DELETE` | `/clientes/{id}` | Remove um cliente |

###  Pedidos (`/pedidos`)

| Método | Rota | Descrição |
| :--- | :--- | :--- |
| `GET` | `/pedidos` | Lista todos os pedidos realizados |
| `GET` | `/pedidos/{id}` | Busca os detalhes de um pedido específico |
| `POST` | `/pedidos` | Registra um novo pedido |
| `PUT` | `/pedidos/{id}` | Atualiza o status ou dados de um pedido |
| `DELETE` | `/pedidos/{id}` | Cancela/remove um pedido |

---

##  Interface Web de Testes (Front-end)

Com o servidor Spring Boot em execução no Eclipse, você também pode visualizar e testar o consumo das rotas diretamente pelo navegador:

* **URL da Aplicação:** `http://localhost:8081/index.html` (ou `http://localhost:8081/`)

---

##  Autor

* **Rodrigo Simplicio** - [GitHub](https://github.com | [https://github.com/RidrigoSimplicioS/ERP-baozi-store]
