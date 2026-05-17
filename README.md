# Clínica Popular — resumo do projeto #
FEITO COM SQL, PYTHON E SUAS BIBLIOTECAS

### O que é: ###

Sistema de API REST para clínicas populares (SUS): prontuário eletrônico, agendamento, fila inteligente e Machine Learning (tempo de espera e risco de falta). Não há site visual completo — o uso é pela documentação interativa (Swagger) ou por outro frontend que consuma a API.

### O que você precisa para testar ###

*Requisito* -------------------------------------------	*Por quê*

Docker Desktop instalado e aberto-----------------Sobe a API + MongoDB com um comando, sem instalar Python no PC

## Como subir ##

cd c:\Users\gisla\Documents\clinica-popular
docker compose up --build


```
clinica-popular/
├── backend/                 # API FastAPI
│   ├── app/
│   │   ├── main.py          # Entrada da API, rotas, página inicial
│   │   ├── init_db.py       # Cria tabelas + dados demo no SQLite
│   │   ├── core/            # Config, banco, JWT/senhas
│   │   ├── models/          # Tabelas (usuários, pacientes, fila…)
│   │   ├── schemas/         # Validação JSON entrada/saída
│   │   ├── routers/         # Endpoints por módulo
│   │   └── services/        # Regras de fila, ML, logs
│   ├── data/clinica.db      # Banco SQLite (dados reais do sistema)
│   ├── tests/               # Testes automáticos (pytest)
│   ├── requirements.txt     # Bibliotecas Python (obrigatório)
│   ├── pytest.ini           # Config dos testes
│   └── Dockerfile           # Imagem Docker da API
├── ml/                      # Treino e teste dos modelos ML (opcional)
├── database/
│   ├── sql/                 # Schema/queries SQL de referência (documentação)
│   └── nosql/               # Init do MongoDB (coleções de log)
├── docs/                    # Documentação acadêmica (não roda com a API)
├── docker-compose.yml       # Sobe API + MongoDB
└── run.bat / run.ps1        # Atalho para docker compose up
```
