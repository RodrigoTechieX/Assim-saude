# 🏥 Assim Saúde — Sistema de Gestão Administrativa em Saúde

O **Assim Saúde** é um **sistema web de gestão administrativa para clínicas e unidades de saúde**, desenvolvido como **avaliação técnica**.

O objetivo do projeto é demonstrar, de forma prática, organizada e profissional, conhecimentos em:

- Backend com **Python + Flask**
- **API REST**
- Banco de dados **MySQL**
- Frontend desacoplado
- **Docker e Docker Compose**
- Organização de código e **arquitetura em camadas**

---

## 🎯 Escopo do Sistema (Implementado)

Atualmente, o sistema oferece:

- ✅ Cadastro, listagem, edição e exclusão de **Cargos**
- ✅ Cadastro, listagem, edição e exclusão de **Funcionários**
- ✅ Relacionamento entre **Funcionários** e **Cargos**
- ✅ Inicialização automática do banco de dados
- ✅ Consumo da API via **Frontend**, **Postman** ou **cURL**

> ⚠️ Funcionalidades como **Pacientes**, **Consultas** e **Autenticação** estão planejadas, mas **não fazem parte do escopo desta avaliação técnica**.

---

# 🚀 Guia Completo — Como Executar o Projeto (SEM ERROS)

## 1️⃣ Pré-requisitos

Instale os softwares abaixo:

- **Git**
- **Docker**
- **Docker Compose**
- **Visual Studio Code**

Verificação rápida:

```bash
git --version
docker --version
docker compose version
```

---

## 2️⃣ Clonar o repositório e abrir no VS Code (Windows — PowerShell)

✅ Utilize o terminal padrão do VS Code (**PowerShell**)  
⚠️ **Não use `&&` no PowerShell**

### 2.1 Clonar o repositório no local recomendado

```powershell
git clone https://github.com/RodrigoTechieX/Assim-saude.git "$env:USERPROFILE\Documents\Projetos\Assim-saude"
```

### 2.2 Entrar na pasta correta (**PASSO OBRIGATÓRIO**)

```powershell
cd "$env:USERPROFILE\Documents\Projetos\Assim-saude"
```

🔍 Confirme que o arquivo `docker-compose.yml` existe:

```powershell
dir docker-compose.yml
```

Se o arquivo aparecer, você está no diretório correto.

### 2.3 Abrir o projeto no VS Code

```powershell
code .
```

---

### ℹ️ Observação (Git Bash / Linux / macOS)

```bash
git clone https://github.com/RodrigoTechieX/Assim-saude.git ~/Projetos/Assim-saude
cd ~/Projetos/Assim-saude
ls docker-compose.yml
code .
```

---

## 3️⃣ Subir o ambiente com Docker (SEM ERRO)

⚠️ Execute este comando **somente** dentro da pasta que contém o `docker-compose.yml`.

```bash
docker compose up -d
```

⏳ Aguarde **10 a 20 segundos** na primeira execução.

### Containers criados

| Serviço   | Função        | Porta |
|----------|---------------|-------|
| MySQL    | Banco de Dados| 3306  |
| Flask API | Backend       | 5000  |
| Nginx    | Frontend      | 8080  |

---

## 4️⃣ Verificar containers

```bash
docker compose ps
```

**Status esperado:** `Up`

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

## 🧪 Teste Funcional da API

### 🧱 Criar Cargo (obrigatório)

```http
POST /cargos
```

```json
{
  "nome": "Enfermeiro",
  "salario": 3500.00,
  "descricao": "Responsável pelo atendimento aos pacientes"
}
```

---

### 👨‍⚕️ Criar Funcionário

```http
POST /funcionarios
```

```json
{
  "nome": "João Silva",
  "cpf": "123.456.789-00",
  "email": "joao@assimsaude.com",
  "telefone": "21999999999",
  "cargo_id": 1
}
```

---

### 📋 Listar Funcionários

```bash
curl http://localhost:5000/funcionarios
```

---

## 🗄️ Conferir dados no banco (opcional)

```bash
docker exec -it assim_db mysql -u root -proot
```

```sql
USE assim_saude;
SELECT * FROM cargos;
SELECT * FROM funcionarios;
```

---

## ♻️ Resetar o ambiente (se necessário)

```bash
docker compose down -v
docker compose up -d
```

---

## 📁 Estrutura do Projeto

```text
Assim-saude/
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

Este projeto está licenciado sob a **Licença MIT**.
