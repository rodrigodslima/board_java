
# 📋 Board JAVA

Este projeto é uma **API REST** construída com **Spring Boot + Maven + JPA/Hibernate + MySQL (via Docker)**.  
  

---

## 🚀 Tecnologias

- **Java 17**  
- **Spring Boot 3.3.2**  
- **Spring Data JPA / Hibernate**  
- **MySQL (Docker)**  
- **Maven**

---

## ⚙️ Banco de Dados (MySQL via Docker)

Na raiz do projeto, execute:

```bash
docker-compose up -d
```

Isso irá criar um container com:  
- Banco: `boarddb`  
- Usuário: `boarduser`  
- Senha: `boardpass`  
- Porta: `3306`

---

▶️ Executando o Projeto
🔹 Windows (CMD ou PowerShell)

Entre na pasta do projeto:

cd board-java


Suba o MySQL:

docker-compose up -d


Rode o projeto:

mvn spring-boot:run


Acesse no navegador:

http://localhost:8080/api/boards
---

## 📌 Endpoints da API

### Listar todos os boards
```
GET /api/boards
```

### Buscar board por ID
```
GET /api/boards/{id}
```

### Criar novo board
```
POST /api/boards
Content-Type: application/json

{
  "title": "Meu primeiro board",
  "description": "Descrição do board"
}
```

### Atualizar um board
```
PUT /api/boards/{id}
Content-Type: application/json

{
  "title": "Board atualizado",
  "description": "Nova descrição"
}
```

### Deletar um board
```
DELETE /api/boards/{id}
```

---





