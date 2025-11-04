# 🚀 Controle de Gastos — Caio Claudino  
**Versão 2.1**

Bem-vindo ao guia de desenvolvimento da aplicação **Controle de Gastos**, criada por **Caio Claudino**.  
Este projeto tem como objetivo aplicar conceitos de **Desenvolvimento Full Stack**, utilizando **Spring Boot** no backend e **HTMX + Thymeleaf** no frontend.

A aplicação permite cadastrar, listar, editar e excluir lançamentos de receitas e despesas de forma simples e moderna.  
Além disso, está preparada para **deploy profissional no Render** com **Docker**.

---

## 🧠 Tecnologias Utilizadas

- **Backend:** Java 21, Spring Boot, Spring Data JPA  
- **Frontend:** Thymeleaf + HTMX  
- **Banco de Dados:** H2 (Desenvolvimento) e PostgreSQL (Produção - Neon)  
- **Deploy:** Docker + Render  

---

## 🧩 Arquitetura do Projeto

O sistema segue o padrão **MVC (Model–View–Controller)**, com camadas bem definidas para garantir organização e manutenção facilitada.

```
Usuário (Browser)
    ↓
View (HTMX + Thymeleaf)
    ↓
Controller (Spring Boot)
    ↓
Repository (Spring Data JPA)
    ↓
Banco de Dados (PostgreSQL/H2)
```

O **HTMX** é responsável por atualizar partes específicas da página sem recarregar tudo, deixando o uso mais fluido.

---

## 📁 Estrutura Final do Projeto

```
controle-de-gastos/
├── src/
│   ├── main/java/br/com/controledegastos/
│   │   ├── ControleDeGastosApplication.java
│   │   ├── controller/LancamentoController.java
│   │   ├── model/Lancamento.java
│   │   ├── model/TipoLancamento.java
│   │   └── repository/LancamentoRepository.java
│   └── resources/
│       ├── templates/index.html
│       ├── application.properties
│       └── application-prod.properties
├── Dockerfile
├── pom.xml
└── README.md
```

---

## ⚙️ Execução Local

### 1. Clonar o repositório

```bash
git clone https://github.com/CaioClaudino/controle-de-gastos.git
cd controle-de-gastos
```

### 2. Executar localmente

```bash
./mvnw spring-boot:run
```

A aplicação estará disponível em:  
👉 **http://localhost:8080**

---

## 🐳 Deploy com Docker e Render

### 1. Criar a imagem Docker
```bash
docker build -t controle-de-gastos .
```

### 2. Executar o container localmente
```bash
docker run -p 8080:8080 controle-de-gastos
```

### 3. Publicar no Render
- Conecte o repositório GitHub  
- Escolha **Runtime: Docker**  
- Configure as variáveis de ambiente:
  - `SPRING_PROFILES_ACTIVE=prod`
  - `DB_URL`, `DB_USERNAME`, `DB_PASSWORD`

🔗 **Link de Deploy:**  
[https://controledegastos-CaioClaudino.onrender.com](https://controledegastos-CaioClaudino.onrender.com)

---

## 🧰 Soluções de Erros Comuns

### ⚠️ Erro: “Permission denied” ao buildar no Render

Execute:
```bash
git update-index --chmod=+x mvnw
git commit -m "fix: adiciona permissão de execução ao mvnw"
git push origin main
```

### ⚠️ Erro de Codificação (`MalformedInputException`)

Garanta que todos os arquivos `.properties` estejam salvos em **UTF-8**  
e que o `pom.xml` possua a seguinte configuração:

```xml
<properties>
    <java.version>21</java.version>
    <project.build.sourceEncoding>UTF-8</project.build.sourceEncoding>
</properties>
```

---

## 👨‍💻 Autor

**Caio Claudino**  
Estudante de **Análise e Desenvolvimento de Sistemas - FEMA**  
💻 Desenvolvedor Full Stack em formação  
🌐 GitHub: [github.com/CaioClaudino](https://github.com/CaioClaudino)

---

## 📜 Licença
Este projeto é de uso acadêmico e livre para estudos e melhorias.
