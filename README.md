# 🏥 Projeto Assim Saúde — Sistema de Gestão Administrativa

O **Projeto Assim Saúde** é uma aplicação web desenvolvida como **avaliação técnica**, com foco na **gestão administrativa de cargos e funcionários** no contexto de uma instituição de saúde.

O sistema permite o **cadastro, listagem, edição e relacionamento entre cargos e funcionários**, utilizando uma arquitetura simples, organizada e facilmente extensível.

---

## 🧩 Arquitetura

- **Backend:** Flask (Python) — API REST  
- **Banco de Dados:** MySQL  
- **Frontend:** HTML, CSS e JavaScript  
- **Infraestrutura:** Docker e Docker Compose  

> ⚠️ Funcionalidades como pacientes, consultas, autenticação e relatórios avançados **não fazem parte do escopo atual**. Estão previstas apenas como **evolução futura** do sistema.

---

## 🎯 Objetivo do Projeto

- Demonstrar domínio em **Python com Flask**
- Implementar **CRUD completo**
- Trabalhar com **relacionamento entre tabelas**
- Criar e consumir uma **API REST**
- Utilizar **Docker e Docker Compose** para padronizar o ambiente
- Permitir que qualquer pessoa consiga **executar e testar o projeto localmente**

---

## 🚀 Quickstart — Executar o Projeto em Qualquer Máquina

### 📋 Pré-requisitos

Antes de começar, você precisa ter instalado:

- **Docker**
- **Docker Compose**

👉 Download:  
https://www.docker.com/products/docker-desktop/

---

### ▶️ Passo a Passo

#### 1️⃣ Clonar o repositório e abrir no VS Code

```bash
git clone https://github.com/RodrigoTechieX/Projeto-Assim-saude.git
cd Projeto-Assim-saude
code .
```

> 💡 O comando `code .` abre a pasta do projeto diretamente no **VS Code**.  
> Caso não funcione, abra manualmente a pasta **Projeto-Assim-saude** pelo menu  
> **File → Open Folder** do VS Code.

---

#### 2️⃣ Subir toda a aplicação com Docker

```bash
docker compose up -d
```

Aguarde alguns segundos até todos os containers iniciarem.

---

## 🌐 Acessos do Sistema

Após a inicialização:

- **Frontend (Interface Web):**  
  http://localhost:8080  

- **Backend (API Flask):**  
  http://localhost:5000  

---

## 🖥️ Funcionalidades Disponíveis

No frontend é possível:

- Cadastrar cargos  
- Cadastrar funcionários  
- Relacionar funcionários a cargos  
- Listar e visualizar registros cadastrados  
- Editar informações já existentes  

### 🔁 Fluxo sugerido para teste

1. Criar um cargo  
2. Criar um funcionário associado ao cargo  
3. Listar os funcionários cadastrados  

---

## 🧩 Estrutura do Projeto

```text
Projeto-Assim-saude/
│
├── backend/                 # API Flask
│   ├── app.py
│   ├── services/
│   └── requirements.txt
│
├── frontend/                # Interface Web
│   ├── index.html
│   └── pages/
│
├── database/
│   └── script.sql           # Criação das tabelas
│
├── docker-compose.yml       # Orquestração dos serviços
└── README.md
```

---

## 🐳 Docker — Serviços Criados

| Serviço            | Porta | Descrição          |
|--------------------|-------|--------------------|
| MySQL              | 3306  | Banco de dados     |
| Backend Flask      | 5000  | API REST           |
| Frontend (Nginx)   | 8080  | Interface Web      |

---

## 🧱 Banco de Dados

O banco de dados é criado automaticamente na primeira execução do Docker, utilizando o arquivo:

```text
database/script.sql
```

### 🔐 Credenciais padrão

- **Usuário:** root  
- **Senha:** root  
- **Banco:** assim_saude  
- **Host:** db  
- **Porta:** 3306  

### 🔄 Recriar o banco do zero

```bash
docker compose down -v
docker compose up -d
```

---

## 🧪 Como Testar a API

### 🔎 Listar funcionários

```bash
curl http://localhost:5000/funcionarios
```

### 🔎 Listar cargos

```bash
curl http://localhost:5000/cargos
```

Você também pode testar usando:

- Postman  
- Insomnia  

---

## 💻 Executar sem Docker (Opcional)

### ▶️ Backend

```bash
cd backend
pip install -r requirements.txt
flask run
```

API disponível em:  
http://localhost:5000  

### ▶️ Frontend

```bash
cd frontend
python -m http.server 8080
```

Interface disponível em:  
http://localhost:8080  

---

## 🛠 Tecnologias Utilizadas

| Camada         | Tecnologias                  |
|---------------|------------------------------|
| Backend        | Python, Flask                |
| Banco de Dados | MySQL                        |
| Frontend       | HTML, CSS, JavaScript        |
| Infraestrutura | Docker, Docker Compose       |

---

## 👨‍💻 Autor

**Rodrigo Ferreira da Silva Filho**

📧 Email:  
contato.rodrigo.tech@gmail.com  

🔗 LinkedIn:  
https://www.linkedin.com/in/rodrigo-ferreira-325527272/

---

Projeto desenvolvido como **avaliação técnica**.
