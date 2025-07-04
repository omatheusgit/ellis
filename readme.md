# Imersão DevOps - Alura com Google Cloud ☁️🐳

Este projeto foi desenvolvido durante a **Imersão DevOps da Alura em parceria com o Google Cloud**, com foco em aprender na prática conceitos de **Cloud Computing**, **Docker**, **CI/CD** e **Google Cloud Run**.

A proposta simulou um cenário real em que uma equipe de DevOps recebe uma aplicação pronta da equipe de desenvolvimento (neste caso, uma API em FastAPI) e precisa garantir que a aplicação funcione corretamente em qualquer ambiente — resolvendo o clássico problema do _"na minha máquina funciona"_.

Etapas da Imersão:

- Leitura da documentação da API e entendimento da estrutura;
- Containerização com Docker;
- Organização do ambiente com Docker Compose;
- Uso do Gemini Code Assist, a nova extensão de IA do Google;
- Criação de uma pipeline CI com GitHub Actions, que realiza o build da imagem automaticamente a cada push;
- Deploy na Google Cloud com o Cloud Run, permitindo acesso público e escalável via navegador.

Ao final da imersão, foi possível aplicar na prática os principais conceitos de DevOps e Cloud, desde a preparação de um ambiente com Docker até a entrega contínua e o deploy automatizado em ambiente de nuvem. 

---

Abaixo, você encontra a **documentação completa da API**.

---


Este projeto é uma API desenvolvida com FastAPI para gerenciar alunos, cursos e matrículas em uma instituição de ensino.

## Pré-requisitos

- [Python 3.10 ou superior instalado](https://www.python.org/downloads/)
- [Git](https://git-scm.com/downloads)
- [Docker](https://www.docker.com/get-started/)

## Passos para subir o projeto

1. **Faça o download do repositório:**
   [Clique aqui para realizar o download](https://github.com/guilhermeonrails/imersao-devops/archive/refs/heads/main.zip)
2. **Crie um ambiente virtual:**

   ```sh
   python3 -m venv ./venv
   ```
3. **Ative o ambiente virtual:**

   - No Linux/Mac:
     ```sh
     source venv/bin/activate
     ```
   - No Windows, abra um terminal no modo administrador e execute o comando:

   ```sh
   Set-ExecutionPolicy RemoteSigned
   ```

   ```sh
   venv\Scripts\activate
   ```
4. **Instale as dependências:**

   ```sh
   pip install -r requirements.txt
   ```
5. **Execute a aplicação:**

   ```sh
   uvicorn app:app --reload
   ```
6. **Acesse a documentação interativa:**

   Abra o navegador e acesse:
   [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)

   Aqui você pode testar todos os endpoints da API de forma interativa.

---

## Estrutura do Projeto

- `app.py`: Arquivo principal da aplicação FastAPI.
- `models.py`: Modelos do banco de dados (SQLAlchemy).
- `schemas.py`: Schemas de validação (Pydantic).
- `database.py`: Configuração do banco de dados SQLite.
- `routers/`: Diretório com os arquivos de rotas (alunos, cursos, matrículas).
- `requirements.txt`: Lista de dependências do projeto.

---

- O banco de dados SQLite será criado automaticamente como `escola.db` na primeira execução.
- Para reiniciar o banco, basta apagar o arquivo `escola.db` (isso apagará todos os dados).

---

## Deploy no Google Cloud Run

```
gcloud init
gcloud auth login
gcloud config set project [PROJECT-ID]
gcloud run deploy --port=8000
```
---

## Créditos

Este projeto é baseado no repositório original [ellis](https://github.com/guilhermeonrails/ellis), desenvolvido para a **Imersão DevOps - Alura com Google Cloud**.

A imersão foi conduzida por um instrutor da Alura, com o apoio de uma **SRE sênior da comunidade** e de um **especialista do Google Cloud**.