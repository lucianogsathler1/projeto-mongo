#  Workshop Spring Boot & MongoDB

API RESTful desenvolvida em Java utilizando **Spring Boot** e **MongoDB** (banco de dados NoSQL orientado a documentos), estruturada em arquitetura em camadas e aplicando conceitos modernos de mapeamento de objetos, tratamento de exceções personalizadas e consultas avançadas (*Full Search*).

---

##  Tecnologias e Ferramentas Utilizadas
* **Java 25**
* **Spring Boot 4.1.2** (Web, Data MongoDB)
* **MongoDB** (Driver Sync)
* **IntelliJ IDEA**
* **Postman** (para testes de API)

---

##  Arquitetura do Projeto
O projeto segue estritamente os padrões de separação de responsabilidades em camadas:
* **Resource (Controller):** Camada de exposição dos endpoints REST (`/users`, `/posts`).
* **Service:** Camada de regras de negócio e validações.
* **Repository:** Interface de comunicação e persistência com o MongoDB (Spring Data).
* **Domain:** Entidades mapeadas (`User`, `Post`) e objetos embutidos (`CommentDTO`, `AuthorDTO`).
* **DTO (Data Transfer Object):** Otimização e transferência limpa de dados.
* **Exception Handling:** Tratamento global de exceções customizadas (`ResourceExceptionHandler`).

---

##  Funcionalidades da API

###  Usuários (`/users`)
* `GET /users`: Retorna todos os usuários cadastrados.
* `GET /users/{id}`: Retorna um usuário específico pelo ID.
* `POST /users`: Cadastra um novo usuário.
* `PUT /users/{id}`: Atualiza os dados de um usuário existente.
* `DELETE /users/{id}`: Remove um usuário do sistema.
* `GET /users/{id}/posts`: Lista todos os posts vinculados a um usuário específico.

###  Posts (`/posts`)
* `GET /posts/{id}`: Busca um post pelo ID (trazendo o autor e os comentários embutidos).
* `GET /posts/titlesearch?text=...`: Realiza busca de posts por título contendo determinado texto (ignorando maiúsculas/minúsculas).
* `GET /posts/fullsearch?text=...&minDate=...&maxDate=...`: Realiza uma busca avançada (*Full Search*) filtrando simultaneamente por termo de texto (título, corpo ou comentários) e intervalo de datas.

---

##  Como Rodar o Projeto na sua Máquina

### Pré-requisitos
* Ter o **Java 25** instalado.
* Ter o **MongoDB** rodando localmente (porta padrão `27017`) ou uma instância na nuvem (MongoDB Atlas).
* Uma IDE de sua preferência (ex: **IntelliJ IDEA**).

### Passo a passo:
1. Clone este repositório:
   ```bash
   git clone [https://github.com/SEU-USUARIO/nome-do-repositorio.git](https://github.com/SEU-USUARIO/nome-do-repositorio.git)
2. Abra o projeto na sua IDE (como projeto Maven).

3. Certifique-se de que o MongoDB está ativo na sua máquina.

4. Execute a classe principal WorkshopmongoApplication.java. (O projeto possui uma classe de instanciação automática Instantiation que popula o banco com dados iniciais para testes).

5. Utilize o Postman ou Insomnia para testar os endpoints na porta http://localhost:8080