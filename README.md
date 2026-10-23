# ADA - Assistente Virtual Inteligente

> Projeto desenvolvido no Hackathon 2025 do Programa Jovem Programador — Senac/SC

[![Django](https://img.shields.io/badge/Django-5.2.4-green.svg)](https://www.djangoproject.com/)
[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4o--mini-orange.svg)](https://openai.com/)

ADA é uma assistente virtual conversacional que responde dúvidas sobre o Programa Jovem Programador, com suporte a voz, acessibilidade em Libras e painel administrativo para gestão de cadastros. O nome é uma homenagem a **Ada Lovelace**, considerada a primeira programadora da história.

## Estado do projeto

Protótipo desenvolvido em equipe durante um hackathon. O deploy está pausado por custo de infraestrutura; o repositório permanece disponível como registro técnico e pode ser executado localmente.

## Funcionalidades

- **Chatbot com IA** — respostas geradas por GPT-4o-mini com scraping automático do site oficial
- **Voz bidirecional** — entrada via Whisper (speech-to-text) e saída via TTS (text-to-speech)
- **Cadastro de interessados** — formulário com validações de CPF, WhatsApp e cidade/polo SC
- **Painel administrativo** — exportação de dados em CSV, Excel e PDF
- **Acessibilidade** — integração com VLibras (Língua Brasileira de Sinais)

## Stack Tecnológica

| Camada | Tecnologia |
|--------|-----------|
| Backend | Django 5.2, Python 3.8+ |
| IA | OpenAI GPT-4o-mini, Whisper, TTS |
| Web Scraping | Playwright, AsyncIO |
| Frontend | Bootstrap 5, HTML5, JavaScript |
| Banco de Dados | SQLite |
| Relatórios | ReportLab, Pandas, openpyxl |

## Como Rodar Localmente

**Pré-requisitos:** Python 3.8+, pip, chave de API da OpenAI

```bash
# 1. Clone o repositório
git clone https://github.com/renatoteodoro/ADA.git
cd ADA

# 2. Crie e ative o ambiente virtual
python -m venv venv
venv\Scripts\activate      # Windows
# source venv/bin/activate   # Linux/Mac

# 3. Instale as dependências
pip install -r requirements.txt

# 4. Configure as variáveis de ambiente
cp .env.example .env
# Edite .env e adicione sua OPENAI_API_KEY

# 5. Execute as migrações
python manage.py migrate

# 6. Inicie o servidor
python manage.py runserver
```

Acesse: `http://127.0.0.1:8000/`

## Variáveis de Ambiente

Crie um arquivo `.env` na raiz do projeto:

```env
SECRET_KEY=sua-secret-key-segura-aqui
OPENAI_API_KEY=sk-...
DEBUG=True
```

## Estrutura do Projeto

```
ADA/
├── chatbot_project/     # Configurações Django
├── chatbot_app/         # App do chatbot com IA e scraping
├── cadastro_app/        # Formulário de cadastro de interessados
├── accounts_app/        # Autenticação e painel admin
├── static/              # Arquivos estáticos
├── media/               # Uploads de mídia
└── manage.py
```

## Equipe — Python Rangers

- Renato Teodoro | Matheus Moraes | Hudson Franco | Gustavo Lohn | Vinícius Costa

**Orientadora:** Karina Fernandes | **Coordenador:** Vlademir Machado

---

> Hackathon 2025 — Programa Jovem Programador — Senac/SC
