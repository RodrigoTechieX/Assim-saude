# 🏥 Assim Saúde — Sistema de Gestão Administrativa em Saúde

O **Assim Saúde** é um **sistema web de gestão administrativa para clínicas e unidades de saúde**, desenvolvido como **avaliação técnica**.

O objetivo do projeto é demonstrar, de forma prática, organizada e profissional, conhecimentos em:

- Backend com **Python + Flask**
- API REST
- Banco de dados **MySQL**
- Frontend desacoplado
- **Docker e Docker Compose**
- Organização de código e arquitetura em camadas

---

## 🎯 Escopo do Sistema (Implementado)

Atualmente, o sistema oferece:

- ✅ Cadastro, listagem, edição e exclusão de **Cargos**
- ✅ Cadastro, listagem, edição e exclusão de **Funcionários**
- ✅ Relacionamento entre Funcionários e Cargos
- ✅ Inicialização automática do banco de dados
- ✅ Consumo da API via Frontend, Postman ou cURL

> ⚠️ Funcionalidades como **Pacientes, Consultas e Autenticação** estão planejadas, mas **não fazem parte do escopo desta avaliação técnica**.

---

# 🚀 Guia Completo — Como Testar o Sistema

## 1️⃣ Pré-requisitos

Certifique-se de ter os seguintes softwares instalados:

- **Git**
- **Docker**
- **Docker Compose**

Validação rápida no terminal:

```bash
git --version
docker --version
docker compose version
```

---

## 2️⃣ Clonar o repositório e abrir no VS Code

Execute o comando abaixo **diretamente no terminal do VS Code**:

```bash
git clone https://github.com/RodrigoTechieX/Assim-saude.git "%USERPROFILE%\Documents\Projetos\Assim-saude" && code "%USERPROFILE%\Documents\Projetos\Assim-saude"
```

📌 Esse comando irá:
- Clonar o repositório
- Criar a pasta `Documentos/Projetos/Assim-saude`
- Abrir automaticamente o projeto no **VS Code**

---

## 3️⃣ Subir todo o ambiente com Docker

Com o projeto aberto no VS Code, execute:

```bash
docker compose up -d
```

⏳ Na primeira execução, aguarde cerca de **10 a 20 segundos**.

### Serviços criados

| Serviço | Função | Porta |
|------|------|------|
| MySQL | Banco de Dados | 3306 |
| Flask API | Backend | 5000 |
| Nginx | Frontend | 8080 |

---

## 4️⃣ Verificar status dos containers

```bash
docker compose ps
```

Todos os serviços devem estar com status **Up**.

---

## 5️⃣ Acessar o sistema

### 🌐 Frontend
```
http://localhost:8080
```

### 🔌 Backend (API)
```
http://localhost:5000
```

---

# 🧪 Teste Funcional do Sistema

## 🧱 Passo 1 — Criar um Cargo

Funcionários dependem de cargos.  
Este deve ser o **primeiro teste**.

### Endpoint
```
POST /cargos
```

### URL completa
```
http://localhost:5000/cargos
```

### Exemplo de payload
```json
{
  "nome": "Enfermeiro",
  "salario": 3500.00,
  "descricao": "Responsável pelo atendimento aos pacientes"
}
```

---

## 👨‍⚕️ Passo 2 — Criar um Funcionário

### Endpoint
```
POST /funcionarios
```

### URL completa
```
http://localhost:5000/funcionarios
```

### Exemplo de payload
```json
{
  "nome": "João Silva",
  "cpf": "123.456.789-00",
  "email": "joao@assimsaude.com",
  "telefone": "21999999999",
  "cargo_id": 1
}
```

> 📌 O `cargo_id` deve existir previamente.

---

## 📋 Passo 3 — Listar Funcionários

```bash
curl http://localhost:5000/funcionarios
```

---

## 🗄️ Passo 4 — Conferir dados no banco (opcional)

```bash
docker exec -it assim_db mysql -u root -proot
```

```sql
USE assim_saude;
SELECT * FROM cargos;
SELECT * FROM funcionarios;
```

---

## ♻️ Recriar o banco do zero (se necessário)

```bash
docker compose down -v
docker compose up -d
```

---

## 📁 Estrutura do Projeto

```
assim-saude/
├── backend/
├── frontend/
├── database/
├── docker-compose.yml
└── README.md
```

---

## 🧑‍💻 Autor

**Rodrigo Ferreira da Silva Filho**  
📧 contato.rodrigo.tech@gmail.com  
🔗 https://www.linkedin.com/in/rodrigo-ferreira-325527272/

---

## 🏁 Licença

Este projeto está licenciado sob a licença **MIT**.
