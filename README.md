# 🏥 Assim Saúde — Sistema de Gestão Administrativa em Saúde

O **Assim Saúde** é um **sistema web de gestão administrativa para clínicas e unidades de saúde**, desenvolvido como **avaliação técnica**.

O projeto tem como objetivo demonstrar, de forma prática e organizada, conhecimentos em:

- Backend com **Python + Flask**
- API REST
- Banco de dados **MySQL**
- Frontend desacoplado
- **Docker e Docker Compose**
- Organização de código e arquitetura em camadas

---

## 🎯 Escopo do Sistema (o que está implementado)

Atualmente, o sistema permite:

- ✅ Cadastro, listagem, edição e exclusão de **Cargos**
- ✅ Cadastro, listagem, edição e exclusão de **Funcionários**
- ✅ Relacionamento entre Funcionários e Cargos
- ✅ Inicialização automática do banco de dados
- ✅ Consumo da API via Frontend, Postman ou cURL

> ⚠️ Funcionalidades como **Pacientes, Consultas e Autenticação** estão planejadas, mas **não fazem parte do escopo atual da avaliação**.

---

# 🚀 GUIA COMPLETO — COMO TESTAR O SISTEMA

## 1️⃣ Pré-requisitos obrigatórios

Antes de iniciar, verifique se você possui instalado:

- **Git**
- **Docker**
- **Docker Compose**

Validação rápida:
```bash
git --version
docker --version
docker compose version
```

---

## 2️⃣ Clonar o repositório

```bash
git clone https://github.com/RodrigoTechieX/Assim-saude.git
cd Assim-saude
```

---

## 3️⃣ Subir todo o ambiente com Docker

```bash
docker compose up -d
```

Na primeira execução, aguarde cerca de **10 a 20 segundos** para inicialização completa.

### Serviços criados

| Serviço | Função | Porta |
|------|------|------|
| MySQL | Banco de dados | 3306 |
| Flask API | Backend | 5000 |
| Nginx | Frontend | 8080 |

---

## 4️⃣ Verificar se os containers estão ativos

```bash
docker compose ps
```

Todos devem estar com status **Up**.

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

# 🧪 TESTE FUNCIONAL DO SISTEMA (PASSO A PASSO)

## 🧱 PASSO 1 — Criar um Cargo (obrigatório)

Funcionários dependem de cargos.  
Este **deve ser o primeiro teste**.

### Endpoint
```
POST /cargos
```

### URL completa
```
http://localhost:5000/cargos
```

### Payload de exemplo
```json
{
  "nome": "Enfermeiro",
  "salario": 3500.00,
  "descricao": "Responsável pelo atendimento aos pacientes"
}
```

---

## 👨‍⚕️ PASSO 2 — Criar um Funcionário

### Endpoint
```
POST /funcionarios
```

### URL completa
```
http://localhost:5000/funcionarios
```

### Payload de exemplo
```json
{
  "nome": "João Silva",
  "cpf": "123.456.789-00",
  "email": "joao@assimsaude.com",
  "telefone": "21999999999",
  "cargo_id": 1
}
```

> 📌 **Importante:**  
> O `cargo_id` deve existir na tabela `cargos`.

---

## 📋 PASSO 3 — Listar Funcionários

```bash
curl http://localhost:5000/funcionarios
```

---

## 🗄️ PASSO 4 — Conferir dados no banco (opcional)

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

Licença **MIT**.
